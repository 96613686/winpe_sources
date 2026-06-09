# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007430`
- end: `0x1800074ed`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b80`

## callees

- `0x180004fd8`
- `0x180007430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000748a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000748a`

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
0x180007430  mov     [rsp+arg_0], rbx
0x180007435  push    rdi
0x180007436  sub     rsp, 20h
0x18000743a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007441  xor     ebx, ebx
0x180007443  test    rdi, rdi
0x180007446  jz      loc_1800074DF
0x18000744c  cmp     [rdi+8], rbx
0x180007450  jnz     short loc_180007477
0x180007452  mov     rcx, [rdi]
0x180007455  lea     rdx, [rsp+28h+arg_8]
0x18000745a  mov     [rsp+28h+arg_8], rbx
0x18000745f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007464  test    eax, eax
0x180007466  js      short loc_180007477
0x180007468  cmp     [rdi+8], rbx
0x18000746c  jnz     short loc_180007477
0x18000746e  mov     rax, [rsp+28h+arg_8]
0x180007473  mov     [rdi+8], rax
0x180007477  mov     rax, [rdi+8]
0x18000747b  lea     rcx, [rax+20h]
0x18000747f  neg     rax
0x180007482  sbb     rdi, rdi
0x180007485  and     rdi, rcx
0x180007488  jz      short loc_1800074DF
0x18000748a  call    cs:__imp_GetCurrentThreadId
0x180007490  mov     r8d, eax
0x180007493  mov     r9d, eax
0x180007496  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800074a0  shr     r8, 2
0x1800074a4  mul     r8
0x1800074a7  shr     rdx, 3
0x1800074ab  lea     rcx, [rdx+rdx*4]
0x1800074af  add     rcx, rcx
0x1800074b2  sub     r8, rcx
0x1800074b5  mov     rbx, [rdi+r8*8+8]
0x1800074ba  test    rbx, rbx
0x1800074bd  jz      short loc_1800074DF
0x1800074bf  cmp     [rbx], r9d
0x1800074c2  jz      short loc_1800074CA
0x1800074c4  mov     rbx, [rbx+8]
0x1800074c8  jmp     short loc_1800074BA
0x1800074ca  add     rbx, 10h
0x1800074ce  jz      short loc_1800074DF
0x1800074d0  cmp     qword ptr [rbx+8], 0
0x1800074d5  jnz     short loc_1800074DF
0x1800074d7  lea     rax, [rdi+4]
0x1800074db  mov     [rbx+8], rax
0x1800074df  mov     rax, rbx
0x1800074e2  mov     rbx, [rsp+28h+arg_0]
0x1800074e7  add     rsp, 20h
0x1800074eb  pop     rdi
0x1800074ec  retn
```
