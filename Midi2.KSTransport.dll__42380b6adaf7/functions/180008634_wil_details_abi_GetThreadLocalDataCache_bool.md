# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008634`
- end: `0x1800086ef`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e40`

## callees

- `0x1800066b8`
- `0x180008634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000868a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000868a`

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
0x180008634  mov     [rsp+arg_0], rbx
0x180008639  push    rdi
0x18000863a  sub     rsp, 20h
0x18000863e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008645  xor     ebx, ebx
0x180008647  test    rdi, rdi
0x18000864a  jz      short loc_1800086CA
0x18000864c  cmp     [rdi+8], rbx
0x180008650  jnz     short loc_180008677
0x180008652  mov     rcx, [rdi]
0x180008655  lea     rdx, [rsp+28h+arg_8]
0x18000865a  mov     [rsp+28h+arg_8], rbx
0x18000865f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008664  test    eax, eax
0x180008666  js      short loc_180008677
0x180008668  cmp     [rdi+8], rbx
0x18000866c  jnz     short loc_180008677
0x18000866e  mov     rax, [rsp+28h+arg_8]
0x180008673  mov     [rdi+8], rax
0x180008677  mov     rax, [rdi+8]
0x18000867b  lea     rcx, [rax+20h]
0x18000867f  neg     rax
0x180008682  sbb     rdi, rdi
0x180008685  and     rdi, rcx
0x180008688  jz      short loc_1800086CA
0x18000868a  call    cs:__imp_GetCurrentThreadId
0x180008690  mov     r8d, eax
0x180008693  mov     r9d, eax
0x180008696  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800086a0  shr     r8, 2
0x1800086a4  mul     r8
0x1800086a7  shr     rdx, 3
0x1800086ab  lea     rcx, [rdx+rdx*4]
0x1800086af  add     rcx, rcx
0x1800086b2  sub     r8, rcx
0x1800086b5  mov     rbx, [rdi+r8*8+8]
0x1800086ba  jmp     short loc_1800086C5
0x1800086bc  cmp     [rbx], r9d
0x1800086bf  jz      short loc_1800086D8
0x1800086c1  mov     rbx, [rbx+8]
0x1800086c5  test    rbx, rbx
0x1800086c8  jnz     short loc_1800086BC
0x1800086ca  mov     rax, rbx
0x1800086cd  mov     rbx, [rsp+28h+arg_0]
0x1800086d2  add     rsp, 20h
0x1800086d6  pop     rdi
0x1800086d7  retn
0x1800086d8  add     rbx, 10h
0x1800086dc  jz      short loc_1800086CA
0x1800086de  cmp     qword ptr [rbx+8], 0
0x1800086e3  jnz     short loc_1800086CA
0x1800086e5  lea     rax, [rdi+4]
0x1800086e9  mov     [rbx+8], rax
0x1800086ed  jmp     short loc_1800086CA
```
