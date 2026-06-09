# AppxAllUserStore::AddPackageToDynamicPackageArray(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,bool,bool,bool,ushort const *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)

- ea: `0x18000bf10`
- end: `0x18000c58e`
- name: `?AddPackageToDynamicPackageArray@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@_N3311PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z`
- size: `1662`
- prototype: `__int64 __fastcall(int, Common::Deployment *, struct Common::StringBuffer *, int *, char, char, int, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000af10`
- `0x18000bba0`
- `0x180038a80`
- `0x18003a4b8`

## callees

- `0x180001f94`
- `0x180004920`
- `0x180007354`
- `0x180008db0`
- `0x180009438`
- `0x180009d80`
- `0x18000bf10`
- `0x18000d710`
- `0x18000d770`
- `0x180010384`
- `0x180010de4`
- `0x180014a38`
- `0x180015430`
- `0x180017f50`
- `0x180018248`
- `0x18001a604`
- `0x18001b3f0`
- `0x18001bb7c`
- `0x180033768`
- `0x1800384e8`
- `0x180039f80`
- `0x18003ebe8`
- `0x18004002c`
- `0x180040304`
- `0x18004be74`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c0dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c0dd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000c2b5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000c2b5`

## string_xrefs

- `0x18000c04e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`
- `0x18000c05a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`
- `0x18000c119`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::AddPackageToDynamicPackageArray(
        int a1,
        Common::Deployment *a2,
        struct Common::StringBuffer *a3,
        int *a4,
        char a5,
        char a6,
        int a7,
        __int64 a8,
        _QWORD *a9)
{
  int SetupPhase; // ebx
  char v10; // r12
  int VersionlessNameFromPackageFullName; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  LSTATUS ValueW; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // r14d
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // eax
  bool *v31; // r8
  __int64 v32; // rdx
  struct AppxAllUserStore::_MainPackageInfo *v33; // rdx
  __int64 v34; // rcx
  unsigned int v35; // r15d
  HKEY v36; // rbx
  int v37; // eax
  __int64 v38; // rcx
  struct AppxAllUserStore::_MainPackageInfo *v39; // rdx
  struct AppxAllUserStore::_MainPackageInfo *v40; // rdx
  AppxAllUserStore *v41; // rdi
  __int64 v42; // rdx
  struct AppxAllUserStore::_MainPackageInfo *v43; // rdx
  struct AppxAllUserStore::_MainPackageInfo *v44; // rdx
  AppxAllUserStore *v45; // rcx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  bool v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  AppxAllUserStore *v50; // [rsp+58h] [rbp-A8h]
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v52[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v53[8]; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+80h] [rbp-80h]
  DWORD pcbData[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v59[72]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Dst[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  SetupPhase = 0;
  v10 = (char)a4;
  v58 = a8;
  if ( (_BYTE)a4 )
  {
    v54 = 0;
    *(_OWORD *)v53 = 0;
    VersionlessNameFromPackageFullName = Common::Deployment::GetVersionlessNameFromPackageFullName(a2, v53, a3);
    if ( VersionlessNameFromPackageFullName < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AC,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)VersionlessNameFromPackageFullName);
      if ( (byte_180064BC1 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(v15, AppxAllUserStoreInvalidEndOfLifePackage, a2);
      goto LABEL_16;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56375041>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56375041>::GetImpl'::`2'::impl) )
    {
      memset_0(v59, 0, 0x82u);
      pvData = 65;
      v16 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFamilyNameFromFullName((LPCWCH)a2);
      if ( v16 )
      {
        SetupPhase = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x2BB,
                       (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                       (const char *)v16,
                       pdwType);
LABEL_16:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
        return (unsigned int)SetupPhase;
      }
      if ( Common::String::CaseInsensitiveEquals(v59, L"MicrosoftWindows.Client.AIX_cw5n1h2txyewy") )
      {
        hkey = 0;
        v18 = wil::reg::open_unique_key_nothrow(
                v17,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
                &hkey);
        LOBYTE(pdwType) = v18 + 2147024894 > 1;
        wil::details::in1diag3::Log_HrIfMsg(
          retaddr,
          (void *)0x2C6,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)v18,
          pdwType,
          (bool)"Key:%ls",
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration");
        if ( hkey )
        {
          pvData = 0;
          pcbData[0] = 4;
          ValueW = RegGetValueW(hkey, 0, L"Selection", 0x10u, 0, &pvData, pcbData);
          v20 = (unsigned int)ValueW;
          if ( ValueW > 0 )
            v20 = (unsigned __int16)ValueW | 0x80070000;
          LOBYTE(pdwTypea) = (unsigned int)(v20 + 2147024894) > 1;
          wil::details::in1diag3::Log_HrIfMsg(
            retaddr,
            (void *)0x2CB,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)v20,
            pdwTypea,
            (bool)"Key:%ls, valuename:%ls",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
            L"Selection");
          if ( pvData )
          {
            if ( (byte_180064BC1 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(v21, AppxAllUserStoreInvalidEndOfLifePackage, a2);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            goto LABEL_16;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      }
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
  }
  *(_DWORD *)v52 = 0;
  pvData = 0;
  SetupPhase = AppxAllUserStore::GetSetupPhase(a2, v52, (enum AppxAllUserStore::SetupPhase *)&pvData, a4);
  if ( SetupPhase < 0 )
  {
    v25 = 730;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)SetupPhase,
      pdwType);
    return (unsigned int)SetupPhase;
  }
  if ( (*(_DWORD *)v52 & a1) != 0 )
  {
    v26 = 0;
    if ( !v10 )
    {
      v48[0] = 0;
      SetupPhase = Common::Deployment::EndOfLifeSet::IsPackageEndOfLife((const unsigned __int16 *)a2, v48);
      if ( SetupPhase < 0 )
      {
        v25 = 744;
        goto LABEL_22;
      }
      if ( v48[0] )
      {
        v27 = AppxAllUserStoreTelemetry::Provider();
        if ( *(_DWORD *)v27 > 4u )
        {
          hkey = (HKEY)0x1000000;
          *(_QWORD *)pcbData = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            (__int64)v27,
            (__int64)word_18005D272,
            v28,
            v29,
            (const unsigned __int16 **)pcbData,
            (__int64)&hkey);
        }
        return 0;
      }
    }
    LOBYTE(v24) = a5;
    LOBYTE(v23) = v10;
    v50 = 0;
    v30 = AppxAllUserStore::BuildMainPackageForPackageFullName(a2, a3, v23, v24);
    SetupPhase = v30;
    if ( v30 < 0 )
    {
      v32 = 767;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v30,
        a7);
LABEL_53:
      AppxAllUserStore::MainPackageInfoCleanup(v50, v33);
      return (unsigned int)SetupPhase;
    }
    if ( !v10 && ExpandEnvironmentStringsW(*((LPCWSTR *)v50 + 1), Dst, 0x104u) )
    {
      v48[0] = 0;
      v30 = Common::FileExists((Common *)Dst, (const unsigned __int16 *)v48, v31);
      SetupPhase = v30;
      if ( v30 < 0 )
      {
        v32 = 774;
        goto LABEL_52;
      }
      if ( !v48[0] )
      {
        if ( (byte_180064BC1 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(v34, AppxAllUserStorePackagePathMissing, a2);
LABEL_39:
        SetupPhase = v26;
        goto LABEL_53;
      }
    }
    if ( a6 )
    {
      v35 = 0;
      if ( *((_DWORD *)v50 + 8) )
      {
        while ( 1 )
        {
          hkey = 0;
          Common::GlobalHeap::Alloc(0x60u, (void **)&hkey);
          v36 = hkey;
          if ( !hkey )
            break;
          memset_0(hkey, 0, 0x60u);
          v56 = 0;
          v57 = 0;
          v37 = Common::StringBuffer::SetValueFromString(
                  (Common::StringBuffer *)&v56,
                  **(const unsigned __int16 ***)(*((_QWORD *)v50 + 3) + 8LL * v35));
          v26 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x317,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
              (const char *)(unsigned int)v37,
              a7);
            goto LABEL_58;
          }
          *(_QWORD *)v36 = *((_QWORD *)&v56 + 1);
          *((_QWORD *)&v56 + 1) = 0;
          LODWORD(v56) = 0;
          v57 = 0;
          v54 = 0;
          v38 = *((_QWORD *)v50 + 3);
          *(_OWORD *)v53 = 0;
          v26 = Common::StringBuffer::SetValueFromString(
                  (Common::StringBuffer *)v53,
                  *(const unsigned __int16 **)(*(_QWORD *)(v38 + 8LL * v35) + 8LL));
          if ( v26 < 0 )
          {
            v42 = 795;
LABEL_56:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v42,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
              (const char *)(unsigned int)v26,
              a7);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
LABEL_58:
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v56);
            AppxAllUserStore::MainPackageInfoCleanup((AppxAllUserStore *)v36, v43);
            goto LABEL_39;
          }
          *((_QWORD *)v36 + 1) = *(_QWORD *)&v53[4];
          *((_DWORD *)v36 + 8) = 0;
          *(_QWORD *)&v53[4] = 0;
          *(_DWORD *)v53 = 0;
          v54 = 0;
          if ( !(unsigned __int8)AppxAllUserStore::PackageExistsInPackageArray(
                                   a9,
                                   **(_QWORD **)(*((_QWORD *)v50 + 3) + 8LL * v35),
                                   0) )
          {
            v26 = Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>>::Add(
                    a9,
                    0,
                    (__int64)v36);
            if ( v26 < 0 )
            {
              v42 = 804;
              goto LABEL_56;
            }
            v36 = 0;
          }
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v53);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v56);
          AppxAllUserStore::MainPackageInfoCleanup((AppxAllUserStore *)v36, v39);
          if ( ++v35 >= *((_DWORD *)v50 + 8) )
            goto LABEL_49;
        }
        SetupPhase = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x314,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)0x8007000ELL,
          a7);
        AppxAllUserStore::MainPackageInfoCleanup(0, v44);
        goto LABEL_53;
      }
    }
