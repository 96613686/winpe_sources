# NgcSvc::NgcServiceFixIndividualAcl

- ea: `0x180063630`
- end: `0x1800638ea`
- name: `NgcSvc::NgcServiceFixIndividualAcl`
- size: `698`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180063fa4`

## callees

- `0x180001098`
- `0x180028d18`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180046d90`
- `0x18005cee0`
- `0x18005dd44`
- `0x180063630`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800637fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800638ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800637fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800638ba`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006377c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006377c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800636a6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180063834`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800636a6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180063834`

## string_xrefs

- `0x1800636c9`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x1800637a6`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcSvc::NgcServiceFixIndividualAcl(WCHAR *pObjectName, char a2, __int64 a3)
{
  WCHAR *v5; // rbx
  DWORD v6; // edi
  __int64 v8; // rdx
  unsigned __int8 *v9; // rdx
  HLOCAL v10; // rcx
  WCHAR *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  HLOCAL v15; // rcx
  unsigned int psidGroup; // [rsp+20h] [rbp-99h]
  HLOCAL hMem; // [rsp+48h] [rbp-71h] BYREF
  WCHAR *v18; // [rsp+50h] [rbp-69h] BYREF
  HLOCAL *p_hMem; // [rsp+58h] [rbp-61h] BYREF
  PACL NewAcl; // [rsp+60h] [rbp-59h] BYREF
  char v21; // [rsp+68h] [rbp-51h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp-49h] BYREF
  int v23; // [rsp+A0h] [rbp-19h]
  int v24; // [rsp+A4h] [rbp-15h]
  DWORD grfInheritance; // [rsp+A8h] [rbp-11h]
  int v26; // [rsp+BCh] [rbp+3h]
  __int64 v27; // [rsp+C8h] [rbp+Fh]
  _DWORD psidOwner[4]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v5 = pObjectName;
  psidOwner[0] = 257;
  psidOwner[1] = 83886080;
  psidOwner[2] = 18;
  if ( *((_QWORD *)pObjectName + 3) > 7u )
    pObjectName = *(WCHAR **)pObjectName;
  v6 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
  if ( v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
        (const char *)v6,
        psidGroup);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v18) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_1800FD3AE,
        0,
        0,
        (__int64)&v18);
    }
    return v6;
  }
  hMem = 0;
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfAccessPermissions = 2032127;
  pListOfExplicitEntries.grfInheritance = a2 != 0 ? 3 : 0;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
  v24 = 1;
  v23 = 2032127;
  grfInheritance = pListOfExplicitEntries.grfInheritance;
  v26 = 0;
  v27 = a3;
  p_hMem = &hMem;
  NewAcl = 0;
  v21 = 1;
  v6 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v8 = 201;
LABEL_12:
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
        (const char *)v6,
        psidGroup);
      goto LABEL_16;
    }
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v9 = (unsigned __int8 *)&byte_1800FD387;
LABEL_15:
      LODWORD(v18) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        v9,
        0,
        0,
        (__int64)&v18);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( *((_QWORD *)v5 + 3) <= 7u )
    v11 = v5;
  else
    v11 = *(WCHAR **)v5;
  v6 = SetNamedSecurityInfoW(v11, SE_FILE_OBJECT, 4u, 0, 0, (PACL)hMem, 0);
  if ( v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v8 = 225;
      goto LABEL_12;
    }
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v9 = (unsigned __int8 *)&dword_1800FD354;
      goto LABEL_15;
    }
LABEL_16:
    v10 = hMem;
    hMem = 0;
    if ( v10 )
      LocalFree(v10);
    return v6;
  }
  if ( (unsigned int)dword_180122070 > 4 )
  {
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(WCHAR **)v5;
    v18 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
      v12,
      (__int64)byte_1800FD311,
      v13,
      v14,
      &v18);
  }
  v15 = hMem;
  hMem = 0;
  if ( v15 )
    LocalFree(v15);
  return 0;
}

