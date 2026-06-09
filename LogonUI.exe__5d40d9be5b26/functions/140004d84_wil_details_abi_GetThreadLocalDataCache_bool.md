# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004d84`
- end: `0x140004e41`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400047d0`

## callees

- `0x140003ee4`
- `0x140004d84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004dde`

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
0x140004d84  mov     [rsp+arg_0], rbx
0x140004d89  push    rdi
0x140004d8a  sub     rsp, 20h
0x140004d8e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004d95  xor     ebx, ebx
0x140004d97  test    rdi, rdi
0x140004d9a  jz      loc_140004E33
0x140004da0  cmp     [rdi+8], rbx
0x140004da4  jnz     short loc_140004DCB
0x140004da6  mov     rcx, [rdi]
0x140004da9  lea     rdx, [rsp+28h+arg_8]
0x140004dae  mov     [rsp+28h+arg_8], rbx
0x140004db3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004db8  test    eax, eax
0x140004dba  js      short loc_140004DCB
0x140004dbc  cmp     [rdi+8], rbx
0x140004dc0  jnz     short loc_140004DCB
0x140004dc2  mov     rax, [rsp+28h+arg_8]
0x140004dc7  mov     [rdi+8], rax
0x140004dcb  mov     rax, [rdi+8]
0x140004dcf  lea     rcx, [rax+20h]
0x140004dd3  neg     rax
0x140004dd6  sbb     rdi, rdi
0x140004dd9  and     rdi, rcx
0x140004ddc  jz      short loc_140004E33
0x140004dde  call    cs:__imp_GetCurrentThreadId
0x140004de4  mov     r8d, eax
0x140004de7  mov     r9d, eax
0x140004dea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004df4  shr     r8, 2
0x140004df8  mul     r8
0x140004dfb  shr     rdx, 3
0x140004dff  lea     rcx, [rdx+rdx*4]
0x140004e03  add     rcx, rcx
0x140004e06  sub     r8, rcx
0x140004e09  mov     rbx, [rdi+r8*8+8]
0x140004e0e  test    rbx, rbx
0x140004e11  jz      short loc_140004E33
0x140004e13  cmp     [rbx], r9d
0x140004e16  jz      short loc_140004E1E
0x140004e18  mov     rbx, [rbx+8]
0x140004e1c  jmp     short loc_140004E0E
0x140004e1e  add     rbx, 10h
0x140004e22  jz      short loc_140004E33
0x140004e24  cmp     qword ptr [rbx+8], 0
0x140004e29  jnz     short loc_140004E33
0x140004e2b  lea     rax, [rdi+4]
0x140004e2f  mov     [rbx+8], rax
0x140004e33  mov     rax, rbx
0x140004e36  mov     rbx, [rsp+28h+arg_0]
0x140004e3b  add     rsp, 20h
0x140004e3f  pop     rdi
0x140004e40  retn
```
