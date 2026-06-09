# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800069ec`
- end: `0x180006ab2`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006630`

## callees

- `0x180005eb4`
- `0x1800069ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a46`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x1800069ec  mov     [rsp+arg_0], rbx
0x1800069f1  push    rdi
0x1800069f2  sub     rsp, 20h
0x1800069f6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800069fd  xor     ebx, ebx
0x1800069ff  test    rdi, rdi
0x180006a02  jz      loc_180006A8C
0x180006a08  cmp     [rdi+8], rbx
0x180006a0c  jnz     short loc_180006A33
0x180006a0e  mov     rcx, [rdi]
0x180006a11  lea     rdx, [rsp+28h+arg_8]
0x180006a16  mov     [rsp+28h+arg_8], rbx
0x180006a1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006a20  test    eax, eax
0x180006a22  js      short loc_180006A33
0x180006a24  cmp     [rdi+8], rbx
0x180006a28  jnz     short loc_180006A33
0x180006a2a  mov     rax, [rsp+28h+arg_8]
0x180006a2f  mov     [rdi+8], rax
0x180006a33  mov     rax, [rdi+8]
0x180006a37  lea     rcx, [rax+20h]
0x180006a3b  neg     rax
0x180006a3e  sbb     rdi, rdi
0x180006a41  and     rdi, rcx
0x180006a44  jz      short loc_180006A8C
0x180006a46  call    cs:__imp_GetCurrentThreadId
0x180006a4d  nop     dword ptr [rax+rax+00h]
0x180006a52  mov     r8d, eax
0x180006a55  mov     r9d, eax
0x180006a58  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006a62  shr     r8, 2
0x180006a66  mul     r8
0x180006a69  shr     rdx, 3
0x180006a6d  lea     rcx, [rdx+rdx*4]
0x180006a71  add     rcx, rcx
0x180006a74  sub     r8, rcx
0x180006a77  mov     rbx, [rdi+r8*8+8]
0x180006a7c  jmp     short loc_180006A87
0x180006a7e  cmp     [rbx], r9d
0x180006a81  jz      short loc_180006A9B
0x180006a83  mov     rbx, [rbx+8]
0x180006a87  test    rbx, rbx
0x180006a8a  jnz     short loc_180006A7E
0x180006a8c  mov     rax, rbx
0x180006a8f  mov     rbx, [rsp+28h+arg_0]
0x180006a94  add     rsp, 20h
0x180006a98  pop     rdi
0x180006a99  retn
0x180006a9b  add     rbx, 10h
0x180006a9f  jz      short loc_180006A8C
0x180006aa1  cmp     qword ptr [rbx+8], 0
0x180006aa6  jnz     short loc_180006A8C
0x180006aa8  lea     rax, [rdi+4]
0x180006aac  mov     [rbx+8], rax
0x180006ab0  jmp     short loc_180006A8C
```
