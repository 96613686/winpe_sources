# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004a50`
- end: `0x180004b16`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c80`

## callees

- `0x180004a50`
- `0x180005680`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004aa7`
- `KERNEL32!GetCurrentThreadId` at `0x180004aa7`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  __int64 v3; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v5; // rcx
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v7 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                &v7) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v7;
    }
  }
  v2 = *(_QWORD *)(v1 + 8);
  v3 = v2 + 32;
  if ( !v2 )
    v3 = 0;
  if ( !v3 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v5 = *(_QWORD *)(v3 + 8 * (CurrentThreadId % 0xAuLL) + 8);
  if ( !v5 )
    return 0;
  while ( *(_DWORD *)v5 != CurrentThreadId )
  {
    v5 = *(_QWORD *)(v5 + 8);
    if ( !v5 )
      return 0;
  }
  result = (struct wil::details_abi::ThreadLocalData *)(v5 + 16);
  if ( v5 != -16 && !*(_QWORD *)(v5 + 24) )
    *(_QWORD *)(v5 + 24) = v3 + 4;
  return result;
}

```

## disassembly

```asm
0x180004a50  mov     [rsp+arg_0], rbx
0x180004a55  push    rdi
0x180004a56  sub     rsp, 20h
0x180004a5a  xor     edi, edi
0x180004a5c  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004a63  test    rbx, rbx
0x180004a66  jz      short loc_180004AE6
0x180004a68  cmp     [rbx+8], rdi
0x180004a6c  jnz     short loc_180004A93
0x180004a6e  mov     [rsp+28h+arg_8], rdi
0x180004a73  lea     rdx, [rsp+28h+arg_8]
0x180004a78  mov     rcx, [rbx]
0x180004a7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004a80  test    eax, eax
0x180004a82  js      short loc_180004A93
0x180004a84  cmp     [rbx+8], rdi
0x180004a88  jnz     short loc_180004A93
0x180004a8a  mov     rax, [rsp+28h+arg_8]
0x180004a8f  mov     [rbx+8], rax
0x180004a93  mov     rax, [rbx+8]
0x180004a97  lea     rbx, [rax+20h]
0x180004a9b  test    rax, rax
0x180004a9e  cmovz   rbx, rdi
0x180004aa2  test    rbx, rbx
0x180004aa5  jz      short loc_180004AE6
0x180004aa7  call    cs:__imp_GetCurrentThreadId
0x180004aad  mov     r9d, eax
0x180004ab0  mov     r8d, eax
0x180004ab3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004abd  mul     r9
0x180004ac0  shr     rdx, 3
0x180004ac4  lea     rcx, [rdx+rdx*4]
0x180004ac8  add     rcx, rcx
0x180004acb  sub     r8, rcx
0x180004ace  mov     rcx, [rbx+r8*8+8]
0x180004ad3  test    rcx, rcx
0x180004ad6  jz      short loc_180004AE6
0x180004ad8  cmp     [rcx], r9d
0x180004adb  jz      short loc_180004AF4
0x180004add  mov     rcx, [rcx+8]
0x180004ae1  test    rcx, rcx
0x180004ae4  jnz     short loc_180004AD8
0x180004ae6  mov     rax, rdi
0x180004ae9  mov     rbx, [rsp+28h+arg_0]
0x180004aee  add     rsp, 20h
0x180004af2  pop     rdi
0x180004af3  retn
0x180004af4  lea     rax, [rcx+10h]
0x180004af8  test    rax, rax
0x180004afb  jz      short loc_180004AE9
0x180004afd  cmp     [rax+8], rdi
0x180004b01  jnz     short loc_180004AE9
0x180004b03  lea     rcx, [rbx+4]
0x180004b07  mov     [rax+8], rcx
0x180004b0b  mov     rbx, [rsp+28h+arg_0]
0x180004b10  add     rsp, 20h
0x180004b14  pop     rdi
0x180004b15  retn
```
