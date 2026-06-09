# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800065e0`
- end: `0x18000669b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a50`

## callees

- `0x180003eb0`
- `0x1800065e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006636`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006636`

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
0x1800065e0  mov     [rsp+arg_0], rbx
0x1800065e5  push    rdi
0x1800065e6  sub     rsp, 20h
0x1800065ea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800065f1  xor     ebx, ebx
0x1800065f3  test    rdi, rdi
0x1800065f6  jz      short loc_180006676
0x1800065f8  cmp     [rdi+8], rbx
0x1800065fc  jnz     short loc_180006623
0x1800065fe  mov     rcx, [rdi]
0x180006601  lea     rdx, [rsp+28h+arg_8]
0x180006606  mov     [rsp+28h+arg_8], rbx
0x18000660b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006610  test    eax, eax
0x180006612  js      short loc_180006623
0x180006614  cmp     [rdi+8], rbx
0x180006618  jnz     short loc_180006623
0x18000661a  mov     rax, [rsp+28h+arg_8]
0x18000661f  mov     [rdi+8], rax
0x180006623  mov     rax, [rdi+8]
0x180006627  lea     rcx, [rax+20h]
0x18000662b  neg     rax
0x18000662e  sbb     rdi, rdi
0x180006631  and     rdi, rcx
0x180006634  jz      short loc_180006676
0x180006636  call    cs:__imp_GetCurrentThreadId
0x18000663c  mov     r8d, eax
0x18000663f  mov     r9d, eax
0x180006642  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000664c  shr     r8, 2
0x180006650  mul     r8
0x180006653  shr     rdx, 3
0x180006657  lea     rcx, [rdx+rdx*4]
0x18000665b  add     rcx, rcx
0x18000665e  sub     r8, rcx
0x180006661  mov     rbx, [rdi+r8*8+8]
0x180006666  jmp     short loc_180006671
0x180006668  cmp     [rbx], r9d
0x18000666b  jz      short loc_180006684
0x18000666d  mov     rbx, [rbx+8]
0x180006671  test    rbx, rbx
0x180006674  jnz     short loc_180006668
0x180006676  mov     rax, rbx
0x180006679  mov     rbx, [rsp+28h+arg_0]
0x18000667e  add     rsp, 20h
0x180006682  pop     rdi
0x180006683  retn
0x180006684  add     rbx, 10h
0x180006688  jz      short loc_180006676
0x18000668a  cmp     qword ptr [rbx+8], 0
0x18000668f  jnz     short loc_180006676
0x180006691  lea     rax, [rdi+4]
0x180006695  mov     [rbx+8], rax
0x180006699  jmp     short loc_180006676
```
