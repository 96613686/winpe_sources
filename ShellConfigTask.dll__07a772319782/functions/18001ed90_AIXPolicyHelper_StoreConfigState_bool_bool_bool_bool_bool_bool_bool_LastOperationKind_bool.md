# AIXPolicyHelper::StoreConfigState(bool,bool,bool,bool,bool,bool,bool,LastOperationKind *,bool)

- ea: `0x18001ed90`
- end: `0x18001f18f`
- name: `?StoreConfigState@AIXPolicyHelper@@YAX_N000000PEAW4LastOperationKind@@0@Z`
- size: `1023`
- prototype: `void __fastcall(AIXPolicyHelper *this, unsigned __int8, unsigned __int8, unsigned __int8, bool, bool, bool, DWORD *, enum LastOperationKind *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e518`
- `0x18002b864`

## callees

- `0x18001ed90`
- `0x18002065c`
- `0x180020d3c`
- `0x180020f7c`
- `0x180020fbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f0aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f0aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ee0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ee0a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ee51`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ee8d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001eeca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef06`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef4c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef9c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001efec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f043`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f089`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ee51`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ee8d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001eeca`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef06`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef4c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ef9c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001efec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f043`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f089`

## string_xrefs

- `0x18001eef9`: `PolicyConfigured`
- `0x18001ee44`: `HardwareCompatibility`
- `0x18001edfc`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`
- `0x18001f0c0`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f0d5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f0ea`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f0ff`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f114`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f129`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f13e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f153`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f168`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001f17d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall AIXPolicyHelper::StoreConfigState(
        AIXPolicyHelper *this,
        unsigned __int8 a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        bool a5,
        bool a6,
        bool a7,
        DWORD *a8,
        enum LastOperationKind *a9)
{
  DWORD v9; // ebx
  DWORD v10; // r14d
  DWORD v11; // esi
  DWORD v12; // edi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int dwOptions; // [rsp+20h] [rbp-58h]
  int dwOptionsa; // [rsp+20h] [rbp-58h]
  int dwOptionsb; // [rsp+20h] [rbp-58h]
  int dwOptionsc; // [rsp+20h] [rbp-58h]
  int dwOptionsd; // [rsp+20h] [rbp-58h]
  int dwOptionse; // [rsp+20h] [rbp-58h]
  int dwOptionsf; // [rsp+20h] [rbp-58h]
  int dwOptionsg; // [rsp+20h] [rbp-58h]
  int dwOptionsh; // [rsp+20h] [rbp-58h]
  int dwOptionsi; // [rsp+20h] [rbp-58h]
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v9 = a4;
  v10 = a3;
  v11 = a2;
  v12 = (unsigned __int8)this;
  hKey = 0;
  dwDisposition = 0;
  v13 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hKey,
          &dwDisposition);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v13,
      dwOptions);
  dwDisposition = v12;
  v14 = RegSetKeyValueW(hKey, 0, L"HardwareCompatibility", 4u, &dwDisposition, 4u);
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x80070000;
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v14,
      dwOptionsa);
  dwDisposition = v11;
  v15 = RegSetKeyValueW(hKey, 0, L"ITManaged", 4u, &dwDisposition, 4u);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v15,
      dwOptionsb);
  dwDisposition = v10;
  v16 = RegSetKeyValueW(hKey, 0, L"AllowedInRegion", 4u, &dwDisposition, 4u);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v16,
      dwOptionsc);
  dwDisposition = v9;
  v17 = RegSetKeyValueW(hKey, 0, L"PolicyConfigured", 4u, &dwDisposition, 4u);
  if ( v17 > 0 )
    v17 = (unsigned __int16)v17 | 0x80070000;
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v17,
      dwOptionsd);
  dwDisposition = (_BYTE)v9 != 0 && a5;
  v18 = RegSetKeyValueW(hKey, 0, L"PolicyEnabled", 4u, &dwDisposition, 4u);
  if ( v18 > 0 )
    v18 = (unsigned __int16)v18 | 0x80070000;
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v18,
      dwOptionse);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl'::`2'::impl) )
  {
    dwDisposition = a7;
    v19 = RegSetKeyValueW(hKey, 0, L"FTDisabledState", 4u, &dwDisposition, 4u);
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v19,
        dwOptionsf);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl'::`2'::impl) )
  {
    dwDisposition = a6;
    v20 = RegSetKeyValueW(hKey, 0, L"MeetsAdditionalDriverRequirements", 4u, &dwDisposition, 4u);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v20,
        dwOptionsg);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl'::`2'::impl)
    && a8 )
  {
    dwDisposition = *a8;
    v21 = RegSetKeyValueW(hKey, 0, L"LastOperationKind", 4u, &dwDisposition, 4u);
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v21,
        dwOptionsh);
  }
  if ( (_BYTE)a9 )
  {
    dwDisposition = 1;
    v22 = RegSetKeyValueW(hKey, 0, L"DesiredStateMismatch ", 4u, &dwDisposition, 4u);
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v22,
        dwOptionsi);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001ed90  push    rbp
