# OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::InstallPackage(OSIntegration::Package const *)

- ea: `0x18016237c`
- end: `0x18016298a`
- name: `?InstallPackage@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@@Z`
- size: `1550`
- prototype: `__int64 __fastcall(OSIntegration::DEH::LoopbackAccessRulesExtensionHandler *__hidden this, const struct OSIntegration::Package *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180161270`

## callees

- `0x180002eb8`
- `0x18000e6e0`
- `0x1800102b0`
- `0x180067050`
- `0x1800853cc`
- `0x180095fdc`
- `0x180098bf4`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1800f10e4`
- `0x1801617ac`
- `0x1801618fc`
- `0x1801620b0`
- `0x1801621d4`
- `0x18016237c`
- `0x180162ff0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180162620`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180162681`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801626bc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016272c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180162620`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180162681`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801626bc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016272c`
- `FirewallAPI!NetworkIsolationCreateAppContainerLoopbackRules` at `0x180162526`
- `FirewallAPI!NetworkIsolationCreateAppContainerLoopbackRules` at `0x1801627fa`
- `FirewallAPI!NetworkIsolationCreateAppContainerLoopbackRules` at `0x180162526`
- `FirewallAPI!NetworkIsolationCreateAppContainerLoopbackRules` at `0x1801627fa`

## string_xrefs

- `0x180162406`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x1801625eb`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x180162644`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x1801626f7`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016291c`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016294c`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x180162973`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016256b`: `NetworkIsolationCreateAppContainerLoopbackRules`
- `0x18016288c`: `NetworkIsolationCreateAppContainerLoopbackRules`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::InstallPackage(
        OSIntegration::DEH::LoopbackAccessRulesExtensionHandler *this,
        const struct OSIntegration::Package *a2)
{
  int MatchedLoopbackRulePackages; // eax
  signed int v5; // ebx
  unsigned __int64 v6; // r13
  unsigned int v7; // edi
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  __int64 v10; // r15
  int CentennialByPackageFamilyName; // eax
  signed int v12; // r14d
  int PackageSidByPackageFamilyName; // eax
  unsigned __int16 *v14; // r14
  void *v15; // r15
  int AppContainerLoopbackRules; // eax
  int v17; // ecx
  int v18; // r8d
  unsigned __int64 v19; // rdx
  struct _SID_AND_ATTRIBUTES *v20; // rcx
  unsigned int v21; // edi
  unsigned __int64 v22; // rdx
  struct _SID_AND_ATTRIBUTES *v23; // rcx
  unsigned int v24; // ebx
  struct _SID_AND_ATTRIBUTES *v25; // rcx
  unsigned int i; // ebx
  __int64 v27; // rdi
  unsigned __int64 v28; // r15
  __int64 v29; // r13
  unsigned int v30; // ebx
  __int64 v31; // rbx
  int v32; // eax
  int v33; // eax
  int PackageFullNameByPackageFamilyName; // eax
  const unsigned __int16 *v35; // r14
  int v36; // eax
  int v38; // ecx
  int v39; // r8d
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  unsigned int v42; // [rsp+20h] [rbp-89h]
  int v43; // [rsp+20h] [rbp-89h]
  unsigned __int16 *v44; // [rsp+40h] [rbp-69h] BYREF
  void *v45; // [rsp+48h] [rbp-61h] BYREF
  __int64 v46; // [rsp+50h] [rbp-59h] BYREF
  __int64 v47; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *v48[2]; // [rsp+60h] [rbp-49h] BYREF
  int v49; // [rsp+70h] [rbp-39h]
  __int64 v50; // [rsp+78h] [rbp-31h] BYREF
  _SID_AND_ATTRIBUTES v51; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v52[2]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v53; // [rsp+A0h] [rbp-9h]
  char v54; // [rsp+A8h] [rbp-1h]
  _QWORD v55[2]; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int64 v56; // [rsp+C0h] [rbp+17h]
  char v57; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  signed int v59; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned __int64 v60; // [rsp+120h] [rbp+77h] BYREF
  struct _SID_AND_ATTRIBUTES *v61; // [rsp+128h] [rbp+7Fh] BYREF

  v44 = (unsigned __int16 *)*((_QWORD *)a2 + 28);
  v45 = (void *)*((_QWORD *)a2 + 87);
  v55[0] = 0;
  v55[1] = 0;
  v56 = 0;
  v57 = 1;
  v52[0] = 0;
  v52[1] = 0;
  v53 = 0;
  v54 = 1;
  MatchedLoopbackRulePackages = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetMatchedLoopbackRulePackages(
                                  this,
                                  a2,
                                  v55,
                                  v52);
  v5 = MatchedLoopbackRulePackages;
  if ( MatchedLoopbackRulePackages < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x205,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
      (const char *)(unsigned int)MatchedLoopbackRulePackages,
      v42);
    goto LABEL_56;
  }
  v6 = v56;
  if ( v56 )
  {
    LODWORD(v60) = v56;
    v61 = (struct _SID_AND_ATTRIBUTES *)operator new[](saturated_mul((unsigned int)v56, 0x10u));
    memset_0(v61, 0, 16LL * (unsigned int)v60);
    v48[0] = (unsigned __int16 *)&v61;
    v48[1] = (unsigned __int16 *)&v60;
    LOBYTE(v49) = 1;
    v7 = 0;
    v8 = 0;
    v9 = (unsigned int)v60;
    if ( (_DWORD)v60 )
    {
      while ( 1 )
      {
        if ( (unsigned int)v8 < v6 )
        {
          _mm_lfence();
          v10 = *(_QWORD *)(v55[0] + 8 * v8);
        }
        else
        {
          v10 = 0;
        }
        LOBYTE(v59) = 0;
        CentennialByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(
                                          this,
                                          *(const unsigned __int16 **)(v10 + 8),
                                          (bool *)&v59);
        v12 = CentennialByPackageFamilyName;
        if ( CentennialByPackageFamilyName < 0 )
          break;
        if ( !(_BYTE)v59 )
        {
          PackageSidByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(
                                            this,
                                            (const struct Common::COMMON_STRING *)v10,
                                            &v61[v7].Sid);
          v12 = PackageSidByPackageFamilyName;
          if ( PackageSidByPackageFamilyName < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x22F,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
              (const char *)(unsigned int)PackageSidByPackageFamilyName,
              v42);
            v23 = v61;
            if ( v61 )
            {
              v24 = 0;
              v22 = (unsigned int)v60;
              if ( (_DWORD)v60 )
              {
                do
                {
                  if ( v23[v24].Sid )
                  {
                    FreeSid(v23[v24].Sid);
                    v22 = (unsigned int)v60;
                    v23 = v61;
                  }
                  ++v24;
                }
                while ( v24 < (unsigned int)v22 );
              }
            }
LABEL_46:
            operator delete(v23, v22);
            goto LABEL_47;
          }
          ++v7;
        }
        v8 = (unsigned int)(v8 + 1);
        v9 = (unsigned int)v60;
        if ( (unsigned int)v8 >= (unsigned int)v60 )
        {
          if ( !v7 )
            goto LABEL_33;
          v42 = (*((_DWORD *)a2 + 96) & 4u) >> 2;
          v14 = v44;
          v15 = v45;
          AppContainerLoopbackRules = NetworkIsolationCreateAppContainerLoopbackRules(v45, v44, v44, v44);
          v5 = AppContainerLoopbackRules;
          if ( AppContainerLoopbackRules > 0 )
            v5 = (unsigned __int16)AppContainerLoopbackRules | 0x80070000;
          if ( v5 >= 0 )
          {
            v9 = (unsigned int)v60;
            goto LABEL_33;
          }
          if ( (unsigned int)dword_1802E09C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1802E09C8, 0x400000000000LL) )
          {
            v59 = v5;
            v45 = L"NetworkIsolationCreateAppContainerLoopbackRules";
            v44 = (unsigned __int16 *)*((_QWORD *)a2 + 58);
            v46 = *((_QWORD *)a2 + 56);
            v47 = 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v17,
              (unsigned int)byte_1802B420D,
              v18,
              (unsigned int)&v47,
              (__int64)&v46,
              (__int64)&v44,
              (__int64)&v45,
              (__int64)&v59);
          }
          OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(1, v5, v15, v14, v61, v7);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
            (const char *)(unsigned int)v5,
            v43);
          v20 = v61;
          if ( v61 )
          {
            v21 = 0;
            v19 = (unsigned int)v60;
            if ( (_DWORD)v60 )
            {
              do
              {
                if ( v20[v21].Sid )
                {
                  FreeSid(v20[v21].Sid);
                  v19 = (unsigned int)v60;
                  v20 = v61;
                }
                ++v21;
              }
              while ( v21 < (unsigned int)v19 );
            }
          }
          operator delete(v20, v19);
          goto LABEL_56;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
        (const char *)(unsigned int)CentennialByPackageFamilyName,
        v42);
      v23 = v61;
      if ( v61 )
      {
        v30 = 0;
        v22 = (unsigned int)v60;
        if ( (_DWORD)v60 )
        {
          do
          {
            if ( v23[v30].Sid )
            {
              FreeSid(v23[v30].Sid);
              v22 = (unsigned int)v60;
              v23 = v61;
            }
            ++v30;
          }
          while ( v30 < (unsigned int)v22 );
        }
      }
      goto LABEL_46;
    }
