# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180042bb0`
- end: `0x180042c76`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180042de0`

## callees

- `0x180042bb0`
- `0x1800435d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180042c07`
- `KERNEL32!GetCurrentThreadId` at `0x180042c07`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v6; // rcx
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v2 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
    v8 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v2, &v8) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v8;
    }
  }
  v3 = *(_QWORD *)(v1 + 8);
  v4 = v3 + 32;
  if ( !v3 )
    v4 = 0;
  if ( !v4 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8);
  if ( !v6 )
    return 0;
  while ( *(_DWORD *)v6 != CurrentThreadId )
  {
    v6 = *(_QWORD *)(v6 + 8);
    if ( !v6 )
      return 0;
  }
  result = (struct wil::details_abi::ThreadLocalData *)(v6 + 16);
  if ( v6 != -16 && !*(_QWORD *)(v6 + 24) )
    *(_QWORD *)(v6 + 24) = v4 + 4;
  return result;
}

```

## disassembly

```asm
0x180042bb0  mov     [rsp+arg_0], rbx
0x180042bb5  push    rdi
0x180042bb6  sub     rsp, 20h
0x180042bba  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180042bc1  xor     edi, edi
0x180042bc3  test    rbx, rbx
0x180042bc6  jz      short loc_180042C46
0x180042bc8  cmp     [rbx+8], rdi
0x180042bcc  jnz     short loc_180042BF3
0x180042bce  mov     rcx, [rbx]
0x180042bd1  lea     rdx, [rsp+28h+arg_8]
0x180042bd6  mov     [rsp+28h+arg_8], rdi
0x180042bdb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180042be0  test    eax, eax
0x180042be2  js      short loc_180042BF3
0x180042be4  cmp     [rbx+8], rdi
0x180042be8  jnz     short loc_180042BF3
0x180042bea  mov     rax, [rsp+28h+arg_8]
0x180042bef  mov     [rbx+8], rax
0x180042bf3  mov     rax, [rbx+8]
0x180042bf7  test    rax, rax
0x180042bfa  lea     rbx, [rax+20h]
0x180042bfe  cmovz   rbx, rdi
0x180042c02  test    rbx, rbx
0x180042c05  jz      short loc_180042C46
0x180042c07  call    cs:__imp_GetCurrentThreadId
0x180042c0d  mov     r8d, eax
0x180042c10  mov     r9d, eax
0x180042c13  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180042c1d  mul     r9
0x180042c20  shr     rdx, 3
0x180042c24  lea     rcx, [rdx+rdx*4]
0x180042c28  add     rcx, rcx
0x180042c2b  sub     r8, rcx
0x180042c2e  mov     rcx, [rbx+r8*8+8]
0x180042c33  test    rcx, rcx
0x180042c36  jz      short loc_180042C46
0x180042c38  cmp     [rcx], r9d
0x180042c3b  jz      short loc_180042C54
0x180042c3d  mov     rcx, [rcx+8]
0x180042c41  test    rcx, rcx
0x180042c44  jnz     short loc_180042C38
0x180042c46  mov     rax, rdi
0x180042c49  mov     rbx, [rsp+28h+arg_0]
0x180042c4e  add     rsp, 20h
0x180042c52  pop     rdi
0x180042c53  retn
0x180042c54  lea     rax, [rcx+10h]
0x180042c58  test    rax, rax
0x180042c5b  jz      short loc_180042C49
0x180042c5d  cmp     [rax+8], rdi
0x180042c61  jnz     short loc_180042C49
0x180042c63  lea     rcx, [rbx+4]
0x180042c67  mov     rbx, [rsp+28h+arg_0]
0x180042c6c  mov     [rax+8], rcx
0x180042c70  add     rsp, 20h
0x180042c74  pop     rdi
0x180042c75  retn
```
