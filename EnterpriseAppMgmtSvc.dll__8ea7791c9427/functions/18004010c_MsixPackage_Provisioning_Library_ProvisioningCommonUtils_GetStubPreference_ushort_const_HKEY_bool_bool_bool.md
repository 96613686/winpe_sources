# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetStubPreference(ushort const *,HKEY__ *,bool,bool *,bool *)

- ea: `0x18004010c`
- end: `0x1800403f9`
- name: `?GetStubPreference@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAUHKEY__@@_NPEA_N3@Z`
- size: `749`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, HKEY hKey@<rdx>, bool@<r8b>, bool *@<r9>, bool *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180035260`
- `0x180051edc`
- `0x180056d60`

## callees

- `0x18000cfe8`
- `0x18004010c`
- `0x1800407a4`
- `0x180065a64`
- `0x180065e5c`
- `0x180065ea8`
- `0x180065f6c`
- `0x180066224`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18004017f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401cf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800403af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004017f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401cf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800401df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800403af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040245`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800402a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004038b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800403a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040245`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800402a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004038b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800403a0`

## string_xrefs

- `0x180040169`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800401aa`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180040225`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180040282`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800402e7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800403d5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

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
0x18004010c  mov     [rsp-28h+arg_0], rbx
0x180040111  mov     [rsp-28h+arg_8], rsi
0x180040116  push    rbp
0x180040117  push    rdi
0x180040118  push    r12
0x18004011a  push    r14
0x18004011c  push    r15
0x18004011e  mov     rbp, rsp
0x180040121  sub     rsp, 40h
0x180040125  mov     rsi, r9
0x180040128  mov     r15, rdx
0x18004012b  mov     r12, rcx
0x18004012e  mov     byte ptr [r9], 0
0x180040132  mov     r14, [rbp+arg_20]
0x180040136  mov     byte ptr [r14], 0
0x18004013a  xor     eax, eax
0x18004013c  xorps   xmm0, xmm0
0x18004013f  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180040143  mov     [rbp+var_8], eax
0x180040146  test    r8b, r8b
0x180040149  jz      loc_1800401E7
0x18004014f  mov     [rbp+var_20], rax
0x180040153  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180040157  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x18004015c  mov     ebx, eax
0x18004015e  test    eax, eax
0x180040160  jns     short loc_18004018D
0x180040162  mov     rcx, [rbp+28h]; this
0x180040166  mov     r9d, eax; char *
0x180040169  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180040170  mov     edx, 12Dh; void *
0x180040175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004017a  nop
0x18004017b  mov     rcx, [rbp+var_20]
0x18004017f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180040185  nop
0x180040186  mov     eax, ebx
0x180040188  jmp     loc_1800403B7
0x18004018d  lea     rdx, [rbp+lpSubKey]; struct Common::StringBuffer *
0x180040191  mov     rbx, [rbp+var_20]
0x180040195  mov     rcx, rbx; unsigned __int16 *
0x180040198  call    ?StripSubkeyPrefixIfNecessary@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAVStringBuffer@Common@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(ushort const *,Common::StringBuffer *)
0x18004019d  mov     edi, eax
0x18004019f  test    eax, eax
0x1800401a1  jns     short loc_1800401DC
0x1800401a3  mov     rcx, [rbp+28h]; this
0x1800401a7  mov     r9d, eax; char *
0x1800401aa  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800401b1  mov     edx, 12Eh; void *
0x1800401b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401bb  nop
0x1800401bc  mov     rcx, rbx
0x1800401bf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800401c5  nop
0x1800401c6  mov     rcx, [rbp+lpSubKey+8]
0x1800401ca  test    rcx, rcx
0x1800401cd  jz      short loc_1800401D5
0x1800401cf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800401d5  mov     eax, edi
0x1800401d7  jmp     loc_1800403B7
0x1800401dc  mov     rcx, rbx
0x1800401df  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800401e5  jmp     short loc_1800401F7
0x1800401e7  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\App"...
0x1800401ee  lea     rcx, [rbp+lpSubKey]; this
0x1800401f2  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800401f7  mov     [rbp+hKey], 0
0x1800401ff  mov     rbx, [rbp+lpSubKey+8]
0x180040203  mov     r9d, 20019h; samDesired
0x180040209  mov     r8, rbx; lpSubKey
0x18004020c  mov     rdx, r15; hKey
0x18004020f  lea     rcx, [rbp+hKey]; phkResult
0x180040213  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180040218  mov     edi, eax
0x18004021a  test    eax, eax
0x18004021c  jns     short loc_180040259
0x18004021e  mov     rcx, [rbp+28h]; this
0x180040222  mov     r9d, eax; char *
0x180040225  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004022c  mov     edx, 136h; void *
0x180040231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040236  nop
0x180040237  mov     rcx, [rbp+hKey]; hKey
0x18004023b  lea     rdx, [rcx-1]
0x18004023f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180040243  ja      short loc_18004024C
0x180040245  call    cs:__imp_RegCloseKey
0x18004024b  nop
0x18004024c  test    rbx, rbx
0x18004024f  jz      short loc_1800401D5
0x180040251  mov     rcx, rbx
0x180040254  jmp     loc_1800401CF
0x180040259  mov     [rbp+arg_20], 0
0x180040261  lea     r9, [rbp+arg_20]; struct Common::AutoHandleHKEY *
0x180040265  lea     rdx, aStubpreference; "StubPreference"
0x18004026c  lea     rcx, [rbp+hKey]; this
0x180040270  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x180040275  mov     edi, eax
0x180040277  test    eax, eax
0x180040279  jns     short loc_1800402B7
0x18004027b  mov     rcx, [rbp+28h]; this
0x18004027f  mov     r9d, eax; char *
0x180040282  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180040289  mov     edx, 138h; void *
0x18004028e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040293  nop
0x180040294  mov     rcx, [rbp+arg_20]; hKey
0x180040298  lea     rdx, [rcx-1]
0x18004029c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800402a0  ja      short loc_1800402A9
0x1800402a2  call    cs:__imp_RegCloseKey
0x1800402a8  nop
0x1800402a9  mov     rcx, [rbp+hKey]
0x1800402ad  lea     rax, [rcx-1]
0x1800402b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800402b5  jmp     short loc_180040243
0x1800402b7  cmp     [rbp+arg_20], 0
0x1800402bc  jz      loc_18004037D
0x1800402c2  mov     [rbp+var_20], 0
0x1800402ca  lea     r9, [rbp+var_20]; struct Common::AutoHandleHKEY *
0x1800402ce  mov     rdx, r12; unsigned __int16 *
0x1800402d1  lea     rcx, [rbp+arg_20]; this
0x1800402d5  call    ?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)
0x1800402da  mov     edi, eax
0x1800402dc  test    eax, eax
0x1800402de  jns     short loc_18004031C
0x1800402e0  mov     rcx, [rbp+28h]; this
0x1800402e4  mov     r9d, eax; char *
0x1800402e7  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800402ee  mov     edx, 13Ch; void *
0x1800402f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402f8  nop
0x1800402f9  mov     rcx, [rbp+var_20]; hKey
0x1800402fd  lea     rdx, [rcx-1]
0x180040301  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180040305  ja      short loc_18004030E
0x180040307  call    cs:__imp_RegCloseKey
0x18004030d  nop
0x18004030e  mov     rcx, [rbp+arg_20]
0x180040312  lea     rax, [rcx-1]
0x180040316  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004031a  jmp     short loc_1800402A0
0x18004031c  cmp     [rbp+var_20], 0
0x180040321  jz      short loc_180040368
0x180040323  mov     [rbp+arg_10], 0
0x18004032a  lea     r8, [rbp+arg_10]; unsigned int *
0x18004032e  lea     rcx, [rbp+var_20]; this
0x180040332  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x180040337  mov     edi, eax
0x180040339  cmp     eax, 80070001h
0x18004033e  jle     loc_1800403CE
0x180040344  lea     ecx, [rax+7FF8FFFCh]
0x18004034a  cmp     ecx, 7FF8FFFBh
0x180040350  jbe     short loc_1800403CE
0x180040352  shr     edi, 1Fh
0x180040355  xor     dil, 1
0x180040359  jz      short loc_180040368
0x18004035b  cmp     [rbp+arg_10], 0
0x18004035f  setnz   al
0x180040362  mov     [r14], al
0x180040365  mov     byte ptr [rsi], 1
0x180040368  mov     rcx, [rbp+var_20]; hKey
0x18004036c  lea     rax, [rcx-1]
0x180040370  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040374  ja      short loc_18004037D
0x180040376  call    cs:__imp_RegCloseKey
0x18004037c  nop
0x18004037d  mov     rcx, [rbp+arg_20]; hKey
0x180040381  lea     rax, [rcx-1]
0x180040385  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040389  ja      short loc_180040392
0x18004038b  call    cs:__imp_RegCloseKey
0x180040391  nop
0x180040392  mov     rcx, [rbp+hKey]; hKey
0x180040396  lea     rax, [rcx-1]
0x18004039a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004039e  ja      short loc_1800403A7
0x1800403a0  call    cs:__imp_RegCloseKey
0x1800403a6  nop
0x1800403a7  test    rbx, rbx
0x1800403aa  jz      short loc_1800403B5
0x1800403ac  mov     rcx, rbx
0x1800403af  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800403b5  xor     eax, eax
0x1800403b7  mov     rbx, [rsp+40h+arg_0]
0x1800403bc  mov     rsi, [rsp+40h+arg_8]
0x1800403c1  add     rsp, 40h
0x1800403c5  pop     r15
0x1800403c7  pop     r14
0x1800403c9  pop     r12
0x1800403cb  pop     rdi
0x1800403cc  pop     rbp
0x1800403cd  retn
0x1800403ce  mov     rcx, [rbp+28h]; this
0x1800403d2  mov     r9d, edi; char *
0x1800403d5  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800403dc  mov     edx, 141h; void *
0x1800403e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800403e6  nop
0x1800403e7  mov     rcx, [rbp+var_20]
0x1800403eb  lea     rax, [rcx-1]
0x1800403ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800403f3  jmp     loc_180040305
```
