# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003d90`
- end: `0x180003e4b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035b0`

## callees

- `0x180002eb8`
- `0x180003d90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de6`

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
0x180003d90  mov     [rsp+arg_0], rbx
0x180003d95  push    rdi
0x180003d96  sub     rsp, 20h
0x180003d9a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003da1  xor     ebx, ebx
0x180003da3  test    rdi, rdi
0x180003da6  jz      short loc_180003E26
0x180003da8  cmp     [rdi+8], rbx
0x180003dac  jnz     short loc_180003DD3
0x180003dae  mov     rcx, [rdi]
0x180003db1  lea     rdx, [rsp+28h+arg_8]
0x180003db6  mov     [rsp+28h+arg_8], rbx
0x180003dbb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003dc0  test    eax, eax
0x180003dc2  js      short loc_180003DD3
0x180003dc4  cmp     [rdi+8], rbx
0x180003dc8  jnz     short loc_180003DD3
0x180003dca  mov     rax, [rsp+28h+arg_8]
0x180003dcf  mov     [rdi+8], rax
0x180003dd3  mov     rax, [rdi+8]
0x180003dd7  lea     rcx, [rax+20h]
0x180003ddb  neg     rax
0x180003dde  sbb     rdi, rdi
0x180003de1  and     rdi, rcx
0x180003de4  jz      short loc_180003E26
0x180003de6  call    cs:__imp_GetCurrentThreadId
0x180003dec  mov     r8d, eax
0x180003def  mov     r9d, eax
0x180003df2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003dfc  shr     r8, 2
0x180003e00  mul     r8
0x180003e03  shr     rdx, 3
0x180003e07  lea     rcx, [rdx+rdx*4]
0x180003e0b  add     rcx, rcx
0x180003e0e  sub     r8, rcx
0x180003e11  mov     rbx, [rdi+r8*8+8]
0x180003e16  jmp     short loc_180003E21
0x180003e18  cmp     [rbx], r9d
0x180003e1b  jz      short loc_180003E34
0x180003e1d  mov     rbx, [rbx+8]
0x180003e21  test    rbx, rbx
0x180003e24  jnz     short loc_180003E18
0x180003e26  mov     rax, rbx
0x180003e29  mov     rbx, [rsp+28h+arg_0]
0x180003e2e  add     rsp, 20h
0x180003e32  pop     rdi
0x180003e33  retn
0x180003e34  add     rbx, 10h
0x180003e38  jz      short loc_180003E26
0x180003e3a  cmp     qword ptr [rbx+8], 0
0x180003e3f  jnz     short loc_180003E26
0x180003e41  lea     rax, [rdi+4]
0x180003e45  mov     [rbx+8], rax
0x180003e49  jmp     short loc_180003E26
```
