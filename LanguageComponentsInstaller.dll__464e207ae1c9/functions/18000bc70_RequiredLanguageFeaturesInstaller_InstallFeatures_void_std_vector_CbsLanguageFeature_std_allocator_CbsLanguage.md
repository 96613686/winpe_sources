# RequiredLanguageFeaturesInstaller::InstallFeatures<void (std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)>(void (&)(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &))

- ea: `0x18000bc70`
- end: `0x18000bffa`
- name: `??$InstallFeatures@$$A6AXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z@RequiredLanguageFeaturesInstaller@@QEBA?AW4FutureAction@@A6AXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z@Z`
- size: `906`
- prototype: `__int64 __fastcall(__int64 *, void (__fastcall *)(__int128 *))`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800140e0`

## callees

- `0x180003520`
- `0x180003544`
- `0x18000bc70`
- `0x18000c000`
- `0x18000d4a8`
- `0x180011798`
- `0x1800125ec`
- `0x180012b94`
- `0x180016d58`
- `0x180018ac4`
- `0x18001ac28`
- `0x18002085c`
- `0x180021590`
- `0x18002a010`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000bce6`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000bd44`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000bce6`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000bd44`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd1d`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd6f`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd82`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd1d`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd6f`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x18000bd82`

## string_xrefs

- `0x18000bcd8`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x18000bd36`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x18000bcf7`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\RequiredLanguageComponentsInstaller.h`
- `0x18000bd55`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\RequiredLanguageComponentsInstaller.h`

## pseudocode

```c
__int64 __fastcall RequiredLanguageFeaturesInstaller::InstallFeatures<void (std::vector<CbsLanguageFeature> const &)>(
        __int64 *a1,
        void (__fastcall *a2)(__int128 *))
{
  unsigned int v3; // r15d
  unsigned int v4; // r12d
  int Policy; // eax
  __int64 v6; // rcx
  int v7; // eax
  bool v8; // bl
  __int64 v9; // rsi
  __int64 v10; // r13
  int v11; // r15d
  __int64 v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // r15
  _DWORD *v17; // rax
  __int64 v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rax
  char v21; // r8
  __int64 *v22; // rax
  __int64 i; // rcx
  __int64 **v24; // rdx
  __int64 *j; // rcx
  __int64 *k; // rdx
  int v28; // [rsp+20h] [rbp-59h]
  __int128 v30; // [rsp+38h] [rbp-41h] BYREF
  __int64 v31; // [rsp+48h] [rbp-31h]
  __int64 v32; // [rsp+50h] [rbp-29h] BYREF
  int v33; // [rsp+58h] [rbp-21h] BYREF
  int v34; // [rsp+5Ch] [rbp-1Dh]
  __int128 v35; // [rsp+60h] [rbp-19h] BYREF
  _DWORD *v36; // [rsp+70h] [rbp-9h]
  __int64 v37; // [rsp+78h] [rbp-1h] BYREF
  __int64 v38; // [rsp+80h] [rbp+7h] BYREF
  __int64 v39; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v4 = 1;
  v33 = 1;
  v34 = 1;
  if ( !IsRunningAsLocalSystem() )
  {
    v37 = 0;
    Policy = PolicyManager_GetPolicy(L"TimeLanguageSettings", L"RestrictLanguagePacksAndFeaturesInstall", &v33, &v37);
    if ( Policy >= 0 )
    {
      v6 = v37;
      if ( *(_DWORD *)(v37 + 4) == 1 )
        goto LABEL_11;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\RequiredLanguageCom"
                      "ponentsInstaller.h",
        (const char *)(unsigned int)Policy,
        0);
      v6 = v37;
    }
    if ( v6 )
      PolicyManager_FreeGetPolicyData();
  }
  v34 = 2;
  v32 = 0;
  v7 = PolicyManager_GetPolicy(L"TimeLanguageSettings", L"RestrictLanguagePacksAndFeaturesInstall", &v33, &v32);
  if ( v7 >= 0 )
  {
    v6 = v32;
LABEL_11:
    v8 = *(_DWORD *)(v6 + 16) == 0;
    PolicyManager_FreeGetPolicyData();
    if ( !v8 )
      goto LABEL_32;
    goto LABEL_12;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x8E,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\RequiredLanguageComponentsInstaller.h",
    (const char *)(unsigned int)v7,
    v28);
  if ( v32 )
    PolicyManager_FreeGetPolicyData();