LABEL_33:
    v25 = v61;
    if ( v61 )
    {
      for ( i = 0; i < (unsigned int)v9; ++i )
      {
        if ( v25[i].Sid )
        {
          FreeSid(v25[i].Sid);
          v9 = (unsigned int)v60;
          v25 = v61;
        }
      }
    }
    operator delete(v25, v9);
  }
  v27 = 0;
  v28 = v53;
  if ( v53 )
  {
    v29 = v52[0];
    while ( 1 )
    {
      v31 = *(_QWORD *)(v29 + 8 * v27);
      LOBYTE(v59) = 0;
      v32 = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(
              this,
              *(const unsigned __int16 **)(v31 + 8),
              (bool *)&v59);
      v12 = v32;
      if ( v32 < 0 )
        break;
      v44 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v44,
        0);
      v33 = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(
              this,
              (const struct Common::COMMON_STRING *)v31,
              (void **)&v44);
      v12 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x261,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
          (const char *)(unsigned int)v33,
          v42);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v44);
        goto LABEL_47;
      }
      *(_OWORD *)v48 = 0;
      v49 = 0;
      PackageFullNameByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageFullNameByPackageFamilyName(
                                             this,
                                             (const struct Common::COMMON_STRING *)v31,
                                             (struct Common::StringBuffer *)v48);
      v5 = PackageFullNameByPackageFamilyName;
      if ( PackageFullNameByPackageFamilyName < 0 )
      {
        v40 = (unsigned int)PackageFullNameByPackageFamilyName;
        v41 = 614;
LABEL_62:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
          (const char *)v40,
          v42);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v44);
        goto LABEL_56;
      }
      v51.Sid = v45;
      *(_QWORD *)&v51.Attributes = 0;
      v42 = (unsigned __int8)v59;
      v35 = v48[1];
      v36 = NetworkIsolationCreateAppContainerLoopbackRules(v44, v48[1], v48[1], v48[1]);
      v5 = v36;
      if ( v36 > 0 )
        v5 = (unsigned __int16)v36 | 0x80070000;
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_1802E09C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1802E09C8, 0x400000000000LL) )
        {
          v59 = v5;
          v47 = (__int64)L"NetworkIsolationCreateAppContainerLoopbackRules";
          v46 = *((_QWORD *)a2 + 58);
          v45 = (void *)*((_QWORD *)a2 + 56);
          v50 = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v38,
            (unsigned int)byte_1802B4299,
            v39,
            (unsigned int)&v50,
            (__int64)&v45,
            (__int64)&v46,
            (__int64)&v47,
            (__int64)&v59);
        }
        OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(1, v5, v44, v35, &v51, 1u);
        v40 = (unsigned int)v5;
        v41 = 644;
        goto LABEL_62;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v44);
      if ( ++v27 >= v28 )
        goto LABEL_55;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
      (const char *)(unsigned int)v32,
      v42);
