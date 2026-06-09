# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::SetStubPreference(ushort const *,HKEY__ *,bool,bool)

- ea: `0x1800440d0`
- end: `0x1800443a7`
- name: `?SetStubPreference@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAUHKEY__@@_N2@Z`
- size: `727`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005b444`

## callees

- `0x18000d3dc`
- `0x1800440d0`
- `0x1800443b0`
- `0x18006b444`
- `0x18006b7bc`
- `0x18006b894`
- `0x18006ba68`
- `0x18006bc58`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180044134`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004417a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180044190`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800441a6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180044388`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180044134`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004417a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180044190`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800441a6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180044388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004433d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044373`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004433d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044373`

## string_xrefs

- `0x18004411e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180044165`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800441f2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180044266`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800442d2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

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
  int v12; // edi
  WCHAR *v13; // rcx
  WCHAR *v14; // rbx
  int v15; // eax
  unsigned int v16; // r9d
  HKEY v17; // rcx
  bool v18; // cc
  int SubKey; // eax
  unsigned int v20; // r9d
  HKEY v21; // rcx
  bool v22; // cc
  __int64 v23; // rdx
  struct _SECURITY_ATTRIBUTES *v24; // [rsp+20h] [rbp-39h]
  struct _SECURITY_ATTRIBUTES *v25; // [rsp+20h] [rbp-39h]
  int v26; // [rsp+20h] [rbp-39h]
  unsigned int *v27; // [rsp+30h] [rbp-29h]
  unsigned int *v28; // [rsp+30h] [rbp-29h]
  HKEY hKeya; // [rsp+40h] [rbp-19h] BYREF
  HKEY v30; // [rsp+48h] [rbp-11h] BYREF
  HKEY v31; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 *v32; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp+7h] BYREF
  int v34; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = a4;
  *(_OWORD *)lpSubKey = 0;
  v34 = 0;
  if ( a3 )
  {
    v32 = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, &v32);
    v8 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        (int)v24);
      operator delete[](v32);
      return v8;
    }
    v10 = v32;
    v11 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(
            v32,
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
  v30 = 0;
  SubKey = Common::RegistryKey::CreateSubKey(
             (Common::RegistryKey *)&hKeya,
             L"StubPreference",
             0x2001Fu,
             v16,
             v24,
             (struct Common::AutoHandleHKEY *)&v30,
             v27);
  v12 = SubKey;
  if ( SubKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)SubKey,
      (int)v25);
    v21 = v30;
    v22 = (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_18:
    if ( v22 )
      RegCloseKey(v21);
    v17 = hKeya;
    v18 = (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_12;
  }
  v31 = 0;
  v12 = Common::RegistryKey::CreateSubKey(
          (Common::RegistryKey *)&v30,
          (const unsigned __int16 *)a1,
          0x2001Fu,
          v20,
          v25,
          (struct Common::AutoHandleHKEY *)&v31,
          v28);
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
    if ( (unsigned __int64)v31 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(v31);
    v21 = v30;
    v22 = (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_18;
  }
  v12 = Common::RegistryKey::SetUInt32Value((Common::RegistryKey *)&v31, L"PreferStub", v4);
  if ( v12 < 0 )
  {
    v23 = 282;
    goto LABEL_23;
  }
  if ( (unsigned __int64)v31 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v31);
  if ( (unsigned __int64)v30 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v30);
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKeya);
  if ( v14 )
    operator delete[](v14);
  return 0;
}

```

## disassembly

