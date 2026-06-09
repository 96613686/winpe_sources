# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b918`
- end: `0x18000b9d5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `wil::details_abi::ThreadLocalData *__fastcall(bool allocate)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b050`

## callees

- `0x18000a5a8`
- `0x18000b918`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b972`

## pseudocode

```c
wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(bool allocate)
{
  wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> *v1; // rdi
  __int64 i; // rbx
  const char *m_staticNameWithVersion; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> *data; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !wil::details_abi::g_pProcessLocalData->m_data )
    {
      m_staticNameWithVersion = wil::details_abi::g_pProcessLocalData->m_staticNameWithVersion;
      data = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  m_staticNameWithVersion,
                  &data) >= 0
        && !v1->m_data )
      {
        v1->m_data = data;
      }
    }
    v4 = (__int64)&v1->m_data->m_data & -(__int64)(v1->m_data != 0);
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
          return (wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x18000b918  mov     [rsp+arg_0], rbx
0x18000b91d  push    rdi
0x18000b91e  sub     rsp, 20h
0x18000b922  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b929  xor     ebx, ebx
0x18000b92b  test    rdi, rdi
0x18000b92e  jz      loc_18000B9C7
0x18000b934  cmp     [rdi+8], rbx
0x18000b938  jnz     short loc_18000B95F
0x18000b93a  mov     rcx, [rdi]; staticNameWithVersion
0x18000b93d  lea     rdx, [rsp+28h+data]; data
0x18000b942  mov     [rsp+28h+data], rbx
0x18000b947  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b94c  test    eax, eax
0x18000b94e  js      short loc_18000B95F
0x18000b950  cmp     [rdi+8], rbx
0x18000b954  jnz     short loc_18000B95F
0x18000b956  mov     rax, [rsp+28h+data]
0x18000b95b  mov     [rdi+8], rax
0x18000b95f  mov     rax, [rdi+8]
0x18000b963  lea     rcx, [rax+20h]
0x18000b967  neg     rax
0x18000b96a  sbb     rdi, rdi
0x18000b96d  and     rdi, rcx
0x18000b970  jz      short loc_18000B9C7
0x18000b972  call    cs:__imp_GetCurrentThreadId
0x18000b978  mov     r8d, eax
0x18000b97b  mov     r9d, eax
0x18000b97e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b988  shr     r8, 2
0x18000b98c  mul     r8
0x18000b98f  shr     rdx, 3
0x18000b993  lea     rcx, [rdx+rdx*4]
0x18000b997  add     rcx, rcx
0x18000b99a  sub     r8, rcx
0x18000b99d  mov     rbx, [rdi+r8*8+8]
0x18000b9a2  test    rbx, rbx
0x18000b9a5  jz      short loc_18000B9C7
0x18000b9a7  cmp     [rbx], r9d
0x18000b9aa  jz      short loc_18000B9B2
0x18000b9ac  mov     rbx, [rbx+8]
0x18000b9b0  jmp     short loc_18000B9A2
0x18000b9b2  add     rbx, 10h
0x18000b9b6  jz      short loc_18000B9C7
0x18000b9b8  cmp     qword ptr [rbx+8], 0
0x18000b9bd  jnz     short loc_18000B9C7
0x18000b9bf  lea     rax, [rdi+4]
0x18000b9c3  mov     [rbx+8], rax
0x18000b9c7  mov     rax, rbx
0x18000b9ca  mov     rbx, [rsp+28h+arg_0]
0x18000b9cf  add     rsp, 20h
0x18000b9d3  pop     rdi
0x18000b9d4  retn
```
