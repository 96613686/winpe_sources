# CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy(void)

- ea: `0x180059900`
- end: `0x180059ac8`
- name: `?DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy@CLocationPermissionManagerCam@@AEAA_NXZ`
- size: `456`
- prototype: `bool __fastcall(CLocationPermissionManagerCam *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800598f0`

## callees

- `0x18001be08`
- `0x18004c480`
- `0x180059900`
- `0x1800a98c0`
- `0x180116c58`
- `0x180116cd4`
- `0x18015e010`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18005999b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x1800599fc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18005999b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x1800599fc`

## string_xrefs

- `0x180059981`: `LetAppsAccessLocation_ForceAllowTheseApps`
- `0x1800599ea`: `LetAppsAccessLocation_UserInControlOfTheseApps`
- `0x18005993d`: `CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy`
- `0x1800599a9`: `CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy`
- `0x180059a0a`: `CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy`

## pseudocode

```c
bool __fastcall CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy(
        CLocationPermissionManagerCam *this)
{
  __int64 v1; // rax
  int v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  char v6; // bl
  int PolicyString; // eax
  int v8; // eax
  char *v10; // [rsp+28h] [rbp-48h]
  int v11; // [rsp+30h] [rbp-40h] BYREF
  _WORD **v12; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  char v14; // [rsp+48h] [rbp-28h]
  int v15; // [rsp+50h] [rbp-20h] BYREF
  _WORD *v16; // [rsp+58h] [rbp-18h] BYREF
  _WORD *v17; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = *(_QWORD *)this;
  v15 = 0;
  v2 = (*(__int64 (__fastcall **)(CLocationPermissionManagerCam *, int *))(v1 + 64))(this, &v15);
  if ( v2 < 0 )
  {
    LODWORD(v10) = v2;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy",
      "GetGlobalPermission(&consentGranted)",
      v10,
      v11);
  }
  v6 = 0;
  if ( !v15 )
  {
    v17 = 0;
    v12 = &v17;
    v16 = 0;
    v13 = 0;
    v14 = 1;
    PolicyString = PolicyManager_GetPolicyString(L"Privacy", L"LetAppsAccessLocation_ForceAllowTheseApps", &v13);
    if ( PolicyString < 0 )
    {
      LODWORD(v10) = PolicyString;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
        "CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy",
        "PolicyManager_GetPolicyString(c_policyPrivacyArea, c_locationForceAllowTheseApps, wil::out_param(forceAllowAppList))",
        v10,
        v11);
    }
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
    v13 = 0;
    v12 = &v16;
    v14 = 1;
    v8 = PolicyManager_GetPolicyString(L"Privacy", L"LetAppsAccessLocation_UserInControlOfTheseApps", &v13);
    if ( v8 < 0 )
    {
      LODWORD(v10) = v8;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
        "CLocationPermissionManagerCam::DoesLocationServiceHaveAccessThroughGlobalSwitchOrPolicy",
        "PolicyManager_GetPolicyString( c_policyPrivacyArea, c_locationUserInControlOfTheseApps, wil::out_param(userInControlAppList))",
        v10,
        v11);
    }
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
    if ( v17 && *v17 || v16 && *v16 )
    {
      v15 = 1;
      v6 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(unsigned short *),&long PolicyManager_FreeStringValue(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  if ( (unsigned int)dword_1801DDF30 > 5 )
  {
    LODWORD(v16) = v15;
    LOBYTE(v11) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v3,
      (unsigned int)&dword_1801B408C,
      v4,
      v5,
      (__int64)&v16,
      (__int64)&v11);
  }
  return v15 != 0;
}

