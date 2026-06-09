# ScheduleUserLogonTask(ushort const *,ushort const *,DMAlertType)

- ea: `0x140031bc4`
- end: `0x1400326b5`
- name: `?ScheduleUserLogonTask@@YAJPEBG0W4DMAlertType@@@Z`
- size: `2801`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140012178`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x140009fc4`
- `0x14000a0fc`
- `0x14001ea48`
- `0x14001ef20`
- `0x14001ef94`
- `0x14002e088`
- `0x14002f150`
- `0x140031bc4`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003218c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003218c`
- `OLEAUT32!__imp_SysAllocString` at `0x14003243c`
- `OLEAUT32!__imp_SysAllocString` at `0x14003243c`
- `OLEAUT32!__imp_VariantInit` at `0x140032411`
- `OLEAUT32!__imp_VariantInit` at `0x140032424`
- `OLEAUT32!__imp_VariantInit` at `0x140032411`
- `OLEAUT32!__imp_VariantInit` at `0x140032424`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140032182`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140032182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003252f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400325ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003252f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400325ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140032079`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140032079`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140031e7c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140031f61`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003209c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400321f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140032535`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400325b1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140031e7c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140031f61`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003209c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400321f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140032535`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400325b1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140031e28`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140031e28`

## string_xrefs

- `0x140031d45`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x140031d35`: `/s "%s" /c /Win10SModeAlert /SID "%s"`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScheduleUserLogonTask(__int64 a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HRESULT v5; // ebx
  const unsigned __int16 *v7; // rbx
  const unsigned __int16 *v8; // r14
  __int64 v9; // rdx
  struct ITaskDefinition *v10; // rcx
  const unsigned __int16 *v11; // rcx
  int v12; // eax
  struct ITaskDefinition *v13; // rbx
  int v14; // esi
  __int64 v15; // rdx
  struct ITaskFolderVtbl *lpVtbl; // rax
  signed int LastError; // eax
  signed int v18; // edi
  signed int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64); // rsi
  struct ITaskFolder *v23; // rdi
  struct ITaskFolderVtbl *v24; // rsi
  __int128 v25; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v27; // xmm8
  IRecordInfo *v28; // xmm9_8
  BSTR v29; // rax
  __int64 v30; // xmm11_8
  __int128 v31; // xmm10
  _bstr_t *v32; // rax
  __int64 v33; // rdx
  HRESULT (__stdcall *RegisterTaskDefinition)(ITaskFolder *, BSTR, ITaskDefinition *, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // rax
  int ReferencedDomainName; // [rsp+28h] [rbp-E0h]
  int ReferencedDomainNamea; // [rsp+28h] [rbp-E0h]
  int ReferencedDomainNameb; // [rsp+28h] [rbp-E0h]
  __int64 v38; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A8h] BYREF
  struct ITaskDefinition *v40; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-98h] BYREF
  __int64 v42; // [rsp+78h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h]
  struct ITaskFolder *v44; // [rsp+88h] [rbp-80h] BYREF
  PSID Sid; // [rsp+90h] [rbp-78h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp-70h] BYREF
  struct ITaskDefinition *v47; // [rsp+A0h] [rbp-68h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cchName; // [rsp+ACh] [rbp-5Ch] BYREF
  __int128 v50; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-48h]
  VARIANTARG v52; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v54; // [rsp+F8h] [rbp-10h]
  IRecordInfo *v55; // [rsp+108h] [rbp+0h]
  __int128 v56; // [rsp+118h] [rbp+10h]
  IRecordInfo *v57; // [rsp+128h] [rbp+20h]
  int v58[4]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v59; // [rsp+148h] [rbp+40h]
  WCHAR v60[128]; // [rsp+158h] [rbp+50h] BYREF
  WCHAR Name[128]; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int16 v62[264]; // [rsp+358h] [rbp+250h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F0h] [rbp+4E8h]

  v47 = 0;
  v40 = 0;
  v43 = 0;
  v44 = 0;
  v42 = 0;
  v39 = 0;
  v41 = 0;
  v38 = 0;
  Sid = 0;
  cchName = 128;
  cchReferencedDomainName = 128;
  peUse = SidTypeInvalid;
  if ( (_DWORD)a3 )
  {
    if ( (_DWORD)a3 != 1 )
    {
      v5 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF64,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)0x8000FFFFLL,
        ReferencedDomainName);
      return (unsigned int)v5;
    }
    v7 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
    v8 = L"Win10 S Mode alert to server after user logs on";
  }
  else
  {
    v7 = L"/s \"%s\" /c /OsEditionUpgradeAlert /SID \"%s\"";
    v8 = L"OS Edition Upgrade alert to server after user logs on";
  }
  DeleteTask(v8, a2, a3);
  v5 = StringCchPrintfW(v62, 0x104u, v7, a1);
  if ( v5 < 0 )
  {
    v9 = 3952;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      (int)a2);
    v10 = v40;
LABEL_10:
    if ( v10 )
      ((void (*)(void))v10->lpVtbl->Release)();
    return (unsigned int)v5;
  }
  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
  {
    v9 = 3954;
    goto LABEL_9;
  }
  v12 = CreateTaskForUser(v11, &v47, &v44, v62, a2);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF74,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v12,
      ReferencedDomainNamea);
    CoUninitialize();
    if ( v44 )
      ((void (__fastcall *)(struct ITaskFolder *))v44->lpVtbl->Release)(v44);
    v10 = v47;
    goto LABEL_10;
  }
  v13 = v47;
  v14 = ((__int64 (__fastcall *)(struct ITaskDefinition *, struct ITaskDefinition **))v47->lpVtbl->get_Triggers)(
          v47,
          &v40);
  if ( v14 < 0 )
  {
    v15 = 3957;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v14,
      ReferencedDomainNamea);
    CoUninitialize();
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( !v44 )
      goto LABEL_29;
    lpVtbl = v44->lpVtbl;
LABEL_28:
    ((void (*)(void))lpVtbl->Release)();
LABEL_29:
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v40 )
      ((void (__fastcall *)(struct ITaskDefinition *))v40->lpVtbl->Release)(v40);
    if ( v13 )
      ((void (__fastcall *)(struct ITaskDefinition *))v13->lpVtbl->Release)(v13);
    return (unsigned int)v14;
  }
  v14 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64, __int64 *))v40->lpVtbl->put_Triggers)(v40, 9, &v42);
  if ( v14 < 0 )
  {
    v15 = 3958;
    goto LABEL_20;
  }
  v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v42)(v42, &IID_ILogonTrigger, &v39);
  if ( v14 < 0 )
  {
    v15 = 3959;
    goto LABEL_20;
  }
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_43;
  }
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, v60, &cchReferencedDomainName, &peUse) )
  {
    v19 = GetLastError();
    v18 = v19;
    if ( v19 > 0 )
      v18 = (unsigned __int16)v19 | 0x80070000;
    LocalFree(Sid);
LABEL_43:
    CoUninitialize();
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v44 )
      ((void (__fastcall *)(struct ITaskFolder *))v44->lpVtbl->Release)(v44);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v40 )
      ((void (__fastcall *)(struct ITaskDefinition *))v40->lpVtbl->Release)(v40);
    if ( !v13 )
      return (unsigned int)v18;
    goto LABEL_56;
  }
  v18 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v13->lpVtbl->get_Settings)(v13, &v41);
  if ( v18 < 0 )
  {
    v20 = 3975;
    goto LABEL_64;
  }
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(
          v41,
          &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
          &v38);
  if ( v18 < 0 )
  {
    v20 = 3976;
    goto LABEL_64;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 208LL))(v38, 0xFFFFFFFFLL);
  if ( v18 < 0 )
  {
    v20 = 3977;
    goto LABEL_64;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 176LL))(v38, 0xFFFFFFFFLL);
  if ( v18 < 0 )
  {
    v20 = 3978;
    goto LABEL_64;
  }
  cchReferencedDomainName = 128;
  v18 = StringCchCatW(v60, 0x80u, L"\\");
  if ( v18 < 0 )
  {
    v20 = 3981;
    goto LABEL_64;
  }
  v18 = StringCchCatW(v60, cchReferencedDomainName, Name);
  if ( v18 < 0 )
  {
    v20 = 3982;
    goto LABEL_64;
  }
  v21 = v39;
  v22 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 184LL);
  _bstr_t::_bstr_t((_bstr_t *)&v47, v60);
  v18 = v22(v21);
  _bstr_t::~_bstr_t((_bstr_t *)&v47);
  if ( v18 < 0 )
  {
    v20 = 3984;
    goto LABEL_64;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 152LL))(v39, 0xFFFFFFFFLL);
  if ( v18 < 0 )
  {
    v20 = 3985;
    goto LABEL_64;
  }
  v18 = ((__int64 (__fastcall *)(struct ITaskDefinition *, struct ITaskDefinition *))v13->lpVtbl->put_Triggers)(
          v13,
          v40);
  if ( v18 < 0 )
  {
    v20 = 3986;
LABEL_64:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v18,
      ReferencedDomainNameb);
    LocalFree(Sid);
    CoUninitialize();
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v44 )
      ((void (__fastcall *)(struct ITaskFolder *))v44->lpVtbl->Release)(v44);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v40 )
      ((void (__fastcall *)(struct ITaskDefinition *))v40->lpVtbl->Release)(v40);
    if ( !v13 )
      return (unsigned int)v18;
LABEL_56:
    ((void (__fastcall *)(struct ITaskDefinition *))v13->lpVtbl->Release)(v13);
    return (unsigned int)v18;
  }
  v23 = v44;
  v24 = v44->lpVtbl;
  VariantInit(&pvarg);
  v25 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v52);
  v27 = *(_OWORD *)&v52.vt;
  v28 = v52.pRecInfo;
  v29 = SysAllocString(L"S-1-5-18");
  if ( !v29 )
    _com_issue_error(-2147024882);
  v30 = v51;
  LOWORD(v50) = 8;
  *((_QWORD *)&v50 + 1) = v29;
  v31 = v50;
  v32 = _bstr_t::_bstr_t((_bstr_t *)&v47, v8);
  if ( *(_QWORD *)v32 )
    v33 = **(_QWORD **)v32;
  else
    v33 = 0;
  v54 = v25;
  v55 = pRecInfo;
  v56 = v27;
  RegisterTaskDefinition = v24->RegisterTaskDefinition;
  v57 = v28;
  *(_OWORD *)v58 = v31;
  v59 = v30;
  v14 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct ITaskDefinition *, __int64))RegisterTaskDefinition)(
          v23,
          v33,
          v13,
          6);
  _bstr_t::~_bstr_t((_bstr_t *)&v47);
  _variant_t::~_variant_t((_variant_t *)&v50);
  _variant_t::~_variant_t((_variant_t *)&v52);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v14,
      (int)v58);
    LocalFree(Sid);
    CoUninitialize();
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( !v23 )
      goto LABEL_29;
    lpVtbl = v23->lpVtbl;
    goto LABEL_28;
  }
  LocalFree(Sid);
  CoUninitialize();
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v23 )
    ((void (__fastcall *)(struct ITaskFolder *))v23->lpVtbl->Release)(v23);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v40 )
    ((void (__fastcall *)(struct ITaskDefinition *))v40->lpVtbl->Release)(v40);
  if ( v13 )
    ((void (__fastcall *)(struct ITaskDefinition *))v13->lpVtbl->Release)(v13);
  return 0;
}

```

