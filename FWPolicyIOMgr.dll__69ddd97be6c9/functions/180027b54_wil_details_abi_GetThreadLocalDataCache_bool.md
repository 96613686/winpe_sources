# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180027b54`
- end: `0x180027c11`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027550`

## callees

- `0x180024fa8`
- `0x180027b54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027bae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027bae`

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
0x180027b54  mov     [rsp+arg_0], rbx
0x180027b59  push    rdi
0x180027b5a  sub     rsp, 20h
0x180027b5e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180027b65  xor     ebx, ebx
0x180027b67  test    rdi, rdi
0x180027b6a  jz      loc_180027C03
0x180027b70  cmp     [rdi+8], rbx
0x180027b74  jnz     short loc_180027B9B
0x180027b76  mov     rcx, [rdi]
0x180027b79  lea     rdx, [rsp+28h+arg_8]
0x180027b7e  mov     [rsp+28h+arg_8], rbx
0x180027b83  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180027b88  test    eax, eax
0x180027b8a  js      short loc_180027B9B
0x180027b8c  cmp     [rdi+8], rbx
0x180027b90  jnz     short loc_180027B9B
0x180027b92  mov     rax, [rsp+28h+arg_8]
0x180027b97  mov     [rdi+8], rax
0x180027b9b  mov     rax, [rdi+8]
0x180027b9f  lea     rcx, [rax+20h]
0x180027ba3  neg     rax
0x180027ba6  sbb     rdi, rdi
0x180027ba9  and     rdi, rcx
0x180027bac  jz      short loc_180027C03
0x180027bae  call    cs:__imp_GetCurrentThreadId
0x180027bb4  mov     r8d, eax
0x180027bb7  mov     r9d, eax
0x180027bba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180027bc4  shr     r8, 2
0x180027bc8  mul     r8
0x180027bcb  shr     rdx, 3
0x180027bcf  lea     rcx, [rdx+rdx*4]
0x180027bd3  add     rcx, rcx
0x180027bd6  sub     r8, rcx
0x180027bd9  mov     rbx, [rdi+r8*8+8]
0x180027bde  test    rbx, rbx
0x180027be1  jz      short loc_180027C03
0x180027be3  cmp     [rbx], r9d
0x180027be6  jz      short loc_180027BEE
0x180027be8  mov     rbx, [rbx+8]
0x180027bec  jmp     short loc_180027BDE
0x180027bee  add     rbx, 10h
0x180027bf2  jz      short loc_180027C03
0x180027bf4  cmp     qword ptr [rbx+8], 0
0x180027bf9  jnz     short loc_180027C03
0x180027bfb  lea     rax, [rdi+4]
0x180027bff  mov     [rbx+8], rax
0x180027c03  mov     rax, rbx
0x180027c06  mov     rbx, [rsp+28h+arg_0]
0x180027c0b  add     rsp, 20h
0x180027c0f  pop     rdi
0x180027c10  retn
```
