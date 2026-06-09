# DdcUserInfoHelper::GetDefaultBrowser(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180027cbc`
- end: `0x180027dbf`
- name: `?GetDefaultBrowser@DdcUserInfoHelper@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027dc8`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18000869c`
- `0x180008d04`
- `0x180027cbc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027cfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027cfc`

## string_xrefs

- `0x180027d96`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcuserinfohelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcUserInfoHelper::GetDefaultBrowser(void **a1)
{
  int v2; // edx
  int v3; // ecx
  HRESULT v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, void **); // rbp
  void *v7; // rbx
  int v8; // edx
  int v9; // ecx
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF
  char v12; // [rsp+60h] [rbp+18h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v4 = CoCreateInstance(
         &CLSID_ApplicationAssociationRegistration,
         0,
         1u,
         &GUID_a357134e_8c1e_4edd_8474_40a80546f54f,
         &ppv);
  if ( v4 >= 0 )
  {
    v5 = ppv;
    v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, void **))(*(_QWORD *)ppv + 72LL);
    v7 = *a1;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      CoTaskMemFree(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *a1 = 0;
    v4 = v6(v5, 0, a1);
    if ( v4 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        v4,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
        68,
        "CHR(hr)");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcuserinfohelper.cpp",
      65,
      "CHR(hr)");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027cbc  mov     [rsp+arg_0], rbx
0x180027cc1  push    rbp
0x180027cc2  push    rsi
0x180027cc3  push    rdi
0x180027cc4  sub     rsp, 30h
0x180027cc8  mov     rsi, rcx
0x180027ccb  mov     [rsp+48h+arg_8], 0
0x180027cd4  lea     rcx, [rsp+48h+arg_8]
0x180027cd9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027cde  lea     rax, [rsp+48h+arg_8]
0x180027ce3  mov     [rsp+48h+ppv], rax; ppv
0x180027ce8  lea     r9, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x180027cef  xor     edx, edx; pUnkOuter
0x180027cf1  lea     r8d, [rdx+1]; dwClsContext
0x180027cf5  lea     rcx, CLSID_ApplicationAssociationRegistration; rclsid
0x180027cfc  call    cs:__imp_CoCreateInstance
0x180027d02  mov     ebx, eax
0x180027d04  test    eax, eax
0x180027d06  jns     short loc_180027D2B
0x180027d08  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027d0f  jz      loc_180027DA6
0x180027d15  lea     rax, aChrHr; "CHR(hr)"
0x180027d1c  mov     [rsp+48h+var_20], rax
0x180027d21  mov     dword ptr [rsp+48h+ppv], 41h ; 'A'
0x180027d29  jmp     short loc_180027D96
0x180027d2b  mov     rdi, [rsp+48h+arg_8]
0x180027d30  mov     rax, [rdi]
0x180027d33  mov     rbp, [rax+48h]
0x180027d37  mov     rbx, [rsi]
0x180027d3a  test    rbx, rbx
0x180027d3d  jz      short loc_180027D5C
0x180027d3f  lea     rcx, [rsp+48h+arg_10]; this
0x180027d44  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180027d49  mov     rcx, rbx; pv
0x180027d4c  call    cs:__imp_CoTaskMemFree
0x180027d52  lea     rcx, [rsp+48h+arg_10]; this
0x180027d57  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180027d5c  mov     qword ptr [rsi], 0
0x180027d63  mov     r8, rsi
0x180027d66  xor     edx, edx
0x180027d68  mov     rcx, rdi
0x180027d6b  mov     rax, rbp
0x180027d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d73  mov     ebx, eax
0x180027d75  test    eax, eax
0x180027d77  jns     short loc_180027DA6
0x180027d79  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180027d80  jz      short loc_180027DA6
0x180027d82  lea     rax, aChrHr; "CHR(hr)"
0x180027d89  mov     [rsp+48h+var_20], rax
0x180027d8e  mov     dword ptr [rsp+48h+ppv], 44h ; 'D'
0x180027d96  lea     r9, aOnecoreuapShel_16; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180027d9d  mov     r8d, ebx
0x180027da0  call    McTemplateU0dsqs_EventWriteTransfer
0x180027da5  nop
0x180027da6  lea     rcx, [rsp+48h+arg_8]
0x180027dab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027db0  mov     eax, ebx
0x180027db2  mov     rbx, [rsp+48h+arg_0]
0x180027db7  add     rsp, 30h
0x180027dbb  pop     rdi
0x180027dbc  pop     rsi
0x180027dbd  pop     rbp
0x180027dbe  retn
```
