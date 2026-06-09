# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002f200`
- end: `0x18002f2c6`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f430`

## callees

- `0x18002f200`
- `0x1800300f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002f257`
- `KERNEL32!GetCurrentThreadId` at `0x18002f257`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002f200  mov     [rsp+arg_0], rbx
0x18002f205  push    rdi
0x18002f206  sub     rsp, 20h
0x18002f20a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002f211  xor     edi, edi
0x18002f213  test    rbx, rbx
0x18002f216  jz      short loc_18002F296
0x18002f218  cmp     [rbx+8], rdi
0x18002f21c  jnz     short loc_18002F243
0x18002f21e  mov     rcx, [rbx]
0x18002f221  lea     rdx, [rsp+28h+arg_8]
0x18002f226  mov     [rsp+28h+arg_8], rdi
0x18002f22b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002f230  test    eax, eax
0x18002f232  js      short loc_18002F243
0x18002f234  cmp     [rbx+8], rdi
0x18002f238  jnz     short loc_18002F243
0x18002f23a  mov     rax, [rsp+28h+arg_8]
0x18002f23f  mov     [rbx+8], rax
0x18002f243  mov     rax, [rbx+8]
0x18002f247  test    rax, rax
0x18002f24a  lea     rbx, [rax+20h]
0x18002f24e  cmovz   rbx, rdi
0x18002f252  test    rbx, rbx
0x18002f255  jz      short loc_18002F296
0x18002f257  call    cs:__imp_GetCurrentThreadId
0x18002f25d  mov     r8d, eax
0x18002f260  mov     r9d, eax
0x18002f263  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002f26d  mul     r9
0x18002f270  shr     rdx, 3
0x18002f274  lea     rcx, [rdx+rdx*4]
0x18002f278  add     rcx, rcx
0x18002f27b  sub     r8, rcx
0x18002f27e  mov     rcx, [rbx+r8*8+8]
0x18002f283  test    rcx, rcx
0x18002f286  jz      short loc_18002F296
0x18002f288  cmp     [rcx], r9d
0x18002f28b  jz      short loc_18002F2A4
0x18002f28d  mov     rcx, [rcx+8]
0x18002f291  test    rcx, rcx
0x18002f294  jnz     short loc_18002F288
0x18002f296  mov     rax, rdi
0x18002f299  mov     rbx, [rsp+28h+arg_0]
0x18002f29e  add     rsp, 20h
0x18002f2a2  pop     rdi
0x18002f2a3  retn
0x18002f2a4  lea     rax, [rcx+10h]
0x18002f2a8  test    rax, rax
0x18002f2ab  jz      short loc_18002F299
0x18002f2ad  cmp     [rax+8], rdi
0x18002f2b1  jnz     short loc_18002F299
0x18002f2b3  lea     rcx, [rbx+4]
0x18002f2b7  mov     rbx, [rsp+28h+arg_0]
0x18002f2bc  mov     [rax+8], rcx
0x18002f2c0  add     rsp, 20h
0x18002f2c4  pop     rdi
0x18002f2c5  retn
```