```asm
0x1800440d0  push    rbp
0x1800440d2  push    rbx
0x1800440d3  push    rsi
0x1800440d4  push    rdi
0x1800440d5  push    r14
0x1800440d7  push    r15
0x1800440d9  lea     rbp, [rsp-2Fh]
0x1800440de  sub     rsp, 88h
0x1800440e5  movzx   r14d, r9b
0x1800440e9  mov     rsi, rdx
0x1800440ec  mov     r15, rcx
0x1800440ef  xor     eax, eax
0x1800440f1  xorps   xmm0, xmm0
0x1800440f4  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1800440f8  mov     [rbp+57h+var_40], eax
0x1800440fb  test    r8b, r8b
0x1800440fe  jz      loc_1800441B4
0x180044104  mov     [rbp+57h+var_58], rax
0x180044108  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x18004410c  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x180044111  mov     ebx, eax
0x180044113  test    eax, eax
0x180044115  jns     short loc_180044148
0x180044117  mov     rcx, [rbp+5Fh]; this
0x18004411b  mov     r9d, eax; char *
0x18004411e  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044125  mov     edx, 10Ch; void *
0x18004412a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004412f  nop
0x180044130  mov     rcx, [rbp+57h+var_58]
0x180044134  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004413b  nop     dword ptr [rax+rax+00h]
0x180044140  nop
0x180044141  mov     eax, ebx
0x180044143  jmp     loc_180044396
0x180044148  lea     rdx, [rbp+57h+lpSubKey]; struct Common::StringBuffer *
0x18004414c  mov     rbx, [rbp+57h+var_58]
0x180044150  mov     rcx, rbx; unsigned __int16 *
0x180044153  call    ?StripSubkeyPrefixIfNecessary@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGPEAVStringBuffer@Common@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::StripSubkeyPrefixIfNecessary(ushort const *,Common::StringBuffer *)
0x180044158  mov     edi, eax
0x18004415a  test    eax, eax
0x18004415c  jns     short loc_1800441A3
0x18004415e  mov     rcx, [rbp+5Fh]; this
0x180044162  mov     r9d, eax; char *
0x180044165  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004416c  mov     edx, 10Dh; void *
0x180044171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044176  nop
0x180044177  mov     rcx, rbx
0x18004417a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180044181  nop     dword ptr [rax+rax+00h]
0x180044186  nop
0x180044187  mov     rcx, [rbp+57h+lpSubKey+8]
0x18004418b  test    rcx, rcx
0x18004418e  jz      short loc_18004419C
0x180044190  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180044197  nop     dword ptr [rax+rax+00h]
0x18004419c  mov     eax, edi
0x18004419e  jmp     loc_180044396
0x1800441a3  mov     rcx, rbx
0x1800441a6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800441ad  nop     dword ptr [rax+rax+00h]
0x1800441b2  jmp     short loc_1800441C4
0x1800441b4  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\App"...
0x1800441bb  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800441bf  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800441c4  mov     [rbp+57h+hKey], 0
0x1800441cc  mov     rbx, [rbp+57h+lpSubKey+8]
0x1800441d0  mov     r9d, 20019h; samDesired
0x1800441d6  mov     r8, rbx; lpSubKey
0x1800441d9  mov     rdx, rsi; hKey
0x1800441dc  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800441e0  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x1800441e5  mov     edi, eax
0x1800441e7  test    eax, eax
0x1800441e9  jns     short loc_180044230
0x1800441eb  mov     rcx, [rbp+5Fh]; this
0x1800441ef  mov     r9d, eax; char *
0x1800441f2  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800441f9  mov     edx, 115h; void *
0x1800441fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044203  nop
0x180044204  mov     rcx, [rbp+57h+hKey]; hKey
0x180044208  lea     rdx, [rcx-1]
0x18004420c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180044210  ja      short loc_18004421F
0x180044212  call    cs:__imp_RegCloseKey
0x180044219  nop     dword ptr [rax+rax+00h]
0x18004421e  nop
0x18004421f  test    rbx, rbx
0x180044222  jz      loc_18004419C
0x180044228  mov     rcx, rbx
0x18004422b  jmp     loc_180044190
0x180044230  mov     [rbp+57h+var_68], 0
0x180044238  lea     rax, [rbp+57h+var_68]
0x18004423c  mov     [rsp+0B0h+var_88], rax; struct Common::AutoHandleHKEY *
0x180044241  mov     esi, 2001Fh
0x180044246  mov     r8d, esi; unsigned int
0x180044249  lea     rdx, aStubpreference; "StubPreference"
0x180044250  lea     rcx, [rbp+57h+hKey]; this
0x180044254  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x180044259  mov     edi, eax
0x18004425b  test    eax, eax
0x18004425d  jns     short loc_1800442A4
0x18004425f  mov     rcx, [rbp+5Fh]; this
0x180044263  mov     r9d, eax; char *
0x180044266  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004426d  mov     edx, 117h; void *
0x180044272  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044277  nop
0x180044278  mov     rcx, [rbp+57h+var_68]; hKey
0x18004427c  lea     rdx, [rcx-1]
0x180044280  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180044284  ja      short loc_180044293
0x180044286  call    cs:__imp_RegCloseKey
0x18004428d  nop     dword ptr [rax+rax+00h]
0x180044292  nop
0x180044293  mov     rcx, [rbp+57h+hKey]
0x180044297  lea     rax, [rcx-1]
0x18004429b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004429f  jmp     loc_180044210
0x1800442a4  mov     [rbp+57h+var_60], 0
0x1800442ac  lea     rax, [rbp+57h+var_60]
0x1800442b0  mov     [rsp+0B0h+var_88], rax; struct Common::AutoHandleHKEY *
0x1800442b5  mov     r8d, esi; unsigned int
0x1800442b8  mov     rdx, r15; unsigned __int16 *
0x1800442bb  lea     rcx, [rbp+57h+var_68]; this
0x1800442bf  call    ?CreateSubKey@RegistryKey@Common@@QEAAJPEBGKKQEAU_SECURITY_ATTRIBUTES@@AEAVAutoHandleHKEY@2@PEAK@Z; Common::RegistryKey::CreateSubKey(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,Common::AutoHandleHKEY &,ulong *)
0x1800442c4  mov     edi, eax
0x1800442c6  test    eax, eax
0x1800442c8  jns     short loc_18004430F
0x1800442ca  mov     edx, 119h; void *
0x1800442cf  mov     r9d, edi; char *
0x1800442d2  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800442d9  mov     rcx, [rbp+5Fh]; this
0x1800442dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442e2  nop
0x1800442e3  mov     rcx, [rbp+57h+var_60]; hKey
0x1800442e7  lea     rdx, [rcx-1]
0x1800442eb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800442ef  ja      short loc_1800442FE
0x1800442f1  call    cs:__imp_RegCloseKey
0x1800442f8  nop     dword ptr [rax+rax+00h]
0x1800442fd  nop
0x1800442fe  mov     rcx, [rbp+57h+var_68]
0x180044302  lea     rax, [rcx-1]
0x180044306  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004430a  jmp     loc_180044284
0x18004430f  mov     r8d, r14d; unsigned int
0x180044312  lea     rdx, aPreferstub; "PreferStub"
0x180044319  lea     rcx, [rbp+57h+var_60]; this
0x18004431d  call    ?SetUInt32Value@RegistryKey@Common@@QEAAJPEBGI@Z; Common::RegistryKey::SetUInt32Value(ushort const *,uint)
0x180044322  mov     edi, eax
0x180044324  test    eax, eax
0x180044326  jns     short loc_18004432F
0x180044328  mov     edx, 11Ah
0x18004432d  jmp     short loc_1800442CF
0x18004432f  mov     rcx, [rbp+57h+var_60]; hKey
0x180044333  lea     rax, [rcx-1]
0x180044337  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004433b  ja      short loc_18004434A
0x18004433d  call    cs:__imp_RegCloseKey
0x180044344  nop     dword ptr [rax+rax+00h]
0x180044349  nop
0x18004434a  mov     rcx, [rbp+57h+var_68]; hKey
0x18004434e  lea     rax, [rcx-1]
0x180044352  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180044356  ja      short loc_180044365
0x180044358  call    cs:__imp_RegCloseKey
0x18004435f  nop     dword ptr [rax+rax+00h]
0x180044364  nop
0x180044365  mov     rcx, [rbp+57h+hKey]; hKey
0x180044369  lea     rax, [rcx-1]
0x18004436d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180044371  ja      short loc_180044380
0x180044373  call    cs:__imp_RegCloseKey
0x18004437a  nop     dword ptr [rax+rax+00h]
0x18004437f  nop
0x180044380  test    rbx, rbx
0x180044383  jz      short loc_180044394
0x180044385  mov     rcx, rbx
0x180044388  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004438f  nop     dword ptr [rax+rax+00h]
0x180044394  xor     eax, eax
0x180044396  add     rsp, 88h
0x18004439d  pop     r15
0x18004439f  pop     r14
0x1800443a1  pop     rdi
0x1800443a2  pop     rsi
0x1800443a3  pop     rbx
0x1800443a4  pop     rbp
0x1800443a5  retn
```