LABEL_47:
    v5 = v12;
  }
  else
  {
LABEL_55:
    v5 = 0;
  }
LABEL_56:
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v52);
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v55);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18016237c  mov     [rsp-8+arg_0], rbx
0x180162381  push    rbp
0x180162382  push    rsi
0x180162383  push    rdi
0x180162384  push    r12
0x180162386  push    r13
0x180162388  push    r14
0x18016238a  push    r15
0x18016238c  lea     rbp, [rsp-27h]
0x180162391  sub     rsp, 0D0h
0x180162398  mov     rsi, rdx
0x18016239b  mov     r12, rcx
0x18016239e  mov     rax, [rdx+0E0h]
0x1801623a5  mov     [rbp+57h+var_C0], rax
0x1801623a9  mov     r15, [rdx+2B8h]
0x1801623b0  mov     [rbp+57h+var_B8], r15
0x1801623b4  mov     [rbp+57h+var_50], 0
0x1801623bc  mov     [rbp+57h+var_48], 0
0x1801623c4  mov     [rbp+57h+var_40], 0
0x1801623cc  mov     [rbp+57h+var_38], 1
0x1801623d0  mov     [rbp+57h+var_70], 0
0x1801623d8  mov     [rbp+57h+var_68], 0
0x1801623e0  mov     [rbp+57h+var_60], 0
0x1801623e8  mov     [rbp+57h+var_58], 1
0x1801623ec  lea     r9, [rbp+57h+var_70]
0x1801623f0  lea     r8, [rbp+57h+var_50]
0x1801623f4  call    ?GetMatchedLoopbackRulePackages@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@AEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@1@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetMatchedLoopbackRulePackages(OSIntegration::Package const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &)
0x1801623f9  mov     ebx, eax
0x1801623fb  test    eax, eax
0x1801623fd  jns     short loc_18016241C
0x1801623ff  mov     rcx, [rbp+5Fh]; this
0x180162403  mov     r9d, eax; char *
0x180162406  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016240d  mov     edx, 205h; void *
0x180162412  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180162417  jmp     loc_180162834
0x18016241c  mov     r13, [rbp+57h+var_40]
0x180162420  test    r13, r13
0x180162423  jz      loc_1801626D4
0x180162429  mov     dword ptr [rbp+57h+arg_10], r13d
0x18016242d  mov     ecx, r13d
0x180162430  mov     eax, 10h
0x180162435  mul     rcx
0x180162438  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18016243f  cmovb   rax, rcx
0x180162443  mov     rcx, rax; unsigned __int64
0x180162446  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18016244b  mov     [rbp+57h+arg_18], rax
0x18016244f  mov     r8d, dword ptr [rbp+57h+arg_10]
0x180162453  shl     r8, 4; Size
0x180162457  xor     edx, edx; Val
0x180162459  mov     rcx, rax; void *
0x18016245c  call    memset_0
0x180162461  lea     rax, [rbp+57h+arg_18]
0x180162465  mov     [rbp+57h+var_A0], rax
0x180162469  lea     rax, [rbp+57h+arg_10]
0x18016246d  mov     [rbp+57h+var_A0+8], rax
0x180162471  mov     byte ptr [rbp+57h+var_90], 1
0x180162475  xor     edi, edi
0x180162477  xor     ebx, ebx
0x180162479  mov     edx, dword ptr [rbp+57h+arg_10]
0x18016247c  test    edx, edx
0x18016247e  jz      loc_18016269C
0x180162484  mov     r15d, ebx
0x180162487  cmp     r15, r13
0x18016248a  jb      short loc_180162491
0x18016248c  xor     r15d, r15d
0x18016248f  jmp     short loc_18016249C
0x180162491  lfence
0x180162494  mov     rax, [rbp+57h+var_50]
0x180162498  mov     r15, [rax+rbx*8]
0x18016249c  mov     byte ptr [rbp+57h+arg_8], 0
0x1801624a0  lea     r8, [rbp+57h+arg_8]; bool *
0x1801624a4  mov     rdx, [r15+8]; unsigned __int16 *
0x1801624a8  mov     rcx, r12; this
0x1801624ab  call    ?GetCentennialByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBGPEA_N@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(ushort const *,bool *)
0x1801624b0  mov     r14d, eax
0x1801624b3  test    eax, eax
0x1801624b5  js      loc_1801626F0
0x1801624bb  cmp     byte ptr [rbp+57h+arg_8], 0
0x1801624bf  jnz     short loc_1801624E4
0x1801624c1  mov     r8d, edi
0x1801624c4  shl     r8, 4
0x1801624c8  add     r8, [rbp+57h+arg_18]; void **
0x1801624cc  mov     rdx, r15; struct Common::COMMON_STRING *
0x1801624cf  mov     rcx, r12; this
0x1801624d2  call    ?GetPackageSidByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(Common::COMMON_STRING const *,void * *)
0x1801624d7  mov     r14d, eax
0x1801624da  test    eax, eax
0x1801624dc  js      loc_18016263D
0x1801624e2  inc     edi
0x1801624e4  inc     ebx
0x1801624e6  mov     edx, dword ptr [rbp+57h+arg_10]
0x1801624e9  cmp     ebx, edx
0x1801624eb  jb      short loc_180162484
0x1801624ed  test    edi, edi
0x1801624ef  jz      loc_18016269C
0x1801624f5  mov     rax, [rbp+57h+arg_18]
0x1801624f9  mov     ecx, [rsi+180h]
0x1801624ff  and     ecx, 4
0x180162502  shr     ecx, 2
0x180162505  mov     dword ptr [rsp+100h+var_D0], edi
0x180162509  mov     qword ptr [rsp+100h+var_D8], rax
0x18016250e  mov     dword ptr [rsp+100h+var_E0], ecx; int
0x180162512  mov     r14, [rbp+57h+var_C0]
0x180162516  mov     r9, r14
0x180162519  mov     r8, r14
0x18016251c  mov     rdx, r14
0x18016251f  mov     r15, [rbp+57h+var_B8]
0x180162523  mov     rcx, r15
0x180162526  call    cs:__imp_NetworkIsolationCreateAppContainerLoopbackRules
0x18016252c  mov     ebx, eax
0x18016252e  test    eax, eax
0x180162530  jle     short loc_18016253B
0x180162532  movzx   ebx, ax
0x180162535  or      ebx, 80070000h
0x18016253b  test    ebx, ebx
0x18016253d  jns     loc_180162699
0x180162543  mov     eax, cs:dword_1802E09C8
0x180162549  cmp     eax, 5
0x18016254c  jbe     short loc_1801625C8
0x18016254e  mov     rdx, 400000000000h
0x180162558  lea     rcx, dword_1802E09C8
0x18016255f  call    _tlgKeywordOn
0x180162564  test    al, al
0x180162566  jz      short loc_1801625C8
0x180162568  mov     [rbp+57h+arg_8], ebx
0x18016256b  lea     rax, aNetworkisolati_3; "NetworkIsolationCreateAppContainerLoopb"...
0x180162572  mov     [rbp+57h+var_B8], rax
0x180162576  mov     rax, [rsi+1D0h]
0x18016257d  mov     [rbp+57h+var_C0], rax
0x180162581  mov     rax, [rsi+1C0h]
0x180162588  mov     [rbp+57h+var_B0], rax
0x18016258c  mov     [rbp+57h+var_A8], 1
0x180162594  lea     rax, [rbp+57h+arg_8]
0x180162598  mov     [rsp+100h+var_C8], rax
0x18016259d  lea     rax, [rbp+57h+var_B8]
0x1801625a1  mov     [rsp+100h+var_D0], rax
0x1801625a6  lea     rax, [rbp+57h+var_C0]
0x1801625aa  mov     qword ptr [rsp+100h+var_D8], rax
0x1801625af  lea     rax, [rbp+57h+var_B0]
0x1801625b3  mov     [rsp+100h+var_E0], rax
0x1801625b8  lea     r9, [rbp+57h+var_A8]
0x1801625bc  lea     rdx, byte_1802B420D
0x1801625c3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@23AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1801625c8  mov     [rsp+100h+var_D8], edi; unsigned int
0x1801625cc  mov     rax, [rbp+57h+arg_18]
0x1801625d0  mov     [rsp+100h+var_E0], rax; int
0x1801625d5  mov     r9, r14; unsigned __int16 *
0x1801625d8  mov     r8, r15; void *
0x1801625db  mov     edx, ebx; int
0x1801625dd  mov     cl, 1; bool
0x1801625df  call    ?ReportError@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@CAX_NJQEAXPEBGPEBU_SID_AND_ATTRIBUTES@@I@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(bool,long,void * const,ushort const *,_SID_AND_ATTRIBUTES const *,uint)
0x1801625e4  mov     rcx, [rbp+5Fh]; this
0x1801625e8  mov     r9d, ebx; char *
0x1801625eb  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801625f2  mov     edx, 24Fh; void *
0x1801625f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801625fc  nop
0x1801625fd  mov     rcx, [rbp+57h+arg_18]
0x180162601  test    rcx, rcx
0x180162604  jz      short loc_180162633
0x180162606  xor     edi, edi
0x180162608  mov     edx, dword ptr [rbp+57h+arg_10]
0x18016260b  test    edx, edx
0x18016260d  jz      short loc_180162633
0x18016260f  mov     eax, edi
0x180162611  add     rax, rax
0x180162614  mov     r8, [rcx+rax*8]
0x180162618  test    r8, r8
0x18016261b  jz      short loc_18016262D
0x18016261d  mov     rcx, r8; pSid
0x180162620  call    cs:__imp_FreeSid
0x180162626  mov     edx, dword ptr [rbp+57h+arg_10]; unsigned __int64
0x180162629  mov     rcx, [rbp+57h+arg_18]; void *
0x18016262d  inc     edi
0x18016262f  cmp     edi, edx
0x180162631  jb      short loc_18016260F
0x180162633  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180162638  jmp     loc_180162834
0x18016263d  mov     rcx, [rbp+5Fh]; this
0x180162641  mov     r9d, r14d; char *
0x180162644  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016264b  mov     edx, 22Fh; void *
0x180162650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180162655  nop
0x180162656  mov     rcx, [rbp+57h+arg_18]
0x18016265a  test    rcx, rcx
0x18016265d  jz      loc_18016273F
0x180162663  xor     ebx, ebx
0x180162665  mov     edx, dword ptr [rbp+57h+arg_10]
0x180162668  test    edx, edx
0x18016266a  jz      loc_18016273F
0x180162670  mov     eax, ebx
0x180162672  add     rax, rax
0x180162675  mov     r8, [rcx+rax*8]
0x180162679  test    r8, r8
0x18016267c  jz      short loc_18016268E
0x18016267e  mov     rcx, r8; pSid
0x180162681  call    cs:__imp_FreeSid
0x180162687  mov     edx, dword ptr [rbp+57h+arg_10]
0x18016268a  mov     rcx, [rbp+57h+arg_18]
0x18016268e  inc     ebx
0x180162690  cmp     ebx, edx
0x180162692  jb      short loc_180162670
0x180162694  jmp     loc_18016273F
0x180162699  mov     edx, dword ptr [rbp+57h+arg_10]
0x18016269c  mov     rcx, [rbp+57h+arg_18]
0x1801626a0  test    rcx, rcx
0x1801626a3  jz      short loc_1801626CF
0x1801626a5  xor     ebx, ebx
0x1801626a7  test    edx, edx
0x1801626a9  jz      short loc_1801626CF
0x1801626ab  mov     eax, ebx
0x1801626ad  add     rax, rax
0x1801626b0  mov     r8, [rcx+rax*8]
0x1801626b4  test    r8, r8
0x1801626b7  jz      short loc_1801626C9
0x1801626b9  mov     rcx, r8; pSid
0x1801626bc  call    cs:__imp_FreeSid
0x1801626c2  mov     edx, dword ptr [rbp+57h+arg_10]; unsigned __int64
0x1801626c5  mov     rcx, [rbp+57h+arg_18]; void *
0x1801626c9  inc     ebx
0x1801626cb  cmp     ebx, edx
0x1801626cd  jb      short loc_1801626AB
0x1801626cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801626d4  xor     edi, edi
0x1801626d6  mov     r15, [rbp+57h+var_60]
0x1801626da  test    r15, r15
0x1801626dd  jz      loc_180162832
0x1801626e3  mov     r13, [rbp+57h+var_70]
0x1801626e7  cmp     rdi, r15
0x1801626ea  jb      short loc_18016274C
0x1801626ec  xor     ebx, ebx
0x1801626ee  jmp     short loc_180162751
0x1801626f0  mov     rcx, [rbp+5Fh]; this
0x1801626f4  mov     r9d, r14d; char *
0x1801626f7  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801626fe  mov     edx, 226h; void *
0x180162703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180162708  nop
0x180162709  mov     rcx, [rbp+57h+arg_18]
0x18016270d  test    rcx, rcx
0x180162710  jz      short loc_18016273F
0x180162712  xor     ebx, ebx
0x180162714  mov     edx, dword ptr [rbp+57h+arg_10]
0x180162717  test    edx, edx
0x180162719  jz      short loc_18016273F
0x18016271b  mov     eax, ebx
0x18016271d  add     rax, rax
0x180162720  mov     r8, [rcx+rax*8]
0x180162724  test    r8, r8
0x180162727  jz      short loc_180162739
0x180162729  mov     rcx, r8; pSid
0x18016272c  call    cs:__imp_FreeSid
0x180162732  mov     edx, dword ptr [rbp+57h+arg_10]; unsigned __int64
0x180162735  mov     rcx, [rbp+57h+arg_18]; void *
0x180162739  inc     ebx
0x18016273b  cmp     ebx, edx
0x18016273d  jb      short loc_18016271B
0x18016273f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180162744  mov     ebx, r14d
0x180162747  jmp     loc_180162834
0x18016274c  mov     rbx, [r13+rdi*8+0]
0x180162751  mov     byte ptr [rbp+57h+arg_8], 0
0x180162755  lea     r8, [rbp+57h+arg_8]; bool *
0x180162759  mov     rdx, [rbx+8]; unsigned __int16 *
0x18016275d  mov     rcx, r12; this
0x180162760  call    ?GetCentennialByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBGPEA_N@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(ushort const *,bool *)
0x180162765  mov     r14d, eax
0x180162768  test    eax, eax
0x18016276a  js      loc_18016296C
0x180162770  mov     [rbp+57h+var_C0], 0
0x180162778  xor     edx, edx
0x18016277a  lea     rcx, [rbp+57h+var_C0]
0x18016277e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180162783  lea     r8, [rbp+57h+var_C0]; void **
0x180162787  mov     rdx, rbx; struct Common::COMMON_STRING *
0x18016278a  mov     rcx, r12; this
0x18016278d  call    ?GetPackageSidByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(Common::COMMON_STRING const *,void * *)
0x180162792  mov     r14d, eax
0x180162795  test    eax, eax
0x180162797  js      loc_180162945
0x18016279d  xor     eax, eax
0x18016279f  xorps   xmm0, xmm0
0x1801627a2  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1801627a6  mov     [rbp+57h+var_90], eax
0x1801627a9  lea     r8, [rbp+57h+var_A0]; struct Common::StringBuffer *
0x1801627ad  mov     rdx, rbx; struct Common::COMMON_STRING *
0x1801627b0  mov     rcx, r12; this
0x1801627b3  call    ?GetPackageFullNameByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@AEAVStringBuffer@5@@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageFullNameByPackageFamilyName(Common::COMMON_STRING const *,Common::StringBuffer &)
0x1801627b8  mov     ebx, eax
0x1801627ba  test    eax, eax
0x1801627bc  js      loc_180162914
0x1801627c2  mov     rax, [rbp+57h+var_B8]
0x1801627c6  mov     [rbp+57h+var_80.Sid], rax
0x1801627ca  xor     eax, eax
0x1801627cc  mov     qword ptr [rbp+57h+var_80.Attributes], rax
0x1801627d0  movzx   eax, byte ptr [rbp+57h+arg_8]
0x1801627d4  mov     dword ptr [rsp+100h+var_D0], 1
  ... truncated ...
```
