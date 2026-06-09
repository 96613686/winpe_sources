# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18005733c`
- end: `0x1800573f9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180056bb0`

## callees

- `0x180056708`
- `0x18005733c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057396`

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
0x18005733c  mov     [rsp+arg_0], rbx
0x180057341  push    rdi
0x180057342  sub     rsp, 20h
0x180057346  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18005734d  xor     ebx, ebx
0x18005734f  test    rdi, rdi
0x180057352  jz      loc_1800573EB
0x180057358  cmp     [rdi+8], rbx
0x18005735c  jnz     short loc_180057383
0x18005735e  mov     rcx, [rdi]
0x180057361  lea     rdx, [rsp+28h+arg_8]
0x180057366  mov     [rsp+28h+arg_8], rbx
0x18005736b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180057370  test    eax, eax
0x180057372  js      short loc_180057383
0x180057374  cmp     [rdi+8], rbx
0x180057378  jnz     short loc_180057383
0x18005737a  mov     rax, [rsp+28h+arg_8]
0x18005737f  mov     [rdi+8], rax
0x180057383  mov     rax, [rdi+8]
0x180057387  lea     rcx, [rax+20h]
0x18005738b  neg     rax
0x18005738e  sbb     rdi, rdi
0x180057391  and     rdi, rcx
0x180057394  jz      short loc_1800573EB
0x180057396  call    cs:__imp_GetCurrentThreadId
0x18005739c  mov     r8d, eax
0x18005739f  mov     r9d, eax
0x1800573a2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800573ac  shr     r8, 2
0x1800573b0  mul     r8
0x1800573b3  shr     rdx, 3
0x1800573b7  lea     rcx, [rdx+rdx*4]
0x1800573bb  add     rcx, rcx
0x1800573be  sub     r8, rcx
0x1800573c1  mov     rbx, [rdi+r8*8+8]
0x1800573c6  test    rbx, rbx
0x1800573c9  jz      short loc_1800573EB
0x1800573cb  cmp     [rbx], r9d
0x1800573ce  jz      short loc_1800573D6
0x1800573d0  mov     rbx, [rbx+8]
0x1800573d4  jmp     short loc_1800573C6
0x1800573d6  add     rbx, 10h
0x1800573da  jz      short loc_1800573EB
0x1800573dc  cmp     qword ptr [rbx+8], 0
0x1800573e1  jnz     short loc_1800573EB
0x1800573e3  lea     rax, [rdi+4]
0x1800573e7  mov     [rbx+8], rax
0x1800573eb  mov     rax, rbx
0x1800573ee  mov     rbx, [rsp+28h+arg_0]
0x1800573f3  add     rsp, 20h
0x1800573f7  pop     rdi
0x1800573f8  retn
```
