# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004e00`
- end: `0x180004ebb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004620`

## callees

- `0x180003e88`
- `0x180004e00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e56`

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
0x180004e00  mov     [rsp+arg_0], rbx
0x180004e05  push    rdi
0x180004e06  sub     rsp, 20h
0x180004e0a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004e11  xor     ebx, ebx
0x180004e13  test    rdi, rdi
0x180004e16  jz      short loc_180004E96
0x180004e18  cmp     [rdi+8], rbx
0x180004e1c  jnz     short loc_180004E43
0x180004e1e  mov     rcx, [rdi]
0x180004e21  lea     rdx, [rsp+28h+arg_8]
0x180004e26  mov     [rsp+28h+arg_8], rbx
0x180004e2b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004e30  test    eax, eax
0x180004e32  js      short loc_180004E43
0x180004e34  cmp     [rdi+8], rbx
0x180004e38  jnz     short loc_180004E43
0x180004e3a  mov     rax, [rsp+28h+arg_8]
0x180004e3f  mov     [rdi+8], rax
0x180004e43  mov     rax, [rdi+8]
0x180004e47  lea     rcx, [rax+20h]
0x180004e4b  neg     rax
0x180004e4e  sbb     rdi, rdi
0x180004e51  and     rdi, rcx
0x180004e54  jz      short loc_180004E96
0x180004e56  call    cs:__imp_GetCurrentThreadId
0x180004e5c  mov     r8d, eax
0x180004e5f  mov     r9d, eax
0x180004e62  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004e6c  shr     r8, 2
0x180004e70  mul     r8
0x180004e73  shr     rdx, 3
0x180004e77  lea     rcx, [rdx+rdx*4]
0x180004e7b  add     rcx, rcx
0x180004e7e  sub     r8, rcx
0x180004e81  mov     rbx, [rdi+r8*8+8]
0x180004e86  jmp     short loc_180004E91
0x180004e88  cmp     [rbx], r9d
0x180004e8b  jz      short loc_180004EA4
0x180004e8d  mov     rbx, [rbx+8]
0x180004e91  test    rbx, rbx
0x180004e94  jnz     short loc_180004E88
0x180004e96  mov     rax, rbx
0x180004e99  mov     rbx, [rsp+28h+arg_0]
0x180004e9e  add     rsp, 20h
0x180004ea2  pop     rdi
0x180004ea3  retn
0x180004ea4  add     rbx, 10h
0x180004ea8  jz      short loc_180004E96
0x180004eaa  cmp     qword ptr [rbx+8], 0
0x180004eaf  jnz     short loc_180004E96
0x180004eb1  lea     rax, [rdi+4]
0x180004eb5  mov     [rbx+8], rax
0x180004eb9  jmp     short loc_180004E96
```
