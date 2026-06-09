# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180014f70`
- end: `0x180015036`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800151a0`

## callees

- `0x180014f70`
- `0x180015990`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180014fc7`
- `KERNEL32!GetCurrentThreadId` at `0x180014fc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180014f70  mov     [rsp+arg_0], rbx
0x180014f75  push    rdi
0x180014f76  sub     rsp, 20h
0x180014f7a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180014f81  xor     edi, edi
0x180014f83  test    rbx, rbx
0x180014f86  jz      short loc_180015006
0x180014f88  cmp     [rbx+8], rdi
0x180014f8c  jnz     short loc_180014FB3
0x180014f8e  mov     rcx, [rbx]
0x180014f91  lea     rdx, [rsp+28h+arg_8]
0x180014f96  mov     [rsp+28h+arg_8], rdi
0x180014f9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180014fa0  test    eax, eax
0x180014fa2  js      short loc_180014FB3
0x180014fa4  cmp     [rbx+8], rdi
0x180014fa8  jnz     short loc_180014FB3
0x180014faa  mov     rax, [rsp+28h+arg_8]
0x180014faf  mov     [rbx+8], rax
0x180014fb3  mov     rax, [rbx+8]
0x180014fb7  test    rax, rax
0x180014fba  lea     rbx, [rax+20h]
0x180014fbe  cmovz   rbx, rdi
0x180014fc2  test    rbx, rbx
0x180014fc5  jz      short loc_180015006
0x180014fc7  call    cs:__imp_GetCurrentThreadId
0x180014fcd  mov     r8d, eax
0x180014fd0  mov     r9d, eax
0x180014fd3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014fdd  mul     r9
0x180014fe0  shr     rdx, 3
0x180014fe4  lea     rcx, [rdx+rdx*4]
0x180014fe8  add     rcx, rcx
0x180014feb  sub     r8, rcx
0x180014fee  mov     rcx, [rbx+r8*8+8]
0x180014ff3  test    rcx, rcx
0x180014ff6  jz      short loc_180015006
0x180014ff8  cmp     [rcx], r9d
0x180014ffb  jz      short loc_180015014
0x180014ffd  mov     rcx, [rcx+8]
0x180015001  test    rcx, rcx
0x180015004  jnz     short loc_180014FF8
0x180015006  mov     rax, rdi
0x180015009  mov     rbx, [rsp+28h+arg_0]
0x18001500e  add     rsp, 20h
0x180015012  pop     rdi
0x180015013  retn
0x180015014  lea     rax, [rcx+10h]
0x180015018  test    rax, rax
0x18001501b  jz      short loc_180015009
0x18001501d  cmp     [rax+8], rdi
0x180015021  jnz     short loc_180015009
0x180015023  lea     rcx, [rbx+4]
0x180015027  mov     rbx, [rsp+28h+arg_0]
0x18001502c  mov     [rax+8], rcx
0x180015030  add     rsp, 20h
0x180015034  pop     rdi
0x180015035  retn
```