LABEL_49:
    LOBYTE(v31) = v10;
    if ( (unsigned __int8)AppxAllUserStore::PackageExistsInPackageArray(a9, a2, v31) )
    {
      v45 = v50;
    }
    else
    {
      v41 = v50;
      v30 = Common::Array<AppxAllUserStore::_PackageInfo,Common::ContainerOperations<AppxAllUserStore::_PackageInfo,AppxAllUserStore::_PackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_PackageInfo>,Common::ArrayOperations<AppxAllUserStore::_PackageInfo,Common::NoKey>>::EnsureCapacity(
              a9,
              a9[2] + 1LL);
      SetupPhase = v30;
      if ( v30 < 0 )
      {
        v32 = 815;
        goto LABEL_52;
      }
      *(_QWORD *)(*a9 + 8LL * a9[2]) = v41;
      v45 = 0;
      ++a9[2];
      v50 = 0;
    }
    AppxAllUserStore::MainPackageInfoCleanup(v45, v40);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bf10  mov     [rsp-8+arg_0], rbx
0x18000bf15  push    rbp
0x18000bf16  push    rsi
0x18000bf17  push    rdi
0x18000bf18  push    r12
0x18000bf1a  push    r13
0x18000bf1c  push    r14
0x18000bf1e  push    r15
0x18000bf20  lea     rbp, [rsp-260h]
0x18000bf28  sub     rsp, 360h
0x18000bf2f  mov     rax, cs:__security_cookie
0x18000bf36  xor     rax, rsp
0x18000bf39  mov     [rbp+290h+var_40], rax
0x18000bf40  mov     rax, [rbp+290h+arg_38]
0x18000bf47  xor     ebx, ebx
0x18000bf49  mov     r13, qword ptr [rbp+290h+arg_30]
0x18000bf50  mov     r12b, r9b
0x18000bf53  mov     rsi, [rbp+290h+arg_40]
0x18000bf5a  mov     r15, r8
0x18000bf5d  mov     [rbp+290h+var_2E8], rax
0x18000bf61  mov     rdi, rdx
0x18000bf64  mov     r14d, ecx
0x18000bf67  test    r9b, r9b
0x18000bf6a  jz      loc_18000C18F
0x18000bf70  xorps   xmm0, xmm0
0x18000bf73  mov     [rbp+290h+var_310], ebx
0x18000bf76  lea     rdx, [rsp+390h+var_320]; unsigned __int16 *
0x18000bf7b  mov     rcx, rdi; this
0x18000bf7e  movups  xmmword ptr [rsp+390h+var_320], xmm0
0x18000bf83  call    ?GetVersionlessNameFromPackageFullName@Deployment@Common@@YAJPEBGPEAVStringBuffer@2@@Z; Common::Deployment::GetVersionlessNameFromPackageFullName(ushort const *,Common::StringBuffer *)
0x18000bf88  test    eax, eax
0x18000bf8a  jns     short loc_18000BFC8
0x18000bf8c  mov     rcx, [rbp+298h]; this
0x18000bf93  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000bf9a  mov     r9d, eax; char *
0x18000bf9d  mov     edx, 2ACh; void *
0x18000bfa2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bfa7  test    cs:byte_180064BC1, 8
0x18000bfae  jz      loc_18000C16A
0x18000bfb4  mov     r8, rdi
0x18000bfb7  lea     rdx, AppxAllUserStoreInvalidEndOfLifePackage
0x18000bfbe  call    McTemplateU0z_EventWriteTransfer
0x18000bfc3  jmp     loc_18000C16A
0x18000bfc8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56375041@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56375041@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56375041> `wil::Feature<__WilFeatureTraits_Feature_56375041>::GetImpl(void)'::`2'::impl
0x18000bfcf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56375041@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56375041>::__private_IsEnabled(void)
0x18000bfd4  test    al, al
0x18000bfd6  jz      loc_18000C185
0x18000bfdc  xor     edx, edx; Val
0x18000bfde  lea     rcx, [rbp+290h+var_2E0]; void *
0x18000bfe2  mov     r8d, 82h; Size
0x18000bfe8  call    memset_0
0x18000bfed  lea     r8, [rbp+290h+var_2E0]
0x18000bff1  mov     [rsp+390h+var_33C], 41h ; 'A'
0x18000bff9  lea     rdx, [rsp+390h+var_33C]
0x18000bffe  mov     rcx, rdi; lpString1
0x18000c001  call    ?PackageFamilyNameFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGPEAIPEAG@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFamilyNameFromFullName(ushort const *,uint *,ushort *)
0x18000c006  test    eax, eax
0x18000c008  jz      short loc_18000C02C
0x18000c00a  mov     rcx, [rbp+298h]; this
0x18000c011  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c018  mov     r9d, eax; char *
0x18000c01b  mov     edx, 2BBh; void *
0x18000c020  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c025  mov     ebx, eax
0x18000c027  jmp     loc_18000C16A
0x18000c02c  lea     rdx, aMicrosoftwindo_0; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x18000c033  lea     rcx, [rbp+290h+var_2E0]; unsigned __int16 *
0x18000c037  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18000c03c  test    eax, eax
0x18000c03e  jz      loc_18000C185
0x18000c044  lea     r8, [rsp+390h+hkey]
0x18000c049  mov     [rsp+390h+hkey], rbx
0x18000c04e  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c055  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18000c05a  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c061  mov     r9d, eax; char *
0x18000c064  mov     [rsp+390h+pcbData], r8; char *
0x18000c069  lea     r8, aKeyLs; "Key:%ls"
0x18000c070  mov     [rsp+390h+pvData], r8; bool
0x18000c075  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c07c  lea     ecx, [rax+7FF8FFFEh]
0x18000c082  cmp     ecx, 1
0x18000c085  mov     rcx, [rbp+298h]; this
0x18000c08c  setnbe  dl
0x18000c08f  mov     byte ptr [rsp+390h+pdwType], dl; int
0x18000c093  mov     edx, 2C6h; void *
0x18000c098  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000c09d  mov     rcx, [rsp+390h+hkey]; hkey
0x18000c0a2  test    rcx, rcx
0x18000c0a5  jz      loc_18000C17B
0x18000c0ab  lea     rax, [rbp+290h+var_308]
0x18000c0af  mov     [rsp+390h+var_33C], ebx
0x18000c0b3  mov     [rsp+390h+pcbData], rax; pcbData
0x18000c0b8  lea     r8, Value; "Selection"
0x18000c0bf  lea     rax, [rsp+390h+var_33C]
0x18000c0c4  mov     [rbp+290h+var_308], 4
0x18000c0cb  mov     [rsp+390h+pvData], rax; pvData
0x18000c0d0  mov     r9d, 10h; dwFlags
0x18000c0d6  xor     edx, edx; lpSubKey
0x18000c0d8  mov     [rsp+390h+pdwType], rbx; pdwType
0x18000c0dd  call    cs:__imp_RegGetValueW
0x18000c0e3  mov     r9d, eax
0x18000c0e6  test    eax, eax
0x18000c0e8  jle     short loc_18000C0F5
0x18000c0ea  movzx   r9d, ax
0x18000c0ee  or      r9d, 80070000h; char *
0x18000c0f5  mov     rcx, [rbp+298h]; this
0x18000c0fc  lea     eax, [r9+7FF8FFFEh]
0x18000c103  lea     rdx, Value; "Selection"
0x18000c10a  cmp     eax, 1
0x18000c10d  mov     [rsp+390h+var_358], rdx
0x18000c112  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c119  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000c120  setnbe  al
0x18000c123  mov     [rsp+390h+pcbData], rdx; char *
0x18000c128  lea     rdx, aKeyLsValuename; "Key:%ls, valuename:%ls"
0x18000c12f  mov     [rsp+390h+pvData], rdx; bool
0x18000c134  mov     edx, 2CBh; void *
0x18000c139  mov     byte ptr [rsp+390h+pdwType], al; int
0x18000c13d  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000c142  cmp     [rsp+390h+var_33C], ebx
0x18000c146  jz      short loc_18000C17B
0x18000c148  test    cs:byte_180064BC1, 8
0x18000c14f  jz      short loc_18000C160
0x18000c151  mov     r8, rdi
0x18000c154  lea     rdx, AppxAllUserStoreInvalidEndOfLifePackage
0x18000c15b  call    McTemplateU0z_EventWriteTransfer
0x18000c160  lea     rcx, [rsp+390h+hkey]
0x18000c165  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c16a  lea     rcx, [rsp+390h+var_320]; this
0x18000c16f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000c174  mov     eax, ebx
0x18000c176  jmp     loc_18000C564
0x18000c17b  lea     rcx, [rsp+390h+hkey]
0x18000c180  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000c185  lea     rcx, [rsp+390h+var_320]; this
0x18000c18a  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000c18f  lea     r8, [rsp+390h+var_33C]; enum AppxAllUserStore::SetupPhase *
0x18000c194  mov     dword ptr [rsp+390h+var_328], ebx
0x18000c198  lea     rdx, [rsp+390h+var_328]; unsigned __int16 *
0x18000c19d  mov     [rsp+390h+var_33C], ebx
0x18000c1a1  mov     rcx, rdi; this
0x18000c1a4  call    ?GetSetupPhase@AppxAllUserStore@@YAJPEBGPEAW4SetupPhase@1@PEAH@Z; AppxAllUserStore::GetSetupPhase(ushort const *,AppxAllUserStore::SetupPhase *,int *)
0x18000c1a9  mov     ebx, eax
0x18000c1ab  test    eax, eax
0x18000c1ad  jns     short loc_18000C1CC
0x18000c1af  mov     edx, 2DAh; void *
0x18000c1b4  mov     rcx, [rbp+298h]; this
0x18000c1bb  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000c1c2  mov     r9d, ebx; char *
0x18000c1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1ca  jmp     short loc_18000C174
0x18000c1cc  mov     ecx, dword ptr [rsp+390h+var_328]
0x18000c1d0  test    r14d, ecx
0x18000c1d3  jz      loc_18000C562
0x18000c1d9  xor     r14d, r14d
0x18000c1dc  test    r12b, r12b
0x18000c1df  jnz     short loc_18000C24F
0x18000c1e1  lea     rdx, [rsp+390h+var_340]; bool *
0x18000c1e6  mov     [rsp+390h+var_340], r14b
0x18000c1eb  mov     rcx, rdi; unsigned __int16 *
0x18000c1ee  call    ?IsPackageEndOfLife@EndOfLifeSet@Deployment@Common@@SAJPEBGAEA_N@Z; Common::Deployment::EndOfLifeSet::IsPackageEndOfLife(ushort const *,bool &)
0x18000c1f3  mov     ebx, eax
0x18000c1f5  test    eax, eax
0x18000c1f7  jns     short loc_18000C200
0x18000c1f9  mov     edx, 2E8h
0x18000c1fe  jmp     short loc_18000C1B4
0x18000c200  cmp     [rsp+390h+var_340], r14b
0x18000c205  jz      short loc_18000C24B
0x18000c207  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x18000c20c  mov     ecx, [rax]
0x18000c20e  cmp     ecx, 4
0x18000c211  jbe     loc_18000C562
0x18000c217  lea     rcx, [rsp+390h+hkey]
0x18000c21c  mov     [rsp+390h+hkey], 1000000h
0x18000c225  mov     [rsp+390h+pvData], rcx
0x18000c22a  lea     rdx, word_18005D272
0x18000c231  lea     rcx, [rbp+290h+var_308]
0x18000c235  mov     qword ptr [rbp+290h+var_308], rdi
0x18000c239  mov     [rsp+390h+pdwType], rcx
0x18000c23e  mov     rcx, rax
0x18000c241  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18000c246  jmp     loc_18000C562
0x18000c24b  mov     ecx, dword ptr [rsp+390h+var_328]
0x18000c24f  mov     r9b, [rbp+290h+arg_20]
0x18000c256  lea     rax, [rsp+390h+var_338]
0x18000c25b  mov     [rsp+390h+var_350], rax
0x18000c260  mov     r8b, r12b
0x18000c263  mov     eax, [rsp+390h+var_33C]
0x18000c267  mov     rdx, r15
0x18000c26a  mov     dword ptr [rsp+390h+var_358], eax
0x18000c26e  mov     rax, [rbp+290h+var_2E8]
0x18000c272  mov     dword ptr [rsp+390h+pcbData], ecx
0x18000c276  mov     rcx, rdi
0x18000c279  mov     [rsp+390h+pvData], rax
0x18000c27e  mov     [rsp+390h+pdwType], r13; int
0x18000c283  mov     [rsp+390h+var_338], r14
0x18000c288  call    ?BuildMainPackageForPackageFullName@AppxAllUserStore@@YAJPEBGPEAVRegistryKey@Common@@_N200W4SetupPhase@1@HPEAPEAU_MainPackageInfo@1@@Z; AppxAllUserStore::BuildMainPackageForPackageFullName(ushort const *,Common::RegistryKey *,bool,bool,ushort const *,ushort const *,AppxAllUserStore::SetupPhase,int,AppxAllUserStore::_MainPackageInfo * *)
0x18000c28d  mov     ebx, eax
0x18000c28f  test    eax, eax
0x18000c291  jns     short loc_18000C29D
0x18000c293  mov     edx, 2FFh
0x18000c298  jmp     loc_18000C48F
0x18000c29d  test    r12b, r12b
0x18000c2a0  jnz     short loc_18000C309
0x18000c2a2  mov     rcx, [rsp+390h+var_338]
0x18000c2a7  lea     rdx, [rbp+290h+Dst]; lpDst
0x18000c2ab  mov     r8d, 104h; nSize
0x18000c2b1  mov     rcx, [rcx+8]; lpSrc
0x18000c2b5  call    cs:__imp_ExpandEnvironmentStringsW
0x18000c2bb  test    eax, eax
0x18000c2bd  jz      short loc_18000C309
0x18000c2bf  lea     rdx, [rsp+390h+var_340]; unsigned __int16 *
0x18000c2c4  mov     [rsp+390h+var_340], r14b
0x18000c2c9  lea     rcx, [rbp+290h+Dst]; this
0x18000c2cd  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18000c2d2  mov     ebx, eax
0x18000c2d4  test    eax, eax
0x18000c2d6  jns     short loc_18000C2E2
0x18000c2d8  mov     edx, 306h
0x18000c2dd  jmp     loc_18000C48F
0x18000c2e2  cmp     [rsp+390h+var_340], r14b
0x18000c2e7  jnz     short loc_18000C309
0x18000c2e9  test    cs:byte_180064BC1, 8
0x18000c2f0  jz      short loc_18000C301
0x18000c2f2  mov     r8, rdi
0x18000c2f5  lea     rdx, AppxAllUserStorePackagePathMissing
0x18000c2fc  call    McTemplateU0z_EventWriteTransfer
0x18000c301  mov     ebx, r14d
0x18000c304  jmp     loc_18000C4A5
0x18000c309  cmp     [rbp+290h+arg_28], r14b
0x18000c310  jz      loc_18000C456
0x18000c316  mov     rax, [rsp+390h+var_338]
0x18000c31b  mov     r15d, r14d
0x18000c31e  cmp     [rax+20h], r14d
0x18000c322  jbe     loc_18000C456
0x18000c328  lea     rdx, [rsp+390h+hkey]; void **
0x18000c32d  mov     [rsp+390h+hkey], r14
0x18000c332  mov     ecx, 60h ; '`'; Size
0x18000c337  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18000c33c  mov     rbx, [rsp+390h+hkey]
0x18000c341  test    rbx, rbx
0x18000c344  jz      loc_18000C513
0x18000c34a  xor     edx, edx; Val
0x18000c34c  mov     rcx, rbx; void *
0x18000c34f  lea     r8d, [rdx+60h]; Size
0x18000c353  call    memset_0
0x18000c358  mov     rax, [rsp+390h+var_338]
0x18000c35d  xorps   xmm0, xmm0
0x18000c360  mov     r13d, r15d
0x18000c363  movups  [rbp+290h+var_300], xmm0
0x18000c367  mov     [rbp+290h+var_2F0], r14d
0x18000c36b  mov     rcx, [rax+18h]
0x18000c36f  mov     rdx, [rcx+r13*8]
0x18000c373  lea     rcx, [rbp+290h+var_300]; this
0x18000c377  mov     rdx, [rdx]; Src
0x18000c37a  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18000c37f  xor     ecx, ecx
0x18000c381  mov     r14d, eax
0x18000c384  test    eax, eax
0x18000c386  js      loc_18000C4E2
0x18000c38c  mov     rax, qword ptr [rbp+290h+var_300+8]
0x18000c390  xorps   xmm0, xmm0
0x18000c393  mov     [rbx], rax
0x18000c396  mov     rax, [rsp+390h+var_338]
0x18000c39b  mov     qword ptr [rbp+290h+var_300+8], rcx
0x18000c39f  mov     dword ptr [rbp+290h+var_300], ecx
0x18000c3a2  mov     [rbp+290h+var_2F0], ecx
0x18000c3a5  mov     [rbp+290h+var_310], ecx
0x18000c3a8  mov     rcx, [rax+18h]
0x18000c3ac  movups  xmmword ptr [rsp+390h+var_320], xmm0
0x18000c3b1  mov     rdx, [rcx+r13*8]
0x18000c3b5  lea     rcx, [rsp+390h+var_320]; this
0x18000c3ba  mov     rdx, [rdx+8]; Src
0x18000c3be  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18000c3c3  mov     r14d, eax
0x18000c3c6  test    eax, eax
0x18000c3c8  js      loc_18000C4BB
0x18000c3ce  mov     rax, qword ptr [rsp+390h+var_320+8]
0x18000c3d3  xor     r14d, r14d
0x18000c3d6  mov     [rbx+8], rax
0x18000c3da  xor     r8d, r8d
0x18000c3dd  mov     [rbx+20h], r14d
0x18000c3e1  mov     rax, [rsp+390h+var_338]
0x18000c3e6  mov     qword ptr [rsp+390h+var_320+8], r14
0x18000c3eb  mov     dword ptr [rsp+390h+var_320], r14d
0x18000c3f0  mov     [rbp+290h+var_310], r14d
0x18000c3f4  mov     rcx, [rax+18h]
0x18000c3f8  mov     rdx, [rcx+r13*8]
0x18000c3fc  mov     rcx, rsi
0x18000c3ff  mov     rdx, [rdx]
0x18000c402  call    ?PackageExistsInPackageArray@AppxAllUserStore@@YA_NPEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@PEBG_N@Z; AppxAllUserStore::PackageExistsInPackageArray(Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *,ushort const *,bool)
0x18000c407  test    al, al
0x18000c409  jnz     short loc_18000C429
0x18000c40b  mov     r8, rbx
0x18000c40e  xor     edx, edx
0x18000c410  mov     rcx, rsi
0x18000c413  call    ?Add@?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAAJ_KPEAU_MainPackageInfo@AppxAllUserStore@@@Z; Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>>::Add(unsigned __int64,AppxAllUserStore::_MainPackageInfo *)
0x18000c418  mov     r14d, eax
0x18000c41b  test    eax, eax
  ... truncated ...
```
