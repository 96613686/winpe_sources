# CBaseFilter::Register(void)

- ea: `0x180005950`
- end: `0x1800059e9`
- name: `?Register@CBaseFilter@@UEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a140`
- `0x18000ab40`

## callees

- `0x180005950`
- `0x1800065c4`
- `0x180034010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800059a7`
- `ole32!CoCreateInstance` at `0x1800059a7`
- `ole32!CoUninitialize` at `0x1800059db`
- `ole32!CoUninitialize` at `0x1800059db`
- `ole32!CoFreeUnusedLibraries` at `0x1800059d5`
- `ole32!CoFreeUnusedLibraries` at `0x1800059d5`
- `ole32!CoInitializeEx` at `0x18000597a`
- `ole32!CoInitializeEx` at `0x18000597a`

## pseudocode

```c
__int64 __fastcall CBaseFilter::Register(CBaseFilter *this)
{
  __int64 v1; // rbx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 4) + 64LL))((char *)this - 32);
  if ( !v1 )
    return 1;
  CoInitializeEx(0, 2u);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &ppv) >= 0 )
  {
    AMovieSetupRegisterFilter(v1, ppv, 1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  CoFreeUnusedLibraries();
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180005950  push    rbx
0x180005952  sub     rsp, 30h
0x180005956  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18000595a  mov     rax, [rcx]
0x18000595d  mov     rax, [rax+40h]
0x180005961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005966  mov     rbx, rax
0x180005969  test    rax, rax
0x18000596c  jnz     short loc_180005973
0x18000596e  lea     eax, [rbx+1]
0x180005971  jmp     short loc_1800059E3
0x180005973  mov     edx, 2; dwCoInit
0x180005978  xor     ecx, ecx; pvReserved
0x18000597a  call    cs:__imp_CoInitializeEx
0x180005980  xor     edx, edx; pUnkOuter
0x180005982  mov     [rsp+38h+arg_0], 0
0x18000598b  lea     rax, [rsp+38h+arg_0]
0x180005990  lea     r9, IID_IFilterMapper; riid
0x180005997  mov     [rsp+38h+ppv], rax; ppv
0x18000599c  lea     rcx, CLSID_FilterMapper; rclsid
0x1800059a3  lea     r8d, [rdx+1]; dwClsContext
0x1800059a7  call    cs:__imp_CoCreateInstance
0x1800059ad  test    eax, eax
0x1800059af  js      short loc_1800059D5
0x1800059b1  mov     rdx, [rsp+38h+arg_0]
0x1800059b6  mov     r8d, 1
0x1800059bc  mov     rcx, rbx
0x1800059bf  call    AMovieSetupRegisterFilter
0x1800059c4  mov     rcx, [rsp+38h+arg_0]
0x1800059c9  mov     rax, [rcx]
0x1800059cc  mov     rax, [rax+10h]
0x1800059d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d5  call    cs:__imp_CoFreeUnusedLibraries
0x1800059db  call    cs:__imp_CoUninitialize
0x1800059e1  xor     eax, eax
0x1800059e3  add     rsp, 30h
0x1800059e7  pop     rbx
0x1800059e8  retn
```
