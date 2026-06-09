# NgcFirst::GetSwitchCounts

- ea: `0x180042a1c`
- end: `0x180042e2b`
- name: `NgcFirst::GetSwitchCounts`
- size: `1039`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042e40`

## callees

- `0x18000782c`
- `0x180032b6c`
- `0x180032c20`
- `0x180042a1c`
- `0x180044714`
- `0x1800856b8`
- `0x180085e40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ac0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042bc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ac0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042bc7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042b07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042c5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042d17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042b07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042c5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180042d17`

## string_xrefs

- `0x180042a52`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180042c88`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180042dfe`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFirst::GetSwitchCounts(LPCWSTR lpSubKey, char a2, int *a3, int *a4)
{
  unsigned int SwitchCountsHelper; // ebx
  __int64 v9; // rdx
  char v10; // si
  LSTATUS v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  LSTATUS ValueW; // eax
  int v15; // r14d
  LSTATUS v16; // eax
  bool v17; // sf
  bool v18; // r15
  LSTATUS v19; // eax
  signed int v20; // edi
  bool v21; // di
  LSTATUS v22; // eax
  int v23; // eax
  int phkResult; // [rsp+20h] [rbp-48h]
  int phkResulta; // [rsp+20h] [rbp-48h]
  DWORD pdwType; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-24h] BYREF
  int pvData; // [rsp+48h] [rbp-20h] BYREF
  int v30; // [rsp+4Ch] [rbp-1Ch] BYREF
  int v31; // [rsp+50h] [rbp-18h] BYREF
  HKEY hkey[2]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  if ( lpSubKey )
  {
    if ( !a3 && !a4 )
    {
      SwitchCountsHelper = -2147024809;
      v9 = 700;
      goto LABEL_3;
    }
    hkey[0] = 0;
    pdwType = 0;
    pvData = 0;
    pcbData = 4;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hkey,
      0);
    v10 = 1;
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
            0,
            1u,
            hkey);
    SwitchCountsHelper = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v13 = 732;
LABEL_70:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
        (const char *)v12,
        phkResulta);
      goto LABEL_71;
    }
    ValueW = RegGetValueW(hkey[0], 0, L"NgcFirstMaxSwitchCountOverride", 0x10u, &pdwType, &pvData, &pcbData);
    SwitchCountsHelper = ValueW;
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          SwitchCountsHelper = (unsigned __int16)ValueW | 0x80070000;
        if ( (SwitchCountsHelper & 0x80000000) == 0 )
          goto LABEL_71;
        v13 = 744;
        goto LABEL_69;
      }
    }
    else
    {
      if ( pdwType != 4 || pcbData != 4 )
      {
        v13 = 747;
        goto LABEL_68;
      }
      v15 = pvData;
      if ( pvData )
      {
LABEL_19:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
        {
          SwitchCountsHelper = NgcFirst::GetSwitchCountsHelper(lpSubKey, L"ConsecutiveSwitchCount", (__int64)a4, v15);
LABEL_71:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
          return SwitchCountsHelper;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          hkey,
          0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          hkey,
          0);
        v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, hkey);
        SwitchCountsHelper = v16;
        if ( (v16 & 0xFFFFFFFD) != 0 )
        {
          v17 = v16 < 0;
          if ( v16 > 0 )
          {
            SwitchCountsHelper = (unsigned __int16)v16 | 0x80070000;
            v17 = 1;
          }
          if ( !v17 )
            goto LABEL_71;
          v13 = 786;
          goto LABEL_69;
        }
        v18 = v16 == 2;
        v30 = 0;
        v31 = 0;
        pdwType = 0;
        pvData = 0;
        pcbData = 4;
        if ( a3 && v16 != 2 )
        {
          v19 = RegGetValueW(hkey[0], 0, L"ConsecutiveSwitchCount", 0x10u, &pdwType, &pvData, &pcbData);
          v20 = v19;
          if ( v19 )
          {
            if ( v19 != 2 )
            {
              if ( v19 > 0 )
                v20 = (unsigned __int16)v19 | 0x80070000;
              if ( v20 < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x32B,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v20,
                  phkResulta);
              SwitchCountsHelper = v20;
              goto LABEL_71;
            }
            v21 = 1;
            goto LABEL_40;
          }
          if ( pdwType != 4 || pcbData != 4 )
          {
            v13 = 818;
            goto LABEL_68;
          }
          v30 = pvData;
        }
        v21 = SwitchCountsHelper == 2;
LABEL_40:
        pdwType = 0;
        pvData = 0;
        pcbData = 4;
        if ( !a4 || SwitchCountsHelper == 2 )
        {
LABEL_53:
          v10 = v18;
          goto LABEL_54;
        }
        v22 = RegGetValueW(hkey[0], 0, L"MaxSwitchCount", 0x10u, &pdwType, &pvData, &pcbData);
        SwitchCountsHelper = v22;
        if ( v22 )
        {
          if ( v22 != 2 )
          {
            if ( v22 > 0 )
              SwitchCountsHelper = (unsigned __int16)v22 | 0x80070000;
            if ( (SwitchCountsHelper & 0x80000000) == 0 )
              goto LABEL_71;
            v13 = 838;
            goto LABEL_69;
          }
LABEL_54:
          if ( !v21 )
          {
            if ( !v10 )
              goto LABEL_56;
LABEL_63:
            v31 = v15;
LABEL_64:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              hkey,
              0);
            v23 = NgcFirst::SetSwitchCounts(
                    lpSubKey,
                    (BYTE *)((unsigned __int64)&v30 & -(__int64)v21),
                    (BYTE *)((unsigned __int64)&v31 & -(__int64)(v10 != 0)));
            SwitchCountsHelper = v23;
            if ( v23 < 0 )
            {
              v12 = (unsigned int)v23;
              v13 = 877;
              goto LABEL_70;
            }
LABEL_56:
            if ( a3 )
              *a3 = v30;
            if ( a4 )
              *a4 = v31;
            SwitchCountsHelper = 0;
            goto LABEL_71;
          }
LABEL_62:
          v30 = 0;
          if ( !v10 )
            goto LABEL_64;
          goto LABEL_63;
        }
        if ( pdwType == 4 && pcbData == 4 )
        {
          if ( pvData != v15 )
          {
            v21 = 1;
            goto LABEL_62;
          }
          v31 = pvData;
          goto LABEL_53;
        }
        v13 = 845;
LABEL_68:
        SwitchCountsHelper = -2147418113;
LABEL_69:
        v12 = SwitchCountsHelper;
        goto LABEL_70;
      }
    }
    v15 = 3 - (a2 != 0);
    goto LABEL_19;
  }
  SwitchCountsHelper = -2147467261;
  v9 = 699;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
    (const char *)SwitchCountsHelper,
    phkResult);
  return SwitchCountsHelper;
}

```