```

## disassembly

```asm
0x180059900  mov     [rsp-8+arg_8], rbx
0x180059905  mov     [rsp-8+arg_10], rdi
0x18005990a  push    rbp
0x18005990b  mov     rbp, rsp
0x18005990e  sub     rsp, 70h
0x180059912  mov     rax, cs:__security_cookie
0x180059919  xor     rax, rsp
0x18005991c  mov     [rbp+var_8], rax
0x180059920  mov     rax, [rcx]
0x180059923  lea     rdx, [rbp+var_20]
0x180059927  xor     edi, edi
0x180059929  mov     [rbp+var_20], edi
0x18005992c  mov     rax, [rax+40h]
0x180059930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059935  test    eax, eax
0x180059937  jns     short loc_180059965
0x180059939  mov     rcx, [rbp+8]; this
0x18005993d  lea     r9, aClocationpermi_7; "CLocationPermissionManagerCam::DoesLoca"...
0x180059944  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180059948  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18005994f  lea     rax, aGetglobalpermi; "GetGlobalPermission(&consentGranted)"
0x180059956  mov     edx, 11Dh; void *
0x18005995b  mov     [rsp+70h+var_50], rax; char *
0x180059960  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059965  mov     bl, dil
0x180059968  cmp     [rbp+var_20], edi
0x18005996b  jnz     loc_180059A72
0x180059971  lea     rax, [rbp+var_10]
0x180059975  mov     [rbp+var_10], rdi
0x180059979  lea     r8, [rbp+var_30]
0x18005997d  mov     [rbp+var_38], rax
0x180059981  lea     rdx, aLetappsaccessl; "LetAppsAccessLocation_ForceAllowTheseAp"...
0x180059988  mov     [rbp+var_18], rdi
0x18005998c  lea     rcx, aPrivacy; "Privacy"
0x180059993  mov     [rbp+var_30], rdi
0x180059997  mov     [rbp+var_28], 1
0x18005999b  call    cs:__imp_PolicyManager_GetPolicyString
0x1800599a1  test    eax, eax
0x1800599a3  jns     short loc_1800599D1
0x1800599a5  mov     rcx, [rbp+8]; this
0x1800599a9  lea     r9, aClocationpermi_7; "CLocationPermissionManagerCam::DoesLoca"...
0x1800599b0  mov     dword ptr [rsp+70h+var_48], eax; char *
0x1800599b4  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800599bb  lea     rax, aPolicymanagerG_0; "PolicyManager_GetPolicyString(c_policyP"...
0x1800599c2  mov     edx, 127h; void *
0x1800599c7  mov     [rsp+70h+var_50], rax; char *
0x1800599cc  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800599d1  lea     rcx, [rbp+var_38]
0x1800599d5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800599da  lea     rax, [rbp+var_18]
0x1800599de  mov     [rbp+var_30], rdi
0x1800599e2  lea     r8, [rbp+var_30]
0x1800599e6  mov     [rbp+var_38], rax
0x1800599ea  lea     rdx, aLetappsaccessl_0; "LetAppsAccessLocation_UserInControlOfTh"...
0x1800599f1  mov     [rbp+var_28], 1
0x1800599f5  lea     rcx, aPrivacy; "Privacy"
0x1800599fc  call    cs:__imp_PolicyManager_GetPolicyString
0x180059a02  test    eax, eax
0x180059a04  jns     short loc_180059A32
0x180059a06  mov     rcx, [rbp+8]; this
0x180059a0a  lea     r9, aClocationpermi_7; "CLocationPermissionManagerCam::DoesLoca"...
0x180059a11  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180059a15  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x180059a1c  lea     rax, aPolicymanagerG_1; "PolicyManager_GetPolicyString( c_policy"...
0x180059a23  mov     edx, 129h; void *
0x180059a28  mov     [rsp+70h+var_50], rax; char *
0x180059a2d  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059a32  lea     rcx, [rbp+var_38]
0x180059a36  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180059a3b  mov     rax, [rbp+var_10]
0x180059a3f  test    rax, rax
0x180059a42  jz      short loc_180059A49
0x180059a44  cmp     [rax], di
0x180059a47  jnz     short loc_180059A57
0x180059a49  mov     rax, [rbp+var_18]
0x180059a4d  test    rax, rax
0x180059a50  jz      short loc_180059A60
0x180059a52  cmp     [rax], di
0x180059a55  jz      short loc_180059A60
0x180059a57  mov     [rbp+var_20], 1
0x180059a5e  mov     bl, 1
0x180059a60  lea     rcx, [rbp+var_18]
0x180059a64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180059a69  lea     rcx, [rbp+var_10]
0x180059a6d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAG@Z$1?PolicyManager_FreeStringValue@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(ushort *),&PolicyManager_FreeStringValue(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180059a72  mov     eax, cs:dword_1801DDF30
0x180059a78  cmp     eax, 5
0x180059a7b  jbe     short loc_180059AA4
0x180059a7d  mov     eax, [rbp+var_20]
0x180059a80  lea     rdx, dword_1801B408C
0x180059a87  mov     dword ptr [rbp+var_18], eax
0x180059a8a  lea     rax, [rbp+var_40]
0x180059a8e  mov     [rsp+70h+var_48], rax
0x180059a93  lea     rax, [rbp+var_18]
0x180059a97  mov     [rsp+70h+var_50], rax
0x180059a9c  mov     byte ptr [rbp+var_40], bl
0x180059a9f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180059aa4  cmp     [rbp+var_20], edi
0x180059aa7  setnz   al
0x180059aaa  mov     rcx, [rbp+var_8]
0x180059aae  xor     rcx, rsp; StackCookie
0x180059ab1  call    __security_check_cookie
0x180059ab6  lea     r11, [rsp+70h+var_s0]
0x180059abb  mov     rbx, [r11+18h]
0x180059abf  mov     rdi, [r11+20h]
0x180059ac3  mov     rsp, r11
0x180059ac6  pop     rbp
0x180059ac7  retn
```
