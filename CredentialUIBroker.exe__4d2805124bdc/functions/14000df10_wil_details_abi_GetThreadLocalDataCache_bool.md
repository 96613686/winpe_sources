# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000df10`
- end: `0x14000dfcd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cf70`

## callees

- `0x14000a67c`
- `0x14000df10`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000df6a`
- `KERNEL32!GetCurrentThreadId` at `0x14000df6a`

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
0x14000df10  mov     [rsp+arg_0], rbx
0x14000df15  push    rdi
0x14000df16  sub     rsp, 20h
0x14000df1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000df21  xor     ebx, ebx
0x14000df23  test    rdi, rdi
0x14000df26  jz      loc_14000DFBF
0x14000df2c  cmp     [rdi+8], rbx
0x14000df30  jnz     short loc_14000DF57
0x14000df32  mov     rcx, [rdi]
0x14000df35  lea     rdx, [rsp+28h+arg_8]
0x14000df3a  mov     [rsp+28h+arg_8], rbx
0x14000df3f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000df44  test    eax, eax
0x14000df46  js      short loc_14000DF57
0x14000df48  cmp     [rdi+8], rbx
0x14000df4c  jnz     short loc_14000DF57
0x14000df4e  mov     rax, [rsp+28h+arg_8]
0x14000df53  mov     [rdi+8], rax
0x14000df57  mov     rax, [rdi+8]
0x14000df5b  lea     rcx, [rax+20h]
0x14000df5f  neg     rax
0x14000df62  sbb     rdi, rdi
0x14000df65  and     rdi, rcx
0x14000df68  jz      short loc_14000DFBF
0x14000df6a  call    cs:__imp_GetCurrentThreadId
0x14000df70  mov     r8d, eax
0x14000df73  mov     r9d, eax
0x14000df76  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000df80  shr     r8, 2
0x14000df84  mul     r8
0x14000df87  shr     rdx, 3
0x14000df8b  lea     rcx, [rdx+rdx*4]
0x14000df8f  add     rcx, rcx
0x14000df92  sub     r8, rcx
0x14000df95  mov     rbx, [rdi+r8*8+8]
0x14000df9a  test    rbx, rbx
0x14000df9d  jz      short loc_14000DFBF
0x14000df9f  cmp     [rbx], r9d
0x14000dfa2  jz      short loc_14000DFAA
0x14000dfa4  mov     rbx, [rbx+8]
0x14000dfa8  jmp     short loc_14000DF9A
0x14000dfaa  add     rbx, 10h
0x14000dfae  jz      short loc_14000DFBF
0x14000dfb0  cmp     qword ptr [rbx+8], 0
0x14000dfb5  jnz     short loc_14000DFBF
0x14000dfb7  lea     rax, [rdi+4]
0x14000dfbb  mov     [rbx+8], rax
0x14000dfbf  mov     rax, rbx
0x14000dfc2  mov     rbx, [rsp+28h+arg_0]
0x14000dfc7  add     rsp, 20h
0x14000dfcb  pop     rdi
0x14000dfcc  retn
```
