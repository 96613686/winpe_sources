# OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::UninstallPackage(OSIntegration::Package const *)

- ea: `0x18016315c`
- end: `0x1801636ff`
- name: `?UninstallPackage@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@@Z`
- size: `1443`
- prototype: `__int64 __fastcall(OSIntegration::DEH::LoopbackAccessRulesExtensionHandler *__hidden this, const struct OSIntegration::Package *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c2310`
- `0x1800cd570`

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
- `0x180162ff0`
- `0x18016315c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180163300`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016342b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016349a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180163300`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016342b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18016349a`
- `FirewallAPI!NetworkIsolationDeleteAppContainerLoopbackRules` at `0x180163346`
- `FirewallAPI!NetworkIsolationDeleteAppContainerLoopbackRules` at `0x18016355f`
- `FirewallAPI!NetworkIsolationDeleteAppContainerLoopbackRules` at `0x180163346`
- `FirewallAPI!NetworkIsolationDeleteAppContainerLoopbackRules` at `0x18016355f`

## string_xrefs

- `0x1801632c3`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x180163465`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016365b`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016369c`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x1801636c0`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x1801636e8`: `onecore\admin\appmodel\osim\src\deh\appx\loopbackaccess\loopbackaccessrulesextensionhandler.cpp`
- `0x18016338b`: `NetworkIsolationCreateDeleteContainerLoopbackRules`
- `0x1801635a4`: `NetworkIsolationCreateDeleteContainerLoopbackRules`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::UninstallPackage(
        OSIntegration::DEH::LoopbackAccessRulesExtensionHandler *this,
        const struct OSIntegration::Package *a2)
{
  OSIntegration::DEH::LoopbackAccessRulesExtensionHandler *v3; // rdi
  int MatchedLoopbackRulePackages; // eax
  int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  unsigned __int64 v8; // r12
  unsigned __int64 Sid; // rdx
  unsigned int v10; // esi
  __int64 v11; // r14
  __int64 v12; // r15
  int CentennialByPackageFamilyName; // eax
  int v14; // edi
  int PackageSidByPackageFamilyName; // eax
  unsigned __int64 v16; // rdx
  struct _SID_AND_ATTRIBUTES *v17; // rcx
  unsigned int v18; // ebx
  unsigned __int16 *v19; // r14
  void *v20; // r15
  int v21; // eax
  signed int v22; // edi
  int v23; // ecx
  int v24; // r8d
  struct _SID_AND_ATTRIBUTES *v25; // rcx
  unsigned int i; // edi
  unsigned __int64 v27; // rsi
  unsigned __int64 v28; // r15
  unsigned int v29; // ebx
  __int64 v30; // r14
  int v31; // eax
  int v32; // eax
  int PackageFullNameByPackageFamilyName; // eax
  int v34; // eax
  signed int v35; // edi
  int v36; // ecx
  int v37; // r8d
  int v39; // [rsp+20h] [rbp-A9h]
  unsigned __int16 *v40; // [rsp+40h] [rbp-89h] BYREF
  __int64 v41; // [rsp+48h] [rbp-81h] BYREF
  __int64 v42; // [rsp+50h] [rbp-79h] BYREF
  __int64 v43; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int16 *v44[2]; // [rsp+60h] [rbp-69h] BYREF
  int v45; // [rsp+70h] [rbp-59h]
  void *v46; // [rsp+78h] [rbp-51h]
  __int64 v47; // [rsp+80h] [rbp-49h] BYREF
  struct _SID_AND_ATTRIBUTES v48; // [rsp+88h] [rbp-41h] BYREF
  _QWORD v49[2]; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v50; // [rsp+A8h] [rbp-21h]
  char v51; // [rsp+B0h] [rbp-19h]
  _QWORD v52[2]; // [rsp+B8h] [rbp-11h] BYREF
  unsigned __int64 v53; // [rsp+C8h] [rbp-1h]
  char v54; // [rsp+D0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  signed int v57; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned __int64 v58; // [rsp+140h] [rbp+77h] BYREF
  struct _SID_AND_ATTRIBUTES *v59; // [rsp+148h] [rbp+7Fh] BYREF

  v3 = this;
  v40 = (unsigned __int16 *)*((_QWORD *)a2 + 28);
  v46 = (void *)*((_QWORD *)a2 + 87);
  v52[0] = 0;
  v52[1] = 0;
  v53 = 0;
  v54 = 1;
  v49[0] = 0;
  v49[1] = 0;
  v50 = 0;
  v51 = 1;
  MatchedLoopbackRulePackages = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetMatchedLoopbackRulePackages(
                                  this,
                                  a2,
                                  v52,
                                  v49);
  v5 = MatchedLoopbackRulePackages;
  if ( MatchedLoopbackRulePackages < 0 )
  {
    v6 = (unsigned int)MatchedLoopbackRulePackages;
    v7 = 667;
    goto LABEL_57;
  }
  v5 = 0;
  v8 = v53;
  if ( !v53 )
    goto LABEL_34;
  LODWORD(v58) = v53;
  v59 = (struct _SID_AND_ATTRIBUTES *)operator new[](saturated_mul((unsigned int)v53, 0x10u));
  memset_0(v59, 0, 16LL * (unsigned int)v58);
  v44[0] = (unsigned __int16 *)&v59;
  v44[1] = (unsigned __int16 *)&v58;
  LOBYTE(v45) = 1;
  v10 = 0;
  v11 = 0;
  if ( !(_DWORD)v58 )
    goto LABEL_28;
  while ( 1 )
  {
    if ( (unsigned int)v11 < v8 )
    {
      _mm_lfence();
      v12 = *(_QWORD *)(v52[0] + 8 * v11);
    }
    else
    {
      v12 = 0;
    }
    LOBYTE(v57) = 0;
    CentennialByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(
                                      v3,
                                      *(const unsigned __int16 **)(v12 + 8),
                                      (bool *)&v57);
    v14 = CentennialByPackageFamilyName;
    if ( CentennialByPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
        (const char *)(unsigned int)CentennialByPackageFamilyName,
        v39);
      v17 = v59;
      if ( v59 )
      {
        v29 = 0;
        v16 = (unsigned int)v58;
        if ( (_DWORD)v58 )
        {
          do
          {
            if ( v17[v29].Sid )
            {
              FreeSid(v17[v29].Sid);
              v16 = (unsigned int)v58;
              v17 = v59;
            }
            ++v29;
          }
          while ( v29 < (unsigned int)v16 );
        }
      }
      goto LABEL_41;
    }
    if ( (_BYTE)v57 )
      goto LABEL_12;
    PackageSidByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(
                                      this,
                                      (const struct Common::COMMON_STRING *)v12,
                                      &v59[v10].Sid);
    v14 = PackageSidByPackageFamilyName;
    if ( PackageSidByPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
        (const char *)(unsigned int)PackageSidByPackageFamilyName,
        v39);
      v17 = v59;
      if ( v59 )
      {
        v18 = 0;
        v16 = (unsigned int)v58;
        if ( (_DWORD)v58 )
        {
          do
          {
            if ( v17[v18].Sid )
            {
              FreeSid(v17[v18].Sid);
              v16 = (unsigned int)v58;
              v17 = v59;
            }
            ++v18;
          }
          while ( v18 < (unsigned int)v16 );
        }
      }
LABEL_41:
      operator delete(v17, v16);
      goto LABEL_42;
    }
    ++v10;
LABEL_12:
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= (unsigned int)v58 )
      break;
    v3 = this;
  }
  if ( v10 )
  {
    v39 = v10;
    v19 = v40;
    v20 = v46;
    v21 = NetworkIsolationDeleteAppContainerLoopbackRules(v46, v40, (*((_DWORD *)a2 + 96) & 4u) >> 2, v59);
    v22 = v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    if ( v22 < 0 )
    {
      if ( (unsigned int)dword_1802E09C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1802E09C8, 0x400000000000LL) )
      {
        v57 = v22;
        v40 = L"NetworkIsolationCreateDeleteContainerLoopbackRules";
        v41 = *((_QWORD *)a2 + 58);
        v42 = *((_QWORD *)a2 + 56);
        v43 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v23,
          (unsigned int)byte_1802B4333,
          v24,
          (unsigned int)&v43,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v57);
      }
      OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(0, v22, v20, v19, v59, v10);
      v5 = v22;
    }
  }
LABEL_28:
  v25 = v59;
  if ( v59 )
  {
    for ( i = 0; i < (unsigned int)v58; ++i )
    {
      Sid = (unsigned __int64)v25[i].Sid;
      if ( Sid )
      {
        FreeSid(v25[i].Sid);
        v25 = v59;
      }
    }
  }
  operator delete(v25, Sid);
  v3 = this;
LABEL_34:
  v27 = 0;
  v28 = v50;
  if ( !v50 )
  {
LABEL_55:
    if ( v5 >= 0 )
      goto LABEL_58;
    v6 = (unsigned int)v5;
    v7 = 791;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
      (const char *)v6,
      v39);
    goto LABEL_58;
  }
  while ( 1 )
  {
    v30 = *(_QWORD *)(v49[0] + 8 * v27);
    LOBYTE(v57) = 0;
    v31 = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(
            v3,
            *(const unsigned __int16 **)(v30 + 8),
            (bool *)&v57);
    v14 = v31;
    if ( v31 < 0 )
      break;
    v40 = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v40,
      0);
    v32 = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(
            this,
            (const struct Common::COMMON_STRING *)v30,
            (void **)&v40);
    v14 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
        (const char *)(unsigned int)v32,
        v39);
      goto LABEL_61;
    }
    *(_OWORD *)v44 = 0;
    v45 = 0;
    PackageFullNameByPackageFamilyName = OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageFullNameByPackageFamilyName(
                                           this,
                                           (const struct Common::COMMON_STRING *)v30,
                                           (struct Common::StringBuffer *)v44);
    v14 = PackageFullNameByPackageFamilyName;
    if ( PackageFullNameByPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
        (const char *)(unsigned int)PackageFullNameByPackageFamilyName,
        v39);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v44);
LABEL_61:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v40);
      goto LABEL_42;
    }
    v48.Sid = v46;
    *(_QWORD *)&v48.Attributes = 0;
    v39 = 1;
    v34 = NetworkIsolationDeleteAppContainerLoopbackRules(v40, v44[1], (unsigned __int8)v57, &v48);
    v35 = v34;
    if ( v34 > 0 )
      v35 = (unsigned __int16)v34 | 0x80070000;
    if ( v35 < 0 )
    {
      if ( (unsigned int)dword_1802E09C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1802E09C8, 0x400000000000LL) )
      {
        v57 = v35;
        v43 = (__int64)L"NetworkIsolationCreateDeleteContainerLoopbackRules";
        v42 = *((_QWORD *)a2 + 58);
        v41 = *((_QWORD *)a2 + 56);
        v47 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v36,
          (unsigned int)&word_1802B42E6,
          v37,
          (unsigned int)&v47,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v57);
      }
      OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(0, v35, v40, v44[1], &v48, 1u);
      if ( v5 >= 0 )
        v5 = v35;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v44);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v40);
    ++v27;
    v3 = this;
    if ( v27 >= v28 )
      goto LABEL_55;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2EE,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\loopbackaccess\\loopbackaccessrulesextensionhandler.cpp",
    (const char *)(unsigned int)v31,
    v39);
LABEL_42:
  v5 = v14;
LABEL_58:
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v49);
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v52);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18016315c  mov     [rsp-8+arg_0], rcx
0x180163161  push    rbp
0x180163162  push    rbx
0x180163163  push    rsi
0x180163164  push    rdi
0x180163165  push    r12
0x180163167  push    r13
0x180163169  push    r14
0x18016316b  push    r15
0x18016316d  lea     rbp, [rsp-1Fh]
0x180163172  sub     rsp, 0E8h
0x180163179  mov     r13, rdx
0x18016317c  mov     rdi, rcx
0x18016317f  mov     rax, [rdx+0E0h]
0x180163186  mov     [rsp+120h+var_E0], rax
0x18016318b  mov     r15, [rdx+2B8h]
0x180163192  mov     [rbp+57h+var_A8], r15
0x180163196  mov     [rbp+57h+var_68], 0
0x18016319e  mov     [rbp+57h+var_60], 0
0x1801631a6  mov     [rbp+57h+var_58], 0
0x1801631ae  mov     [rbp+57h+var_50], 1
0x1801631b2  mov     [rbp+57h+var_88], 0
0x1801631ba  mov     [rbp+57h+var_80], 0
0x1801631c2  mov     [rbp+57h+var_78], 0
0x1801631ca  mov     [rbp+57h+var_70], 1
0x1801631ce  lea     r9, [rbp+57h+var_88]
0x1801631d2  lea     r8, [rbp+57h+var_68]
0x1801631d6  call    ?GetMatchedLoopbackRulePackages@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@AEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@1@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetMatchedLoopbackRulePackages(OSIntegration::Package const *,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &)
0x1801631db  mov     ebx, eax
0x1801631dd  test    eax, eax
0x1801631df  jns     short loc_1801631EE
0x1801631e1  mov     r9d, eax
0x1801631e4  mov     edx, 29Bh
0x1801631e9  jmp     loc_18016365B
0x1801631ee  xor     ebx, ebx
0x1801631f0  mov     r12, [rbp+57h+var_58]
0x1801631f4  test    r12, r12
0x1801631f7  jz      loc_180163445
0x1801631fd  mov     dword ptr [rbp+57h+arg_10], r12d
0x180163201  mov     ecx, r12d
0x180163204  lea     eax, [rbx+10h]
0x180163207  mul     rcx
0x18016320a  lea     rcx, [rbx-1]
0x18016320e  cmovb   rax, rcx
0x180163212  mov     rcx, rax; unsigned __int64
0x180163215  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18016321a  mov     [rbp+57h+arg_18], rax
0x18016321e  mov     r8d, dword ptr [rbp+57h+arg_10]
0x180163222  shl     r8, 4; Size
0x180163226  xor     edx, edx; Val
0x180163228  mov     rcx, rax; void *
0x18016322b  call    memset_0
0x180163230  lea     rax, [rbp+57h+arg_18]
0x180163234  mov     [rbp+57h+var_C0], rax
0x180163238  lea     rax, [rbp+57h+arg_10]
0x18016323c  mov     [rbp+57h+var_C0+8], rax
0x180163240  mov     byte ptr [rbp+57h+var_B0], 1
0x180163244  xor     esi, esi
0x180163246  xor     r14d, r14d
0x180163249  cmp     dword ptr [rbp+57h+arg_10], esi
0x18016324c  jbe     loc_18016340A
0x180163252  mov     r15d, r14d
0x180163255  cmp     r15, r12
0x180163258  jb      short loc_18016325F
0x18016325a  xor     r15d, r15d
0x18016325d  jmp     short loc_18016326A
0x18016325f  lfence
0x180163262  mov     rax, [rbp+57h+var_68]
0x180163266  mov     r15, [rax+r14*8]
0x18016326a  mov     byte ptr [rbp+57h+arg_8], 0
0x18016326e  lea     r8, [rbp+57h+arg_8]; bool *
0x180163272  mov     rdx, [r15+8]; unsigned __int16 *
0x180163276  mov     rcx, rdi; this
0x180163279  call    ?GetCentennialByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBGPEA_N@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(ushort const *,bool *)
0x18016327e  mov     edi, eax
0x180163280  test    eax, eax
0x180163282  js      loc_18016345E
0x180163288  cmp     byte ptr [rbp+57h+arg_8], 0
0x18016328c  jnz     short loc_1801632AD
0x18016328e  mov     r8d, esi
0x180163291  shl     r8, 4
0x180163295  add     r8, [rbp+57h+arg_18]; void **
0x180163299  mov     rdx, r15; struct Common::COMMON_STRING *
0x18016329c  mov     rcx, [rbp+57h+arg_0]; this
0x1801632a0  call    ?GetPackageSidByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(Common::COMMON_STRING const *,void * *)
0x1801632a5  mov     edi, eax
0x1801632a7  test    eax, eax
0x1801632a9  js      short loc_1801632BC
0x1801632ab  inc     esi
0x1801632ad  inc     r14d
0x1801632b0  cmp     r14d, dword ptr [rbp+57h+arg_10]
0x1801632b4  jnb     short loc_180163318
0x1801632b6  mov     rdi, [rbp+57h+arg_0]
0x1801632ba  jmp     short loc_180163252
0x1801632bc  mov     rcx, [rbp+5Fh]; this
0x1801632c0  mov     r9d, edi; char *
0x1801632c3  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801632ca  mov     edx, 2C3h; void *
0x1801632cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801632d4  nop
0x1801632d5  mov     rcx, [rbp+57h+arg_18]
0x1801632d9  test    rcx, rcx
0x1801632dc  jz      loc_1801634AD
0x1801632e2  xor     ebx, ebx
0x1801632e4  mov     edx, dword ptr [rbp+57h+arg_10]
0x1801632e7  test    edx, edx
0x1801632e9  jz      loc_1801634AD
0x1801632ef  mov     eax, ebx
0x1801632f1  add     rax, rax
0x1801632f4  mov     r8, [rcx+rax*8]
0x1801632f8  test    r8, r8
0x1801632fb  jz      short loc_18016330D
0x1801632fd  mov     rcx, r8; pSid
0x180163300  call    cs:__imp_FreeSid
0x180163306  mov     edx, dword ptr [rbp+57h+arg_10]
0x180163309  mov     rcx, [rbp+57h+arg_18]
0x18016330d  inc     ebx
0x18016330f  cmp     ebx, edx
0x180163311  jb      short loc_1801632EF
0x180163313  jmp     loc_1801634AD
0x180163318  test    esi, esi
0x18016331a  jz      loc_18016340A
0x180163320  mov     r8d, [r13+180h]
0x180163327  and     r8d, 4
0x18016332b  shr     r8d, 2
0x18016332f  mov     dword ptr [rsp+120h+var_100], esi
0x180163333  mov     r9, [rbp+57h+arg_18]
0x180163337  mov     r14, [rsp+120h+var_E0]
0x18016333c  mov     rdx, r14
0x18016333f  mov     r15, [rbp+57h+var_A8]
0x180163343  mov     rcx, r15
0x180163346  call    cs:__imp_NetworkIsolationDeleteAppContainerLoopbackRules
0x18016334c  mov     edi, eax
0x18016334e  test    eax, eax
0x180163350  jle     short loc_18016335B
0x180163352  movzx   edi, ax
0x180163355  or      edi, 80070000h
0x18016335b  test    edi, edi
0x18016335d  jns     loc_18016340A
0x180163363  mov     eax, cs:dword_1802E09C8
0x180163369  cmp     eax, 5
0x18016336c  jbe     short loc_1801633EC
0x18016336e  mov     rdx, 400000000000h
0x180163378  lea     rcx, dword_1802E09C8
0x18016337f  call    _tlgKeywordOn
0x180163384  test    al, al
0x180163386  jz      short loc_1801633EC
0x180163388  mov     [rbp+57h+arg_8], edi
0x18016338b  lea     rax, aNetworkisolati_4; "NetworkIsolationCreateDeleteContainerLo"...
0x180163392  mov     [rsp+120h+var_E0], rax
0x180163397  mov     rax, [r13+1D0h]
0x18016339e  mov     [rsp+120h+var_D8], rax
0x1801633a3  mov     rax, [r13+1C0h]
0x1801633aa  mov     [rbp+57h+var_D0], rax
0x1801633ae  mov     [rbp+57h+var_C8], 1
0x1801633b6  lea     rax, [rbp+57h+arg_8]
0x1801633ba  mov     [rsp+120h+var_E8], rax
0x1801633bf  lea     rax, [rsp+120h+var_E0]
0x1801633c4  mov     [rsp+120h+var_F0], rax
0x1801633c9  lea     rax, [rsp+120h+var_D8]
0x1801633ce  mov     qword ptr [rsp+120h+var_F8], rax
0x1801633d3  lea     rax, [rbp+57h+var_D0]
0x1801633d7  mov     [rsp+120h+var_100], rax
0x1801633dc  lea     r9, [rbp+57h+var_C8]
0x1801633e0  lea     rdx, byte_1802B4333
0x1801633e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@23AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1801633ec  mov     [rsp+120h+var_F8], esi; unsigned int
0x1801633f0  mov     rax, [rbp+57h+arg_18]
0x1801633f4  mov     [rsp+120h+var_100], rax; int
0x1801633f9  mov     r9, r14; unsigned __int16 *
0x1801633fc  mov     r8, r15; void *
0x1801633ff  mov     edx, edi; int
0x180163401  xor     ecx, ecx; bool
0x180163403  call    ?ReportError@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@CAX_NJQEAXPEBGPEBU_SID_AND_ATTRIBUTES@@I@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::ReportError(bool,long,void * const,ushort const *,_SID_AND_ATTRIBUTES const *,uint)
0x180163408  mov     ebx, edi
0x18016340a  mov     rcx, [rbp+57h+arg_18]
0x18016340e  test    rcx, rcx
0x180163411  jz      short loc_18016343C
0x180163413  xor     edi, edi
0x180163415  cmp     dword ptr [rbp+57h+arg_10], edi
0x180163418  jbe     short loc_18016343C
0x18016341a  mov     eax, edi
0x18016341c  add     rax, rax
0x18016341f  mov     rdx, [rcx+rax*8]
0x180163423  test    rdx, rdx
0x180163426  jz      short loc_180163435
0x180163428  mov     rcx, rdx; pSid
0x18016342b  call    cs:__imp_FreeSid
0x180163431  mov     rcx, [rbp+57h+arg_18]; void *
0x180163435  inc     edi
0x180163437  cmp     edi, dword ptr [rbp+57h+arg_10]
0x18016343a  jb      short loc_18016341A
0x18016343c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180163441  mov     rdi, [rbp+57h+arg_0]
0x180163445  xor     esi, esi
0x180163447  mov     r15, [rbp+57h+var_78]
0x18016344b  test    r15, r15
0x18016344e  jz      loc_18016364F
0x180163454  cmp     rsi, r15
0x180163457  jb      short loc_1801634B9
0x180163459  xor     r14d, r14d
0x18016345c  jmp     short loc_1801634C1
0x18016345e  mov     rcx, [rbp+5Fh]; this
0x180163462  mov     r9d, edi; char *
0x180163465  lea     r8, aOnecoreAdminAp_67; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016346c  mov     edx, 2BCh; void *
0x180163471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163476  nop
0x180163477  mov     rcx, [rbp+57h+arg_18]
0x18016347b  test    rcx, rcx
0x18016347e  jz      short loc_1801634AD
0x180163480  xor     ebx, ebx
0x180163482  mov     edx, dword ptr [rbp+57h+arg_10]
0x180163485  test    edx, edx
0x180163487  jz      short loc_1801634AD
0x180163489  mov     eax, ebx
0x18016348b  add     rax, rax
0x18016348e  mov     r8, [rcx+rax*8]
0x180163492  test    r8, r8
0x180163495  jz      short loc_1801634A7
0x180163497  mov     rcx, r8; pSid
0x18016349a  call    cs:__imp_FreeSid
0x1801634a0  mov     edx, dword ptr [rbp+57h+arg_10]; unsigned __int64
0x1801634a3  mov     rcx, [rbp+57h+arg_18]; void *
0x1801634a7  inc     ebx
0x1801634a9  cmp     ebx, edx
0x1801634ab  jb      short loc_180163489
0x1801634ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801634b2  mov     ebx, edi
0x1801634b4  jmp     loc_18016366C
0x1801634b9  mov     rax, [rbp+57h+var_88]
0x1801634bd  mov     r14, [rax+rsi*8]
0x1801634c1  mov     byte ptr [rbp+57h+arg_8], 0
0x1801634c5  lea     r8, [rbp+57h+arg_8]; bool *
0x1801634c9  mov     rdx, [r14+8]; unsigned __int16 *
0x1801634cd  mov     rcx, rdi; this
0x1801634d0  call    ?GetCentennialByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBGPEA_N@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetCentennialByPackageFamilyName(ushort const *,bool *)
0x1801634d5  mov     edi, eax
0x1801634d7  test    eax, eax
0x1801634d9  js      loc_1801636E1
0x1801634df  mov     [rsp+120h+var_E0], 0
0x1801634e8  xor     edx, edx
0x1801634ea  lea     rcx, [rsp+120h+var_E0]
0x1801634ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801634f4  lea     r8, [rsp+120h+var_E0]; void **
0x1801634f9  mov     rdx, r14; struct Common::COMMON_STRING *
0x1801634fc  mov     r12, [rbp+57h+arg_0]
0x180163500  mov     rcx, r12; this
0x180163503  call    ?GetPackageSidByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageSidByPackageFamilyName(Common::COMMON_STRING const *,void * *)
0x180163508  mov     edi, eax
0x18016350a  test    eax, eax
0x18016350c  js      loc_1801636B9
0x180163512  xor     eax, eax
0x180163514  xorps   xmm0, xmm0
0x180163517  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x18016351b  mov     [rbp+57h+var_B0], eax
0x18016351e  lea     r8, [rbp+57h+var_C0]; struct Common::StringBuffer *
0x180163522  mov     rdx, r14; struct Common::COMMON_STRING *
0x180163525  mov     rcx, r12; this
0x180163528  call    ?GetPackageFullNameByPackageFamilyName@LoopbackAccessRulesExtensionHandler@DEH@OSIntegration@@AEAAJPEBUCOMMON_STRING@Common@@AEAVStringBuffer@5@@Z; OSIntegration::DEH::LoopbackAccessRulesExtensionHandler::GetPackageFullNameByPackageFamilyName(Common::COMMON_STRING const *,Common::StringBuffer &)
0x18016352d  mov     edi, eax
0x18016352f  test    eax, eax
0x180163531  js      loc_180163695
0x180163537  mov     rax, [rbp+57h+var_A8]
0x18016353b  mov     [rbp+57h+var_98.Sid], rax
0x18016353f  xor     eax, eax
0x180163541  mov     qword ptr [rbp+57h+var_98.Attributes], rax
0x180163545  movzx   r8d, byte ptr [rbp+57h+arg_8]
0x18016354a  mov     dword ptr [rsp+120h+var_100], 1
0x180163552  lea     r9, [rbp+57h+var_98]
0x180163556  mov     rdx, [rbp+57h+var_C0+8]
0x18016355a  mov     rcx, [rsp+120h+var_E0]
0x18016355f  call    cs:__imp_NetworkIsolationDeleteAppContainerLoopbackRules
0x180163565  mov     edi, eax
0x180163567  test    eax, eax
0x180163569  jle     short loc_180163574
0x18016356b  movzx   edi, ax
0x18016356e  or      edi, 80070000h
0x180163574  test    edi, edi
0x180163576  jns     loc_18016362B
0x18016357c  mov     eax, cs:dword_1802E09C8
0x180163582  cmp     eax, 5
0x180163585  jbe     short loc_180163603
0x180163587  mov     rdx, 400000000000h
0x180163591  lea     rcx, dword_1802E09C8
0x180163598  call    _tlgKeywordOn
0x18016359d  test    al, al
0x18016359f  jz      short loc_180163603
0x1801635a1  mov     [rbp+57h+arg_8], edi
0x1801635a4  lea     rax, aNetworkisolati_4; "NetworkIsolationCreateDeleteContainerLo"...
0x1801635ab  mov     [rbp+57h+var_C8], rax
0x1801635af  mov     rax, [r13+1D0h]
0x1801635b6  mov     [rbp+57h+var_D0], rax
0x1801635ba  mov     rax, [r13+1C0h]
0x1801635c1  mov     [rsp+120h+var_D8], rax
0x1801635c6  mov     [rbp+57h+var_A0], 1
0x1801635ce  lea     rax, [rbp+57h+arg_8]
0x1801635d2  mov     [rsp+120h+var_E8], rax
0x1801635d7  lea     rax, [rbp+57h+var_C8]
0x1801635db  mov     [rsp+120h+var_F0], rax
  ... truncated ...
```
