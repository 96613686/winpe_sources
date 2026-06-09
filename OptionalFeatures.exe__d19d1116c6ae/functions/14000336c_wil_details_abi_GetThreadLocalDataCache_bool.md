# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000336c`
- end: `0x140003427`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b90`

## callees

- `0x1400024f4`
- `0x14000336c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400033c2`
- `KERNEL32!GetCurrentThreadId` at `0x1400033c2`

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
0x14000336c  mov     [rsp+arg_0], rbx
0x140003371  push    rdi
0x140003372  sub     rsp, 20h
0x140003376  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000337d  xor     ebx, ebx
0x14000337f  test    rdi, rdi
0x140003382  jz      short loc_140003402
0x140003384  cmp     [rdi+8], rbx
0x140003388  jnz     short loc_1400033AF
0x14000338a  mov     rcx, [rdi]
0x14000338d  lea     rdx, [rsp+28h+arg_8]
0x140003392  mov     [rsp+28h+arg_8], rbx
0x140003397  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000339c  test    eax, eax
0x14000339e  js      short loc_1400033AF
0x1400033a0  cmp     [rdi+8], rbx
0x1400033a4  jnz     short loc_1400033AF
0x1400033a6  mov     rax, [rsp+28h+arg_8]
0x1400033ab  mov     [rdi+8], rax
0x1400033af  mov     rax, [rdi+8]
0x1400033b3  lea     rcx, [rax+20h]
0x1400033b7  neg     rax
0x1400033ba  sbb     rdi, rdi
0x1400033bd  and     rdi, rcx
0x1400033c0  jz      short loc_140003402
0x1400033c2  call    cs:__imp_GetCurrentThreadId
0x1400033c8  mov     r8d, eax
0x1400033cb  mov     r9d, eax
0x1400033ce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400033d8  shr     r8, 2
0x1400033dc  mul     r8
0x1400033df  shr     rdx, 3
0x1400033e3  lea     rcx, [rdx+rdx*4]
0x1400033e7  add     rcx, rcx
0x1400033ea  sub     r8, rcx
0x1400033ed  mov     rbx, [rdi+r8*8+8]
0x1400033f2  jmp     short loc_1400033FD
0x1400033f4  cmp     [rbx], r9d
0x1400033f7  jz      short loc_140003410
0x1400033f9  mov     rbx, [rbx+8]
0x1400033fd  test    rbx, rbx
0x140003400  jnz     short loc_1400033F4
0x140003402  mov     rax, rbx
0x140003405  mov     rbx, [rsp+28h+arg_0]
0x14000340a  add     rsp, 20h
0x14000340e  pop     rdi
0x14000340f  retn
0x140003410  add     rbx, 10h
0x140003414  jz      short loc_140003402
0x140003416  cmp     qword ptr [rbx+8], 0
0x14000341b  jnz     short loc_140003402
0x14000341d  lea     rax, [rdi+4]
0x140003421  mov     [rbx+8], rax
0x140003425  jmp     short loc_140003402
```
