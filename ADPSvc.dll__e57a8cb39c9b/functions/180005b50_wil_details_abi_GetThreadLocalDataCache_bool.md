# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b50`
- end: `0x180005c0b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005370`

## callees

- `0x180004ba8`
- `0x180005b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ba6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ba6`

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
0x180005b50  mov     [rsp+arg_0], rbx
0x180005b55  push    rdi
0x180005b56  sub     rsp, 20h
0x180005b5a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005b61  xor     ebx, ebx
0x180005b63  test    rdi, rdi
0x180005b66  jz      short loc_180005BE6
0x180005b68  cmp     [rdi+8], rbx
0x180005b6c  jnz     short loc_180005B93
0x180005b6e  mov     rcx, [rdi]
0x180005b71  lea     rdx, [rsp+28h+arg_8]
0x180005b76  mov     [rsp+28h+arg_8], rbx
0x180005b7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005b80  test    eax, eax
0x180005b82  js      short loc_180005B93
0x180005b84  cmp     [rdi+8], rbx
0x180005b88  jnz     short loc_180005B93
0x180005b8a  mov     rax, [rsp+28h+arg_8]
0x180005b8f  mov     [rdi+8], rax
0x180005b93  mov     rax, [rdi+8]
0x180005b97  lea     rcx, [rax+20h]
0x180005b9b  neg     rax
0x180005b9e  sbb     rdi, rdi
0x180005ba1  and     rdi, rcx
0x180005ba4  jz      short loc_180005BE6
0x180005ba6  call    cs:__imp_GetCurrentThreadId
0x180005bac  mov     r8d, eax
0x180005baf  mov     r9d, eax
0x180005bb2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005bbc  shr     r8, 2
0x180005bc0  mul     r8
0x180005bc3  shr     rdx, 3
0x180005bc7  lea     rcx, [rdx+rdx*4]
0x180005bcb  add     rcx, rcx
0x180005bce  sub     r8, rcx
0x180005bd1  mov     rbx, [rdi+r8*8+8]
0x180005bd6  jmp     short loc_180005BE1
0x180005bd8  cmp     [rbx], r9d
0x180005bdb  jz      short loc_180005BF4
0x180005bdd  mov     rbx, [rbx+8]
0x180005be1  test    rbx, rbx
0x180005be4  jnz     short loc_180005BD8
0x180005be6  mov     rax, rbx
0x180005be9  mov     rbx, [rsp+28h+arg_0]
0x180005bee  add     rsp, 20h
0x180005bf2  pop     rdi
0x180005bf3  retn
0x180005bf4  add     rbx, 10h
0x180005bf8  jz      short loc_180005BE6
0x180005bfa  cmp     qword ptr [rbx+8], 0
0x180005bff  jnz     short loc_180005BE6
0x180005c01  lea     rax, [rdi+4]
0x180005c05  mov     [rbx+8], rax
0x180005c09  jmp     short loc_180005BE6
```
