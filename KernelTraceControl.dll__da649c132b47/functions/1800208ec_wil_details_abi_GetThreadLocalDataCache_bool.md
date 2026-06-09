# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800208ec`
- end: `0x1800209a4`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `184`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020aa0`

## callees

- `0x1800208ec`
- `0x180023288`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020945`
- `KERNEL32!GetCurrentThreadId` at `0x180020945`

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
    v4 = *(_QWORD *)(v1 + 8);
    if ( v4 )
      v4 += 32;
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8);
            i && *(_DWORD *)(i + 40) != CurrentThreadId;
            i = *(_QWORD *)(i + 48) )
      {
        ;
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v4 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x1800208ec  mov     [rsp+arg_0], rbx
0x1800208f1  push    rdi
0x1800208f2  sub     rsp, 20h
0x1800208f6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800208fd  xor     ebx, ebx
0x1800208ff  test    rdi, rdi
0x180020902  jz      loc_180020996
0x180020908  cmp     [rdi+8], rbx
0x18002090c  jnz     short loc_180020933
0x18002090e  mov     rcx, [rdi]
0x180020911  lea     rdx, [rsp+28h+arg_8]
0x180020916  and     [rsp+28h+arg_8], rbx
0x18002091b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180020920  test    eax, eax
0x180020922  js      short loc_180020933
0x180020924  cmp     [rdi+8], rbx
0x180020928  jnz     short loc_180020933
0x18002092a  mov     rax, [rsp+28h+arg_8]
0x18002092f  mov     [rdi+8], rax
0x180020933  mov     rdi, [rdi+8]
0x180020937  test    rdi, rdi
0x18002093a  jz      short loc_180020940
0x18002093c  add     rdi, 20h ; ' '
0x180020940  test    rdi, rdi
0x180020943  jz      short loc_180020996
0x180020945  call    cs:__imp_GetCurrentThreadId
0x18002094b  mov     r8d, eax
0x18002094e  mov     r9d, eax
0x180020951  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002095b  mul     r9
0x18002095e  shr     rdx, 3
0x180020962  lea     rcx, [rdx+rdx*4]
0x180020966  add     rcx, rcx
0x180020969  sub     r8, rcx
0x18002096c  mov     rbx, [rdi+r8*8+8]
0x180020971  jmp     short loc_18002097D
0x180020973  cmp     [rbx+28h], r9d
0x180020977  jz      short loc_180020982
0x180020979  mov     rbx, [rbx+30h]
0x18002097d  test    rbx, rbx
0x180020980  jnz     short loc_180020973
0x180020982  test    rbx, rbx
0x180020985  jz      short loc_180020996
0x180020987  cmp     qword ptr [rbx+8], 0
0x18002098c  jnz     short loc_180020996
0x18002098e  lea     rcx, [rdi+4]
0x180020992  mov     [rbx+8], rcx
0x180020996  mov     rax, rbx
0x180020999  mov     rbx, [rsp+28h+arg_0]
0x18002099e  add     rsp, 20h
0x1800209a2  pop     rdi
0x1800209a3  retn
```
