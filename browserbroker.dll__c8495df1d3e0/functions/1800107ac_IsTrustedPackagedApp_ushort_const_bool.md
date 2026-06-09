# IsTrustedPackagedApp(ushort const *,bool *)

- ea: `0x1800107ac`
- end: `0x180010b45`
- name: `?IsTrustedPackagedApp@@YAJPEBGPEA_N@Z`
- size: `921`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010ba0`

## callees

- `0x180003170`
- `0x180007018`
- `0x18000a4d0`
- `0x18000c164`
- `0x18000dc74`
- `0x18001078c`
- `0x1800107ac`
- `0x180010b4c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010ada`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010ada`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x1800107ef`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x1800107ef`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromId` at `0x1800109fa`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromId` at `0x180010a61`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromId` at `0x1800109fa`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromId` at `0x180010a61`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18001096e`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x1800109c9`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18001096e`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x1800109c9`

## string_xrefs

- `0x180010800`: `onecoreuap\inetcore\spartan\desktopbroker\determineverbhandlertype.cpp`
- `0x18001087d`: `onecoreuap\inetcore\spartan\desktopbroker\determineverbhandlertype.cpp`
- `0x180010997`: `onecoreuap\inetcore\spartan\desktopbroker\determineverbhandlertype.cpp`
- `0x180010a1f`: `onecoreuap\inetcore\spartan\desktopbroker\determineverbhandlertype.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IsTrustedPackagedApp(const unsigned __int16 *a1, bool *a2)
{
  HRESULT v4; // eax
  signed int v5; // ebx
  void *v6; // rbx
  __int64 (__fastcall *v7)(void *, GUID *, __int64 *); // rdi
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, GUID *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, void **); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, const wchar_t *, PCWSTR *); // rbx
  LONG v15; // eax
  PACKAGE_ID *v16; // rdi
  LONG v17; // eax
  LONG v18; // eax
  WCHAR *v19; // rsi
  LONG v20; // eax
  __int64 (**i)[2]; // rbx
  bool v23; // al
  int v24; // [rsp+20h] [rbp-50h]
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  PCWSTR packageFullName; // [rsp+38h] [rbp-38h] BYREF
  void *v27; // [rsp+40h] [rbp-30h] BYREF
  void *ppv; // [rsp+48h] [rbp-28h] BYREF
  void *v29[2]; // [rsp+50h] [rbp-20h] BYREF
  CLSID clsid; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  UINT32 bufferLength; // [rsp+A8h] [rbp+38h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+48h] BYREF

  *a2 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppv);
  clsid = CLSID_QueryAssociations;
  v4 = AssocCreate(&clsid, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x42,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\determineverbhandlertype.cpp",
      (const char *)(unsigned int)v4,
      v24);
  v5 = (*(__int64 (__fastcall **)(void *, __int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppv + 24LL))(
         ppv,
         4096,
         a1,
         0);
  if ( v5 < 0 )
    goto LABEL_30;
  v25 = 0;
  v6 = ppv;
  v7 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v25);
  v8 = v7(v6, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &v25);
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x46,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\determineverbhandlertype.cpp",
      (const char *)(unsigned int)v8,
      0);
  v34 = 0;
  v9 = v25;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v25 + 64LL);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v34);
  v5 = v10(v9, 35651598, 0, &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502);
  if ( v5 < 0 )
  {
LABEL_29:
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v25);
LABEL_30:
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppv);
    return (unsigned int)v5;
  }
  v27 = 0;
  v11 = v34;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, void **))(*(_QWORD *)v34 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  v5 = v12(v11, 458757, 0, &v27);
  if ( v5 < 0 )
  {
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    goto LABEL_29;
  }
  packageFullName = 0;
  v13 = v34;
  v14 = *(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, PCWSTR *))(*(_QWORD *)v34 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &packageFullName,
    0);
  v5 = v14(v13, 17760256, L"PackageId", &packageFullName);
  if ( v5 < 0 )
  {
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&packageFullName);
    goto LABEL_28;
  }
  bufferLength = 0;
  v15 = PackageIdFromFullName(packageFullName, 0, &bufferLength, 0);
  v5 = v15;
  if ( v15 != 122 )
  {
    if ( v15 > 0 )
      v5 = (unsigned __int16)v15 | 0x80070000;
    if ( v5 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\determineverbhandlertype.cpp",
        (const char *)(unsigned int)v5,
        (int)&v34);
    goto LABEL_27;
  }
  v16 = (PACKAGE_ID *)operator new[](bufferLength);
  v29[0] = v16;
  v17 = PackageIdFromFullName(packageFullName, 0, &bufferLength, (BYTE *)v16);
  v5 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
LABEL_26:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v29);
    goto LABEL_27;
  }
  packageFamilyNameLength = 0;
  v18 = PackageFamilyNameFromId(v16, &packageFamilyNameLength, 0);
  v5 = v18;
  if ( v18 != 122 )
  {
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
    if ( v5 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\determineverbhandlertype.cpp",
        (const char *)(unsigned int)v5,
        (int)&v34);
    goto LABEL_26;
  }
  v19 = (WCHAR *)operator new[](saturated_mul(packageFamilyNameLength, 2u));
  *(_QWORD *)&clsid.Data1 = v19;
  v20 = PackageFamilyNameFromId(v16, &packageFamilyNameLength, v19);
  v5 = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      v5 = (unsigned __int16)v20 | 0x80070000;
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&clsid);
    goto LABEL_26;
  }
  for ( i = (__int64 (**)[2])off_18002EA40; i != SettingStore::IEVALUE_HVSI_HVSIEnabled; ++i )
  {
    if ( !(unsigned int)_o__wcsicmp(v19, (__int64 *)*i) )
    {
      v23 = 1;
      goto LABEL_37;
    }
  }
  v23 = 0;
LABEL_37:
  *a2 = v23;
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&clsid);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&packageFullName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&ppv);
  return 0;
}

```

