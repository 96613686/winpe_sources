# UiaInitCrossMachineConnectionW(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x1800727e0`
- end: `0x180072926`
- name: `?UiaInitCrossMachineConnectionW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `326`
- prototype: `void __fastcall(HWND, HINSTANCE, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067f8`
- `0x18007243c`
- `0x180072508`
- `0x180072554`
- `0x1800727e0`
- `0x18007ee70`
- `0x18007ef94`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180072910`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180072910`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072851`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072851`

## string_xrefs

- `0x18007289f`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactoryclassfactory.cpp`
- `0x1800728ee`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestubfactoryclassfactory.cpp`
- `0x180072890`: `Fail to create local cross machine stub factory with elevation moniker`
- `0x180072857`: `Fail to create local cross machine stub factory`
- `0x1800728df`: `Failed to create local cross machine stub`

## pseudocode

```c
void __fastcall UiaInitCrossMachineConnectionW(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  const struct _GUID *v3; // rdx
  const struct _GUID *v4; // r8
  LPVOID v5; // rcx
  wil::details::in1diag3 *v6; // rbx
  unsigned int v7; // edi
  unsigned int ElevatedInstanceWithElevationMoniker; // eax
  const char *v9; // rcx
  HWND v10; // rcx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, __int128 *); // rbx
  unsigned int v13; // eax
  const char *v14; // [rsp+28h] [rbp-38h]
  const char *v15; // [rsp+28h] [rbp-38h]
  _BYTE v16[8]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  struct _GUID v19; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  wil::CoInitializeEx_failfast(v16, a2, a3);
  ppv = 0;
  if ( BasicUiaUtils::IsUiaManagerElevated() )
  {
    v10 = (HWND)ppv;
    ppv = 0;
    if ( v10 )
      (*(void (__fastcall **)(HWND))(*(_QWORD *)v10 + 16LL))(v10);
    v6 = retaddr;
    v7 = 143;
    ElevatedInstanceWithElevationMoniker = BasicUiaUtils::GetElevatedInstanceWithElevationMoniker(v10, v3, v4, &ppv);
    v9 = "Fail to create local cross machine stub factory with elevation moniker";
  }
  else
  {
    v5 = ppv;
    ppv = 0;
    if ( v5 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = retaddr;
    v7 = 131;
    ElevatedInstanceWithElevationMoniker = CoCreateInstance(
                                             &CLSID_UiaManagerCrossMachineStubFactory,
                                             0,
                                             4u,
                                             &GUID_37284c45_c0c6_4cf8_b858_c4867cdf986e,
                                             &ppv);
    v9 = "Fail to create local cross machine stub factory";
  }
  wil::details::in1diag3::FailFast_IfFailedMsg(
    v6,
    (void *)v7,
    (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactoryclassfactory.cpp",
    (const char *)ElevatedInstanceWithElevationMoniker,
    (int)v9,
    v14);
  v11 = ppv;
  v12 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 24LL);
  v18 = (__int128)*GetMachineIdInRemoteSessionFromRegistry(&v19);
  v13 = v12(v11, &v18);
  wil::details::in1diag3::FailFast_IfFailedMsg(
    retaddr,
    (void *)0x91,
    (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestubfactoryclassfactory.cpp",
    (const char *)v13,
    (int)"Failed to create local cross machine stub",
    v15);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&ppv);
  if ( v16[0] )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800727e0  mov     [rsp-8+arg_0], rbx; UiaInitCrossMachineConnection
0x1800727e5  mov     [rsp-8+arg_8], rdi
0x1800727ea  push    rbp
0x1800727eb  mov     rbp, rsp
0x1800727ee  sub     rsp, 60h
0x1800727f2  lea     rcx, [rbp+var_30]
0x1800727f6  call    ?CoInitializeEx_failfast@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx_failfast(ulong)
0x1800727fb  nop
0x1800727fc  mov     [rbp+var_28], 0
0x180072804  call    ?IsUiaManagerElevated@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsUiaManagerElevated(void)
0x180072809  test    al, al
0x18007280b  jnz     short loc_180072860
0x18007280d  mov     rcx, [rbp+var_28]
0x180072811  mov     [rbp+var_28], 0
0x180072819  test    rcx, rcx
0x18007281c  jz      short loc_18007282B
0x18007281e  mov     rax, [rcx]
0x180072821  mov     rax, [rax+10h]
0x180072825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007282a  nop
0x18007282b  mov     rbx, [rbp+8]
0x18007282f  mov     edi, 83h
0x180072834  lea     rax, [rbp+var_28]
0x180072838  mov     [rsp+60h+ppv], rax; ppv
0x18007283d  lea     r9, _GUID_37284c45_c0c6_4cf8_b858_c4867cdf986e; riid
0x180072844  xor     edx, edx; pUnkOuter
0x180072846  lea     r8d, [rdi-7Fh]; dwClsContext
0x18007284a  lea     rcx, CLSID_UiaManagerCrossMachineStubFactory; rclsid
0x180072851  call    cs:__imp_CoCreateInstance
0x180072857  lea     rcx, aFailToCreateLo; "Fail to create local cross machine stub"...
0x18007285e  jmp     short loc_180072897
0x180072860  mov     rcx, [rbp+var_28]
0x180072864  mov     [rbp+var_28], 0
0x18007286c  test    rcx, rcx
0x18007286f  jz      short loc_18007287E
0x180072871  mov     rax, [rcx]
0x180072874  mov     rax, [rax+10h]
0x180072878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007287d  nop
0x18007287e  mov     rbx, [rbp+8]
0x180072882  mov     edi, 8Fh
0x180072887  lea     r9, [rbp+var_28]; void **
0x18007288b  call    ?GetElevatedInstanceWithElevationMoniker@BasicUiaUtils@@SAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; BasicUiaUtils::GetElevatedInstanceWithElevationMoniker(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180072890  lea     rcx, aFailToCreateLo_0; "Fail to create local cross machine stub"...
0x180072897  mov     [rsp+60h+ppv], rcx; int
0x18007289c  mov     r9d, eax; char *
0x18007289f  lea     r8, aOnecoreWindows_9; "onecore\\windows\\accessibletech\\uiama"...
0x1800728a6  mov     edx, edi; void *
0x1800728a8  mov     rcx, rbx; this
0x1800728ab  call    ?FailFast_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800728b0  mov     rdi, [rbp+var_28]
0x1800728b4  mov     rax, [rdi]
0x1800728b7  mov     rbx, [rax+18h]
0x1800728bb  lea     rcx, [rbp+var_10]; retstr
0x1800728bf  call    ?GetMachineIdInRemoteSessionFromRegistry@@YA?AU_GUID@@XZ; GetMachineIdInRemoteSessionFromRegistry(void)
0x1800728c4  movups  xmm0, xmmword ptr [rax]
0x1800728c7  movdqu  [rbp+var_20], xmm0
0x1800728cc  lea     rdx, [rbp+var_20]
0x1800728d0  mov     rcx, rdi
0x1800728d3  mov     rax, rbx
0x1800728d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800728db  mov     rcx, [rbp+8]; this
0x1800728df  lea     rdx, aFailedToCreate; "Failed to create local cross machine st"...
0x1800728e6  mov     [rsp+60h+ppv], rdx; int
0x1800728eb  mov     r9d, eax; char *
0x1800728ee  lea     r8, aOnecoreWindows_9; "onecore\\windows\\accessibletech\\uiama"...
0x1800728f5  mov     edx, 91h; void *
0x1800728fa  call    ?FailFast_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800728ff  nop
0x180072900  lea     rcx, [rbp+var_28]
0x180072904  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180072909  nop
0x18007290a  cmp     [rbp+var_30], 0
0x18007290e  jz      short loc_180072916
0x180072910  call    cs:__imp_CoUninitialize
0x180072916  mov     rbx, [rsp+60h+arg_0]
0x18007291b  mov     rdi, [rsp+60h+arg_8]
0x180072920  add     rsp, 60h
0x180072924  pop     rbp
0x180072925  retn
```
