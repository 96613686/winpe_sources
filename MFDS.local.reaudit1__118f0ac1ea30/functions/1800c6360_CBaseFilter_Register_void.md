# CBaseFilter::Register(void)

- ea: `0x1800c6360`
- end: `0x1800c6415`
- name: `?Register@CBaseFilter@@UEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CBaseFilter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800c6360`
- `0x1800c6b00`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c63c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c63c0`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800c63f4`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800c63f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6400`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6400`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c638d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c638d`

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
0x1800c6360  push    rbx
0x1800c6362  sub     rsp, 30h
0x1800c6366  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800c636a  mov     rax, [rcx]
0x1800c636d  mov     rax, [rax+40h]
0x1800c6371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6376  mov     rbx, rax
0x1800c6379  test    rax, rax
0x1800c637c  jnz     short loc_1800C6386
0x1800c637e  lea     eax, [rbx+1]
0x1800c6381  jmp     loc_1800C640E
0x1800c6386  mov     edx, 2; dwCoInit
0x1800c638b  xor     ecx, ecx; pvReserved
0x1800c638d  call    cs:__imp_CoInitializeEx
0x1800c6394  nop     dword ptr [rax+rax+00h]
0x1800c6399  xor     edx, edx; pUnkOuter
0x1800c639b  mov     [rsp+38h+arg_0], 0
0x1800c63a4  lea     rax, [rsp+38h+arg_0]
0x1800c63a9  lea     r9, IID_IFilterMapper; riid
0x1800c63b0  mov     [rsp+38h+ppv], rax; ppv
0x1800c63b5  lea     rcx, CLSID_FilterMapper; rclsid
0x1800c63bc  lea     r8d, [rdx+1]; dwClsContext
0x1800c63c0  call    cs:__imp_CoCreateInstance
0x1800c63c7  nop     dword ptr [rax+rax+00h]
0x1800c63cc  test    eax, eax
0x1800c63ce  js      short loc_1800C63F4
0x1800c63d0  mov     rdx, [rsp+38h+arg_0]
0x1800c63d5  mov     r8d, 1
0x1800c63db  mov     rcx, rbx
0x1800c63de  call    AMovieSetupRegisterFilter
0x1800c63e3  mov     rcx, [rsp+38h+arg_0]
0x1800c63e8  mov     rax, [rcx]
0x1800c63eb  mov     rax, [rax+10h]
0x1800c63ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c63f4  call    cs:__imp_CoFreeUnusedLibraries
0x1800c63fb  nop     dword ptr [rax+rax+00h]
0x1800c6400  call    cs:__imp_CoUninitialize
0x1800c6407  nop     dword ptr [rax+rax+00h]
0x1800c640c  xor     eax, eax
0x1800c640e  add     rsp, 30h
0x1800c6412  pop     rbx
0x1800c6413  retn
```
