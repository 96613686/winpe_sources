# CBaseFilter::Unregister(void)

- ea: `0x180028860`
- end: `0x18002892c`
- name: `?Unregister@CBaseFilter@@UEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180028860`
- `0x180028934`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800288c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800288c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028892`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180028892`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800288fb`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800288fb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180028907`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180028907`

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
0x180028860  mov     [rsp+arg_8], rbx
0x180028865  push    rdi
0x180028866  sub     rsp, 30h
0x18002886a  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18002886e  mov     rax, [rcx]
0x180028871  mov     rax, [rax+40h]
0x180028875  call    cs:__guard_dispatch_icall_fptr
0x18002887b  mov     rdi, rax
0x18002887e  test    rax, rax
0x180028881  jnz     short loc_18002888B
0x180028883  lea     eax, [rdi+1]
0x180028886  jmp     loc_180028920
0x18002888b  mov     edx, 2; dwCoInit
0x180028890  xor     ecx, ecx; pvReserved
0x180028892  call    cs:__imp_CoInitializeEx
0x180028899  nop     dword ptr [rax+rax+00h]
0x18002889e  xor     edx, edx; pUnkOuter
0x1800288a0  mov     [rsp+38h+arg_0], 0
0x1800288a9  lea     rax, [rsp+38h+arg_0]
0x1800288ae  lea     r9, IID_IFilterMapper; riid
0x1800288b5  mov     [rsp+38h+ppv], rax; ppv
0x1800288ba  lea     rcx, CLSID_FilterMapper; rclsid
0x1800288c1  lea     r8d, [rdx+1]; dwClsContext
0x1800288c5  call    cs:__imp_CoCreateInstance
0x1800288cc  nop     dword ptr [rax+rax+00h]
0x1800288d1  mov     ebx, eax
0x1800288d3  test    eax, eax
0x1800288d5  js      short loc_1800288FB
0x1800288d7  mov     rdx, [rsp+38h+arg_0]
0x1800288dc  xor     r8d, r8d
0x1800288df  mov     rcx, rdi
0x1800288e2  call    AMovieSetupRegisterFilter
0x1800288e7  mov     rcx, [rsp+38h+arg_0]
0x1800288ec  mov     ebx, eax
0x1800288ee  mov     rax, [rcx]
0x1800288f1  mov     rax, [rax+10h]
0x1800288f5  call    cs:__guard_dispatch_icall_fptr
0x1800288fb  call    cs:__imp_CoFreeUnusedLibraries
0x180028902  nop     dword ptr [rax+rax+00h]
0x180028907  call    cs:__imp_CoUninitialize
0x18002890e  nop     dword ptr [rax+rax+00h]
0x180028913  xor     eax, eax
0x180028915  cmp     ebx, 80070002h
0x18002891b  cmovz   ebx, eax
0x18002891e  mov     eax, ebx
0x180028920  mov     rbx, [rsp+38h+arg_8]
0x180028925  add     rsp, 30h
0x180028929  pop     rdi
0x18002892a  retn
```