```

## disassembly

```asm
0x180063630  mov     [rsp-8+arg_8], rbx
0x180063635  mov     [rsp-8+arg_10], rsi
0x18006363a  push    rbp
0x18006363b  push    rdi
0x18006363c  push    r12
0x18006363e  push    r14
0x180063640  push    r15
0x180063642  lea     rbp, [rsp-37h]
0x180063647  sub     rsp, 0F0h
0x18006364e  mov     rax, cs:__security_cookie
0x180063655  xor     rax, rsp
0x180063658  mov     [rbp+57h+var_30], rax
0x18006365c  mov     r14, r8
0x18006365f  mov     sil, dl
0x180063662  mov     rbx, rcx
0x180063665  mov     r12d, 1
0x18006366b  mov     [rbp+57h+psidOwner], 101h
0x180063672  xor     r15d, r15d
0x180063675  mov     [rbp+57h+var_3C], 5000000h
0x18006367c  mov     [rbp+57h+var_38], 12h
0x180063683  cmp     qword ptr [rcx+18h], 7
0x180063688  jbe     short loc_18006368D
0x18006368a  mov     rcx, [rcx]; pObjectName
0x18006368d  mov     [rsp+110h+pSacl], r15; pSacl
0x180063692  mov     [rsp+110h+pDacl], r15; pDacl
0x180063697  mov     [rsp+110h+psidGroup], r15; unsigned int
0x18006369c  lea     r9, [rbp+57h+psidOwner]; psidOwner
0x1800636a0  mov     r8d, r12d; SecurityInfo
0x1800636a3  mov     edx, r12d; ObjectType
0x1800636a6  call    cs:__imp_SetNamedSecurityInfoW
0x1800636ac  mov     edi, eax
0x1800636ae  test    eax, eax
0x1800636b0  jz      short loc_180063713
0x1800636b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800636b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800636be  test    al, al
0x1800636c0  jz      short loc_1800636DC
0x1800636c2  mov     rcx, [rbp+5Fh]; this
0x1800636c6  mov     r9d, edi; char *
0x1800636c9  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800636d0  mov     edx, 0A6h; void *
0x1800636d5  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800636da  jmp     short loc_18006370C
0x1800636dc  mov     eax, cs:dword_180122070
0x1800636e2  cmp     eax, 2
0x1800636e5  jbe     short loc_18006370C
0x1800636e7  mov     dword ptr [rbp+57h+var_C0], edi
0x1800636ea  lea     rax, [rbp+57h+var_C0]
0x1800636ee  mov     [rsp+110h+psidGroup], rax
0x1800636f3  xor     r9d, r9d
0x1800636f6  xor     r8d, r8d
0x1800636f9  lea     rdx, word_1800FD3AE
0x180063700  lea     rcx, dword_180122070
0x180063707  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006370c  mov     eax, edi
0x18006370e  jmp     loc_1800638C2
0x180063713  mov     [rbp+57h+hMem], r15
0x180063717  xor     edx, edx; Val
0x180063719  lea     r8d, [rdx+60h]; Size
0x18006371d  lea     rcx, [rbp+57h+pListOfExplicitEntries]; void *
0x180063721  call    memset_0
0x180063726  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r12d
0x18006372a  mov     edx, 1F01FFh
0x18006372f  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], edx
0x180063732  mov     al, sil
0x180063735  neg     al
0x180063737  sbb     ecx, ecx
0x180063739  and     ecx, 3
0x18006373c  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], ecx
0x18006373f  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x180063743  lea     rax, [rbp+57h+psidOwner]
0x180063747  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18006374b  mov     [rbp+57h+var_6C], r12d
0x18006374f  mov     [rbp+57h+var_70], edx
0x180063752  mov     [rbp+57h+var_68], ecx
0x180063755  mov     [rbp+57h+var_54], r15d
0x180063759  mov     [rbp+57h+var_48], r14
0x18006375d  lea     rax, [rbp+57h+hMem]
0x180063761  mov     [rbp+57h+var_B8], rax
0x180063765  mov     [rbp+57h+NewAcl], r15
0x180063769  mov     [rbp+57h+var_A8], r12b
0x18006376d  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180063771  xor     r8d, r8d; OldAcl
0x180063774  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180063778  lea     ecx, [r8+2]; cCountOfExplicitEntries
0x18006377c  call    cs:__imp_SetEntriesInAclW
0x180063782  mov     edi, eax
0x180063784  lea     rcx, [rbp+57h+var_B8]
0x180063788  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006378d  test    edi, edi
0x18006378f  jz      short loc_180063808
0x180063791  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063798  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006379d  test    al, al
0x18006379f  jz      short loc_1800637BB
0x1800637a1  mov     edx, 0C9h; void *
0x1800637a6  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800637ad  mov     r9d, edi; char *
0x1800637b0  mov     rcx, [rbp+5Fh]; this
0x1800637b4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800637b9  jmp     short loc_1800637EC
0x1800637bb  mov     eax, cs:dword_180122070
0x1800637c1  cmp     eax, 2
0x1800637c4  jbe     short loc_1800637EC
0x1800637c6  lea     rdx, byte_1800FD387
0x1800637cd  xor     r9d, r9d
0x1800637d0  lea     rax, [rbp+57h+var_C0]
0x1800637d4  xor     r8d, r8d
0x1800637d7  mov     [rsp+110h+psidGroup], rax
0x1800637dc  mov     dword ptr [rbp+57h+var_C0], edi
0x1800637df  lea     rcx, dword_180122070
0x1800637e6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800637eb  nop
0x1800637ec  mov     rcx, [rbp+57h+hMem]; hMem
0x1800637f0  mov     [rbp+57h+hMem], r15
0x1800637f4  test    rcx, rcx
0x1800637f7  jz      loc_18006370C
0x1800637fd  call    cs:__imp_LocalFree
0x180063803  jmp     loc_18006370C
0x180063808  mov     rax, [rbp+57h+hMem]
0x18006380c  cmp     qword ptr [rbx+18h], 7
0x180063811  jbe     short loc_180063818
0x180063813  mov     rcx, [rbx]
0x180063816  jmp     short loc_18006381B
0x180063818  mov     rcx, rbx; pObjectName
0x18006381b  mov     [rsp+110h+pSacl], r15; pSacl
0x180063820  mov     [rsp+110h+pDacl], rax; pDacl
0x180063825  mov     [rsp+110h+psidGroup], r15; psidGroup
0x18006382a  xor     r9d, r9d; psidOwner
0x18006382d  lea     r8d, [r9+4]; SecurityInfo
0x180063831  mov     edx, r12d; ObjectType
0x180063834  call    cs:__imp_SetNamedSecurityInfoW
0x18006383a  mov     edi, eax
0x18006383c  test    eax, eax
0x18006383e  jz      short loc_180063871
0x180063840  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063847  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006384c  test    al, al
0x18006384e  jz      short loc_18006385A
0x180063850  mov     edx, 0E1h
0x180063855  jmp     loc_1800637A6
0x18006385a  mov     eax, cs:dword_180122070
0x180063860  cmp     eax, 2
0x180063863  jbe     short loc_1800637EC
0x180063865  lea     rdx, dword_1800FD354
0x18006386c  jmp     loc_1800637CD
0x180063871  mov     eax, cs:dword_180122070
0x180063877  cmp     eax, 4
0x18006387a  jbe     short loc_1800638AD
0x18006387c  mov     [rbp+57h+var_D0], sil
0x180063880  cmp     qword ptr [rbx+18h], 7
0x180063885  jbe     short loc_18006388A
0x180063887  mov     rbx, [rbx]
0x18006388a  mov     [rbp+57h+var_C0], rbx
0x18006388e  lea     rax, [rbp+57h+var_D0]
0x180063892  mov     [rsp+110h+pDacl], rax
0x180063897  lea     rax, [rbp+57h+var_C0]
0x18006389b  mov     [rsp+110h+psidGroup], rax
0x1800638a0  lea     rdx, byte_1800FD311
0x1800638a7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x1800638ac  nop
0x1800638ad  mov     rcx, [rbp+57h+hMem]; hMem
0x1800638b1  mov     [rbp+57h+hMem], r15
0x1800638b5  test    rcx, rcx
0x1800638b8  jz      short loc_1800638C0
0x1800638ba  call    cs:__imp_LocalFree
0x1800638c0  xor     eax, eax
0x1800638c2  mov     rcx, [rbp+57h+var_30]
0x1800638c6  xor     rcx, rsp; StackCookie
0x1800638c9  call    __security_check_cookie
0x1800638ce  lea     r11, [rsp+110h+var_20]
0x1800638d6  mov     rbx, [r11+38h]
0x1800638da  mov     rsi, [r11+40h]
0x1800638de  mov     rsp, r11
0x1800638e1  pop     r15
0x1800638e3  pop     r14
0x1800638e5  pop     r12
0x1800638e7  pop     rdi
0x1800638e8  pop     rbp
0x1800638e9  retn
```
