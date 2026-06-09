# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800065f4`
- end: `0x1800066b1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ee0`

## callees

- `0x180005618`
- `0x1800065f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000664e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000664e`

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
0x1800065f4  mov     [rsp+arg_0], rbx
0x1800065f9  push    rdi
0x1800065fa  sub     rsp, 20h
0x1800065fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006605  xor     ebx, ebx
0x180006607  test    rdi, rdi
0x18000660a  jz      loc_1800066A3
0x180006610  cmp     [rdi+8], rbx
0x180006614  jnz     short loc_18000663B
0x180006616  mov     rcx, [rdi]
0x180006619  lea     rdx, [rsp+28h+arg_8]
0x18000661e  mov     [rsp+28h+arg_8], rbx
0x180006623  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006628  test    eax, eax
0x18000662a  js      short loc_18000663B
0x18000662c  cmp     [rdi+8], rbx
0x180006630  jnz     short loc_18000663B
0x180006632  mov     rax, [rsp+28h+arg_8]
0x180006637  mov     [rdi+8], rax
0x18000663b  mov     rax, [rdi+8]
0x18000663f  lea     rcx, [rax+20h]
0x180006643  neg     rax
0x180006646  sbb     rdi, rdi
0x180006649  and     rdi, rcx
0x18000664c  jz      short loc_1800066A3
0x18000664e  call    cs:__imp_GetCurrentThreadId
0x180006654  mov     r8d, eax
0x180006657  mov     r9d, eax
0x18000665a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006664  shr     r8, 2
0x180006668  mul     r8
0x18000666b  shr     rdx, 3
0x18000666f  lea     rcx, [rdx+rdx*4]
0x180006673  add     rcx, rcx
0x180006676  sub     r8, rcx
0x180006679  mov     rbx, [rdi+r8*8+8]
0x18000667e  test    rbx, rbx
0x180006681  jz      short loc_1800066A3
0x180006683  cmp     [rbx], r9d
0x180006686  jz      short loc_18000668E
0x180006688  mov     rbx, [rbx+8]
0x18000668c  jmp     short loc_18000667E
0x18000668e  add     rbx, 10h
0x180006692  jz      short loc_1800066A3
0x180006694  cmp     qword ptr [rbx+8], 0
0x180006699  jnz     short loc_1800066A3
0x18000669b  lea     rax, [rdi+4]
0x18000669f  mov     [rbx+8], rax
0x1800066a3  mov     rax, rbx
0x1800066a6  mov     rbx, [rsp+28h+arg_0]
0x1800066ab  add     rsp, 20h
0x1800066af  pop     rdi
0x1800066b0  retn
```