0x18001ed92  push    rbx
0x18001ed93  push    rsi
0x18001ed94  push    rdi
0x18001ed95  push    r12
0x18001ed97  push    r14
0x18001ed99  mov     rbp, rsp
0x18001ed9c  sub     rsp, 78h
0x18001eda0  movzx   ebx, r9b
0x18001eda4  movzx   r14d, r8b
0x18001eda8  movzx   esi, dl
0x18001edab  movzx   edi, cl
0x18001edae  mov     [rbp+var_28], 0
0x18001edb5  mov     [rbp+var_28], 1
0x18001edbc  mov     [rbp+hKey], 0
0x18001edc4  mov     [rbp+dwDisposition], 0
0x18001edcb  lea     rax, [rbp+dwDisposition]
0x18001edcf  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001edd4  lea     rax, [rbp+hKey]
0x18001edd8  mov     [rsp+78h+phkResult], rax; phkResult
0x18001eddd  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001ede6  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18001edee  mov     [rsp+78h+dwOptions], 0; int
0x18001edf6  xor     r9d, r9d; lpClass
0x18001edf9  xor     r8d, r8d; Reserved
0x18001edfc  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ee03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ee0a  call    cs:__imp_RegCreateKeyExW
0x18001ee10  mov     r12d, 80070000h
0x18001ee16  test    eax, eax
0x18001ee18  jle     short loc_18001EE20
0x18001ee1a  movzx   eax, ax
0x18001ee1d  or      eax, r12d
0x18001ee20  mov     rcx, [rbp+30h]; this
0x18001ee24  test    eax, eax
0x18001ee26  js      loc_18001F0D2
0x18001ee2c  mov     [rbp+dwDisposition], edi
0x18001ee2f  mov     edi, 4
0x18001ee34  mov     [rsp+78h+samDesired], edi; cbData
0x18001ee38  lea     rax, [rbp+dwDisposition]
0x18001ee3c  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001ee41  mov     r9d, edi; dwType
0x18001ee44  lea     r8, aHardwarecompat; "HardwareCompatibility"
0x18001ee4b  xor     edx, edx; lpSubKey
0x18001ee4d  mov     rcx, [rbp+hKey]; hKey
0x18001ee51  call    cs:__imp_RegSetKeyValueW
0x18001ee57  test    eax, eax
0x18001ee59  jle     short loc_18001EE61
0x18001ee5b  movzx   eax, ax
0x18001ee5e  or      eax, r12d
0x18001ee61  mov     rcx, [rbp+30h]; this
0x18001ee65  test    eax, eax
0x18001ee67  js      loc_18001F0E7
0x18001ee6d  mov     [rbp+dwDisposition], esi
0x18001ee70  mov     [rsp+78h+samDesired], edi; cbData
0x18001ee74  lea     rax, [rbp+dwDisposition]
0x18001ee78  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001ee7d  mov     r9d, edi; dwType
0x18001ee80  lea     r8, aItmanaged; "ITManaged"
0x18001ee87  xor     edx, edx; lpSubKey
0x18001ee89  mov     rcx, [rbp+hKey]; hKey
0x18001ee8d  call    cs:__imp_RegSetKeyValueW
0x18001ee93  test    eax, eax
0x18001ee95  jle     short loc_18001EE9D
0x18001ee97  movzx   eax, ax
0x18001ee9a  or      eax, r12d
0x18001ee9d  mov     rcx, [rbp+30h]; this
0x18001eea1  test    eax, eax
0x18001eea3  js      loc_18001F0FC
0x18001eea9  mov     [rbp+dwDisposition], r14d
0x18001eead  mov     [rsp+78h+samDesired], edi; cbData
0x18001eeb1  lea     rax, [rbp+dwDisposition]
0x18001eeb5  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001eeba  mov     r9d, edi; dwType
0x18001eebd  lea     r8, aAllowedinregio; "AllowedInRegion"
0x18001eec4  xor     edx, edx; lpSubKey
0x18001eec6  mov     rcx, [rbp+hKey]; hKey
0x18001eeca  call    cs:__imp_RegSetKeyValueW
0x18001eed0  test    eax, eax
0x18001eed2  jle     short loc_18001EEDA
0x18001eed4  movzx   eax, ax
0x18001eed7  or      eax, r12d
0x18001eeda  mov     rcx, [rbp+30h]; this
0x18001eede  test    eax, eax
0x18001eee0  js      loc_18001F111
0x18001eee6  mov     [rbp+dwDisposition], ebx
0x18001eee9  mov     [rsp+78h+samDesired], edi; cbData
0x18001eeed  lea     rax, [rbp+dwDisposition]
0x18001eef1  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001eef6  mov     r9d, edi; dwType
0x18001eef9  lea     r8, aPolicyconfigur; "PolicyConfigured"
0x18001ef00  xor     edx, edx; lpSubKey
0x18001ef02  mov     rcx, [rbp+hKey]; hKey
0x18001ef06  call    cs:__imp_RegSetKeyValueW
0x18001ef0c  test    eax, eax
0x18001ef0e  jle     short loc_18001EF16
0x18001ef10  movzx   eax, ax
0x18001ef13  or      eax, r12d
0x18001ef16  mov     rcx, [rbp+30h]; this
0x18001ef1a  test    eax, eax
0x18001ef1c  js      loc_18001F126
0x18001ef22  movzx   ecx, [rbp+arg_20]
0x18001ef26  neg     bl
0x18001ef28  sbb     eax, eax
0x18001ef2a  and     eax, ecx
0x18001ef2c  mov     [rbp+dwDisposition], eax
0x18001ef2f  mov     [rsp+78h+samDesired], edi; cbData
0x18001ef33  lea     rax, [rbp+dwDisposition]
0x18001ef37  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001ef3c  mov     r9d, edi; dwType
0x18001ef3f  lea     r8, aPolicyenabled; "PolicyEnabled"
0x18001ef46  xor     edx, edx; lpSubKey
0x18001ef48  mov     rcx, [rbp+hKey]; hKey
0x18001ef4c  call    cs:__imp_RegSetKeyValueW
0x18001ef52  test    eax, eax
0x18001ef54  jle     short loc_18001EF5C
0x18001ef56  movzx   eax, ax
0x18001ef59  or      eax, r12d
0x18001ef5c  mov     rcx, [rbp+30h]; this
0x18001ef60  test    eax, eax
0x18001ef62  js      loc_18001F13B
0x18001ef68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57247651@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651> `wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl(void)'::`2'::impl
0x18001ef6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(void)
0x18001ef74  test    al, al
0x18001ef76  jz      short loc_18001EFB8
0x18001ef78  movzx   eax, [rbp+arg_30]
0x18001ef7c  mov     [rbp+dwDisposition], eax
0x18001ef7f  mov     [rsp+78h+samDesired], edi; cbData
0x18001ef83  lea     rax, [rbp+dwDisposition]
0x18001ef87  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001ef8c  mov     r9d, edi; dwType
0x18001ef8f  lea     r8, aFtdisabledstat; "FTDisabledState"
0x18001ef96  xor     edx, edx; lpSubKey
0x18001ef98  mov     rcx, [rbp+hKey]; hKey
0x18001ef9c  call    cs:__imp_RegSetKeyValueW
0x18001efa2  test    eax, eax
0x18001efa4  jle     short loc_18001EFAC
0x18001efa6  movzx   eax, ax
0x18001efa9  or      eax, r12d
0x18001efac  mov     rcx, [rbp+30h]; this
0x18001efb0  test    eax, eax
0x18001efb2  js      loc_18001F150
0x18001efb8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55856303@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303> `wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl(void)'::`2'::impl
0x18001efbf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(void)
0x18001efc4  test    al, al
0x18001efc6  jz      short loc_18001F008
0x18001efc8  movzx   eax, [rbp+arg_28]
0x18001efcc  mov     [rbp+dwDisposition], eax
0x18001efcf  mov     [rsp+78h+samDesired], edi; cbData
0x18001efd3  lea     rax, [rbp+dwDisposition]
0x18001efd7  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001efdc  mov     r9d, edi; dwType
0x18001efdf  lea     r8, aMeetsadditiona; "MeetsAdditionalDriverRequirements"
0x18001efe6  xor     edx, edx; lpSubKey
0x18001efe8  mov     rcx, [rbp+hKey]; hKey
0x18001efec  call    cs:__imp_RegSetKeyValueW
0x18001eff2  test    eax, eax
0x18001eff4  jle     short loc_18001EFFC
0x18001eff6  movzx   eax, ax
0x18001eff9  or      eax, r12d
0x18001effc  mov     rcx, [rbp+30h]; this
0x18001f000  test    eax, eax
0x18001f002  js      loc_18001F165
0x18001f008  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617> `wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl(void)'::`2'::impl
0x18001f00f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(void)
0x18001f014  test    al, al
0x18001f016  jz      short loc_18001F05F
0x18001f018  mov     rax, [rbp+arg_38]
0x18001f01c  test    rax, rax
0x18001f01f  jz      short loc_18001F05F
0x18001f021  mov     eax, [rax]
0x18001f023  mov     [rbp+dwDisposition], eax
0x18001f026  mov     [rsp+78h+samDesired], edi; cbData
0x18001f02a  lea     rax, [rbp+dwDisposition]
0x18001f02e  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001f033  mov     r9d, edi; dwType
0x18001f036  lea     r8, aLastoperationk; "LastOperationKind"
0x18001f03d  xor     edx, edx; lpSubKey
0x18001f03f  mov     rcx, [rbp+hKey]; hKey
0x18001f043  call    cs:__imp_RegSetKeyValueW
0x18001f049  test    eax, eax
0x18001f04b  jle     short loc_18001F053
0x18001f04d  movzx   eax, ax
0x18001f050  or      eax, r12d
0x18001f053  mov     rcx, [rbp+30h]; this
0x18001f057  test    eax, eax
0x18001f059  js      loc_18001F17A
0x18001f05f  cmp     byte ptr [rbp+arg_40], 0
0x18001f063  jz      short loc_18001F0A1
0x18001f065  mov     [rbp+dwDisposition], 1
0x18001f06c  mov     [rsp+78h+samDesired], edi; cbData
0x18001f070  lea     rax, [rbp+dwDisposition]
0x18001f074  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18001f079  mov     r9d, edi; dwType
0x18001f07c  lea     r8, aDesiredstatemi; "DesiredStateMismatch "
0x18001f083  xor     edx, edx; lpSubKey
0x18001f085  mov     rcx, [rbp+hKey]; hKey
0x18001f089  call    cs:__imp_RegSetKeyValueW
0x18001f08f  test    eax, eax
0x18001f091  jle     short loc_18001F099
0x18001f093  movzx   eax, ax
0x18001f096  or      eax, r12d
0x18001f099  mov     rcx, [rbp+30h]; this
0x18001f09d  test    eax, eax
0x18001f09f  js      short loc_18001F0BD
0x18001f0a1  mov     rcx, [rbp+hKey]; hKey
0x18001f0a5  test    rcx, rcx
0x18001f0a8  jz      short loc_18001F0B0
0x18001f0aa  call    cs:__imp_RegCloseKey
0x18001f0b0  add     rsp, 78h
0x18001f0b4  pop     r14
0x18001f0b6  pop     r12
0x18001f0b8  pop     rdi
0x18001f0b9  pop     rsi
0x18001f0ba  pop     rbx
0x18001f0bb  pop     rbp
0x18001f0bc  retn
0x18001f0bd  mov     r9d, eax; char *
0x18001f0c0  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f0c7  mov     edx, 1CBEh; void *
0x18001f0cc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f0d2  mov     r9d, eax; char *
0x18001f0d5  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f0dc  mov     edx, 1CBEh; void *
0x18001f0e1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f0e7  mov     r9d, eax; char *
0x18001f0ea  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f0f1  mov     edx, 1CBEh; void *
0x18001f0f6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f0fc  mov     r9d, eax; char *
0x18001f0ff  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f106  mov     edx, 1CBEh; void *
0x18001f10b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f111  mov     r9d, eax; char *
0x18001f114  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f11b  mov     edx, 1CBEh; void *
0x18001f120  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f126  mov     r9d, eax; char *
0x18001f129  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f130  mov     edx, 1CBEh; void *
0x18001f135  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f13b  mov     r9d, eax; char *
0x18001f13e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f145  mov     edx, 1CBEh; void *
0x18001f14a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f150  mov     r9d, eax; char *
0x18001f153  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f15a  mov     edx, 1CBEh; void *
0x18001f15f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f165  mov     r9d, eax; char *
0x18001f168  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f16f  mov     edx, 1CBEh; void *
0x18001f174  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f17a  mov     r9d, eax; char *
0x18001f17d  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f184  mov     edx, 1CBEh; void *
0x18001f189  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
