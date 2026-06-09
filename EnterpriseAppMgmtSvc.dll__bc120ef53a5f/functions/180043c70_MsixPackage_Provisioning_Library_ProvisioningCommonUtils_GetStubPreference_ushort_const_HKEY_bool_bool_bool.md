# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetStubPreference(ushort const *,HKEY__ *,bool,bool *,bool *)

- ea: `0x180043c70`
- end: `0x180043fae`
- name: `?GetStubPreference@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAUHKEY__@@_NPEA_N3@Z`
- size: `830`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, HKEY hKey@<rdx>, bool@<r8b>, bool *@<r9>, bool *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003856c`
- `0x1800562d4`
- `0x18005b444`

## callees

- `0x18000d3dc`
- `0x180043c70`
- `0x1800443b0`
- `0x18006b444`
- `0x18006b848`
- `0x18006b894`
- `0x18006b968`
- `0x18006bc58`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180043ce3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d29`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d3f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043f5d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043ce3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d29`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d3f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043d55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180043f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043e96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043e96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043f48`

## string_xrefs

- `0x180043ccd`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043d14`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043da1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043e08`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043e76`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180043f8a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetStubPreference(
        const struct Common::StateSeparationRedirectionMapping *a1,
        HKEY hKey,
        char a3,
        bool *a4,
        bool *a5)
{
  bool *v8; // r14
  int PersistedRegKeyPath; // eax
  unsigned int v10; // ebx
  HKEY v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  WCHAR *v15; // rcx
  WCHAR *v16; // rbx
  int v17; // eax
  unsigned int v18; // r8d
  HKEY v19; // rcx
  bool v20; // cc
  int v21; // eax
  unsigned int v22; // r8d
  HKEY v23; // rcx
  bool v24; // cc
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  HKEY v27; // rcx
  bool v28; // cc
  int UInt32Value; // eax
  HKEY v30; // [rsp+20h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+28h] [rbp-18h] BYREF
  int v32; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v34; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  v8 = a5;
  *a5 = 0;
  *(_OWORD *)lpSubKey = 0;
  v32 = 0;
  if ( a3 )
  {
    v30 = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, (unsigned __int16 **)&v30);
    v10 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        (int)v30);
      operator delete[](v30);
      return v10;
    }
    v12 = v30;
    v13 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(
            (const unsigned __int16 *)v30,
            (struct Common::StringBuffer *)lpSubKey);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)v13,
        (int)v30);
      operator delete[](v12);
      v15 = (WCHAR *)lpSubKey[1];
      if ( !lpSubKey[1] )
        return v14;
LABEL_6:
      operator delete[](v15);
      return v14;
    }
    operator delete[](v12);
  }
  else
  {
    Common::StringBuffer::SetValueFromString(
      (Common::StringBuffer *)lpSubKey,
      L"Microsoft\\Windows\\CurrentVersion\\AppModel");
  }
  hKeya = 0;
  v16 = (WCHAR *)lpSubKey[1];
  v17 = Common::RegistryKey::Open(&hKeya, hKey, lpSubKey[1], 0x20019u);
  v14 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v17,
      (int)v30);
    v19 = hKeya;
    v20 = (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_12:
    if ( v20 )
      RegCloseKey(v19);
    if ( !v16 )
      return v14;
    v15 = v16;
    goto LABEL_6;
  }
  a5 = 0;
  v21 = Common::RegistryKey::OpenSubKeyIfExists(
          (Common::RegistryKey *)&hKeya,
          L"StubPreference",
          v18,
          (struct Common::AutoHandleHKEY *)&a5);
  v14 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v21,
      (int)v30);
    v23 = (HKEY)a5;
    v24 = (unsigned __int64)(a5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_18:
    if ( v24 )
      RegCloseKey(v23);
    v19 = hKeya;
    v20 = (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_12;
  }
  if ( a5 )
  {
    v30 = 0;
    v25 = Common::RegistryKey::OpenSubKeyIfExists(
            (Common::RegistryKey *)&a5,
            (const unsigned __int16 *)a1,
            v22,
            (struct Common::AutoHandleHKEY *)&v30);
    v14 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)v25,
        (int)v30);
      v27 = v30;
      v28 = (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_24:
      if ( v28 )
        RegCloseKey(v27);
      v23 = (HKEY)a5;
      v24 = (unsigned __int64)(a5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_18;
    }
    if ( v30 )
    {
      v34 = 0;
      UInt32Value = Common::RegistryKey::GetUInt32Value((Common::RegistryKey *)&v30, v26, &v34);
      v14 = UInt32Value;
      if ( UInt32Value <= -2147024895 || (unsigned int)(UInt32Value + 2147024892) <= 0x7FF8FFFB )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
          (const char *)(unsigned int)UInt32Value,
          (int)v30);
        v27 = v30;
        v28 = (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_24;
      }
      if ( UInt32Value >= 0 )
      {
        *v8 = v34 != 0;
        *a4 = 1;
      }
    }
    if ( (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(v30);
  }
  if ( (unsigned __int64)(a5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey((HKEY)a5);
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKeya);
  if ( v16 )
    operator delete[](v16);
  return 0;
}

```

