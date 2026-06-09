# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b8c8`
- end: `0x18000b983`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a500`

## callees

- `0x180007de8`
- `0x18000b8c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b91e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b91e`

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
0x18000b8c8  mov     [rsp+arg_0], rbx
0x18000b8cd  push    rdi
0x18000b8ce  sub     rsp, 20h
0x18000b8d2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b8d9  xor     ebx, ebx
0x18000b8db  test    rdi, rdi
0x18000b8de  jz      short loc_18000B95E
0x18000b8e0  cmp     [rdi+8], rbx
0x18000b8e4  jnz     short loc_18000B90B
0x18000b8e6  mov     rcx, [rdi]
0x18000b8e9  lea     rdx, [rsp+28h+arg_8]
0x18000b8ee  mov     [rsp+28h+arg_8], rbx
0x18000b8f3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b8f8  test    eax, eax
0x18000b8fa  js      short loc_18000B90B
0x18000b8fc  cmp     [rdi+8], rbx
0x18000b900  jnz     short loc_18000B90B
0x18000b902  mov     rax, [rsp+28h+arg_8]
0x18000b907  mov     [rdi+8], rax
0x18000b90b  mov     rax, [rdi+8]
0x18000b90f  lea     rcx, [rax+20h]
0x18000b913  neg     rax
0x18000b916  sbb     rdi, rdi
0x18000b919  and     rdi, rcx
0x18000b91c  jz      short loc_18000B95E
0x18000b91e  call    cs:__imp_GetCurrentThreadId
0x18000b924  mov     r8d, eax
0x18000b927  mov     r9d, eax
0x18000b92a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b934  shr     r8, 2
0x18000b938  mul     r8
0x18000b93b  shr     rdx, 3
0x18000b93f  lea     rcx, [rdx+rdx*4]
0x18000b943  add     rcx, rcx
0x18000b946  sub     r8, rcx
0x18000b949  mov     rbx, [rdi+r8*8+8]
0x18000b94e  jmp     short loc_18000B959
0x18000b950  cmp     [rbx], r9d
0x18000b953  jz      short loc_18000B96C
0x18000b955  mov     rbx, [rbx+8]
0x18000b959  test    rbx, rbx
0x18000b95c  jnz     short loc_18000B950
0x18000b95e  mov     rax, rbx
0x18000b961  mov     rbx, [rsp+28h+arg_0]
0x18000b966  add     rsp, 20h
0x18000b96a  pop     rdi
0x18000b96b  retn
0x18000b96c  add     rbx, 10h
0x18000b970  jz      short loc_18000B95E
0x18000b972  cmp     qword ptr [rbx+8], 0
0x18000b977  jnz     short loc_18000B95E
0x18000b979  lea     rax, [rdi+4]
0x18000b97d  mov     [rbx+8], rax
0x18000b981  jmp     short loc_18000B95E
```
