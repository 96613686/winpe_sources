# JobExecution::SetupCustomHeaders(ATL::CComPtr<IBackgroundCopyJob>,bool *,_GUID)

- ea: `0x14004c794`
- end: `0x14004ccd1`
- name: `?SetupCustomHeaders@JobExecution@@SAJV?$CComPtr@UIBackgroundCopyJob@@@ATL@@PEA_NU_GUID@@@Z`
- size: `1341`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob **, bool *, struct _GUID *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004a9a4`
- `0x14004ce50`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14001e784`
- `0x14001ed14`
- `0x140036110`
- `0x14004a1ec`
- `0x14004a4a0`
- `0x14004c1c4`
- `0x14004c794`
- `0x14004daa0`
- `0x14004dcbc`
- `0x14004dfdc`
- `0x14004e740`
- `0x14004f12c`
- `0x14004f4d0`
- `0x14004f5e4`
- `0x140050128`
- `0x14005d010`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x14004c93e`
- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x14004c93e`
- `DMCmnUtils!MBToUnicode` at `0x14004c9bb`
- `DMCmnUtils!MBToUnicode` at `0x14004c9bb`

## string_xrefs

- `0x14004cb5e`: `JobExecution::SetupCustomHeaders - User impersonation succeeded`
- `0x14004cb67`: `JobExecution::SetupCustomHeaders - User impersonation not succeeded`
- `0x14004cab9`: `JobExecution::SetupCustomHeaders - UserSID %1 and sessionID is %2!d!`
- `0x14004cb8f`: `JobExecution::StartDownload -  Failed to getJobConfig`

## pseudocode