## disassembly

```asm
0x180043c70  mov     [rsp-28h+arg_0], rbx
0x180043c75  mov     [rsp-28h+arg_8], rsi
0x180043c7a  push    rbp
0x180043c7b  push    rdi
0x180043c7c  push    r12
0x180043c7e  push    r14
0x180043c80  push    r15
0x180043c82  mov     rbp, rsp
0x180043c85  sub     rsp, 40h
0x180043c89  mov     rsi, r9
0x180043c8c  mov     r15, rdx
0x180043c8f  mov     r12, rcx
0x180043c92  mov     byte ptr [r9], 0
0x180043c96  mov     r14, [rbp+arg_20]
0x180043c9a  mov     byte ptr [r14], 0
0x180043c9e  xor     eax, eax
0x180043ca0  xorps   xmm0, xmm0
0x180043ca3  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180043ca7  mov     [rbp+var_8], eax
0x180043caa  test    r8b, r8b
0x180043cad  jz      loc_180043D63
0x180043cb3  mov     [rbp+var_20], rax
0x180043cb7  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180043cbb  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x180043cc0  mov     ebx, eax
0x180043cc2  test    eax, eax
0x180043cc4  jns     short loc_180043CF7
0x180043cc6  mov     rcx, [rbp+28h]; this
0x180043cca  mov     r9d, eax; char *
0x180043ccd  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043cd4  mov     edx, 12Dh; void *
0x180043cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043cde  nop
0x180043cdf  mov     rcx, [rbp+var_20]
0x180043ce3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180043cea  nop     dword ptr [rax+rax+00h]
0x180043cef  nop
0x180043cf0  mov     eax, ebx
0x180043cf2  jmp     loc_180043F6B
0x180043cf7  lea     rdx, [rbp+lpSubKey]; struct Common::StringBuffer *
0x180043cfb  mov     rbx, [rbp+var_20]
0x180043cff  mov     rcx, rbx; unsigned __int16 *
0x180043d02  call    ?StripSubkeyPrefixIfNecessary@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAVStringBuffer@Common@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(ushort const *,Common::StringBuffer *)
0x180043d07  mov     edi, eax
0x180043d09  test    eax, eax
0x180043d0b  jns     short loc_180043D52
0x180043d0d  mov     rcx, [rbp+28h]; this
0x180043d11  mov     r9d, eax; char *
0x180043d14  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043d1b  mov     edx, 12Eh; void *
0x180043d20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043d25  nop
0x180043d26  mov     rcx, rbx
0x180043d29  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180043d30  nop     dword ptr [rax+rax+00h]
0x180043d35  nop
0x180043d36  mov     rcx, [rbp+lpSubKey+8]
0x180043d3a  test    rcx, rcx
0x180043d3d  jz      short loc_180043D4B
0x180043d3f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180043d46  nop     dword ptr [rax+rax+00h]
0x180043d4b  mov     eax, edi
0x180043d4d  jmp     loc_180043F6B
0x180043d52  mov     rcx, rbx
0x180043d55  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180043d5c  nop     dword ptr [rax+rax+00h]
0x180043d61  jmp     short loc_180043D73
0x180043d63  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\App"...
0x180043d6a  lea     rcx, [rbp+lpSubKey]; this
0x180043d6e  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180043d73  mov     [rbp+hKey], 0
0x180043d7b  mov     rbx, [rbp+lpSubKey+8]
0x180043d7f  mov     r9d, 20019h; samDesired
0x180043d85  mov     r8, rbx; lpSubKey
0x180043d88  mov     rdx, r15; hKey
0x180043d8b  lea     rcx, [rbp+hKey]; phkResult
0x180043d8f  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180043d94  mov     edi, eax
0x180043d96  test    eax, eax
0x180043d98  jns     short loc_180043DDF
0x180043d9a  mov     rcx, [rbp+28h]; this
0x180043d9e  mov     r9d, eax; char *
0x180043da1  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043da8  mov     edx, 136h; void *
0x180043dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043db2  nop
0x180043db3  mov     rcx, [rbp+hKey]; hKey
0x180043db7  lea     rdx, [rcx-1]
0x180043dbb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180043dbf  ja      short loc_180043DCE
0x180043dc1  call    cs:__imp_RegCloseKey
0x180043dc8  nop     dword ptr [rax+rax+00h]
0x180043dcd  nop
0x180043dce  test    rbx, rbx
0x180043dd1  jz      loc_180043D4B
0x180043dd7  mov     rcx, rbx
0x180043dda  jmp     loc_180043D3F
0x180043ddf  mov     [rbp+arg_20], 0
0x180043de7  lea     r9, [rbp+arg_20]; struct Common::AutoHandleHKEY *
0x180043deb  lea     rdx, aStubpreference; "StubPreference"
0x180043df2  lea     rcx, [rbp+hKey]; this
0x180043df6  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x180043dfb  mov     edi, eax
0x180043dfd  test    eax, eax
0x180043dff  jns     short loc_180043E46
0x180043e01  mov     rcx, [rbp+28h]; this
0x180043e05  mov     r9d, eax; char *
0x180043e08  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043e0f  mov     edx, 138h; void *
0x180043e14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043e19  nop
0x180043e1a  mov     rcx, [rbp+arg_20]; hKey
0x180043e1e  lea     rdx, [rcx-1]
0x180043e22  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180043e26  ja      short loc_180043E35
0x180043e28  call    cs:__imp_RegCloseKey
0x180043e2f  nop     dword ptr [rax+rax+00h]
0x180043e34  nop
0x180043e35  mov     rcx, [rbp+hKey]
0x180043e39  lea     rax, [rcx-1]
0x180043e3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043e41  jmp     loc_180043DBF
0x180043e46  cmp     [rbp+arg_20], 0
0x180043e4b  jz      loc_180043F1F
0x180043e51  mov     [rbp+var_20], 0
0x180043e59  lea     r9, [rbp+var_20]; struct Common::AutoHandleHKEY *
0x180043e5d  mov     rdx, r12; unsigned __int16 *
0x180043e60  lea     rcx, [rbp+arg_20]; this
0x180043e64  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x180043e69  mov     edi, eax
0x180043e6b  test    eax, eax
0x180043e6d  jns     short loc_180043EB4
0x180043e6f  mov     rcx, [rbp+28h]; this
0x180043e73  mov     r9d, eax; char *
0x180043e76  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043e7d  mov     edx, 13Ch; void *
0x180043e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043e87  nop
0x180043e88  mov     rcx, [rbp+var_20]; hKey
0x180043e8c  lea     rdx, [rcx-1]
0x180043e90  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180043e94  ja      short loc_180043EA3
0x180043e96  call    cs:__imp_RegCloseKey
0x180043e9d  nop     dword ptr [rax+rax+00h]
0x180043ea2  nop
0x180043ea3  mov     rcx, [rbp+arg_20]
0x180043ea7  lea     rax, [rcx-1]
0x180043eab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043eaf  jmp     loc_180043E26
0x180043eb4  cmp     [rbp+var_20], 0
0x180043eb9  jz      short loc_180043F04
0x180043ebb  mov     [rbp+arg_10], 0
0x180043ec2  lea     r8, [rbp+arg_10]; unsigned int *
0x180043ec6  lea     rcx, [rbp+var_20]; this
0x180043eca  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x180043ecf  mov     edi, eax
0x180043ed1  cmp     eax, 80070001h
0x180043ed6  jle     loc_180043F83
0x180043edc  lea     ecx, [rax+7FF8FFFCh]
0x180043ee2  cmp     ecx, 7FF8FFFBh
0x180043ee8  jbe     loc_180043F83
0x180043eee  shr     edi, 1Fh
0x180043ef1  xor     dil, 1
0x180043ef5  jz      short loc_180043F04
0x180043ef7  cmp     [rbp+arg_10], 0
0x180043efb  setnz   al
0x180043efe  mov     [r14], al
0x180043f01  mov     byte ptr [rsi], 1
0x180043f04  mov     rcx, [rbp+var_20]; hKey
0x180043f08  lea     rax, [rcx-1]
0x180043f0c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043f10  ja      short loc_180043F1F
0x180043f12  call    cs:__imp_RegCloseKey
0x180043f19  nop     dword ptr [rax+rax+00h]
0x180043f1e  nop
0x180043f1f  mov     rcx, [rbp+arg_20]; hKey
0x180043f23  lea     rax, [rcx-1]
0x180043f27  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043f2b  ja      short loc_180043F3A
0x180043f2d  call    cs:__imp_RegCloseKey
0x180043f34  nop     dword ptr [rax+rax+00h]
0x180043f39  nop
0x180043f3a  mov     rcx, [rbp+hKey]; hKey
0x180043f3e  lea     rax, [rcx-1]
0x180043f42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043f46  ja      short loc_180043F55
0x180043f48  call    cs:__imp_RegCloseKey
0x180043f4f  nop     dword ptr [rax+rax+00h]
0x180043f54  nop
0x180043f55  test    rbx, rbx
0x180043f58  jz      short loc_180043F69
0x180043f5a  mov     rcx, rbx
0x180043f5d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180043f64  nop     dword ptr [rax+rax+00h]
0x180043f69  xor     eax, eax
0x180043f6b  mov     rbx, [rsp+40h+arg_0]
0x180043f70  mov     rsi, [rsp+40h+arg_8]
0x180043f75  add     rsp, 40h
0x180043f79  pop     r15
0x180043f7b  pop     r14
0x180043f7d  pop     r12
0x180043f7f  pop     rdi
0x180043f80  pop     rbp
0x180043f81  retn
0x180043f83  mov     rcx, [rbp+28h]; this
0x180043f87  mov     r9d, edi; char *
0x180043f8a  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043f91  mov     edx, 141h; void *
0x180043f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043f9b  nop
0x180043f9c  mov     rcx, [rbp+var_20]
0x180043fa0  lea     rax, [rcx-1]
0x180043fa4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043fa8  jmp     loc_180043E94
```
