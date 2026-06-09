# CapabilityAccessManagerDoStoreMaintenance(void)

- ea: `0x1800237d0`
- end: `0x1800238e1`
- name: `?CapabilityAccessManagerDoStoreMaintenance@@YAJXZ`
- size: `273`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094c0`
- `0x18001ab9c`
- `0x18001f5f4`
- `0x1800237d0`
- `0x1800238e8`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023828`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023828`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002388a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800238bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002388a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800238bf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002384c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002384c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002380f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002380f`

## string_xrefs

- `0x180023808`: `Windows.Internal.CapabilityAccess.UsageHistory.AppCapabilityUsageHistory`
- `0x180023860`: `onecore\base\devices\cam\svc\maintenancetasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CapabilityAccessManagerDoStoreMaintenance(void)
{
  HSTRING v0; // rbx
  int ActivationFactory; // eax
  unsigned int v2; // ebx
  char v3; // cl
  unsigned int v5; // ebx
  char v6; // cl
  int v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  wil::CoInitializeEx(&v7);
  v8 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.UsageHistory.AppCapabilityUsageHistory",
         0x48u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v0 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v0, &GUID_aa586bf0_def5_4462_ad34_a90c602d2aac, &v8);
  v2 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 80LL))(v8);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    v6 = v7;
    LOBYTE(v7) = 0;
    if ( v6 )
      CoUninitialize();
    return v5;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\devices\\cam\\svc\\maintenancetasks.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v7);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    v3 = v7;
    LOBYTE(v7) = 0;
    if ( v3 )
      CoUninitialize();
    return v2;
  }
}

```

## disassembly

```asm
0x1800237d0  push    rbx
0x1800237d2  sub     rsp, 60h
0x1800237d6  mov     rax, cs:__security_cookie
0x1800237dd  xor     rax, rsp
0x1800237e0  mov     [rsp+68h+var_18], rax
0x1800237e5  lea     rcx, [rsp+68h+var_48]
0x1800237ea  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800237ef  nop
0x1800237f0  mov     [rsp+68h+var_40], 0
0x1800237f9  lea     r9, [rsp+68h+string]; string
0x1800237fe  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180023803  mov     edx, 48h ; 'H'; length
0x180023808  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_UsageHistory_AppCapabilityUsageHistory@@3QBGB; "Windows.Internal.CapabilityAccess.Usage"...
0x18002380f  call    cs:__imp_WindowsCreateStringReference
0x180023815  test    eax, eax
0x180023817  jns     short loc_18002382E
0x180023819  xor     r9d, r9d; lpArguments
0x18002381c  xor     r8d, r8d; nNumberOfArguments
0x18002381f  lea     edx, [r9+1]; dwExceptionFlags
0x180023823  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023828  call    cs:__imp_RaiseException
0x18002382e  mov     rbx, [rsp+68h+string]
0x180023833  lea     rcx, [rsp+68h+var_40]
0x180023838  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002383d  lea     r8, [rsp+68h+var_40]
0x180023842  lea     rdx, _GUID_aa586bf0_def5_4462_ad34_a90c602d2aac
0x180023849  mov     rcx, rbx
0x18002384c  call    cs:__imp_RoGetActivationFactory
0x180023852  mov     ebx, eax
0x180023854  test    eax, eax
0x180023856  jns     short loc_180023894
0x180023858  mov     rcx, [rsp+68h]; this
0x18002385d  mov     r9d, eax; char *
0x180023860  lea     r8, aOnecoreBaseDev_24; "onecore\\base\\devices\\cam\\svc\\maint"...
0x180023867  mov     edx, 11h; void *
0x18002386c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023871  nop
0x180023872  lea     rcx, [rsp+68h+var_40]
0x180023877  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002387c  nop
0x18002387d  mov     cl, byte ptr [rsp+68h+var_48]
0x180023881  mov     byte ptr [rsp+68h+var_48], 0
0x180023886  test    cl, cl
0x180023888  jz      short loc_180023890
0x18002388a  call    cs:__imp_CoUninitialize
0x180023890  mov     eax, ebx
0x180023892  jmp     short loc_1800238CD
0x180023894  mov     rcx, [rsp+68h+var_40]
0x180023899  mov     rax, [rcx]
0x18002389c  mov     rax, [rax+50h]
0x1800238a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238a5  mov     ebx, eax
0x1800238a7  lea     rcx, [rsp+68h+var_40]
0x1800238ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800238b1  nop
0x1800238b2  mov     cl, byte ptr [rsp+68h+var_48]
0x1800238b6  mov     byte ptr [rsp+68h+var_48], 0
0x1800238bb  test    cl, cl
0x1800238bd  jz      short loc_1800238C5
0x1800238bf  call    cs:__imp_CoUninitialize
0x1800238c5  mov     eax, ebx
0x1800238c7  jmp     short loc_1800238CD
0x1800238c9  mov     eax, dword ptr [rsp+68h+var_40]
0x1800238cd  mov     rcx, [rsp+68h+var_18]
0x1800238d2  xor     rcx, rsp; StackCookie
0x1800238d5  call    __security_check_cookie
0x1800238da  add     rsp, 60h
0x1800238de  pop     rbx
0x1800238df  retn
```