```c
__int64 __fastcall JobExecution::SetupCustomHeaders(struct IBackgroundCopyJob **a1, bool *a2, struct _GUID *a3)
{
  bool v6; // si
  int MDMClientCert; // eax
  unsigned int CorrelationVectorForDmSession; // edi
  int UserAadToken; // eax
  int EnrollmentEntDmId; // eax
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // r8
  int SessionIDFromUserSid; // eax
  unsigned int v16; // esi
  int v17; // eax
  const wchar_t *v18; // rcx
  const unsigned __int16 *v19; // r8
  int JobConfig; // r14d
  const unsigned __int16 *v21; // r9
  int v22; // eax
  int v23; // eax
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+30h] [rbp-D0h] BYREF
  bool v27[3]; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v28; // [rsp+34h] [rbp-CCh] BYREF
  BG_CERT_STORE_LOCATION v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  int v38; // [rsp+90h] [rbp-70h]
  bool v39[4]; // [rsp+94h] [rbp-6Ch]
  _QWORD v40[4]; // [rsp+98h] [rbp-68h] BYREF
  char v41; // [rsp+B8h] [rbp-48h]
  struct IBackgroundCopyJob **v42; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v43[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v45; // [rsp+E0h] [rbp-20h]
  char v46[144]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v42 = a1;
  v6 = 0;
  v27[0] = 0;
  v26 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  *(_QWORD *)v30 = 0;
  v29 = BG_CERT_STORE_LOCATION_CURRENT_USER;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(v43[0]) = 0;
  v28 = 0;
  v37 = 0;
  v38 = 600;
  v39[0] = 1;
  v40[0] = v30;
  v40[1] = &v36;
  v40[2] = &v35;
  v40[3] = &v34;
  v41 = 1;
  v31 = *a3;
  MDMClientCert = GetMDMClientCert(
                    (unsigned int)&v31,
                    (unsigned int)&v29,
                    (unsigned int)v43,
                    (unsigned int)&v26,
                    (__int64)v30);
  CorrelationVectorForDmSession = MDMClientCert;
  if ( MDMClientCert < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
      (const char *)(unsigned int)MDMClientCert,
      v24);
    wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
    std::wstring::~wstring(v43);
    if ( *a1 )
      ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
    return CorrelationVectorForDmSession;
  }
  v31 = *a3;
  UserAadToken = FetchUserAadToken(&v31, &v36);
  CorrelationVectorForDmSession = UserAadToken;
  if ( UserAadToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
      (const char *)(unsigned int)UserAadToken,
      v24);
    wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
    std::wstring::~wstring(v43);
    if ( *a1 )
      ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
    return CorrelationVectorForDmSession;
  }
  v31 = *a3;
  EnrollmentEntDmId = GetEnrollmentEntDmId(&v31, &v35);
  CorrelationVectorForDmSession = EnrollmentEntDmId;
  if ( EnrollmentEntDmId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
      (const char *)(unsigned int)EnrollmentEntDmId,
      v24);
    wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
    std::wstring::~wstring(v43);
    if ( *a1 )
      ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
    return CorrelationVectorForDmSession;
  }
  CorrelationVectorForDmSession = GetCorrelationVectorForDmSession(v12, v46);
  if ( (CorrelationVectorForDmSession & 0x80000000) != 0
    || (v31.Data1 = 0,
        CorrelationVectorForDmSession = MBToUnicode(v46, 0xFDE9u, &v34, &v31.Data1),
        (CorrelationVectorForDmSession & 0x80000000) != 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
      (const char *)CorrelationVectorForDmSession,
      v24);
    wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
    std::wstring::~wstring(v43);
    if ( *a1 )
      ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
    return CorrelationVectorForDmSession;
  }
  if ( v26 )
  {
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*(_QWORD *)v30 + 2 * v14) );
    std::wstring::_Construct<1,unsigned short const *>(&v31, *(_QWORD *)v30);
    SessionIDFromUserSid = FindSessionIDFromUserSid(&v31, &v28);
    v16 = SessionIDFromUserSid;
    if ( SessionIDFromUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
        (const char *)(unsigned int)SessionIDFromUserSid,
        v24);
      wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
      std::wstring::~wstring(v43);
      if ( *a1 )
        ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
      return v16;
    }
    LogTelemetryInfo(L"JobExecution::SetupCustomHeaders - UserSID %1 and sessionID is %2!d!", *(_QWORD *)v30, v28);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    do
      ++v13;
    while ( *(_WORD *)(*(_QWORD *)v30 + 2 * v13) );
    std::wstring::_Construct<1,unsigned short const *>(&v31, *(_QWORD *)v30);
    v17 = ImpersonateUser((unsigned __int16 *)&v31, v28, v27);
    CorrelationVectorForDmSession = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
        (const char *)(unsigned int)v17,
        v24);
      wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
      std::wstring::~wstring(v43);
      if ( *a1 )
        ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
      return CorrelationVectorForDmSession;
    }
    v6 = v27[0];
    v18 = L"JobExecution::SetupCustomHeaders - User impersonation succeeded";
    if ( !v27[0] )
      v18 = L"JobExecution::SetupCustomHeaders - User impersonation not succeeded";
    LogTelemetryInfo(v18);
  }
  SetHelperTokens(*a1, v6);
  JobConfig = JobHelper::GetJobConfig((struct _JobConfig *)&v37);
  if ( JobConfig < 0 )
    LogTelemetryError(L"JobExecution::StartDownload -  Failed to getJobConfig");
  if ( v44 )
  {
    v21 = (const unsigned __int16 *)v43;
    if ( v45 > 7 )
      v21 = v43[0];
    v22 = SetSecurityOptions2(*a1, v29, v19, v21, v39[0], v6);
    CorrelationVectorForDmSession = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
        (const char *)(unsigned int)v22,
        v25);
      wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
      std::wstring::~wstring(v43);
      if ( *a1 )
        ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
      return CorrelationVectorForDmSession;
    }
    v23 = AttachCustomHeaders(*a1, v36, v35, v34);
    CorrelationVectorForDmSession = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobexecution.cpp",
        (const char *)(unsigned int)v23,
        v25);
      wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
      std::wstring::~wstring(v43);
      if ( *a1 )
        ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
      return CorrelationVectorForDmSession;
    }
  }
  *a2 = v6;
  wil::details::ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___::_ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___(v40);
  std::wstring::~wstring(v43);
  if ( *a1 )
    ((void (__fastcall *)(struct IBackgroundCopyJob *))(*a1)->lpVtbl->Release)(*a1);
  return (unsigned int)JobConfig;
}

```

## disassembly

