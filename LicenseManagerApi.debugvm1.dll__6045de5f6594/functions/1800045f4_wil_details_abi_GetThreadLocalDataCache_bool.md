# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800045f4`
- end: `0x1800046af`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e20`

## callees

- `0x1800037a8`
- `0x1800045f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000464a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000464a`

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
0x1800045f4  mov     [rsp+arg_0], rbx
0x1800045f9  push    rdi
0x1800045fa  sub     rsp, 20h
0x1800045fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004605  xor     ebx, ebx
0x180004607  test    rdi, rdi
0x18000460a  jz      short loc_18000468A
0x18000460c  cmp     [rdi+8], rbx
0x180004610  jnz     short loc_180004637
0x180004612  mov     rcx, [rdi]
0x180004615  lea     rdx, [rsp+28h+arg_8]
0x18000461a  mov     [rsp+28h+arg_8], rbx
0x18000461f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004624  test    eax, eax
0x180004626  js      short loc_180004637
0x180004628  cmp     [rdi+8], rbx
0x18000462c  jnz     short loc_180004637
0x18000462e  mov     rax, [rsp+28h+arg_8]
0x180004633  mov     [rdi+8], rax
0x180004637  mov     rax, [rdi+8]
0x18000463b  lea     rcx, [rax+20h]
0x18000463f  neg     rax
0x180004642  sbb     rdi, rdi
0x180004645  and     rdi, rcx
0x180004648  jz      short loc_18000468A
0x18000464a  call    cs:__imp_GetCurrentThreadId
0x180004650  mov     r8d, eax
0x180004653  mov     r9d, eax
0x180004656  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004660  shr     r8, 2
0x180004664  mul     r8
0x180004667  shr     rdx, 3
0x18000466b  lea     rcx, [rdx+rdx*4]
0x18000466f  add     rcx, rcx
0x180004672  sub     r8, rcx
0x180004675  mov     rbx, [rdi+r8*8+8]
0x18000467a  jmp     short loc_180004685
0x18000467c  cmp     [rbx], r9d
0x18000467f  jz      short loc_180004698
0x180004681  mov     rbx, [rbx+8]
0x180004685  test    rbx, rbx
0x180004688  jnz     short loc_18000467C
0x18000468a  mov     rax, rbx
0x18000468d  mov     rbx, [rsp+28h+arg_0]
0x180004692  add     rsp, 20h
0x180004696  pop     rdi
0x180004697  retn
0x180004698  add     rbx, 10h
0x18000469c  jz      short loc_18000468A
0x18000469e  cmp     qword ptr [rbx+8], 0
0x1800046a3  jnz     short loc_18000468A
0x1800046a5  lea     rax, [rdi+4]
0x1800046a9  mov     [rbx+8], rax
0x1800046ad  jmp     short loc_18000468A
```