## disassembly

```asm
0x140031bc4  mov     rax, rsp
0x140031bc7  mov     [rax+18h], rbx
0x140031bcb  mov     [rax+20h], rsi
0x140031bcf  push    rbp
0x140031bd0  push    rdi
0x140031bd1  push    r14
0x140031bd3  lea     rbp, [rax-4E8h]
0x140031bda  sub     rsp, 5D0h
0x140031be1  movaps  xmmword ptr [rax-28h], xmm6
0x140031be5  movaps  xmmword ptr [rax-38h], xmm7
0x140031be9  movaps  xmmword ptr [rax-48h], xmm8
0x140031bee  movaps  xmmword ptr [rax-58h], xmm9
0x140031bf3  movaps  xmmword ptr [rax-68h], xmm10
0x140031bf8  movaps  xmmword ptr [rax-78h], xmm11
0x140031bfd  mov     rax, cs:__security_cookie
0x140031c04  xor     rax, rsp
0x140031c07  mov     [rbp+4E0h+var_80], rax
0x140031c0e  mov     [rbp+4E0h+var_548], 0
0x140031c16  mov     rdi, rdx
0x140031c19  mov     [rsp+5E0h+var_580], 0
0x140031c22  mov     rsi, rcx
0x140031c25  mov     [rsp+5E0h+var_568], 0
0x140031c2e  mov     [rbp+4E0h+var_560], 0
0x140031c36  mov     [rsp+5E0h+var_570], 0
0x140031c3f  mov     [rsp+5E0h+var_588], 0
0x140031c48  mov     [rsp+5E0h+var_578], 0
0x140031c51  mov     [rsp+5E0h+var_590], 0
0x140031c5a  mov     [rbp+4E0h+Sid], 0
0x140031c62  mov     [rbp+4E0h+cchName], 80h
0x140031c69  mov     [rbp+4E0h+var_550], 80h
0x140031c70  mov     [rbp+4E0h+var_540], 7
0x140031c77  test    r8d, r8d
0x140031c7a  jz      loc_140031D45
0x140031c80  cmp     r8d, 1
0x140031c84  jz      loc_140031D35
0x140031c8a  mov     rcx, [rbp+4E8h]; this
0x140031c91  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140031c98  mov     ebx, 8000FFFFh
0x140031c9d  mov     edx, 0F64h; void *
0x140031ca2  mov     r9d, ebx; char *
0x140031ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031caa  mov     rcx, [rsp+5E0h+var_590]
0x140031caf  test    rcx, rcx
0x140031cb2  jz      short loc_140031CC0
0x140031cb4  mov     rax, [rcx]
0x140031cb7  mov     rax, [rax+10h]
0x140031cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031cc0  mov     rcx, [rsp+5E0h+var_578]
0x140031cc5  test    rcx, rcx
0x140031cc8  jz      short loc_140031CD6
0x140031cca  mov     rax, [rcx]
0x140031ccd  mov     rax, [rax+10h]
0x140031cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031cd6  mov     rcx, [rsp+5E0h+var_588]
0x140031cdb  test    rcx, rcx
0x140031cde  jz      short loc_140031CEC
0x140031ce0  mov     rax, [rcx]
0x140031ce3  mov     rax, [rax+10h]
0x140031ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031cec  mov     rcx, [rsp+5E0h+var_570]
0x140031cf1  test    rcx, rcx
0x140031cf4  jz      short loc_140031D02
0x140031cf6  mov     rax, [rcx]
0x140031cf9  mov     rax, [rax+10h]
0x140031cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031d02  mov     rcx, [rsp+5E0h+var_568]
0x140031d07  test    rcx, rcx
0x140031d0a  jz      short loc_140031D18
0x140031d0c  mov     rax, [rcx]
0x140031d0f  mov     rax, [rax+10h]
0x140031d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031d18  mov     rcx, [rsp+5E0h+var_580]
0x140031d1d  test    rcx, rcx
0x140031d20  jz      short loc_140031D2E
0x140031d22  mov     rdx, [rcx]
0x140031d25  mov     rax, [rdx+10h]
0x140031d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031d2e  mov     eax, ebx
0x140031d30  jmp     loc_140032665
0x140031d35  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x140031d3c  lea     r14, aWin10SModeAler; "Win10 S Mode alert to server after user"...
0x140031d43  jmp     short loc_140031D53
0x140031d45  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x140031d4c  lea     r14, aOsEditionUpgra_0; "OS Edition Upgrade alert to server afte"...
0x140031d53  mov     rcx, r14; unsigned __int16 *
0x140031d56  call    ?DeleteTask@@YAJPEBG00@Z; DeleteTask(ushort const *,ushort const *,ushort const *)
0x140031d5b  mov     r9, rsi
0x140031d5e  mov     [rsp+5E0h+ReferencedDomainName], rdi; int
0x140031d63  mov     r8, rbx; unsigned __int16 *
0x140031d66  lea     rcx, [rbp+4E0h+var_290]; unsigned __int16 *
0x140031d6d  mov     edx, 104h; unsigned __int64
0x140031d72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140031d77  mov     ebx, eax
0x140031d79  test    eax, eax
0x140031d7b  jns     loc_140031E24
0x140031d81  mov     edx, 0F70h; void *
0x140031d86  mov     rcx, [rbp+4E8h]; this
0x140031d8d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140031d94  mov     r9d, ebx; char *
0x140031d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031d9c  mov     rcx, [rsp+5E0h+var_590]
0x140031da1  test    rcx, rcx
0x140031da4  jz      short loc_140031DB2
0x140031da6  mov     rdx, [rcx]
0x140031da9  mov     rax, [rdx+10h]
0x140031dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031db2  mov     rcx, [rsp+5E0h+var_578]
0x140031db7  test    rcx, rcx
0x140031dba  jz      short loc_140031DC8
0x140031dbc  mov     rax, [rcx]
0x140031dbf  mov     rax, [rax+10h]
0x140031dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031dc8  mov     rcx, [rsp+5E0h+var_588]
0x140031dcd  test    rcx, rcx
0x140031dd0  jz      short loc_140031DDE
0x140031dd2  mov     rax, [rcx]
0x140031dd5  mov     rax, [rax+10h]
0x140031dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031dde  mov     rcx, [rsp+5E0h+var_570]
0x140031de3  test    rcx, rcx
0x140031de6  jz      short loc_140031DF4
0x140031de8  mov     rax, [rcx]
0x140031deb  mov     rax, [rax+10h]
0x140031def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031df4  mov     rcx, [rsp+5E0h+var_568]
0x140031df9  test    rcx, rcx
0x140031dfc  jz      short loc_140031E0A
0x140031dfe  mov     rax, [rcx]
0x140031e01  mov     rax, [rax+10h]
0x140031e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031e0a  mov     rcx, [rsp+5E0h+var_580]
0x140031e0f  test    rcx, rcx
0x140031e12  jz      loc_140031D2E
0x140031e18  mov     rax, [rcx]
0x140031e1b  mov     rax, [rax+10h]
0x140031e1f  jmp     loc_140031D29
0x140031e24  xor     edx, edx; dwCoInit
0x140031e26  xor     ecx, ecx; pvReserved
0x140031e28  call    cs:__imp_CoInitializeEx
0x140031e2e  mov     ebx, eax
0x140031e30  test    eax, eax
0x140031e32  jns     short loc_140031E3E
0x140031e34  mov     edx, 0F72h
0x140031e39  jmp     loc_140031D86
0x140031e3e  lea     r9, [rbp+4E0h+var_290]; unsigned __int16 *
0x140031e45  mov     [rsp+5E0h+ReferencedDomainName], rdi; int
0x140031e4a  lea     r8, [rbp+4E0h+var_560]; struct ITaskFolder **
0x140031e4e  lea     rdx, [rbp+4E0h+var_548]; struct ITaskDefinition **
0x140031e52  call    ?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z; CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)
0x140031e57  mov     ebx, eax
0x140031e59  test    eax, eax
0x140031e5b  jns     loc_140031F24
0x140031e61  mov     rcx, [rbp+4E8h]; this
0x140031e68  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140031e6f  mov     r9d, eax; char *
0x140031e72  mov     edx, 0F74h; void *
0x140031e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031e7c  call    cs:__imp_CoUninitialize
0x140031e82  mov     rcx, [rsp+5E0h+var_590]
0x140031e87  test    rcx, rcx
0x140031e8a  jz      short loc_140031E98
0x140031e8c  mov     rax, [rcx]
0x140031e8f  mov     rax, [rax+10h]
0x140031e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031e98  mov     rcx, [rsp+5E0h+var_578]
0x140031e9d  test    rcx, rcx
0x140031ea0  jz      short loc_140031EAE
0x140031ea2  mov     rax, [rcx]
0x140031ea5  mov     rax, [rax+10h]
0x140031ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031eae  mov     rcx, [rsp+5E0h+var_588]
0x140031eb3  test    rcx, rcx
0x140031eb6  jz      short loc_140031EC4
0x140031eb8  mov     rax, [rcx]
0x140031ebb  mov     rax, [rax+10h]
0x140031ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031ec4  mov     rcx, [rsp+5E0h+var_570]
0x140031ec9  test    rcx, rcx
0x140031ecc  jz      short loc_140031EDA
0x140031ece  mov     rax, [rcx]
0x140031ed1  mov     rax, [rax+10h]
0x140031ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031eda  mov     rcx, [rbp+4E0h+var_560]
0x140031ede  test    rcx, rcx
0x140031ee1  jz      short loc_140031EEF
0x140031ee3  mov     rax, [rcx]
0x140031ee6  mov     rax, [rax+10h]
0x140031eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031eef  mov     rcx, [rsp+5E0h+var_568]
0x140031ef4  test    rcx, rcx
0x140031ef7  jz      short loc_140031F05
0x140031ef9  mov     rax, [rcx]
0x140031efc  mov     rax, [rax+10h]
0x140031f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f05  mov     rcx, [rsp+5E0h+var_580]
0x140031f0a  test    rcx, rcx
0x140031f0d  jz      short loc_140031F1B
0x140031f0f  mov     rax, [rcx]
0x140031f12  mov     rax, [rax+10h]
0x140031f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f1b  mov     rcx, [rbp+4E0h+var_548]
0x140031f1f  jmp     loc_140031E0F
0x140031f24  mov     rbx, [rbp+4E0h+var_548]
0x140031f28  lea     rdx, [rsp+5E0h+var_580]
0x140031f2d  mov     rcx, rbx
0x140031f30  mov     rax, [rbx]
0x140031f33  mov     rax, [rax+48h]
0x140031f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f3c  mov     esi, eax
0x140031f3e  test    eax, eax
0x140031f40  jns     loc_14003201B
0x140031f46  mov     edx, 0F75h; void *
0x140031f4b  mov     rcx, [rbp+4E8h]; this
0x140031f52  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140031f59  mov     r9d, esi; char *
0x140031f5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031f61  call    cs:__imp_CoUninitialize
0x140031f67  mov     rcx, [rsp+5E0h+var_590]
0x140031f6c  test    rcx, rcx
0x140031f6f  jz      short loc_140031F7D
0x140031f71  mov     rax, [rcx]
0x140031f74  mov     rax, [rax+10h]
0x140031f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f7d  mov     rcx, [rsp+5E0h+var_578]
0x140031f82  test    rcx, rcx
0x140031f85  jz      short loc_140031F93
0x140031f87  mov     rax, [rcx]
0x140031f8a  mov     rax, [rax+10h]
0x140031f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f93  mov     rcx, [rsp+5E0h+var_588]
0x140031f98  test    rcx, rcx
0x140031f9b  jz      short loc_140031FA9
0x140031f9d  mov     rax, [rcx]
0x140031fa0  mov     rax, [rax+10h]
0x140031fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031fa9  mov     rcx, [rsp+5E0h+var_570]
0x140031fae  test    rcx, rcx
0x140031fb1  jz      short loc_140031FBF
0x140031fb3  mov     rax, [rcx]
0x140031fb6  mov     rax, [rax+10h]
0x140031fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031fbf  mov     rcx, [rbp+4E0h+var_560]
0x140031fc3  test    rcx, rcx
0x140031fc6  jz      short loc_140031FD4
0x140031fc8  mov     rax, [rcx]
0x140031fcb  mov     rax, [rax+10h]
0x140031fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031fd4  mov     rcx, [rsp+5E0h+var_568]
0x140031fd9  test    rcx, rcx
0x140031fdc  jz      short loc_140031FEA
0x140031fde  mov     rax, [rcx]
0x140031fe1  mov     rax, [rax+10h]
0x140031fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031fea  mov     rcx, [rsp+5E0h+var_580]
0x140031fef  test    rcx, rcx
0x140031ff2  jz      short loc_140032000
0x140031ff4  mov     rax, [rcx]
0x140031ff7  mov     rax, [rax+10h]
0x140031ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032000  test    rbx, rbx
0x140032003  jz      short loc_140032014
0x140032005  mov     rax, [rbx]
0x140032008  mov     rcx, rbx
0x14003200b  mov     rax, [rax+10h]
0x14003200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032014  mov     eax, esi
0x140032016  jmp     loc_140032665
0x14003201b  mov     rcx, [rsp+5E0h+var_580]
0x140032020  lea     r8, [rsp+5E0h+var_570]
0x140032025  mov     edx, 9
0x14003202a  mov     rax, [rcx]
0x14003202d  mov     rax, [rax+50h]
0x140032031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032036  mov     esi, eax
0x140032038  test    eax, eax
0x14003203a  jns     short loc_140032046
0x14003203c  mov     edx, 0F76h
0x140032041  jmp     loc_140031F4B
0x140032046  mov     rcx, [rsp+5E0h+var_570]
0x14003204b  lea     r8, [rsp+5E0h+var_588]
0x140032050  lea     rdx, IID_ILogonTrigger
0x140032057  mov     rax, [rcx]
0x14003205a  mov     rax, [rax]
0x14003205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032062  mov     esi, eax
0x140032064  test    eax, eax
0x140032066  jns     short loc_140032072
0x140032068  mov     edx, 0F77h
0x14003206d  jmp     loc_140031F4B
0x140032072  lea     rdx, [rbp+4E0h+Sid]; Sid
0x140032076  mov     rcx, rdi; StringSid
0x140032079  call    cs:__imp_ConvertStringSidToSidW
0x14003207f  test    eax, eax
0x140032081  jnz     loc_140032156
0x140032087  call    cs:__imp_GetLastError
0x14003208d  mov     edi, eax
0x14003208f  test    eax, eax
0x140032091  jle     short loc_14003209C
0x140032093  movzx   edi, ax
0x140032096  or      edi, 80070000h
  ... truncated ...
```
