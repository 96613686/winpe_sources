# CBaseFilter::Unregister(void)

- ea: `0x180006510`
- end: `0x1800065be`
- name: `?Unregister@CBaseFilter@@UEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a3f0`

## callees

- `0x180006510`
- `0x1800065c4`
- `0x180034010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000656b`
- `ole32!CoCreateInstance` at `0x18000656b`
- `ole32!CoUninitialize` at `0x1800065a0`
- `ole32!CoUninitialize` at `0x1800065a0`
- `ole32!CoFreeUnusedLibraries` at `0x18000659a`
- `ole32!CoFreeUnusedLibraries` at `0x18000659a`
- `ole32!CoInitializeEx` at `0x18000653e`
- `ole32!CoInitializeEx` at `0x18000653e`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Unregister(CBaseFilter *this)
{
  __int64 v1; // rdi
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 4) + 64LL))((char *)this - 32);
  if ( !v1 )
    return 1;
  CoInitializeEx(0, 2u);
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv);
  if ( v3 >= 0 )
  {
    v3 = AMovieSetupRegisterFilter(v1, ppv, 0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  if ( v3 == -2147024894 )
    return 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006510  mov     [rsp+arg_8], rbx
0x180006515  push    rdi
0x180006516  sub     rsp, 30h
0x18000651a  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18000651e  mov     rax, [rcx]
0x180006521  mov     rax, [rax+40h]
0x180006525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652a  mov     rdi, rax
0x18000652d  test    rax, rax
0x180006530  jnz     short loc_180006537
0x180006532  lea     eax, [rdi+1]
0x180006535  jmp     short loc_1800065B3
0x180006537  mov     edx, 2; dwCoInit
0x18000653c  xor     ecx, ecx; pvReserved
0x18000653e  call    cs:__imp_CoInitializeEx
0x180006544  xor     edx, edx; pUnkOuter
0x180006546  mov     [rsp+38h+arg_0], 0
0x18000654f  lea     rax, [rsp+38h+arg_0]
0x180006554  lea     r9, IID_IFilterMapper; riid
0x18000655b  mov     [rsp+38h+ppv], rax; ppv
0x180006560  lea     rcx, CLSID_FilterMapper; rclsid
0x180006567  lea     r8d, [rdx+1]; dwClsContext
0x18000656b  call    cs:__imp_CoCreateInstance
0x180006571  mov     ebx, eax
0x180006573  test    eax, eax
0x180006575  js      short loc_18000659A
0x180006577  mov     rdx, [rsp+38h+arg_0]
0x18000657c  xor     r8d, r8d
0x18000657f  mov     rcx, rdi
0x180006582  call    AMovieSetupRegisterFilter
0x180006587  mov     rcx, [rsp+38h+arg_0]
0x18000658c  mov     ebx, eax
0x18000658e  mov     rax, [rcx]
0x180006591  mov     rax, [rax+10h]
0x180006595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659a  call    cs:__imp_CoFreeUnusedLibraries
0x1800065a0  call    cs:__imp_CoUninitialize
0x1800065a6  xor     eax, eax
0x1800065a8  cmp     ebx, 80070002h
0x1800065ae  cmovz   ebx, eax
0x1800065b1  mov     eax, ebx
0x1800065b3  mov     rbx, [rsp+38h+arg_8]
0x1800065b8  add     rsp, 30h
0x1800065bc  pop     rdi
0x1800065bd  retn
```