LABEL_12:
  v9 = *a1;
  v10 = a1[1];
  if ( *a1 != v10 )
  {
    do
    {
      BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::GetBestMatchFeaturesForTypes(a1 + 6, &v35, v9, a1 + 6);
      v11 = v3 | 3;
      RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(a1, v9, &v35);
      v12 = *((_QWORD *)&v35 + 1);
      v13 = v35;
      if ( (_QWORD)v35 != *((_QWORD *)&v35 + 1) )
      {
        v14 = *((_QWORD *)&v30 + 1);
        do
        {
          if ( v14 == v31 )
          {
            std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature>(&v30, v14, v13);
            v14 = *((_QWORD *)&v30 + 1);
          }
          else
          {
            CbsLanguageFeature::CbsLanguageFeature(v14, v13);
            v14 = *((_QWORD *)&v30 + 1) + 192LL;
            *((_QWORD *)&v30 + 1) += 192LL;
          }
          v13 += 192;
        }
        while ( v13 != v12 );
      }
      v3 = v11 & 0xFFFFFFFE;
      std::vector<CbsLanguageFeature>::_Tidy(&v35);
      v9 += 32;
    }
    while ( v9 != v10 );
    v4 = 1;
  }
  v15 = a1[3];
  v16 = a1[4];
  while ( v15 != v16 )
  {
    v35 = 0;
    v36 = 0;
    v17 = operator new(4u);
    *(_QWORD *)&v35 = v17;
    v36 = v17 + 1;
    *v17 = 1;
    *((_QWORD *)&v35 + 1) = v17 + 1;
    v32 = 0;
    std::_Tidy_guard<std::vector<enum PayloadType>>::~_Tidy_guard<std::vector<enum PayloadType>>(&v32);
    BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::GetBestMatchFeaturesForTypes(a1 + 6, &v38, v15, &v35);
    std::vector<enum PayloadType>::~vector<enum PayloadType>(&v35);
    RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(a1, v15, &v38);
    v18 = v39;
    v19 = v38;
    if ( v38 != v39 )
    {
      v20 = *((_QWORD *)&v30 + 1);
      do
      {
        if ( v20 == v31 )
        {
          std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature>(&v30, v20, v19);
          v20 = *((_QWORD *)&v30 + 1);
        }
        else
        {
          CbsLanguageFeature::CbsLanguageFeature(v20, v19);
          v20 = *((_QWORD *)&v30 + 1) + 192LL;
          *((_QWORD *)&v30 + 1) += 192LL;
        }
        v19 += 192;
      }
      while ( v19 != v18 );
    }
    std::vector<CbsLanguageFeature>::_Tidy(&v38);
    v15 += 32;
  }
  if ( (_QWORD)v30 != *((_QWORD *)&v30 + 1) )
  {
    NormalizeContainer<std::vector<CbsLanguageFeature>>(&v30);
    a2(&v30);
  }
