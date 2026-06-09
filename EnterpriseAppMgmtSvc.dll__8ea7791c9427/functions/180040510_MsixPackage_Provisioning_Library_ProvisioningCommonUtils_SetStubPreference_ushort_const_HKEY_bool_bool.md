# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::SetStubPreference(ushort const *,HKEY__ *,bool,bool)

- ea: `0x180040510`
- end: `0x18004079d`
- name: `?SetStubPreference@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAUHKEY__@@_N2@Z`
- size: `653`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180056d60`

## callees

- `0x18000cfe8`
- `0x180040510`
- `0x1800407a4`
- `0x180065a64`
- `0x180065dd4`
- `0x180065ea8`
- `0x18006606c`
- `0x180066224`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180040574`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405b4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405d4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180040785`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180040574`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405b4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800405d4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180040785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004063a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800406a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004074c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040761`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004063a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800406a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040709`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004074c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040761`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040776`

## string_xrefs

- `0x18004055e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18004059f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18004061a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180040684`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800406ea`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MsixPackage::Provisioning::Library::ProvisioningCommonUtils::SetStubPreference(
        const struct Common::StateSeparationRedirectionMapping *a1,
        HKEY hKey,
        char a3,
        unsigned __int8 a4)
{
  unsigned int v4; // r14d
  int PersistedRegKeyPath; // eax
  unsigned int v8; // ebx
  unsigned __int16 *v10; // rbx
  int v11; // eax
  LSTATUS v12; // edi
  WCHAR *v13; // rcx
  WCHAR *v14; // rbx
  int v15; // eax
  __int64 v16; // r9
  HKEY v17; // rcx
  bool v18; // cc
  LSTATUS v19; // eax
  __int64 v20; // r9
  HKEY v21; // rcx
  bool v22; // cc
  __int64 v23; // rdx
  struct _SECURITY_ATTRIBUTES *v24; // [rsp+20h] [rbp-39h]
  struct _SECURITY_ATTRIBUTES *v25; // [rsp+20h] [rbp-39h]
  int v26; // [rsp+20h] [rbp-39h]
  HKEY hKeya; // [rsp+40h] [rbp-19h] BYREF
  HKEY v28; // [rsp+48h] [rbp-11h] BYREF
  HKEY v29; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp+7h] BYREF
  int v32; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = a4;
  *(_OWORD *)lpSubKey = 0;
  v32 = 0;
  if ( a3 )
  {
    v30 = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, &v30);
    v8 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        (int)v24);
      operator delete[](v30);
      return v8;
    }
    v10 = v30;
    v11 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(
            v30,
            (struct Common::StringBuffer *)lpSubKey);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)v11,
        (int)v24);
      operator delete[](v10);
      v13 = (WCHAR *)lpSubKey[1];
      if ( !lpSubKey[1] )
        return (unsigned int)v12;
LABEL_6:
      operator delete[](v13);
      return (unsigned int)v12;
    }
    operator delete[](v10);
  }
  else
  {
    Common::StringBuffer::SetValueFromString(
      (Common::StringBuffer *)lpSubKey,
      L"Microsoft\\Windows\\CurrentVersion\\AppModel");
  }
  hKeya = 0;
  v14 = (WCHAR *)lpSubKey[1];
  v15 = Common::RegistryKey::Open(&hKeya, hKey, lpSubKey[1], 0x20019u);
  v12 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v15,
      (int)v24);
    v17 = hKeya;
    v18 = (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_12:
    if ( v18 )
      RegCloseKey(v17);
    if ( !v14 )
      return (unsigned int)v12;
    v13 = v14;
    goto LABEL_6;
  }
  v28 = 0;
  v19 = Common::RegistryKey::CreateSubKey(&hKeya, L"StubPreference", 0x2001Fu, v16, v24, &v28);
  v12 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v19,
      (int)v25);
    v21 = v28;
    v22 = (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_18:
    if ( v22 )
      RegCloseKey(v21);
    v17 = hKeya;
    v18 = (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_12;
  }
  v29 = 0;
  v12 = Common::RegistryKey::CreateSubKey(&v28, (const unsigned __int16 *)a1, 0x2001Fu, v20, v25, &v29);
  if ( v12 < 0 )
  {
    v23 = 281;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v12,
      v26);
    if ( (unsigned __int64)v29 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(v29);
    v21 = v28;
    v22 = (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_18;
  }
  v12 = Common::RegistryKey::SetUInt32Value((Common::RegistryKey *)&v29, L"PreferStub", v4);
  if ( v12 < 0 )
  {
    v23 = 282;
    goto LABEL_23;
  }
  if ( (unsigned __int64)v29 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v29);
  if ( (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v28);
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKeya);
  if ( v14 )
    operator delete[](v14);
  return 0;
}

```

