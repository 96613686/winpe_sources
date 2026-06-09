# DCEngine::AddDocToQueue(OrchestratorDCInfo,_GUID,StateMachineTypeTag)

- ea: `0x18010e580`
- end: `0x18010eb45`
- name: `?AddDocToQueue@DCEngine@@AEAAJUOrchestratorDCInfo@@U_GUID@@W4StateMachineTypeTag@@@Z`
- size: `1477`
- prototype: `int __high(struct OrchestratorDCInfo, struct _GUID, enum StateMachineTypeTag)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180113960`
- `0x1801142c4`

## callees

- `0x18000b9e0`
- `0x18000bf00`
- `0x1800117dc`
- `0x18001438c`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180058630`
- `0x180058b08`
- `0x180058b3c`
- `0x18009a2e4`
- `0x1800a1878`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100ad8`
- `0x18010de88`
- `0x18010e580`
- `0x18010fbb0`
- `0x180112a30`
- `0x18012d02c`
- `0x18012d270`
- `0x18012d40c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e627`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e703`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e627`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e703`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e5f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e68a`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e720`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e5f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e68a`
- `OLEAUT32!__imp_SysAllocString` at `0x18010e720`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010e646`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010e646`

## string_xrefs

- `0x18010e66a`: `DmGetActiveUserSid`
- `0x18010e6ad`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18010e7ba`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18010e882`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18010e9c4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18010e824`: `DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)`
- `0x18010ea1b`: `meta->CreateNotifEventHandle`
- `0x18010ea7f`: `engine->ConfigDC`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DCEngine::AddDocToQueue(DCEngine *a1, _QWORD *a2, struct _GUID *a3, unsigned int a4)
{
  DCEngine *v5; // r13
  const OLECHAR *v6; // rcx
  __int64 v7; // rdx
  const OLECHAR **v8; // r15
  const OLECHAR *v9; // rcx
  int ActiveUserSid; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v12; // r9
  _QWORD *v13; // r14
  _QWORD *v14; // r8
  const OLECHAR *v15; // rcx
  const OLECHAR *v16; // rcx
  _QWORD *v17; // rsi
  _QWORD *v18; // rdx
  CDeclaredConfigurationLogger *v19; // rax
  struct DCDocument *v20; // r12
  _QWORD *v21; // rdx
  __int64 v22; // r13
  unsigned __int16 *v23; // r14
  unsigned __int16 *v24; // rsi
  unsigned __int16 *v25; // rbx
  __int64 v26; // rdx
  unsigned __int16 *v27; // rax
  DCMetaData *v28; // rsi
  CDeclaredConfigurationLogger *v29; // rax
  const unsigned __int16 *v30; // r8
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  HKEY v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  DCMetaData *v36; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-A8h] BYREF
  void *v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v39; // [rsp+70h] [rbp-90h] BYREF
  char v40; // [rsp+80h] [rbp-80h]
  unsigned int v41; // [rsp+90h] [rbp-70h]
  BSTR v42; // [rsp+98h] [rbp-68h] BYREF
  BSTR v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  DCEngine *v47; // [rsp+B8h] [rbp-48h]
  struct _GUID *v48; // [rsp+C0h] [rbp-40h]
  struct DCDocument *v49; // [rsp+C8h] [rbp-38h]
  _BYTE *v50; // [rsp+D0h] [rbp-30h]
  _BYTE *v51; // [rsp+D8h] [rbp-28h]
  _BYTE *v52; // [rsp+E0h] [rbp-20h]
  _BYTE *v53; // [rsp+E8h] [rbp-18h]
  _BYTE *v54; // [rsp+F0h] [rbp-10h]
  _BYTE v55[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v56[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v57[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v58[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v59[32]; // [rsp+178h] [rbp+78h] BYREF
  char v60[32]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD *v61; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v41 = a4;
  v48 = a3;
  v5 = a1;
  v47 = a1;
  v61 = a2;
  v38[0] = 0;
  v43 = 0;
  v44 = 0;
  v45 = 63;
  psz = 0;
  if ( a2[3] <= 7u )
    v6 = (const OLECHAR *)a2;
  else
    v6 = (const OLECHAR *)*a2;
  v42 = SysAllocString(v6);
  if ( !v42 )
  {
    v7 = 4260;
LABEL_17:
    ActiveUserSid = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
      (const char *)0x8007000ELL,
      v32);
LABEL_80:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v42);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v38);
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)a2);
    return (unsigned int)ActiveUserSid;
  }
  v8 = (const OLECHAR **)(a2 + 4);
  if ( a2[7] <= 7u )
    v9 = (const OLECHAR *)(a2 + 4);
  else
    v9 = *v8;
  if ( !(unsigned int)_o__wcsicmp(v9, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &psz,
      0);
    ActiveUserSid = DmGetActiveUserSid(&psz);
    if ( ActiveUserSid < 0 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      if ( a2[3] <= 7u )
        v12 = (const unsigned __int16 *)a2;
      else
        v12 = (const unsigned __int16 *)*a2;
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DCEngine::AddDocToQueue",
        L"DmGetActiveUserSid",
        v12,
        ActiveUserSid);
      goto LABEL_80;
    }
    v43 = SysAllocString(psz);
    if ( !v43 )
    {
      v7 = 4274;
      goto LABEL_17;
    }
    v44 = 1;
LABEL_19:
    v34 = 0;
    *(_QWORD *)&v39.Data1 = &v34;
    *(_QWORD *)v39.Data4 = 0;
    v40 = 1;
    v13 = a2 + 12;
    if ( a2[15] <= 7u )
      LODWORD(v14) = (_DWORD)a2 + 96;
    else
      v14 = (_QWORD *)*v13;
    v17 = a2 + 8;
    if ( a2[11] <= 7u )
      LODWORD(v18) = (_DWORD)a2 + 64;
    else
      v18 = (_QWORD *)*v17;
    ActiveUserSid = GetEnrollmentIdSidStateDocIdVersionRawKey_0(
                      (unsigned int)&v42,
                      (_DWORD)v18,
                      (_DWORD)v14,
                      (unsigned int)v39.Data4,
                      0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v39);
    if ( ActiveUserSid < 0 )
    {
      if ( a2[15] > 7u )
        v13 = (_QWORD *)*v13;
      if ( a2[11] > 7u )
        v17 = (_QWORD *)*v17;
      if ( a2[3] <= 7u )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x10C6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          (int)"can't find WinDC reg key for enrollment %ws doc %ws version %ws",
          (const char *)a2,
          v17,
          v13,
          v34);
      else
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x10C6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          (int)"can't find WinDC reg key for enrollment %ws doc %ws version %ws",
          (const char *)*a2,
          v17,
          v13,
          v34);
      goto LABEL_79;
    }
    v35 = 0;
    *(_QWORD *)&v39.Data1 = &v35;
    *(_QWORD *)v39.Data4 = 0;
    v40 = 1;
    ActiveUserSid = DCCDNUtil_GetRegistryString(v34, 0, L"osdefinedscenario", (unsigned __int16 **)v39.Data4);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v39);
    if ( ActiveUserSid < 0 )
    {
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v19,
        L"DCEngine::AddDocToQueue",
        L"DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)",
        &word_180142E98,
        ActiveUserSid);
      if ( a2[15] > 7u )
        v13 = (_QWORD *)*v13;
      if ( a2[11] > 7u )
        v17 = (_QWORD *)*v17;
      if ( a2[3] <= 7u )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x10D0,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          (int)"can't find OSDefinedScenario for enrollment %ws doc %ws version %ws",
          (const char *)a2,
          v17,
          v13);
      else
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x10D0,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          (int)"can't find OSDefinedScenario for enrollment %ws doc %ws version %ws",
          (const char *)*a2,
          v17,
          v13);
      goto LABEL_78;
    }
    v36 = 0;
    v20 = (struct DCDocument *)operator new(0x388u, (const struct std::nothrow_t *)std::nothrow);
    v49 = v20;
    if ( v20 )
    {
      v50 = v55;
      v46 = std::wstring::wstring((__int64)v55, v35);
      v51 = v56;
      v21 = a2 + 16;
      if ( a2[19] > 7u )
        v21 = (_QWORD *)*v21;
      v22 = std::wstring::wstring((__int64)v56, (__int64)v21);
      v52 = v57;
      if ( a2[15] > 7u )
        v13 = (_QWORD *)*v13;
      v23 = (unsigned __int16 *)std::wstring::wstring((__int64)v57, (__int64)v13);
      v53 = v58;
      if ( a2[11] > 7u )
        v17 = (_QWORD *)*v17;
      v24 = (unsigned __int16 *)std::wstring::wstring((__int64)v58, (__int64)v17);
      v54 = v59;
      if ( a2[7] > 7u )
        v8 = (const OLECHAR **)*v8;
      v25 = (unsigned __int16 *)std::wstring::wstring((__int64)v59, (__int64)v8);
      if ( a2[3] <= 7u )
        v26 = (__int64)a2;
      else
        v26 = *a2;
      v27 = (unsigned __int16 *)std::wstring::wstring((__int64)v60, v26);
      v28 = (DCMetaData *)DCMetaData::DCMetaData(v20, v27, v25, v24, v23, v22, v46);
      v5 = v47;
    }
    else
    {
      v28 = 0;
    }
    v36 = v28;
    if ( !v28 )
    {
      ActiveUserSid = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
        (const char *)0x8007000ELL,
        v33);
LABEL_77:
      std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(&v36);
LABEL_78:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
LABEL_79:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      goto LABEL_80;
    }
    v39 = *v48;
    ActiveUserSid = DCMetaData::set_Key(v28, &v39);
    if ( ActiveUserSid >= 0 )
    {
      ActiveUserSid = DCMetaData::CreateNotifEventHandle(v28);
      if ( ActiveUserSid >= 0 )
      {
        *((_DWORD *)v28 + 218) = 3;
        ActiveUserSid = (*(__int64 (__fastcall **)(DCEngine *, _QWORD))(*(_QWORD *)v5 + 48LL))(v5, v41);
        if ( ActiveUserSid >= 0 )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            v38,
            0);
          ActiveUserSid = DCEngine::ConfigDC(v5, v28, 1, v38);
          if ( ActiveUserSid >= 0 )
            goto LABEL_77;
          v29 = CDeclaredConfigurationLogger::GetLogger();
          v30 = L"engine->ConfigDC";
        }
        else
        {
          v29 = CDeclaredConfigurationLogger::GetLogger();
          v30 = L"engine->SetStateMachine";
        }
      }
      else
      {
        v29 = CDeclaredConfigurationLogger::GetLogger();
        v30 = L"meta->CreateNotifEventHandle";
      }
    }
    else
    {
      v29 = CDeclaredConfigurationLogger::GetLogger();
      v30 = L"meta->set_Key";
    }
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v29,
      L"DCEngine::AddDocToQueue",
      v30,
      &word_180142E98,
      ActiveUserSid);
    goto LABEL_77;
  }
  if ( a2[7] <= 7u )
    v15 = (const OLECHAR *)(a2 + 4);
  else
    v15 = *v8;
  if ( !(unsigned int)_o__wcsicmp(v15, L"device") )
  {
    if ( a2[7] <= 7u )
      v16 = (const OLECHAR *)(a2 + 4);
    else
      v16 = *v8;
    v43 = SysAllocString(v16);
    if ( !v43 )
    {
      v7 = 4280;
      goto LABEL_17;
    }
    goto LABEL_19;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v42);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v38);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)a2);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18010e580  mov     [rsp-8+arg_10], rbx
0x18010e585  push    rbp
0x18010e586  push    rsi
0x18010e587  push    rdi
0x18010e588  push    r12
0x18010e58a  push    r13
0x18010e58c  push    r14
0x18010e58e  push    r15
0x18010e590  lea     rbp, [rsp-0D0h]
0x18010e598  sub     rsp, 1D0h
0x18010e59f  mov     rax, cs:__security_cookie
0x18010e5a6  xor     rax, rsp
0x18010e5a9  mov     [rbp+100h+var_40], rax
0x18010e5b0  mov     [rbp+100h+var_170], r9d
0x18010e5b4  mov     [rbp+100h+var_140], r8
0x18010e5b8  mov     rdi, rdx
0x18010e5bb  mov     r13, rcx
0x18010e5be  mov     [rbp+100h+var_148], rcx
0x18010e5c2  mov     [rbp+100h+var_48], rdx
0x18010e5c9  xor     r12d, r12d
0x18010e5cc  mov     [rsp+200h+var_1A0], r12
0x18010e5d1  mov     [rbp+100h+var_160], r12
0x18010e5d5  mov     [rbp+100h+var_158], r12d
0x18010e5d9  mov     [rbp+100h+var_154], 3Fh ; '?'
0x18010e5e0  mov     [rsp+200h+psz], r12
0x18010e5e5  cmp     qword ptr [rdx+18h], 7
0x18010e5ea  jbe     short loc_18010E5F1
0x18010e5ec  mov     rcx, [rdx]
0x18010e5ef  jmp     short loc_18010E5F4
0x18010e5f1  mov     rcx, rdi; psz
0x18010e5f4  call    cs:__imp_SysAllocString
0x18010e5fa  mov     [rbp+100h+var_168], rax
0x18010e5fe  test    rax, rax
0x18010e601  jnz     short loc_18010E60D
0x18010e603  mov     edx, 10A4h
0x18010e608  jmp     loc_18010E69E
0x18010e60d  lea     r15, [rdi+20h]
0x18010e611  cmp     qword ptr [r15+18h], 7
0x18010e616  jbe     short loc_18010E61D
0x18010e618  mov     rcx, [r15]
0x18010e61b  jmp     short loc_18010E620
0x18010e61d  mov     rcx, r15
0x18010e620  lea     rdx, aUser_0; "user"
0x18010e627  call    cs:__imp__o__wcsicmp
0x18010e62d  test    eax, eax
0x18010e62f  jnz     loc_18010E6ED
0x18010e635  xor     edx, edx
0x18010e637  lea     rcx, [rsp+200h+psz]
0x18010e63c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010e641  lea     rcx, [rsp+200h+psz]
0x18010e646  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18010e64c  mov     ebx, eax
0x18010e64e  test    eax, eax
0x18010e650  jns     short loc_18010E685
0x18010e652  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18010e657  cmp     qword ptr [rdi+18h], 7
0x18010e65c  jbe     short loc_18010E663
0x18010e65e  mov     r9, [rdi]
0x18010e661  jmp     short loc_18010E666
0x18010e663  mov     r9, rdi; unsigned __int16 *
0x18010e666  mov     dword ptr [rsp+200h+var_1E0], ebx; int
0x18010e66a  lea     r8, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x18010e671  lea     rdx, aDcengineAdddoc; "DCEngine::AddDocToQueue"
0x18010e678  mov     rcx, rax; this
0x18010e67b  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18010e680  jmp     loc_18010EAC2
0x18010e685  mov     rcx, [rsp+200h+psz]; psz
0x18010e68a  call    cs:__imp_SysAllocString
0x18010e690  mov     [rbp+100h+var_160], rax
0x18010e694  test    rax, rax
0x18010e697  jnz     short loc_18010E6BE
0x18010e699  mov     edx, 10B2h; void *
0x18010e69e  mov     ebx, 8007000Eh
0x18010e6a3  mov     rcx, [rbp+108h]; this
0x18010e6aa  mov     r9d, ebx; char *
0x18010e6ad  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010e6b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e6b9  jmp     loc_18010EAC2
0x18010e6be  mov     [rbp+100h+var_158], 1
0x18010e6c5  mov     [rsp+200h+var_1C0], r12
0x18010e6ca  lea     rax, [rsp+200h+var_1C0]
0x18010e6cf  mov     qword ptr [rsp+200h+var_190.Data1], rax
0x18010e6d4  mov     qword ptr [rsp+200h+var_190.Data4], r12
0x18010e6d9  mov     [rbp+100h+var_180], 1
0x18010e6dd  lea     r14, [rdi+60h]
0x18010e6e1  cmp     qword ptr [r14+18h], 7
0x18010e6e6  jbe     short loc_18010E739
0x18010e6e8  mov     r8, [r14]
0x18010e6eb  jmp     short loc_18010E73C
0x18010e6ed  cmp     qword ptr [r15+18h], 7
0x18010e6f2  jbe     short loc_18010E6F9
0x18010e6f4  mov     rcx, [r15]
0x18010e6f7  jmp     short loc_18010E6FC
0x18010e6f9  mov     rcx, r15
0x18010e6fc  lea     rdx, aDevice_4; "device"
0x18010e703  call    cs:__imp__o__wcsicmp
0x18010e709  test    eax, eax
0x18010e70b  jnz     loc_18010EAEE
0x18010e711  cmp     qword ptr [r15+18h], 7
0x18010e716  jbe     short loc_18010E71D
0x18010e718  mov     rcx, [r15]
0x18010e71b  jmp     short loc_18010E720
0x18010e71d  mov     rcx, r15; psz
0x18010e720  call    cs:__imp_SysAllocString
0x18010e726  mov     [rbp+100h+var_160], rax
0x18010e72a  test    rax, rax
0x18010e72d  jnz     short loc_18010E6C5
0x18010e72f  mov     edx, 10B8h
0x18010e734  jmp     loc_18010E69E
0x18010e739  mov     r8, r14
0x18010e73c  lea     rsi, [rdi+40h]
0x18010e740  cmp     qword ptr [rsi+18h], 7
0x18010e745  jbe     short loc_18010E74C
0x18010e747  mov     rdx, [rsi]
0x18010e74a  jmp     short loc_18010E74F
0x18010e74c  mov     rdx, rsi
0x18010e74f  mov     dword ptr [rsp+200h+var_1E0], r12d; int
0x18010e754  lea     r9, [rsp+200h+var_190.Data4]
0x18010e759  lea     rcx, [rbp+100h+var_168]
0x18010e75d  call    GetEnrollmentIdSidStateDocIdVersionRawKey_0
0x18010e762  mov     ebx, eax
0x18010e764  lea     rcx, [rsp+200h+var_190]
0x18010e769  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18010e76e  test    ebx, ebx
0x18010e770  jns     short loc_18010E7D0
0x18010e772  cmp     qword ptr [r14+18h], 7
0x18010e777  jbe     short loc_18010E77C
0x18010e779  mov     r14, [r14]
0x18010e77c  cmp     qword ptr [rsi+18h], 7
0x18010e781  jbe     short loc_18010E786
0x18010e783  mov     rsi, [rsi]
0x18010e786  cmp     qword ptr [rdi+18h], 7
0x18010e78b  jbe     short loc_18010E792
0x18010e78d  mov     rax, [rdi]
0x18010e790  jmp     short loc_18010E795
0x18010e792  mov     rax, rdi
0x18010e795  mov     rcx, [rbp+108h]; this
0x18010e79c  mov     [rsp+200h+var_1C8], r14
0x18010e7a1  mov     [rsp+200h+var_1D0], rsi
0x18010e7a6  mov     [rsp+200h+var_1D8], rax; char *
0x18010e7ab  lea     rax, aCanTFindWindcR; "can't find WinDC reg key for enrollment"...
0x18010e7b2  mov     [rsp+200h+var_1E0], rax; int
0x18010e7b7  mov     r9d, ebx; char *
0x18010e7ba  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010e7c1  mov     edx, 10C6h; void *
0x18010e7c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010e7cb  jmp     loc_18010EAB7
0x18010e7d0  mov     [rsp+200h+var_1B8], r12
0x18010e7d5  lea     rax, [rsp+200h+var_1B8]
0x18010e7da  mov     qword ptr [rsp+200h+var_190.Data1], rax
0x18010e7df  mov     qword ptr [rsp+200h+var_190.Data4], r12
0x18010e7e4  mov     [rbp+100h+var_180], 1
0x18010e7e8  lea     r9, [rsp+200h+var_190.Data4]; unsigned __int16 **
0x18010e7ed  lea     r8, aOsdefinedscena; "osdefinedscenario"
0x18010e7f4  xor     edx, edx; unsigned __int16 *
0x18010e7f6  mov     rcx, [rsp+200h+var_1C0]; HKEY
0x18010e7fb  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18010e800  mov     ebx, eax
0x18010e802  lea     rcx, [rsp+200h+var_190]
0x18010e807  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18010e80c  test    ebx, ebx
0x18010e80e  jns     loc_18010E898
0x18010e814  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18010e819  mov     dword ptr [rsp+200h+var_1E0], ebx; int
0x18010e81d  lea     r9, word_180142E98; unsigned __int16 *
0x18010e824  lea     r8, aDccdnutilGetre_11; "DCCDNUtil_GetRegistryString(docIdVersio"...
0x18010e82b  lea     rdx, aDcengineAdddoc; "DCEngine::AddDocToQueue"
0x18010e832  mov     rcx, rax; this
0x18010e835  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18010e83a  cmp     qword ptr [r14+18h], 7
0x18010e83f  jbe     short loc_18010E844
0x18010e841  mov     r14, [r14]
0x18010e844  cmp     qword ptr [rsi+18h], 7
0x18010e849  jbe     short loc_18010E84E
0x18010e84b  mov     rsi, [rsi]
0x18010e84e  cmp     qword ptr [rdi+18h], 7
0x18010e853  jbe     short loc_18010E85A
0x18010e855  mov     rax, [rdi]
0x18010e858  jmp     short loc_18010E85D
0x18010e85a  mov     rax, rdi
0x18010e85d  mov     rcx, [rbp+108h]; this
0x18010e864  mov     [rsp+200h+var_1C8], r14
0x18010e869  mov     [rsp+200h+var_1D0], rsi
0x18010e86e  mov     [rsp+200h+var_1D8], rax; char *
0x18010e873  lea     rax, aCanTFindOsdefi_0; "can't find OSDefinedScenario for enroll"...
0x18010e87a  mov     [rsp+200h+var_1E0], rax; int
0x18010e87f  mov     r9d, ebx; char *
0x18010e882  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010e889  mov     edx, 10D0h; void *
0x18010e88e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010e893  jmp     loc_18010EAAC
0x18010e898  mov     [rsp+200h+var_1B0], r12
0x18010e89d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010e8a4  mov     ecx, 388h; unsigned __int64
0x18010e8a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18010e8ae  mov     r12, rax
0x18010e8b1  mov     [rbp+100h+var_138], rax
0x18010e8b5  test    rax, rax
0x18010e8b8  jz      loc_18010E9A9
0x18010e8be  lea     rax, [rbp+100h+var_108]
0x18010e8c2  mov     [rbp+100h+var_130], rax
0x18010e8c6  mov     rdx, [rsp+200h+var_1B8]
0x18010e8cb  lea     rcx, [rbp+100h+var_108]
0x18010e8cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e8d4  mov     [rbp+100h+var_150], rax
0x18010e8d8  lea     rax, [rbp+100h+var_E8]
0x18010e8dc  mov     [rbp+100h+var_128], rax
0x18010e8e0  lea     rdx, [rdi+80h]
0x18010e8e7  cmp     qword ptr [rdx+18h], 7
0x18010e8ec  jbe     short loc_18010E8F1
0x18010e8ee  mov     rdx, [rdx]
0x18010e8f1  lea     rcx, [rbp+100h+var_E8]
0x18010e8f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e8fa  mov     r13, rax
0x18010e8fd  lea     rax, [rbp+100h+var_C8]
0x18010e901  mov     [rbp+100h+var_120], rax
0x18010e905  cmp     qword ptr [r14+18h], 7
0x18010e90a  jbe     short loc_18010E90F
0x18010e90c  mov     r14, [r14]
0x18010e90f  mov     rdx, r14
0x18010e912  lea     rcx, [rbp+100h+var_C8]
0x18010e916  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e91b  mov     r14, rax
0x18010e91e  lea     rax, [rbp+100h+var_A8]
0x18010e922  mov     [rbp+100h+var_118], rax
0x18010e926  cmp     qword ptr [rsi+18h], 7
0x18010e92b  jbe     short loc_18010E930
0x18010e92d  mov     rsi, [rsi]
0x18010e930  mov     rdx, rsi
0x18010e933  lea     rcx, [rbp+100h+var_A8]
0x18010e937  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e93c  mov     rsi, rax
0x18010e93f  lea     rax, [rbp+100h+var_88]
0x18010e943  mov     [rbp+100h+var_110], rax
0x18010e947  cmp     qword ptr [r15+18h], 7
0x18010e94c  jbe     short loc_18010E951
0x18010e94e  mov     r15, [r15]
0x18010e951  mov     rdx, r15
0x18010e954  lea     rcx, [rbp+100h+var_88]
0x18010e958  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e95d  mov     rbx, rax
0x18010e960  cmp     qword ptr [rdi+18h], 7
0x18010e965  jbe     short loc_18010E96C
0x18010e967  mov     rdx, [rdi]
0x18010e96a  jmp     short loc_18010E96F
0x18010e96c  mov     rdx, rdi
0x18010e96f  lea     rcx, [rbp+100h+var_68]
0x18010e976  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e97b  nop
0x18010e97c  mov     rcx, [rbp+100h+var_150]
0x18010e980  mov     [rsp+200h+var_1D0], rcx; __int64
0x18010e985  mov     [rsp+200h+var_1D8], r13; __int64
0x18010e98a  mov     [rsp+200h+var_1E0], r14; unsigned __int16 *
0x18010e98f  mov     r9, rsi; unsigned __int16 *
0x18010e992  mov     r8, rbx; unsigned __int16 *
0x18010e995  mov     rdx, rax; unsigned __int16 *
0x18010e998  mov     rcx, r12; struct DCDocument *
0x18010e99b  call    ??0DCMetaData@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00000@Z; DCMetaData::DCMetaData(std::wstring,std::wstring,std::wstring,std::wstring,std::wstring,std::wstring)
0x18010e9a0  mov     rsi, rax
0x18010e9a3  mov     r13, [rbp+100h+var_148]
0x18010e9a7  jmp     short loc_18010E9AB
0x18010e9a9  xor     esi, esi
0x18010e9ab  mov     [rsp+200h+var_1B0], rsi
0x18010e9b0  test    rsi, rsi
0x18010e9b3  jnz     short loc_18010E9DA
0x18010e9b5  mov     rcx, [rbp+108h]; this
0x18010e9bc  mov     ebx, 8007000Eh
0x18010e9c1  mov     r9d, ebx; char *
0x18010e9c4  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010e9cb  mov     edx, 10D6h; void *
0x18010e9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e9d5  jmp     loc_18010EAA1
0x18010e9da  mov     rax, [rbp+100h+var_140]
0x18010e9de  movaps  xmm0, xmmword ptr [rax]
0x18010e9e1  movdqa  xmmword ptr [rsp+200h+var_190.Data1], xmm0
0x18010e9e7  lea     rdx, [rsp+200h+var_190]; struct _GUID
0x18010e9ec  mov     rcx, rsi; this
0x18010e9ef  call    ?set_Key@DCMetaData@@QEAAJU_GUID@@@Z; DCMetaData::set_Key(_GUID)
0x18010e9f4  mov     ebx, eax
0x18010e9f6  test    eax, eax
0x18010e9f8  jns     short loc_18010EA08
0x18010e9fa  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18010e9ff  lea     r8, aMetaSetKey; "meta->set_Key"
0x18010ea06  jmp     short loc_18010EA86
0x18010ea08  mov     rcx, rsi; this
0x18010ea0b  call    ?CreateNotifEventHandle@DCMetaData@@QEAAJXZ; DCMetaData::CreateNotifEventHandle(void)
0x18010ea10  mov     ebx, eax
0x18010ea12  test    eax, eax
0x18010ea14  jns     short loc_18010EA24
0x18010ea16  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18010ea1b  lea     r8, aMetaCreatenoti; "meta->CreateNotifEventHandle"
0x18010ea22  jmp     short loc_18010EA86
0x18010ea24  mov     dword ptr [rsi+368h], 3
0x18010ea2e  mov     rax, [r13+0]
0x18010ea32  mov     edx, [rbp+100h+var_170]
0x18010ea35  mov     rcx, r13
0x18010ea38  mov     rax, [rax+30h]
0x18010ea3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea41  mov     ebx, eax
0x18010ea43  test    eax, eax
  ... truncated ...
```
