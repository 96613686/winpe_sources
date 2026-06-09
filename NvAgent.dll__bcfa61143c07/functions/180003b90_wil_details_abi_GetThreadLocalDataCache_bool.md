# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003b90`
- end: `0x180003c4b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033b0`

## callees

- `0x180002d18`
- `0x180003b90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003be6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003be6`

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
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  push    rdi
0x180003b96  sub     rsp, 20h
0x180003b9a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003ba1  xor     ebx, ebx
0x180003ba3  test    rdi, rdi
0x180003ba6  jz      short loc_180003C26
0x180003ba8  cmp     [rdi+8], rbx
0x180003bac  jnz     short loc_180003BD3
0x180003bae  mov     rcx, [rdi]
0x180003bb1  lea     rdx, [rsp+28h+arg_8]
0x180003bb6  mov     [rsp+28h+arg_8], rbx
0x180003bbb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003bc0  test    eax, eax
0x180003bc2  js      short loc_180003BD3
0x180003bc4  cmp     [rdi+8], rbx
0x180003bc8  jnz     short loc_180003BD3
0x180003bca  mov     rax, [rsp+28h+arg_8]
0x180003bcf  mov     [rdi+8], rax
0x180003bd3  mov     rax, [rdi+8]
0x180003bd7  lea     rcx, [rax+20h]
0x180003bdb  neg     rax
0x180003bde  sbb     rdi, rdi
0x180003be1  and     rdi, rcx
0x180003be4  jz      short loc_180003C26
0x180003be6  call    cs:__imp_GetCurrentThreadId
0x180003bec  mov     r8d, eax
0x180003bef  mov     r9d, eax
0x180003bf2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003bfc  shr     r8, 2
0x180003c00  mul     r8
0x180003c03  shr     rdx, 3
0x180003c07  lea     rcx, [rdx+rdx*4]
0x180003c0b  add     rcx, rcx
0x180003c0e  sub     r8, rcx
0x180003c11  mov     rbx, [rdi+r8*8+8]
0x180003c16  jmp     short loc_180003C21
0x180003c18  cmp     [rbx], r9d
0x180003c1b  jz      short loc_180003C34
0x180003c1d  mov     rbx, [rbx+8]
0x180003c21  test    rbx, rbx
0x180003c24  jnz     short loc_180003C18
0x180003c26  mov     rax, rbx
0x180003c29  mov     rbx, [rsp+28h+arg_0]
0x180003c2e  add     rsp, 20h
0x180003c32  pop     rdi
0x180003c33  retn
0x180003c34  add     rbx, 10h
0x180003c38  jz      short loc_180003C26
0x180003c3a  cmp     qword ptr [rbx+8], 0
0x180003c3f  jnz     short loc_180003C26
0x180003c41  lea     rax, [rdi+4]
0x180003c45  mov     [rbx+8], rax
0x180003c49  jmp     short loc_180003C26
```
