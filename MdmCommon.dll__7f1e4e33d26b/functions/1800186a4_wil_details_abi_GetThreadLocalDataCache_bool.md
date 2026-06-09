# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800186a4`
- end: `0x18001875f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018180`

## callees

- `0x180017b0c`
- `0x1800186a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186fa`

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
0x1800186a4  mov     [rsp+arg_0], rbx
0x1800186a9  push    rdi
0x1800186aa  sub     rsp, 20h
0x1800186ae  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800186b5  xor     ebx, ebx
0x1800186b7  test    rdi, rdi
0x1800186ba  jz      short loc_18001873A
0x1800186bc  cmp     [rdi+8], rbx
0x1800186c0  jnz     short loc_1800186E7
0x1800186c2  mov     rcx, [rdi]
0x1800186c5  lea     rdx, [rsp+28h+arg_8]
0x1800186ca  mov     [rsp+28h+arg_8], rbx
0x1800186cf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800186d4  test    eax, eax
0x1800186d6  js      short loc_1800186E7
0x1800186d8  cmp     [rdi+8], rbx
0x1800186dc  jnz     short loc_1800186E7
0x1800186de  mov     rax, [rsp+28h+arg_8]
0x1800186e3  mov     [rdi+8], rax
0x1800186e7  mov     rax, [rdi+8]
0x1800186eb  lea     rcx, [rax+20h]
0x1800186ef  neg     rax
0x1800186f2  sbb     rdi, rdi
0x1800186f5  and     rdi, rcx
0x1800186f8  jz      short loc_18001873A
0x1800186fa  call    cs:__imp_GetCurrentThreadId
0x180018700  mov     r8d, eax
0x180018703  mov     r9d, eax
0x180018706  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180018710  shr     r8, 2
0x180018714  mul     r8
0x180018717  shr     rdx, 3
0x18001871b  lea     rcx, [rdx+rdx*4]
0x18001871f  add     rcx, rcx
0x180018722  sub     r8, rcx
0x180018725  mov     rbx, [rdi+r8*8+8]
0x18001872a  jmp     short loc_180018735
0x18001872c  cmp     [rbx], r9d
0x18001872f  jz      short loc_180018748
0x180018731  mov     rbx, [rbx+8]
0x180018735  test    rbx, rbx
0x180018738  jnz     short loc_18001872C
0x18001873a  mov     rax, rbx
0x18001873d  mov     rbx, [rsp+28h+arg_0]
0x180018742  add     rsp, 20h
0x180018746  pop     rdi
0x180018747  retn
0x180018748  add     rbx, 10h
0x18001874c  jz      short loc_18001873A
0x18001874e  cmp     qword ptr [rbx+8], 0
0x180018753  jnz     short loc_18001873A
0x180018755  lea     rax, [rdi+4]
0x180018759  mov     [rbx+8], rax
0x18001875d  jmp     short loc_18001873A
```