## disassembly

```asm
0x1800107ac  push    rbp
0x1800107ae  push    rbx
0x1800107af  push    rsi
0x1800107b0  push    rdi
0x1800107b1  push    r14
0x1800107b3  mov     rbp, rsp
0x1800107b6  sub     rsp, 70h
0x1800107ba  mov     r14, rdx
0x1800107bd  mov     rbx, rcx
0x1800107c0  mov     byte ptr [rdx], 0
0x1800107c3  mov     [rbp+ppv], 0
0x1800107cb  lea     rcx, [rbp+ppv]
0x1800107cf  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800107d4  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x1800107db  movdqu  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800107e0  lea     r8, [rbp+ppv]; ppv
0x1800107e4  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x1800107eb  lea     rcx, [rbp+clsid]; clsid
0x1800107ef  call    cs:__imp_AssocCreate
0x1800107f5  mov     rcx, [rbp+28h]; this
0x1800107f9  test    eax, eax
0x1800107fb  jns     short loc_180010812
0x1800107fd  mov     r9d, eax; char *
0x180010800  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180010807  mov     edx, 42h ; 'B'; void *
0x18001080c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180010812  mov     rcx, [rbp+ppv]
0x180010816  mov     rax, [rcx]
0x180010819  mov     qword ptr [rsp+70h+var_50], 0; int
0x180010822  xor     r9d, r9d
0x180010825  mov     r8, rbx
0x180010828  mov     edx, 1000h
0x18001082d  mov     rax, [rax+18h]
0x180010831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010836  mov     ebx, eax
0x180010838  test    eax, eax
0x18001083a  js      loc_180010AB4
0x180010840  mov     [rbp+var_40], 0
0x180010848  mov     rbx, [rbp+ppv]
0x18001084c  mov     rax, [rbx]
0x18001084f  mov     rdi, [rax]
0x180010852  lea     rcx, [rbp+var_40]
0x180010856  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18001085b  lea     r8, [rbp+var_40]
0x18001085f  lea     rdx, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x180010866  mov     rcx, rbx
0x180010869  mov     rax, rdi
0x18001086c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010871  nop
0x180010872  mov     rcx, [rbp+28h]; this
0x180010876  test    eax, eax
0x180010878  jns     short loc_18001088F
0x18001087a  mov     r9d, eax; char *
0x18001087d  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180010884  mov     edx, 46h ; 'F'; void *
0x180010889  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001088f  mov     [rbp+arg_18], 0
0x180010897  mov     rdi, [rbp+var_40]
0x18001089b  mov     rax, [rdi]
0x18001089e  mov     rbx, [rax+40h]
0x1800108a2  lea     rcx, [rbp+arg_18]
0x1800108a6  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800108ab  lea     rax, [rbp+arg_18]
0x1800108af  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800108b4  lea     r9, _GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502
0x1800108bb  xor     r8d, r8d
0x1800108be  mov     edx, 220000Eh
0x1800108c3  mov     rcx, rdi
0x1800108c6  mov     rax, rbx
0x1800108c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ce  mov     ebx, eax
0x1800108d0  test    eax, eax
0x1800108d2  js      loc_180010AA0
0x1800108d8  mov     [rbp+var_30], 0
0x1800108e0  mov     rdi, [rbp+arg_18]
0x1800108e4  mov     rax, [rdi]
0x1800108e7  mov     rbx, [rax+18h]
0x1800108eb  xor     edx, edx
0x1800108ed  lea     rcx, [rbp+var_30]
0x1800108f1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800108f6  lea     r9, [rbp+var_30]
0x1800108fa  xor     r8d, r8d
0x1800108fd  mov     edx, 70005h
0x180010902  mov     rcx, rdi
0x180010905  mov     rax, rbx
0x180010908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001090d  mov     ebx, eax
0x18001090f  test    eax, eax
0x180010911  js      loc_180010A96
0x180010917  mov     [rbp+packageFullName], 0
0x18001091f  mov     rdi, [rbp+arg_18]
0x180010923  mov     rax, [rdi]
0x180010926  mov     rbx, [rax+18h]
0x18001092a  xor     edx, edx
0x18001092c  lea     rcx, [rbp+packageFullName]
0x180010930  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010935  lea     r9, [rbp+packageFullName]
0x180010939  lea     r8, aPackageid; "PackageId"
0x180010940  mov     edx, 10F0000h
0x180010945  mov     rcx, rdi
0x180010948  mov     rax, rbx
0x18001094b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010950  mov     ebx, eax
0x180010952  test    eax, eax
0x180010954  js      loc_180010A8C
0x18001095a  mov     [rbp+bufferLength], 0
0x180010961  xor     r9d, r9d; buffer
0x180010964  lea     r8, [rbp+bufferLength]; bufferLength
0x180010968  xor     edx, edx; flags
0x18001096a  mov     rcx, [rbp+packageFullName]; packageFullName
0x18001096e  call    cs:__imp_PackageIdFromFullName
0x180010974  mov     ebx, eax
0x180010976  cmp     eax, 7Ah ; 'z'
0x180010979  jz      short loc_1800109AD
0x18001097b  test    eax, eax
0x18001097d  jle     short loc_180010988
0x18001097f  movzx   ebx, ax
0x180010982  or      ebx, 80070000h
0x180010988  test    ebx, ebx
0x18001098a  jns     loc_180010A8C
0x180010990  mov     rcx, [rbp+28h]; this
0x180010994  mov     r9d, ebx; char *
0x180010997  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001099e  mov     edx, 55h ; 'U'; void *
0x1800109a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109a8  jmp     loc_180010A8C
0x1800109ad  mov     ecx, [rbp+bufferLength]; unsigned __int64
0x1800109b0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800109b5  mov     rdi, rax
0x1800109b8  mov     [rbp+var_20], rax
0x1800109bc  mov     r9, rax; buffer
0x1800109bf  lea     r8, [rbp+bufferLength]; bufferLength
0x1800109c3  xor     edx, edx; flags
0x1800109c5  mov     rcx, [rbp+packageFullName]; packageFullName
0x1800109c9  call    cs:__imp_PackageIdFromFullName
0x1800109cf  mov     ebx, eax
0x1800109d1  test    eax, eax
0x1800109d3  jz      short loc_1800109E9
0x1800109d5  jle     loc_180010A82
0x1800109db  movzx   ebx, ax
0x1800109de  or      ebx, 80070000h
0x1800109e4  jmp     loc_180010A82
0x1800109e9  mov     [rbp+packageFamilyNameLength], 0
0x1800109f0  xor     r8d, r8d; packageFamilyName
0x1800109f3  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x1800109f7  mov     rcx, rdi; packageId
0x1800109fa  call    cs:__imp_PackageFamilyNameFromId
0x180010a00  mov     ebx, eax
0x180010a02  cmp     eax, 7Ah ; 'z'
0x180010a05  jz      short loc_180010A32
0x180010a07  test    eax, eax
0x180010a09  jle     short loc_180010A14
0x180010a0b  movzx   ebx, ax
0x180010a0e  or      ebx, 80070000h
0x180010a14  test    ebx, ebx
0x180010a16  jns     short loc_180010A82
0x180010a18  mov     rcx, [rbp+28h]; this
0x180010a1c  mov     r9d, ebx; char *
0x180010a1f  lea     r8, aOnecoreuapInet_8; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180010a26  mov     edx, 5Eh ; '^'; void *
0x180010a2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a30  jmp     short loc_180010A82
0x180010a32  mov     ecx, [rbp+packageFamilyNameLength]
0x180010a35  mov     eax, 2
0x180010a3a  mul     rcx
0x180010a3d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010a44  cmovb   rax, rcx
0x180010a48  mov     rcx, rax; unsigned __int64
0x180010a4b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010a50  mov     rsi, rax
0x180010a53  mov     qword ptr [rbp+clsid.Data1], rax
0x180010a57  mov     r8, rax; packageFamilyName
0x180010a5a  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x180010a5e  mov     rcx, rdi; packageId
0x180010a61  call    cs:__imp_PackageFamilyNameFromId
0x180010a67  mov     ebx, eax
0x180010a69  test    eax, eax
0x180010a6b  jz      short loc_180010AC1
0x180010a6d  jle     short loc_180010A78
0x180010a6f  movzx   ebx, ax
0x180010a72  or      ebx, 80070000h
0x180010a78  lea     rcx, [rbp+clsid]
0x180010a7c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180010a81  nop
0x180010a82  lea     rcx, [rbp+var_20]
0x180010a86  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180010a8b  nop
0x180010a8c  lea     rcx, [rbp+packageFullName]
0x180010a90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010a95  nop
0x180010a96  lea     rcx, [rbp+var_30]
0x180010a9a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010a9f  nop
0x180010aa0  lea     rcx, [rbp+arg_18]
0x180010aa4  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010aa9  nop
0x180010aaa  lea     rcx, [rbp+var_40]
0x180010aae  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010ab3  nop
0x180010ab4  lea     rcx, [rbp+ppv]
0x180010ab8  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010abd  mov     eax, ebx
0x180010abf  jmp     short loc_180010B3A
0x180010ac1  lea     rbx, off_18002EA40; "Microsoft.MicrosoftOfficeHub_8wekyb3d8b"...
0x180010ac8  lea     rax, ?IEVALUE_HVSI_HVSIEnabled@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_HVSI_HVSIEnabled
0x180010acf  cmp     rbx, rax
0x180010ad2  jz      short loc_180010AEE
0x180010ad4  mov     rdx, [rbx]
0x180010ad7  mov     rcx, rsi
0x180010ada  call    cs:__imp__o__wcsicmp
0x180010ae0  test    eax, eax
0x180010ae2  jz      short loc_180010AEA
0x180010ae4  add     rbx, 8
0x180010ae8  jmp     short loc_180010AC8
0x180010aea  mov     al, 1
0x180010aec  jmp     short loc_180010AF0
0x180010aee  xor     al, al
0x180010af0  mov     [r14], al
0x180010af3  lea     rcx, [rbp+clsid]
0x180010af7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180010afc  nop
0x180010afd  lea     rcx, [rbp+var_20]
0x180010b01  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180010b06  nop
0x180010b07  lea     rcx, [rbp+packageFullName]
0x180010b0b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010b10  nop
0x180010b11  lea     rcx, [rbp+var_30]
0x180010b15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010b1a  nop
0x180010b1b  lea     rcx, [rbp+arg_18]
0x180010b1f  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010b24  nop
0x180010b25  lea     rcx, [rbp+var_40]
0x180010b29  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010b2e  nop
0x180010b2f  lea     rcx, [rbp+ppv]
0x180010b33  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180010b38  xor     eax, eax
0x180010b3a  add     rsp, 70h
0x180010b3e  pop     r14
0x180010b40  pop     rdi
0x180010b41  pop     rsi
0x180010b42  pop     rbx
0x180010b43  pop     rbp
0x180010b44  retn
```