## disassembly

```asm
0x180042a1c  mov     [rsp-40h+lpSubKey], rcx
0x180042a21  push    rbp
0x180042a22  push    rbx
0x180042a23  push    rsi
0x180042a24  push    rdi
0x180042a25  push    r12
0x180042a27  push    r13
0x180042a29  push    r14
0x180042a2b  push    r15
0x180042a2d  mov     rbp, rsp
0x180042a30  sub     rsp, 68h
0x180042a34  mov     r12, r9
0x180042a37  mov     r13, r8
0x180042a3a  mov     dil, dl
0x180042a3d  mov     r15, rcx
0x180042a40  xor     r14d, r14d
0x180042a43  test    rcx, rcx
0x180042a46  jnz     short loc_180042A6A
0x180042a48  mov     ebx, 80004003h
0x180042a4d  mov     edx, 2BBh; void *
0x180042a52  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042a59  mov     r9d, ebx; char *
0x180042a5c  mov     rcx, [rbp+40h]; this
0x180042a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042a65  jmp     loc_180042E18
0x180042a6a  test    r13, r13
0x180042a6d  jnz     short loc_180042A80
0x180042a6f  test    r12, r12
0x180042a72  jnz     short loc_180042A80
0x180042a74  mov     ebx, 80070057h
0x180042a79  mov     edx, 2BCh
0x180042a7e  jmp     short loc_180042A52
0x180042a80  mov     [rbp+hkey], r14
0x180042a84  mov     [rbp+pdwType], r14d
0x180042a88  mov     [rbp+var_20], r14d
0x180042a8c  mov     [rbp+var_24], 4
0x180042a93  xor     edx, edx
0x180042a95  lea     rcx, [rbp+hkey]
0x180042a99  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042a9e  lea     rax, [rbp+hkey]
0x180042aa2  mov     [rsp+68h+phkResult], rax; phkResult
0x180042aa7  mov     esi, 1
0x180042aac  mov     r9d, esi; samDesired
0x180042aaf  xor     r8d, r8d; ulOptions
0x180042ab2  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180042ab9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042ac0  call    cs:__imp_RegOpenKeyExW
0x180042ac6  mov     ebx, eax
0x180042ac8  test    eax, eax
0x180042aca  jns     short loc_180042AD9
0x180042acc  mov     r9d, eax
0x180042acf  mov     edx, 2DCh
0x180042ad4  jmp     loc_180042DFE
0x180042ad9  lea     rax, [rbp+var_24]
0x180042add  mov     [rsp+68h+pcbData], rax; pcbData
0x180042ae2  lea     rax, [rbp+var_20]
0x180042ae6  mov     [rsp+68h+pvData], rax; pvData
0x180042aeb  lea     rax, [rbp+pdwType]
0x180042aef  mov     [rsp+68h+phkResult], rax; int
0x180042af4  mov     r9d, 10h; dwFlags
0x180042afa  lea     r8, aNgcfirstmaxswi; "NgcFirstMaxSwitchCountOverride"
0x180042b01  xor     edx, edx; lpSubKey
0x180042b03  mov     rcx, [rbp+hkey]; hkey
0x180042b07  call    cs:__imp_RegGetValueW
0x180042b0d  mov     ebx, eax
0x180042b0f  test    eax, eax
0x180042b11  jz      short loc_180042B37
0x180042b13  cmp     eax, 2
0x180042b16  jz      short loc_180042B54
0x180042b18  test    eax, eax
0x180042b1a  jle     short loc_180042B25
0x180042b1c  movzx   ebx, ax
0x180042b1f  or      ebx, 80070000h
0x180042b25  test    ebx, ebx
0x180042b27  jns     loc_180042E0F
0x180042b2d  mov     edx, 2E8h
0x180042b32  jmp     loc_180042DFB
0x180042b37  cmp     [rbp+pdwType], 4
0x180042b3b  jnz     loc_180042DF1
0x180042b41  cmp     [rbp+var_24], 4
0x180042b45  jnz     loc_180042DF1
0x180042b4b  mov     r14d, [rbp+var_20]
0x180042b4f  test    r14d, r14d
0x180042b52  jnz     short loc_180042B5E
0x180042b54  neg     dil
0x180042b57  sbb     r14d, r14d
0x180042b5a  add     r14d, 3
0x180042b5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst> `wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl(void)'::`2'::impl
0x180042b65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(void)
0x180042b6a  test    al, al
0x180042b6c  jz      short loc_180042B98
0x180042b6e  mov     dword ptr [rsp+68h+pvData], r14d; int
0x180042b73  mov     [rsp+68h+phkResult], r12; __int64
0x180042b78  lea     r9, aMaxswitchcount; "MaxSwitchCount"
0x180042b7f  mov     r8, r13
0x180042b82  lea     rdx, aConsecutiveswi; "ConsecutiveSwitchCount"
0x180042b89  mov     rcx, r15; lpSubKey
0x180042b8c  call    NgcFirst__GetSwitchCountsHelper
0x180042b91  mov     ebx, eax
0x180042b93  jmp     loc_180042E0F
0x180042b98  xor     edx, edx
0x180042b9a  lea     rcx, [rbp+hkey]
0x180042b9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042ba3  xor     edx, edx
0x180042ba5  lea     rcx, [rbp+hkey]
0x180042ba9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042bae  lea     rax, [rbp+hkey]
0x180042bb2  mov     [rsp+68h+phkResult], rax; phkResult
0x180042bb7  mov     r9d, esi; samDesired
0x180042bba  xor     r8d, r8d; ulOptions
0x180042bbd  mov     rdx, r15; lpSubKey
0x180042bc0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042bc7  call    cs:__imp_RegOpenKeyExW
0x180042bcd  mov     ebx, eax
0x180042bcf  test    eax, 0FFFFFFFDh
0x180042bd4  jz      short loc_180042BF5
0x180042bd6  test    eax, eax
0x180042bd8  jle     short loc_180042BE5
0x180042bda  movzx   ebx, bx
0x180042bdd  or      ebx, 80070000h
0x180042be3  test    ebx, ebx
0x180042be5  jns     loc_180042E0F
0x180042beb  mov     edx, 312h
0x180042bf0  jmp     loc_180042DFB
0x180042bf5  cmp     ebx, 2
0x180042bf8  setz    r15b
0x180042bfc  mov     [rbp+var_1C], 0
0x180042c03  mov     [rbp+var_18], 0
0x180042c0a  mov     [rbp+pdwType], 0
0x180042c11  mov     [rbp+var_20], 0
0x180042c18  mov     [rbp+var_24], 4
0x180042c1f  test    r13, r13
0x180042c22  jz      loc_180042CBF
0x180042c28  cmp     ebx, 2
0x180042c2b  jz      loc_180042CBF
0x180042c31  lea     rax, [rbp+var_24]
0x180042c35  mov     [rsp+68h+pcbData], rax; pcbData
0x180042c3a  lea     rax, [rbp+var_20]
0x180042c3e  mov     [rsp+68h+pvData], rax; pvData
0x180042c43  lea     rax, [rbp+pdwType]
0x180042c47  mov     [rsp+68h+phkResult], rax; int
0x180042c4c  mov     r9d, 10h; dwFlags
0x180042c52  lea     r8, aConsecutiveswi; "ConsecutiveSwitchCount"
0x180042c59  xor     edx, edx; lpSubKey
0x180042c5b  mov     rcx, [rbp+hkey]; hkey
0x180042c5f  call    cs:__imp_RegGetValueW
0x180042c65  mov     edi, eax
0x180042c67  test    eax, eax
0x180042c69  jz      short loc_180042CA5
0x180042c6b  cmp     eax, 2
0x180042c6e  jz      short loc_180042CA0
0x180042c70  test    eax, eax
0x180042c72  jle     short loc_180042C7D
0x180042c74  movzx   edi, ax
0x180042c77  or      edi, 80070000h
0x180042c7d  test    edi, edi
0x180042c7f  jns     short loc_180042C99
0x180042c81  mov     rcx, [rbp+40h]; this
0x180042c85  mov     r9d, edi; char *
0x180042c88  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042c8f  mov     edx, 32Bh; void *
0x180042c94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c99  mov     ebx, edi
0x180042c9b  jmp     loc_180042E0F
0x180042ca0  mov     dil, sil
0x180042ca3  jmp     short loc_180042CC2
0x180042ca5  cmp     [rbp+pdwType], 4
0x180042ca9  jnz     loc_180042D47
0x180042caf  cmp     [rbp+var_24], 4
0x180042cb3  jnz     loc_180042D47
0x180042cb9  mov     eax, [rbp+var_20]
0x180042cbc  mov     [rbp+var_1C], eax
0x180042cbf  mov     dil, r15b
0x180042cc2  mov     [rbp+pdwType], 0
0x180042cc9  mov     [rbp+var_20], 0
0x180042cd0  mov     [rbp+var_24], 4
0x180042cd7  test    r12, r12
0x180042cda  jz      loc_180042D70
0x180042ce0  cmp     ebx, 2
0x180042ce3  jz      loc_180042D70
0x180042ce9  lea     rax, [rbp+var_24]
0x180042ced  mov     [rsp+68h+pcbData], rax; pcbData
0x180042cf2  lea     rax, [rbp+var_20]
0x180042cf6  mov     [rsp+68h+pvData], rax; pvData
0x180042cfb  lea     rax, [rbp+pdwType]
0x180042cff  mov     [rsp+68h+phkResult], rax; pdwType
0x180042d04  mov     r9d, 10h; dwFlags
0x180042d0a  lea     r8, aMaxswitchcount; "MaxSwitchCount"
0x180042d11  xor     edx, edx; lpSubKey
0x180042d13  mov     rcx, [rbp+hkey]; hkey
0x180042d17  call    cs:__imp_RegGetValueW
0x180042d1d  mov     ebx, eax
0x180042d1f  test    eax, eax
0x180042d21  jz      short loc_180042D51
0x180042d23  cmp     eax, 2
0x180042d26  jz      short loc_180042D73
0x180042d28  test    eax, eax
0x180042d2a  jle     short loc_180042D35
0x180042d2c  movzx   ebx, ax
0x180042d2f  or      ebx, 80070000h
0x180042d35  test    ebx, ebx
0x180042d37  jns     loc_180042E0F
0x180042d3d  mov     edx, 346h
0x180042d42  jmp     loc_180042DFB
0x180042d47  mov     edx, 332h
0x180042d4c  jmp     loc_180042DF6
0x180042d51  cmp     [rbp+pdwType], 4
0x180042d55  jnz     loc_180042DEA
0x180042d5b  cmp     [rbp+var_24], 4
0x180042d5f  jnz     loc_180042DEA
0x180042d65  mov     eax, [rbp+var_20]
0x180042d68  cmp     eax, r14d
0x180042d6b  jnz     short loc_180042D99
0x180042d6d  mov     [rbp+var_18], eax
0x180042d70  mov     sil, r15b
0x180042d73  test    dil, dil
0x180042d76  jnz     short loc_180042D9C
0x180042d78  test    sil, sil
0x180042d7b  jnz     short loc_180042DA8
0x180042d7d  test    r13, r13
0x180042d80  jz      short loc_180042D89
0x180042d82  mov     eax, [rbp+var_1C]
0x180042d85  mov     [r13+0], eax
0x180042d89  test    r12, r12
0x180042d8c  jz      short loc_180042D95
0x180042d8e  mov     eax, [rbp+var_18]
0x180042d91  mov     [r12], eax
0x180042d95  xor     ebx, ebx
0x180042d97  jmp     short loc_180042E0F
0x180042d99  mov     dil, sil
0x180042d9c  mov     [rbp+var_1C], 0
0x180042da3  test    sil, sil
0x180042da6  jz      short loc_180042DAC
0x180042da8  mov     [rbp+var_18], r14d
0x180042dac  xor     edx, edx
0x180042dae  lea     rcx, [rbp+hkey]
0x180042db2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042db7  neg     sil
0x180042dba  sbb     r8, r8
0x180042dbd  lea     rax, [rbp+var_18]
0x180042dc1  and     r8, rax; BYTE *
0x180042dc4  neg     dil
0x180042dc7  sbb     rdx, rdx
0x180042dca  lea     rax, [rbp+var_1C]
0x180042dce  and     rdx, rax; lpData
0x180042dd1  mov     rcx, [rbp+lpSubKey]; lpSubKey
0x180042dd5  call    NgcFirst__SetSwitchCounts
0x180042dda  mov     ebx, eax
0x180042ddc  test    eax, eax
0x180042dde  jns     short loc_180042D7D
0x180042de0  mov     r9d, eax
0x180042de3  mov     edx, 36Dh
0x180042de8  jmp     short loc_180042DFE
0x180042dea  mov     edx, 34Dh
0x180042def  jmp     short loc_180042DF6
0x180042df1  mov     edx, 2EBh; void *
0x180042df6  mov     ebx, 8000FFFFh
0x180042dfb  mov     r9d, ebx; char *
0x180042dfe  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042e05  mov     rcx, [rbp+40h]; this
0x180042e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042e0e  nop
0x180042e0f  lea     rcx, [rbp+hkey]
0x180042e13  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042e18  mov     eax, ebx
0x180042e1a  add     rsp, 68h
0x180042e1e  pop     r15
0x180042e20  pop     r14
0x180042e22  pop     r13
0x180042e24  pop     r12
0x180042e26  pop     rdi
0x180042e27  pop     rsi
0x180042e28  pop     rbx
0x180042e29  pop     rbp
0x180042e2a  retn
```