## disassembly

```asm
0x180040510  push    rbp
0x180040512  push    rbx
0x180040513  push    rsi
0x180040514  push    rdi
0x180040515  push    r14
0x180040517  push    r15
0x180040519  lea     rbp, [rsp-2Fh]
0x18004051e  sub     rsp, 88h
0x180040525  movzx   r14d, r9b
0x180040529  mov     rsi, rdx
0x18004052c  mov     r15, rcx
0x18004052f  xor     eax, eax
0x180040531  xorps   xmm0, xmm0
0x180040534  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180040538  mov     [rbp+57h+var_40], eax
0x18004053b  test    r8b, r8b
0x18004053e  jz      loc_1800405DC
0x180040544  mov     [rbp+57h+var_58], rax
0x180040548  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x18004054c  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x180040551  mov     ebx, eax
0x180040553  test    eax, eax
0x180040555  jns     short loc_180040582
0x180040557  mov     rcx, [rbp+5Fh]; this
0x18004055b  mov     r9d, eax; char *
0x18004055e  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180040565  mov     edx, 10Ch; void *
0x18004056a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004056f  nop
0x180040570  mov     rcx, [rbp+57h+var_58]
0x180040574  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004057a  nop
0x18004057b  mov     eax, ebx
0x18004057d  jmp     loc_18004078D
0x180040582  lea     rdx, [rbp+57h+lpSubKey]; struct Common::StringBuffer *
0x180040586  mov     rbx, [rbp+57h+var_58]
0x18004058a  mov     rcx, rbx; unsigned __int16 *
0x18004058d  call    ?StripSubkeyPrefixIfNecessary@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAVStringBuffer@Common@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(ushort const *,Common::StringBuffer *)
0x180040592  mov     edi, eax
0x180040594  test    eax, eax
0x180040596  jns     short loc_1800405D1
0x180040598  mov     rcx, [rbp+5Fh]; this
0x18004059c  mov     r9d, eax; char *
0x18004059f  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800405a6  mov     edx, 10Dh; void *
0x1800405ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800405b0  nop
0x1800405b1  mov     rcx, rbx
0x1800405b4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800405ba  nop
0x1800405bb  mov     rcx, [rbp+57h+lpSubKey+8]
0x1800405bf  test    rcx, rcx
0x1800405c2  jz      short loc_1800405CA
0x1800405c4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800405ca  mov     eax, edi
0x1800405cc  jmp     loc_18004078D
0x1800405d1  mov     rcx, rbx
0x1800405d4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800405da  jmp     short loc_1800405EC
0x1800405dc  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\App"...
0x1800405e3  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800405e7  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800405ec  mov     [rbp+57h+hKey], 0
0x1800405f4  mov     rbx, [rbp+57h+lpSubKey+8]
0x1800405f8  mov     r9d, 20019h; samDesired
0x1800405fe  mov     r8, rbx; lpSubKey
0x180040601  mov     rdx, rsi; hKey
0x180040604  lea     rcx, [rbp+57h+hKey]; phkResult
0x180040608  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18004060d  mov     edi, eax
0x18004060f  test    eax, eax
0x180040611  jns     short loc_18004064E
0x180040613  mov     rcx, [rbp+5Fh]; this
0x180040617  mov     r9d, eax; char *
0x18004061a  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180040621  mov     edx, 115h; void *
0x180040626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004062b  nop
0x18004062c  mov     rcx, [rbp+57h+hKey]; hKey
0x180040630  lea     rdx, [rcx-1]
0x180040634  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180040638  ja      short loc_180040641
0x18004063a  call    cs:__imp_RegCloseKey
0x180040640  nop
0x180040641  test    rbx, rbx
0x180040644  jz      short loc_1800405CA
0x180040646  mov     rcx, rbx
0x180040649  jmp     loc_1800405C4
0x18004064e  mov     [rbp+57h+var_68], 0
0x180040656  lea     rax, [rbp+57h+var_68]
0x18004065a  mov     [rsp+0B0h+var_88], rax; struct Common::AutoHandleHKEY *
0x18004065f  mov     esi, 2001Fh
0x180040664  mov     r8d, esi; unsigned int
0x180040667  lea     rdx, aStubpreference; "StubPreference"
0x18004066e  lea     rcx, [rbp+57h+hKey]; this
0x180040672  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x180040677  mov     edi, eax
0x180040679  test    eax, eax
0x18004067b  jns     short loc_1800406BC
0x18004067d  mov     rcx, [rbp+5Fh]; this
0x180040681  mov     r9d, eax; char *
0x180040684  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004068b  mov     edx, 117h; void *
0x180040690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040695  nop
0x180040696  mov     rcx, [rbp+57h+var_68]; hKey
0x18004069a  lea     rdx, [rcx-1]
0x18004069e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800406a2  ja      short loc_1800406AB
0x1800406a4  call    cs:__imp_RegCloseKey
0x1800406aa  nop
0x1800406ab  mov     rcx, [rbp+57h+hKey]
0x1800406af  lea     rax, [rcx-1]
0x1800406b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800406b7  jmp     loc_180040638
0x1800406bc  mov     [rbp+57h+var_60], 0
0x1800406c4  lea     rax, [rbp+57h+var_60]
0x1800406c8  mov     [rsp+0B0h+var_88], rax; struct Common::AutoHandleHKEY *
0x1800406cd  mov     r8d, esi; unsigned int
0x1800406d0  mov     rdx, r15; unsigned __int16 *
0x1800406d3  lea     rcx, [rbp+57h+var_68]; this
0x1800406d7  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x1800406dc  mov     edi, eax
0x1800406de  test    eax, eax
0x1800406e0  jns     short loc_18004071E
0x1800406e2  mov     edx, 119h; void *
0x1800406e7  mov     r9d, edi; char *
0x1800406ea  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800406f1  mov     rcx, [rbp+5Fh]; this
0x1800406f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800406fa  nop
0x1800406fb  mov     rcx, [rbp+57h+var_60]; hKey
0x1800406ff  lea     rdx, [rcx-1]
0x180040703  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180040707  ja      short loc_180040710
0x180040709  call    cs:__imp_RegCloseKey
0x18004070f  nop
0x180040710  mov     rcx, [rbp+57h+var_68]
0x180040714  lea     rax, [rcx-1]
0x180040718  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004071c  jmp     short loc_1800406A2
0x18004071e  mov     r8d, r14d; unsigned int
0x180040721  lea     rdx, aPreferstub; "PreferStub"
0x180040728  lea     rcx, [rbp+57h+var_60]; this
0x18004072c  call    ?SetUInt32Value@RegistryKey@Common@@QEAAJPEBGI@Z; Common::RegistryKey::SetUInt32Value(ushort const *,uint)
0x180040731  mov     edi, eax
0x180040733  test    eax, eax
0x180040735  jns     short loc_18004073E
0x180040737  mov     edx, 11Ah
0x18004073c  jmp     short loc_1800406E7
0x18004073e  mov     rcx, [rbp+57h+var_60]; hKey
0x180040742  lea     rax, [rcx-1]
0x180040746  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004074a  ja      short loc_180040753
0x18004074c  call    cs:__imp_RegCloseKey
0x180040752  nop
0x180040753  mov     rcx, [rbp+57h+var_68]; hKey
0x180040757  lea     rax, [rcx-1]
0x18004075b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004075f  ja      short loc_180040768
0x180040761  call    cs:__imp_RegCloseKey
0x180040767  nop
0x180040768  mov     rcx, [rbp+57h+hKey]; hKey
0x18004076c  lea     rax, [rcx-1]
0x180040770  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040774  ja      short loc_18004077D
0x180040776  call    cs:__imp_RegCloseKey
0x18004077c  nop
0x18004077d  test    rbx, rbx
0x180040780  jz      short loc_18004078B
0x180040782  mov     rcx, rbx
0x180040785  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004078b  xor     eax, eax
0x18004078d  add     rsp, 88h
0x180040794  pop     r15
0x180040796  pop     r14
0x180040798  pop     rdi
0x180040799  pop     rsi
0x18004079a  pop     rbx
0x18004079b  pop     rbp
0x18004079c  retn
```
