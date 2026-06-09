# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180016500`
- end: `0x1800165bb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015d20`

## callees

- `0x180014d7c`
- `0x180016500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016556`

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
0x180016500  mov     [rsp+arg_0], rbx
0x180016505  push    rdi
0x180016506  sub     rsp, 20h
0x18001650a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180016511  xor     ebx, ebx
0x180016513  test    rdi, rdi
0x180016516  jz      short loc_180016596
0x180016518  cmp     [rdi+8], rbx
0x18001651c  jnz     short loc_180016543
0x18001651e  mov     rcx, [rdi]
0x180016521  lea     rdx, [rsp+28h+arg_8]
0x180016526  mov     [rsp+28h+arg_8], rbx
0x18001652b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180016530  test    eax, eax
0x180016532  js      short loc_180016543
0x180016534  cmp     [rdi+8], rbx
0x180016538  jnz     short loc_180016543
0x18001653a  mov     rax, [rsp+28h+arg_8]
0x18001653f  mov     [rdi+8], rax
0x180016543  mov     rax, [rdi+8]
0x180016547  lea     rcx, [rax+20h]
0x18001654b  neg     rax
0x18001654e  sbb     rdi, rdi
0x180016551  and     rdi, rcx
0x180016554  jz      short loc_180016596
0x180016556  call    cs:__imp_GetCurrentThreadId
0x18001655c  mov     r8d, eax
0x18001655f  mov     r9d, eax
0x180016562  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001656c  shr     r8, 2
0x180016570  mul     r8
0x180016573  shr     rdx, 3
0x180016577  lea     rcx, [rdx+rdx*4]
0x18001657b  add     rcx, rcx
0x18001657e  sub     r8, rcx
0x180016581  mov     rbx, [rdi+r8*8+8]
0x180016586  jmp     short loc_180016591
0x180016588  cmp     [rbx], r9d
0x18001658b  jz      short loc_1800165A4
0x18001658d  mov     rbx, [rbx+8]
0x180016591  test    rbx, rbx
0x180016594  jnz     short loc_180016588
0x180016596  mov     rax, rbx
0x180016599  mov     rbx, [rsp+28h+arg_0]
0x18001659e  add     rsp, 20h
0x1800165a2  pop     rdi
0x1800165a3  retn
0x1800165a4  add     rbx, 10h
0x1800165a8  jz      short loc_180016596
0x1800165aa  cmp     qword ptr [rbx+8], 0
0x1800165af  jnz     short loc_180016596
0x1800165b1  lea     rax, [rdi+4]
0x1800165b5  mov     [rbx+8], rax
0x1800165b9  jmp     short loc_180016596
```
