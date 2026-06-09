# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002389c`
- end: `0x180023959`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800232c0`

## callees

- `0x18001d9a4`
- `0x18002389c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238f6`

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
0x18002389c  mov     [rsp+arg_0], rbx
0x1800238a1  push    rdi
0x1800238a2  sub     rsp, 20h
0x1800238a6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800238ad  xor     ebx, ebx
0x1800238af  test    rdi, rdi
0x1800238b2  jz      loc_18002394B
0x1800238b8  cmp     [rdi+8], rbx
0x1800238bc  jnz     short loc_1800238E3
0x1800238be  mov     rcx, [rdi]
0x1800238c1  lea     rdx, [rsp+28h+arg_8]
0x1800238c6  mov     [rsp+28h+arg_8], rbx
0x1800238cb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800238d0  test    eax, eax
0x1800238d2  js      short loc_1800238E3
0x1800238d4  cmp     [rdi+8], rbx
0x1800238d8  jnz     short loc_1800238E3
0x1800238da  mov     rax, [rsp+28h+arg_8]
0x1800238df  mov     [rdi+8], rax
0x1800238e3  mov     rax, [rdi+8]
0x1800238e7  lea     rcx, [rax+20h]
0x1800238eb  neg     rax
0x1800238ee  sbb     rdi, rdi
0x1800238f1  and     rdi, rcx
0x1800238f4  jz      short loc_18002394B
0x1800238f6  call    cs:__imp_GetCurrentThreadId
0x1800238fc  mov     r8d, eax
0x1800238ff  mov     r9d, eax
0x180023902  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002390c  shr     r8, 2
0x180023910  mul     r8
0x180023913  shr     rdx, 3
0x180023917  lea     rcx, [rdx+rdx*4]
0x18002391b  add     rcx, rcx
0x18002391e  sub     r8, rcx
0x180023921  mov     rbx, [rdi+r8*8+8]
0x180023926  test    rbx, rbx
0x180023929  jz      short loc_18002394B
0x18002392b  cmp     [rbx], r9d
0x18002392e  jz      short loc_180023936
0x180023930  mov     rbx, [rbx+8]
0x180023934  jmp     short loc_180023926
0x180023936  add     rbx, 10h
0x18002393a  jz      short loc_18002394B
0x18002393c  cmp     qword ptr [rbx+8], 0
0x180023941  jnz     short loc_18002394B
0x180023943  lea     rax, [rdi+4]
0x180023947  mov     [rbx+8], rax
0x18002394b  mov     rax, rbx
0x18002394e  mov     rbx, [rsp+28h+arg_0]
0x180023953  add     rsp, 20h
0x180023957  pop     rdi
0x180023958  retn
```
