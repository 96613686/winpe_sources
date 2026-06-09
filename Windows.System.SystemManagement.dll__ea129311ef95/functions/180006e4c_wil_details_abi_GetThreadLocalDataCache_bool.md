# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006e4c`
- end: `0x180006f09`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006700`

## callees

- `0x180006078`
- `0x180006e4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ea6`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x180006e4c  mov     [rsp+arg_0], rbx
0x180006e51  push    rdi
0x180006e52  sub     rsp, 20h
0x180006e56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006e5d  xor     ebx, ebx
0x180006e5f  test    rdi, rdi
0x180006e62  jz      loc_180006EFB
0x180006e68  cmp     [rdi+8], rbx
0x180006e6c  jnz     short loc_180006E93
0x180006e6e  mov     rcx, [rdi]
0x180006e71  lea     rdx, [rsp+28h+arg_8]
0x180006e76  mov     [rsp+28h+arg_8], rbx
0x180006e7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006e80  test    eax, eax
0x180006e82  js      short loc_180006E93
0x180006e84  cmp     [rdi+8], rbx
0x180006e88  jnz     short loc_180006E93
0x180006e8a  mov     rax, [rsp+28h+arg_8]
0x180006e8f  mov     [rdi+8], rax
0x180006e93  mov     rax, [rdi+8]
0x180006e97  lea     rcx, [rax+20h]
0x180006e9b  neg     rax
0x180006e9e  sbb     rdi, rdi
0x180006ea1  and     rdi, rcx
0x180006ea4  jz      short loc_180006EFB
0x180006ea6  call    cs:__imp_GetCurrentThreadId
0x180006eac  mov     r8d, eax
0x180006eaf  mov     r9d, eax
0x180006eb2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006ebc  shr     r8, 2
0x180006ec0  mul     r8
0x180006ec3  shr     rdx, 3
0x180006ec7  lea     rcx, [rdx+rdx*4]
0x180006ecb  add     rcx, rcx
0x180006ece  sub     r8, rcx
0x180006ed1  mov     rbx, [rdi+r8*8+8]
0x180006ed6  test    rbx, rbx
0x180006ed9  jz      short loc_180006EFB
0x180006edb  cmp     [rbx], r9d
0x180006ede  jz      short loc_180006EE6
0x180006ee0  mov     rbx, [rbx+8]
0x180006ee4  jmp     short loc_180006ED6
0x180006ee6  add     rbx, 10h
0x180006eea  jz      short loc_180006EFB
0x180006eec  cmp     qword ptr [rbx+8], 0
0x180006ef1  jnz     short loc_180006EFB
0x180006ef3  lea     rax, [rdi+4]
0x180006ef7  mov     [rbx+8], rax
0x180006efb  mov     rax, rbx
0x180006efe  mov     rbx, [rsp+28h+arg_0]
0x180006f03  add     rsp, 20h
0x180006f07  pop     rdi
0x180006f08  retn
```
