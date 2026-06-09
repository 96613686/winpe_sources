# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004d5c`
- end: `0x180004e22`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004600`

## callees

- `0x18000422c`
- `0x180004d5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004db6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004db6`

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
0x180004d5c  mov     [rsp+arg_0], rbx
0x180004d61  push    rdi
0x180004d62  sub     rsp, 20h
0x180004d66  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004d6d  xor     ebx, ebx
0x180004d6f  test    rdi, rdi
0x180004d72  jz      loc_180004DFC
0x180004d78  cmp     [rdi+8], rbx
0x180004d7c  jnz     short loc_180004DA3
0x180004d7e  mov     rcx, [rdi]
0x180004d81  lea     rdx, [rsp+28h+arg_8]
0x180004d86  mov     [rsp+28h+arg_8], rbx
0x180004d8b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004d90  test    eax, eax
0x180004d92  js      short loc_180004DA3
0x180004d94  cmp     [rdi+8], rbx
0x180004d98  jnz     short loc_180004DA3
0x180004d9a  mov     rax, [rsp+28h+arg_8]
0x180004d9f  mov     [rdi+8], rax
0x180004da3  mov     rax, [rdi+8]
0x180004da7  lea     rcx, [rax+20h]
0x180004dab  neg     rax
0x180004dae  sbb     rdi, rdi
0x180004db1  and     rdi, rcx
0x180004db4  jz      short loc_180004DFC
0x180004db6  call    cs:__imp_GetCurrentThreadId
0x180004dbd  nop     dword ptr [rax+rax+00h]
0x180004dc2  mov     r8d, eax
0x180004dc5  mov     r9d, eax
0x180004dc8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004dd2  shr     r8, 2
0x180004dd6  mul     r8
0x180004dd9  shr     rdx, 3
0x180004ddd  lea     rcx, [rdx+rdx*4]
0x180004de1  add     rcx, rcx
0x180004de4  sub     r8, rcx
0x180004de7  mov     rbx, [rdi+r8*8+8]
0x180004dec  jmp     short loc_180004DF7
0x180004dee  cmp     [rbx], r9d
0x180004df1  jz      short loc_180004E0B
0x180004df3  mov     rbx, [rbx+8]
0x180004df7  test    rbx, rbx
0x180004dfa  jnz     short loc_180004DEE
0x180004dfc  mov     rax, rbx
0x180004dff  mov     rbx, [rsp+28h+arg_0]
0x180004e04  add     rsp, 20h
0x180004e08  pop     rdi
0x180004e09  retn
0x180004e0b  add     rbx, 10h
0x180004e0f  jz      short loc_180004DFC
0x180004e11  cmp     qword ptr [rbx+8], 0
0x180004e16  jnz     short loc_180004DFC
0x180004e18  lea     rax, [rdi+4]
0x180004e1c  mov     [rbx+8], rax
0x180004e20  jmp     short loc_180004DFC
```