```asm
0x14004c794  push    rbp
0x14004c796  push    rbx
0x14004c797  push    rsi
0x14004c798  push    rdi
0x14004c799  push    r12
0x14004c79b  push    r14
0x14004c79d  push    r15
0x14004c79f  lea     rbp, [rsp-90h]
0x14004c7a7  sub     rsp, 190h
0x14004c7ae  mov     rax, cs:__security_cookie
0x14004c7b5  xor     rax, rsp
0x14004c7b8  mov     [rbp+0C0h+var_40], rax
0x14004c7bf  mov     r14, r8
0x14004c7c2  mov     r15, rdx
0x14004c7c5  mov     rbx, rcx
0x14004c7c8  mov     [rbp+0C0h+var_100], rcx
0x14004c7cc  xor     r12d, r12d
0x14004c7cf  mov     sil, r12b
0x14004c7d2  mov     [rsp+1C0h+var_18F], r12b
0x14004c7d7  mov     [rsp+1C0h+var_190], r12b
0x14004c7dc  mov     [rbp+0C0h+var_140], r12
0x14004c7e0  mov     [rsp+1C0h+var_148], r12
0x14004c7e5  mov     [rsp+1C0h+var_150], r12
0x14004c7ea  mov     qword ptr [rsp+1C0h+var_180], r12
0x14004c7ef  mov     [rsp+1C0h+var_188], r12d
0x14004c7f4  xorps   xmm0, xmm0
0x14004c7f7  movups  xmmword ptr [rbp+0C0h+var_F8], xmm0
0x14004c7fb  mov     [rbp+0C0h+var_E8], r12
0x14004c7ff  mov     [rbp+0C0h+var_E0], 7
0x14004c807  mov     word ptr [rbp+0C0h+var_F8], r12w
0x14004c80c  mov     [rsp+1C0h+var_18C], r12d
0x14004c811  mov     [rbp+0C0h+var_138], r12
0x14004c815  mov     [rbp+0C0h+var_130], 258h
0x14004c81c  mov     [rbp+0C0h+var_12C], 1
0x14004c820  lea     rax, [rsp+1C0h+var_180]
0x14004c825  mov     [rbp+0C0h+var_128], rax
0x14004c829  lea     rax, [rbp+0C0h+var_140]
0x14004c82d  mov     [rbp+0C0h+var_120], rax
0x14004c831  lea     rax, [rsp+1C0h+var_148]
0x14004c836  mov     [rbp+0C0h+var_118], rax
0x14004c83a  lea     rax, [rsp+1C0h+var_150]
0x14004c83f  mov     [rbp+0C0h+var_110], rax
0x14004c843  mov     [rbp+0C0h+var_108], 1
0x14004c847  movaps  xmm0, xmmword ptr [r8]
0x14004c84b  movdqa  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x14004c851  lea     rax, [rsp+1C0h+var_180]
0x14004c856  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x14004c85b  lea     r9, [rsp+1C0h+var_190]
0x14004c860  lea     r8, [rbp+0C0h+var_F8]
0x14004c864  lea     rdx, [rsp+1C0h+var_188]
0x14004c869  lea     rcx, [rsp+1C0h+var_170]
0x14004c86e  call    ?GetMDMClientCert@@YAJU_GUID@@AEAW4BG_CERT_STORE_LOCATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NPEAPEAG@Z; GetMDMClientCert(_GUID,BG_CERT_STORE_LOCATION &,std::wstring &,bool &,ushort * *)
0x14004c873  mov     edi, eax
0x14004c875  test    eax, eax
0x14004c877  jns     short loc_14004C8C5
0x14004c879  mov     rcx, [rbp+0C8h]; this
0x14004c880  mov     r9d, eax; char *
0x14004c883  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004c88a  mov     edx, 0D4h; void *
0x14004c88f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004c894  nop
0x14004c895  lea     rcx, [rbp+0C0h+var_128]
0x14004c899  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004c89e  nop
0x14004c89f  lea     rcx, [rbp+0C0h+var_F8]
0x14004c8a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c8a8  nop
0x14004c8a9  mov     rcx, [rbx]
0x14004c8ac  test    rcx, rcx
0x14004c8af  jz      short loc_14004C8BE
0x14004c8b1  mov     rax, [rcx]
0x14004c8b4  mov     rax, [rax+10h]
0x14004c8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c8bd  nop
0x14004c8be  mov     eax, edi
0x14004c8c0  jmp     loc_14004CCB0
0x14004c8c5  movaps  xmm0, xmmword ptr [r14]
0x14004c8c9  movdqa  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x14004c8cf  lea     rdx, [rbp+0C0h+var_140]; unsigned __int16 **
0x14004c8d3  lea     rcx, [rsp+1C0h+var_170]; struct _GUID
0x14004c8d8  call    ?FetchUserAadToken@@YAJU_GUID@@PEAPEAG@Z; FetchUserAadToken(_GUID,ushort * *)
0x14004c8dd  mov     edi, eax
0x14004c8df  test    eax, eax
0x14004c8e1  jns     short loc_14004C92A
0x14004c8e3  mov     rcx, [rbp+0C8h]; this
0x14004c8ea  mov     r9d, eax; char *
0x14004c8ed  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004c8f4  mov     edx, 0D5h; void *
0x14004c8f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004c8fe  nop
0x14004c8ff  lea     rcx, [rbp+0C0h+var_128]
0x14004c903  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004c908  nop
0x14004c909  lea     rcx, [rbp+0C0h+var_F8]
0x14004c90d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c912  nop
0x14004c913  mov     rcx, [rbx]
0x14004c916  test    rcx, rcx
0x14004c919  jz      short loc_14004C928
0x14004c91b  mov     rax, [rcx]
0x14004c91e  mov     rax, [rax+10h]
0x14004c922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c927  nop
0x14004c928  jmp     short loc_14004C8BE
0x14004c92a  movaps  xmm0, xmmword ptr [r14]
0x14004c92e  movdqa  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x14004c934  lea     rdx, [rsp+1C0h+var_148]
0x14004c939  lea     rcx, [rsp+1C0h+var_170]
0x14004c93e  call    cs:__imp_GetEnrollmentEntDmId
0x14004c944  mov     edi, eax
0x14004c946  test    eax, eax
0x14004c948  jns     short loc_14004C994
0x14004c94a  mov     rcx, [rbp+0C8h]; this
0x14004c951  mov     r9d, eax; char *
0x14004c954  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004c95b  mov     edx, 0D6h; void *
0x14004c960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004c965  nop
0x14004c966  lea     rcx, [rbp+0C0h+var_128]
0x14004c96a  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004c96f  nop
0x14004c970  lea     rcx, [rbp+0C0h+var_F8]
0x14004c974  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c979  nop
0x14004c97a  mov     rcx, [rbx]
0x14004c97d  test    rcx, rcx
0x14004c980  jz      short loc_14004C98F
0x14004c982  mov     rax, [rcx]
0x14004c985  mov     rax, [rax+10h]
0x14004c989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c98e  nop
0x14004c98f  jmp     loc_14004C8BE
0x14004c994  lea     rdx, [rbp+0C0h+var_D0]; char *
0x14004c998  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14004c99d  mov     edi, eax
0x14004c99f  test    eax, eax
0x14004c9a1  js      short loc_14004C9C7
0x14004c9a3  mov     [rsp+1C0h+var_170.Data1], r12d
0x14004c9a8  lea     r9, [rsp+1C0h+var_170]
0x14004c9ad  lea     r8, [rsp+1C0h+var_150]
0x14004c9b2  mov     edx, 0FDE9h
0x14004c9b7  lea     rcx, [rbp+0C0h+var_D0]
0x14004c9bb  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x14004c9c1  mov     edi, eax
0x14004c9c3  test    eax, eax
0x14004c9c5  jns     short loc_14004CA11
0x14004c9c7  mov     rcx, [rbp+0C8h]; this
0x14004c9ce  mov     r9d, edi; char *
0x14004c9d1  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004c9d8  mov     edx, 0D7h; void *
0x14004c9dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004c9e2  nop
0x14004c9e3  lea     rcx, [rbp+0C0h+var_128]
0x14004c9e7  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004c9ec  nop
0x14004c9ed  lea     rcx, [rbp+0C0h+var_F8]
0x14004c9f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c9f6  nop
0x14004c9f7  mov     rcx, [rbx]
0x14004c9fa  test    rcx, rcx
0x14004c9fd  jz      short loc_14004CA0C
0x14004c9ff  mov     rdx, [rcx]
0x14004ca02  mov     rax, [rdx+10h]
0x14004ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ca0b  nop
0x14004ca0c  jmp     loc_14004C8BE
0x14004ca11  cmp     [rsp+1C0h+var_190], r12b
0x14004ca16  jz      loc_14004CB73
0x14004ca1c  mov     rdx, qword ptr [rsp+1C0h+var_180]
0x14004ca21  xorps   xmm0, xmm0
0x14004ca24  movups  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x14004ca29  mov     [rsp+1C0h+var_160], r12
0x14004ca2e  mov     [rsp+1C0h+var_158], r12
0x14004ca33  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14004ca37  mov     r8, rdi
0x14004ca3a  inc     r8
0x14004ca3d  cmp     [rdx+r8*2], r12w
0x14004ca42  jnz     short loc_14004CA3A
0x14004ca44  lea     rcx, [rsp+1C0h+var_170]
0x14004ca49  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004ca4e  lea     rdx, [rsp+1C0h+var_18C]
0x14004ca53  lea     rcx, [rsp+1C0h+var_170]
0x14004ca58  call    ?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; FindSessionIDFromUserSid(std::wstring,ulong &)
0x14004ca5d  mov     esi, eax
0x14004ca5f  test    eax, eax
0x14004ca61  jns     short loc_14004CAAF
0x14004ca63  mov     rcx, [rbp+0C8h]; this
0x14004ca6a  mov     r9d, eax; char *
0x14004ca6d  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004ca74  mov     edx, 0DBh; void *
0x14004ca79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ca7e  nop
0x14004ca7f  lea     rcx, [rbp+0C0h+var_128]
0x14004ca83  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004ca88  nop
0x14004ca89  lea     rcx, [rbp+0C0h+var_F8]
0x14004ca8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ca92  nop
0x14004ca93  mov     rcx, [rbx]
0x14004ca96  test    rcx, rcx
0x14004ca99  jz      short loc_14004CAA8
0x14004ca9b  mov     rax, [rcx]
0x14004ca9e  mov     rax, [rax+10h]
0x14004caa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004caa7  nop
0x14004caa8  mov     eax, esi
0x14004caaa  jmp     loc_14004CCB0
0x14004caaf  mov     r8d, [rsp+1C0h+var_18C]
0x14004cab4  mov     rdx, qword ptr [rsp+1C0h+var_180]
0x14004cab9  lea     rcx, aJobexecutionSe_1; "JobExecution::SetupCustomHeaders - User"...
0x14004cac0  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x14004cac5  mov     rdx, qword ptr [rsp+1C0h+var_180]
0x14004caca  xorps   xmm0, xmm0
0x14004cacd  movups  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x14004cad2  mov     [rsp+1C0h+var_160], r12
0x14004cad7  mov     [rsp+1C0h+var_158], r12
0x14004cadc  inc     rdi
0x14004cadf  cmp     [rdx+rdi*2], r12w
0x14004cae4  jnz     short loc_14004CADC
0x14004cae6  mov     r8, rdi
0x14004cae9  lea     rcx, [rsp+1C0h+var_170]
0x14004caee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004caf3  lea     r8, [rsp+1C0h+var_18F]
0x14004caf8  mov     edx, [rsp+1C0h+var_18C]; unsigned int
0x14004cafc  lea     rcx, [rsp+1C0h+var_170]; unsigned __int16 *
0x14004cb01  call    ?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; ImpersonateUser(std::wstring,ulong,bool &)
0x14004cb06  mov     edi, eax
0x14004cb08  test    eax, eax
0x14004cb0a  jns     short loc_14004CB56
0x14004cb0c  mov     rcx, [rbp+0C8h]; this
0x14004cb13  mov     r9d, eax; char *
0x14004cb16  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004cb1d  mov     edx, 0DDh; void *
0x14004cb22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004cb27  nop
0x14004cb28  lea     rcx, [rbp+0C0h+var_128]
0x14004cb2c  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004cb31  nop
0x14004cb32  lea     rcx, [rbp+0C0h+var_F8]
0x14004cb36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cb3b  nop
0x14004cb3c  mov     rcx, [rbx]
0x14004cb3f  test    rcx, rcx
0x14004cb42  jz      short loc_14004CB51
0x14004cb44  mov     rax, [rcx]
0x14004cb47  mov     rax, [rax+10h]
0x14004cb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004cb50  nop
0x14004cb51  jmp     loc_14004C8BE
0x14004cb56  mov     sil, [rsp+1C0h+var_18F]
0x14004cb5b  test    sil, sil
0x14004cb5e  lea     rcx, aJobexecutionSe_0; "JobExecution::SetupCustomHeaders - User"...
0x14004cb65  jnz     short loc_14004CB6E
0x14004cb67  lea     rcx, aJobexecutionSe; "JobExecution::SetupCustomHeaders - User"...
0x14004cb6e  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x14004cb73  movzx   edx, sil; int
0x14004cb77  mov     rcx, [rbx]; struct IBackgroundCopyJob *
0x14004cb7a  call    ?SetHelperTokens@@YAJPEAUIBackgroundCopyJob@@H@Z; SetHelperTokens(IBackgroundCopyJob *,int)
0x14004cb7f  lea     rcx, [rbp+0C0h+var_138]; struct _JobConfig *
0x14004cb83  call    ?GetJobConfig@JobHelper@@SAJAEAU_JobConfig@@@Z; JobHelper::GetJobConfig(_JobConfig &)
0x14004cb88  mov     r14d, eax
0x14004cb8b  test    eax, eax
0x14004cb8d  jns     short loc_14004CB9B
0x14004cb8f  lea     rcx, aJobexecutionSt_4; "JobExecution::StartDownload -  Failed t"...
0x14004cb96  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004cb9b  cmp     [rbp+0C0h+var_E8], r12
0x14004cb9f  jz      loc_14004CC81
0x14004cba5  lea     r9, [rbp+0C0h+var_F8]
0x14004cba9  cmp     [rbp+0C0h+var_E0], 7
0x14004cbae  cmova   r9, [rbp+0C0h+var_F8]; unsigned __int16 *
0x14004cbb3  mov     [rsp+1C0h+var_198], sil; bool
0x14004cbb8  mov     al, [rbp+0C0h+var_12C]
0x14004cbbb  mov     [rsp+1C0h+var_1A0], al; int
0x14004cbbf  mov     edx, [rsp+1C0h+var_188]; enum BG_CERT_STORE_LOCATION
0x14004cbc3  mov     rcx, [rbx]; struct IBackgroundCopyJob *
0x14004cbc6  call    ?SetSecurityOptions2@@YAJPEAUIBackgroundCopyJob@@W4BG_CERT_STORE_LOCATION@@PEBG2_N3@Z; SetSecurityOptions2(IBackgroundCopyJob *,BG_CERT_STORE_LOCATION,ushort const *,ushort const *,bool,bool)
0x14004cbcb  mov     edi, eax
0x14004cbcd  test    eax, eax
0x14004cbcf  jns     short loc_14004CC1B
0x14004cbd1  mov     rcx, [rbp+0C8h]; this
0x14004cbd8  mov     r9d, eax; char *
0x14004cbdb  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004cbe2  mov     edx, 0F9h; void *
0x14004cbe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004cbec  nop
0x14004cbed  lea     rcx, [rbp+0C0h+var_128]
0x14004cbf1  call    wil__details__ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2______ScopeExitFn__lambda_87c42ec57a30779fa782854cdcfdb5c2___
0x14004cbf6  nop
0x14004cbf7  lea     rcx, [rbp+0C0h+var_F8]
0x14004cbfb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cc00  nop
0x14004cc01  mov     rcx, [rbx]
0x14004cc04  test    rcx, rcx
0x14004cc07  jz      short loc_14004CC16
0x14004cc09  mov     rax, [rcx]
0x14004cc0c  mov     rax, [rax+10h]
0x14004cc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004cc15  nop
0x14004cc16  jmp     loc_14004C8BE
0x14004cc1b  mov     r9, [rsp+1C0h+var_150]; unsigned __int16 *
  ... truncated ...
```