LABEL_32:
  if ( (_QWORD)v30 == *((_QWORD *)&v30 + 1) )
  {
    v21 = 0;
    v22 = *(__int64 **)a1[9];
    while ( !*((_BYTE *)v22 + 25) )
    {
      for ( i = v22[5]; i != v22[6]; i += 192 )
        v21 |= 1u;
      v24 = (__int64 **)v22[2];
      if ( *((_BYTE *)v24 + 25) )
      {
        for ( j = (__int64 *)v22[1]; !*((_BYTE *)j + 25) && v22 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v22 = j;
        v22 = j;
      }
      else
      {
        v22 = (__int64 *)v22[2];
        for ( k = *v24; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v22 = k;
      }
    }
    if ( v21 )
      v4 = 0;
  }
  std::vector<CbsLanguageFeature>::_Tidy(&v30);
  return v4;
}

```

## disassembly

```asm
0x18000bc70  mov     [rsp-8+arg_10], rbx
0x18000bc75  push    rbp
0x18000bc76  push    rsi
0x18000bc77  push    rdi
0x18000bc78  push    r12
0x18000bc7a  push    r13
0x18000bc7c  push    r14
0x18000bc7e  push    r15
0x18000bc80  lea     rbp, [rsp-27h]
0x18000bc85  sub     rsp, 0A0h
0x18000bc8c  mov     rax, cs:__security_cookie
0x18000bc93  xor     rax, rsp
0x18000bc96  mov     [rbp+57h+var_38], rax
0x18000bc9a  mov     [rbp+57h+var_A8], rdx
0x18000bc9e  mov     rdi, rcx
0x18000bca1  xor     r14d, r14d
0x18000bca4  mov     r15d, r14d
0x18000bca7  mov     [rbp+57h+var_B0], r14d
0x18000bcab  xorps   xmm0, xmm0
0x18000bcae  movdqu  [rbp+57h+var_98], xmm0
0x18000bcb3  mov     [rbp+57h+var_88], r14
0x18000bcb7  lea     r12d, [r14+1]
0x18000bcbb  mov     [rbp+57h+var_78], r12d
0x18000bcbf  mov     [rbp+57h+var_74], r12d
0x18000bcc3  call    ?IsRunningAsLocalSystem@@YA_NXZ; IsRunningAsLocalSystem(void)
0x18000bcc8  test    al, al
0x18000bcca  jnz     short loc_18000BD23
0x18000bccc  mov     [rbp+57h+var_58], r14
0x18000bcd0  lea     r9, [rbp+57h+var_58]
0x18000bcd4  lea     r8, [rbp+57h+var_78]
0x18000bcd8  lea     rdx, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x18000bcdf  lea     rcx, aTimelanguagese; "TimeLanguageSettings"
0x18000bce6  call    cs:__imp_PolicyManager_GetPolicy
0x18000bcec  mov     rcx, [rbp+5Fh]; this
0x18000bcf0  test    eax, eax
0x18000bcf2  jns     short loc_18000BD0E
0x18000bcf4  mov     r9d, eax; char *
0x18000bcf7  lea     r8, aOnecoreShellCp; "onecore\\shell\\cpls\\internationalsett"...
0x18000bcfe  lea     edx, [r12+7Fh]; void *
0x18000bd03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bd08  mov     rcx, [rbp+57h+var_58]
0x18000bd0c  jmp     short loc_18000BD18
0x18000bd0e  mov     rcx, [rbp+57h+var_58]
0x18000bd12  cmp     [rcx+4], r12d
0x18000bd16  jz      short loc_18000BD7B
0x18000bd18  test    rcx, rcx
0x18000bd1b  jz      short loc_18000BD23
0x18000bd1d  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x18000bd23  mov     [rbp+57h+var_74], 2
0x18000bd2a  mov     [rbp+57h+var_80], r14
0x18000bd2e  lea     r9, [rbp+57h+var_80]
0x18000bd32  lea     r8, [rbp+57h+var_78]
0x18000bd36  lea     rdx, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x18000bd3d  lea     rcx, aTimelanguagese; "TimeLanguageSettings"
0x18000bd44  call    cs:__imp_PolicyManager_GetPolicy
0x18000bd4a  mov     rcx, [rbp+5Fh]; this
0x18000bd4e  test    eax, eax
0x18000bd50  jns     short loc_18000BD77
0x18000bd52  mov     r9d, eax; char *
0x18000bd55  lea     r8, aOnecoreShellCp; "onecore\\shell\\cpls\\internationalsett"...
0x18000bd5c  mov     edx, 8Eh; void *
0x18000bd61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bd66  mov     rcx, [rbp+57h+var_80]
0x18000bd6a  test    rcx, rcx
0x18000bd6d  jz      short loc_18000BD90
0x18000bd6f  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x18000bd75  jmp     short loc_18000BD90
0x18000bd77  mov     rcx, [rbp+57h+var_80]
0x18000bd7b  cmp     [rcx+10h], r14d
0x18000bd7f  setz    bl
0x18000bd82  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x18000bd88  test    bl, bl
0x18000bd8a  jz      loc_18000BF4A
0x18000bd90  mov     rsi, [rdi]
0x18000bd93  mov     r13, [rdi+8]
0x18000bd97  cmp     rsi, r13
0x18000bd9a  jz      loc_18000BE43
0x18000bda0  lea     r9, [rdi+30h]
0x18000bda4  mov     r8, rsi
0x18000bda7  lea     rdx, [rbp+57h+var_70]
0x18000bdab  lea     rcx, [rdi+30h]
0x18000bdaf  call    ?GetBestMatchFeaturesForTypes@?$BaseLanguageFeaturesRegistrar@VCbsLanguageFeature@@@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@3@@Z; BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::GetBestMatchFeaturesForTypes(std::wstring const &,std::vector<PayloadType> const &)
0x18000bdb4  or      r15d, 3
0x18000bdb8  mov     [rbp+57h+var_B0], r15d
0x18000bdbc  lea     r8, [rbp+57h+var_70]
0x18000bdc0  mov     rdx, rsi
0x18000bdc3  mov     rcx, rdi
0x18000bdc6  call    ?RemoveNotApplicableFeatures@RequiredLanguageFeaturesInstaller@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(std::wstring const &,std::vector<CbsLanguageFeature> &)
0x18000bdcb  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x18000bdcf  mov     r14, qword ptr [rbp+57h+var_70]
0x18000bdd3  cmp     r14, rbx
0x18000bdd6  jz      short loc_18000BE1C
0x18000bdd8  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000bddc  cmp     rax, [rbp+57h+var_88]
0x18000bde0  jz      short loc_18000BDFD
0x18000bde2  mov     rdx, r14
0x18000bde5  mov     rcx, rax
0x18000bde8  call    ??0CbsLanguageFeature@@QEAA@$$QEAV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature &&)
0x18000bded  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000bdf1  add     rax, 0C0h
0x18000bdf7  mov     qword ptr [rbp+57h+var_98+8], rax
0x18000bdfb  jmp     short loc_18000BE10
0x18000bdfd  mov     r8, r14
0x18000be00  mov     rdx, rax
0x18000be03  lea     rcx, [rbp+57h+var_98]
0x18000be07  call    ??$_Emplace_reallocate@VCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@$$QEAV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature>(CbsLanguageFeature * const,CbsLanguageFeature &&)
0x18000be0c  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000be10  add     r14, 0C0h
0x18000be17  cmp     r14, rbx
0x18000be1a  jnz     short loc_18000BDDC
0x18000be1c  and     r15d, 0FFFFFFFEh
0x18000be20  mov     [rbp+57h+var_B0], r15d
0x18000be24  lea     rcx, [rbp+57h+var_70]
0x18000be28  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18000be2d  add     rsi, 20h ; ' '
0x18000be31  cmp     rsi, r13
0x18000be34  jnz     loc_18000BDA0
0x18000be3a  mov     r12d, 1
0x18000be40  xor     r14d, r14d
0x18000be43  mov     rsi, [rdi+18h]
0x18000be47  mov     r15, [rdi+20h]
0x18000be4b  jmp     loc_18000BF1E
0x18000be50  mov     [rbp+57h+var_B0], r12d
0x18000be54  xorps   xmm0, xmm0
0x18000be57  movdqu  [rbp+57h+var_70], xmm0
0x18000be5c  mov     [rbp+57h+var_60], r14
0x18000be60  mov     ecx, 4; Size
0x18000be65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000be6a  mov     qword ptr [rbp+57h+var_70], rax
0x18000be6e  lea     rdx, [rax+4]
0x18000be72  mov     [rbp+57h+var_60], rdx
0x18000be76  mov     ecx, [rbp+57h+var_B0]
0x18000be79  mov     [rax], ecx
0x18000be7b  mov     qword ptr [rbp+57h+var_70+8], rdx
0x18000be7f  mov     [rbp+57h+var_80], r14
0x18000be83  lea     rcx, [rbp+57h+var_80]
0x18000be87  call    ??1?$_Tidy_guard@V?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<PayloadType>>::~_Tidy_guard<std::vector<PayloadType>>(void)
0x18000be8c  nop
0x18000be8d  lea     r9, [rbp+57h+var_70]
0x18000be91  mov     r8, rsi
0x18000be94  lea     rdx, [rbp+57h+var_50]
0x18000be98  lea     rcx, [rdi+30h]
0x18000be9c  call    ?GetBestMatchFeaturesForTypes@?$BaseLanguageFeaturesRegistrar@VCbsLanguageFeature@@@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@3@@Z; BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::GetBestMatchFeaturesForTypes(std::wstring const &,std::vector<PayloadType> const &)
0x18000bea1  nop
0x18000bea2  lea     rcx, [rbp+57h+var_70]
0x18000bea6  call    ??1?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@QEAA@XZ; std::vector<PayloadType>::~vector<PayloadType>(void)
0x18000beab  lea     r8, [rbp+57h+var_50]
0x18000beaf  mov     rdx, rsi
0x18000beb2  mov     rcx, rdi
0x18000beb5  call    ?RemoveNotApplicableFeatures@RequiredLanguageFeaturesInstaller@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(std::wstring const &,std::vector<CbsLanguageFeature> &)
0x18000beba  mov     rbx, [rbp+57h+var_48]
0x18000bebe  mov     r14, [rbp+57h+var_50]
0x18000bec2  cmp     r14, rbx
0x18000bec5  jz      short loc_18000BF0B
0x18000bec7  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000becb  cmp     rax, [rbp+57h+var_88]
0x18000becf  jz      short loc_18000BEEC
0x18000bed1  mov     rdx, r14
0x18000bed4  mov     rcx, rax
0x18000bed7  call    ??0CbsLanguageFeature@@QEAA@$$QEAV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature &&)
0x18000bedc  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000bee0  add     rax, 0C0h
0x18000bee6  mov     qword ptr [rbp+57h+var_98+8], rax
0x18000beea  jmp     short loc_18000BEFF
0x18000beec  mov     r8, r14
0x18000beef  mov     rdx, rax
0x18000bef2  lea     rcx, [rbp+57h+var_98]
0x18000bef6  call    ??$_Emplace_reallocate@VCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@$$QEAV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature>(CbsLanguageFeature * const,CbsLanguageFeature &&)
0x18000befb  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000beff  add     r14, 0C0h
0x18000bf06  cmp     r14, rbx
0x18000bf09  jnz     short loc_18000BECB
0x18000bf0b  lea     rcx, [rbp+57h+var_50]
0x18000bf0f  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18000bf14  add     rsi, 20h ; ' '
0x18000bf18  mov     r14d, 0
0x18000bf1e  cmp     rsi, r15
0x18000bf21  jnz     loc_18000BE50
0x18000bf27  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000bf2b  cmp     qword ptr [rbp+57h+var_98], rax
0x18000bf2f  jz      short loc_18000BF47
0x18000bf31  lea     rcx, [rbp+57h+var_98]
0x18000bf35  call    ??$NormalizeContainer@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@@YAXAEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; NormalizeContainer<std::vector<CbsLanguageFeature>>(std::vector<CbsLanguageFeature> &)
0x18000bf3a  lea     rcx, [rbp+57h+var_98]
0x18000bf3e  mov     rax, [rbp+57h+var_A8]
0x18000bf42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf47  xor     r14d, r14d
0x18000bf4a  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18000bf4e  cmp     qword ptr [rbp+57h+var_98], rax
0x18000bf52  jnz     short loc_18000BFC7
0x18000bf54  mov     r8b, r14b
0x18000bf57  mov     rax, [rdi+48h]
0x18000bf5b  mov     rax, [rax]
0x18000bf5e  cmp     [rax+19h], r14b
0x18000bf62  jnz     short loc_18000BFBF
0x18000bf64  mov     rcx, [rax+28h]
0x18000bf68  jmp     short loc_18000BF74
0x18000bf6a  or      r8b, r12b
0x18000bf6d  add     rcx, 0C0h
0x18000bf74  cmp     rcx, [rax+30h]
0x18000bf78  jnz     short loc_18000BF6A
0x18000bf7a  mov     rdx, [rax+10h]
0x18000bf7e  cmp     [rdx+19h], r14b
0x18000bf82  jz      short loc_18000BFA2
0x18000bf84  mov     rcx, [rax+8]
0x18000bf88  jmp     short loc_18000BF97
0x18000bf8a  cmp     rax, [rcx+10h]
0x18000bf8e  jnz     short loc_18000BF9D
0x18000bf90  mov     rax, rcx
0x18000bf93  mov     rcx, [rcx+8]
0x18000bf97  cmp     [rcx+19h], r14b
0x18000bf9b  jz      short loc_18000BF8A
0x18000bf9d  mov     rax, rcx
0x18000bfa0  jmp     short loc_18000BF5E
0x18000bfa2  mov     rax, rdx
0x18000bfa5  mov     rdx, [rdx]
0x18000bfa8  cmp     [rdx+19h], r14b
0x18000bfac  jnz     short loc_18000BF5E
0x18000bfae  mov     rax, rdx
0x18000bfb1  mov     rcx, [rdx]
0x18000bfb4  mov     rdx, rcx
0x18000bfb7  cmp     [rcx+19h], r14b
0x18000bfbb  jz      short loc_18000BFAE
0x18000bfbd  jmp     short loc_18000BF5E
0x18000bfbf  test    r8b, r8b
0x18000bfc2  jz      short loc_18000BFC7
0x18000bfc4  mov     r12d, r14d
0x18000bfc7  lea     rcx, [rbp+57h+var_98]
0x18000bfcb  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18000bfd0  mov     eax, r12d
0x18000bfd3  mov     rcx, [rbp+57h+var_38]
0x18000bfd7  xor     rcx, rsp; StackCookie
0x18000bfda  call    __security_check_cookie
0x18000bfdf  mov     rbx, [rsp+0D0h+arg_10]
0x18000bfe7  add     rsp, 0A0h
0x18000bfee  pop     r15
0x18000bff0  pop     r14
0x18000bff2  pop     r13
0x18000bff4  pop     r12
0x18000bff6  pop     rdi
0x18000bff7  pop     rsi
0x18000bff8  pop     rbp
0x18000bff9  retn
```
