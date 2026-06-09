# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400063f4`
- end: `0x1400064af`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400059f0`

## callees

- `0x1400040c8`
- `0x1400063f4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000644a`
- `KERNEL32!GetCurrentThreadId` at `0x14000644a`

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
0x1400063f4  mov     [rsp+arg_0], rbx
0x1400063f9  push    rdi
0x1400063fa  sub     rsp, 20h
0x1400063fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006405  xor     ebx, ebx
0x140006407  test    rdi, rdi
0x14000640a  jz      short loc_14000648A
0x14000640c  cmp     [rdi+8], rbx
0x140006410  jnz     short loc_140006437
0x140006412  mov     rcx, [rdi]
0x140006415  lea     rdx, [rsp+28h+arg_8]
0x14000641a  mov     [rsp+28h+arg_8], rbx
0x14000641f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140006424  test    eax, eax
0x140006426  js      short loc_140006437
0x140006428  cmp     [rdi+8], rbx
0x14000642c  jnz     short loc_140006437
0x14000642e  mov     rax, [rsp+28h+arg_8]
0x140006433  mov     [rdi+8], rax
0x140006437  mov     rax, [rdi+8]
0x14000643b  lea     rcx, [rax+20h]
0x14000643f  neg     rax
0x140006442  sbb     rdi, rdi
0x140006445  and     rdi, rcx
0x140006448  jz      short loc_14000648A
0x14000644a  call    cs:__imp_GetCurrentThreadId
0x140006450  mov     r8d, eax
0x140006453  mov     r9d, eax
0x140006456  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006460  shr     r8, 2
0x140006464  mul     r8
0x140006467  shr     rdx, 3
0x14000646b  lea     rcx, [rdx+rdx*4]
0x14000646f  add     rcx, rcx
0x140006472  sub     r8, rcx
0x140006475  mov     rbx, [rdi+r8*8+8]
0x14000647a  jmp     short loc_140006485
0x14000647c  cmp     [rbx], r9d
0x14000647f  jz      short loc_140006498
0x140006481  mov     rbx, [rbx+8]
0x140006485  test    rbx, rbx
0x140006488  jnz     short loc_14000647C
0x14000648a  mov     rax, rbx
0x14000648d  mov     rbx, [rsp+28h+arg_0]
0x140006492  add     rsp, 20h
0x140006496  pop     rdi
0x140006497  retn
0x140006498  add     rbx, 10h
0x14000649c  jz      short loc_14000648A
0x14000649e  cmp     qword ptr [rbx+8], 0
0x1400064a3  jnz     short loc_14000648A
0x1400064a5  lea     rax, [rdi+4]
0x1400064a9  mov     [rbx+8], rax
0x1400064ad  jmp     short loc_14000648A
```
