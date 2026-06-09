# Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey(ulong,void *,_UNICODE_STRING &,_KEY_VALUE_INFORMATION_CLASS,Windows::Auto<_LBLOB> *,ulong *)

- ea: `0x180150390`
- end: `0x180150c0d`
- name: `?SysQueryValueKey@OffregRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAXAEAU_UNICODE_STRING@@W4_KEY_VALUE_INFORMATION_CLASS@@PEAV?$Auto@U_LBLOB@@@4@PEAK@Z`
- size: `2173`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800031d0`
- `0x180003b2a`
- `0x180003b66`
- `0x180003c64`
- `0x18000693e`
- `0x18000aedc`
- `0x180030b68`
- `0x1800497c0`
- `0x18004d040`
- `0x180050360`
- `0x180118848`
- `0x18011ac0c`
- `0x18014bd20`
- `0x180150390`
- `0x18017b1e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801505f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801505f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150b36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180150b87`

## string_xrefs

- `0x180150408`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`
- `0x1801507b0`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`
- `0x1801507e1`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`
- `0x1801508b9`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`
- `0x18015095b`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`
- `0x180150aeb`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey(
        int a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        __int64 a3,
        unsigned __int16 *a4,
        int a5,
        size_t *a6,
        _DWORD *a7)
{
  char v10; // al
  unsigned int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rcx
  void *v16; // rbx
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // eax
  const char **v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rcx
  unsigned int v23; // r13d
  size_t v24; // r12
  int v25; // eax
  unsigned int v26; // r14d
  void *v27; // rcx
  size_t v28; // rdx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  size_t v33; // r13
  int v34; // r12d
  void *v35; // rcx
  _DWORD *v36; // r13
  size_t v37; // rdx
  size_t v38; // r12
  void *v39; // rcx
  __int64 v40; // rcx
  const void *v41; // r14
  unsigned int v42; // ecx
  unsigned int v43; // eax
  unsigned int *v44; // r13
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  size_t v48; // rdi
  size_t v49; // r15
  void *v50; // rcx
  _DWORD *v51; // rcx
  size_t v52; // rdx
  size_t v53; // rdi
  void *v54; // rcx
  __int64 v55; // rcx
  int v56; // edi
  const void *v58; // r14
  size_t v59; // rsi
  unsigned int v60; // [rsp+E0h] [rbp-80h] BYREF
  int v61; // [rsp+E4h] [rbp-7Ch] BYREF
  LPVOID pv; // [rsp+E8h] [rbp-78h] BYREF
  const char *v63; // [rsp+F0h] [rbp-70h] BYREF
  const char *v64; // [rsp+F8h] [rbp-68h]
  __int64 v65; // [rsp+100h] [rbp-60h]
  const char *v66; // [rsp+108h] [rbp-58h]
  _QWORD v67[4]; // [rsp+110h] [rbp-50h] BYREF
  _QWORD v68[4]; // [rsp+130h] [rbp-30h] BYREF
  _QWORD v69[4]; // [rsp+150h] [rbp-10h] BYREF
  _QWORD v70[4]; // [rsp+170h] [rbp+10h] BYREF
  _QWORD v71[4]; // [rsp+190h] [rbp+30h] BYREF
  _QWORD v72[4]; // [rsp+1B0h] [rbp+50h] BYREF
  _QWORD v73[4]; // [rsp+1F0h] [rbp+90h] BYREF
  int v74; // [rsp+210h] [rbp+B0h] BYREF
  int v75; // [rsp+218h] [rbp+B8h]
  int v76[14]; // [rsp+220h] [rbp+C0h] BYREF
  char v77; // [rsp+258h] [rbp+F8h]

  v74 = 0;
  v76[10] = 0;
  v77 = 0;
  v75 = (int)a2;
  v76[2] = 1;
  if ( (Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, a2) & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>::Arm(
      (int)v76,
      (int)&v74,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1,
      (__int64)"Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      (unsigned int)"(flags = {flags}, key = {key}, vn = {vn}, kvic = {kvic})",
      (__int64)"(flags = {flags}, key = {key}, vn = {vn}, kvic = {kvic}, kvi = {kvi}, disp = {disp})",
      (__int64)"(kvi = {kvi}, disp = {disp})");
  v10 = v75;
  if ( v75 )
  {
    if ( !a7 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180150C0CLL);
    }
  }
  else if ( !a7 )
  {
    goto LABEL_8;
  }
  *a7 = 0;
LABEL_8:
  *a6 = 0;
  if ( (v10 & 4) != 0 )
  {
    if ( (v10 & 1) != 0 )
    {
      if ( a7 )
        *a7 = 2;
      v77 = 1;
    }
    else
    {
      v67[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
      v67[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
      v67[2] = 860;
      v67[3] = 0;
      v74 = -1073741772;
      RtlReportErrorOrigination(v67, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225524LL);
    }
    v11 = v74;
LABEL_79:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>(v76);
    return v11;
  }
  v12 = *a4;
  v13 = *((_QWORD *)a4 + 1);
  pv = 0;
  v14 = Windows::AutoNullTerminatedString<Windows::COM::CLPCWSTRTraits,Windows::Auto<wchar_t const *>>::AssignCb<wchar_t>(
          &pv,
          v13,
          v12);
  v11 = v14;
  if ( v14 < 0 )
  {
    v74 = v14;
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_79;
  }
  v15 = *(_QWORD *)(a3 + 8);
  v16 = pv;
  v61 = 0;
  v60 = 0;
  if ( !v15 )
    v15 = *(_QWORD *)(a3 + 16);
  v17 = ORGetValue(v15, 0, (_DWORD)pv, (unsigned int)&v61, 0, (__int64)&v60);
  v18 = (unsigned int)v17;
  if ( v17 )
  {
    if ( v17 != 2 )
    {
      v64 = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
      v63 = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
      v66 = "::ORGetValue( Wrapper->GetKey(), nullptr, ValueNameNullTerminated, &Type, nullptr, &ValueSize)";
      v65 = 879;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      v19 = ConvertHResultToNtStatus(v18);
      v20 = &v63;
      goto LABEL_74;
    }
    if ( (v75 & 1) != 0 )
    {
      if ( a7 )
        *a7 = 2;
      v77 = 1;
      goto LABEL_76;
    }
  }
  if ( !a5 )
  {
    v49 = *a4 + 16LL;
    v34 = RtlReallocateLBlob(0, v49, a6);
    if ( v34 < 0 )
      goto LABEL_66;
    v50 = (void *)a6[2];
    *a6 = v49;
    memset_0(v50, 0, v49);
    v51 = (_DWORD *)a6[2];
    v51[1] = v61;
    v52 = *a4;
    v51[2] = v52;
    v53 = *a4;
    if ( !*a4 )
      goto LABEL_83;
    v54 = v51 + 3;
    if ( !v54 )
      goto LABEL_71;
    v58 = (const void *)*((_QWORD *)a4 + 1);
    if ( v58 && v52 >= v53 )
    {
      memcpy_0(v54, v58, v53);
      goto LABEL_83;
    }
    v59 = v52;
    memset_0(v54, 0, v52);
    if ( v58 )
    {
      if ( v59 < v53 )
      {
        *(_DWORD *)o__errno_0() = 34;
        invalid_parameter_noinfo();
        v55 = 2157314082LL;
        goto LABEL_73;
      }
    }
    else
    {
LABEL_71:
      *(_DWORD *)o__errno_0() = 22;
      invalid_parameter_noinfo();
    }
    v55 = 2157314070LL;
LABEL_73:
    v73[2] = 906;
    v73[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
    v73[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
    v73[3] = "::memcpy_s(BasicInfo->Name, BasicInfo->NameLength, ValueName.Buffer, ValueName.Length)";
    v19 = ConvertHResultToNtStatus(v55);
    v20 = (const char **)v73;
    goto LABEL_74;
  }
  if ( a5 == 1 )
  {
    v32 = *a4 + 24LL;
    v33 = v32 + v60;
    if ( v33 < v60 )
    {
      v72[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
      v72[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
      v20 = (const char **)v72;
      v72[2] = 918;
      v72[3] = "BUCL::Rtl::Add<SIZE_T>( sizeof(KEY_VALUE_FULL_INFORMATION), ValueName.Length, ValueSize, FullInfoLength)";
      v21 = 3221225621LL;
      v74 = -1073741675;
      goto LABEL_75;
    }
    v34 = RtlReallocateLBlob(v32, v32 + v60, a6);
    if ( v34 >= 0 )
    {
      v35 = (void *)a6[2];
      *a6 = v33;
      memset_0(v35, 0, v33);
      v36 = (_DWORD *)a6[2];
      v36[1] = v61;
      v37 = *a4;
      v36[4] = v37;
      v38 = *a4;
      if ( *a4 )
      {
        v39 = v36 + 5;
        if ( v36 == (_DWORD *)-20LL )
          goto LABEL_49;
        v41 = (const void *)*((_QWORD *)a4 + 1);
        if ( !v41 || v37 < v38 )
        {
          v48 = v37;
          memset_0(v39, 0, v37);
          if ( v41 )
          {
            if ( v48 < v38 )
            {
              *(_DWORD *)o__errno_0() = 34;
              invalid_parameter_noinfo();
              v40 = 2157314082LL;
              goto LABEL_51;
            }
LABEL_50:
            v40 = 2157314070LL;
LABEL_51:
            v70[2] = 927;
            v70[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
            v70[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
            v70[3] = "::memcpy_s(FullInfo->Name, FullInfo->NameLength, ValueName.Buffer, ValueName.Length)";
            v19 = ConvertHResultToNtStatus(v40);
            v20 = (const char **)v70;
LABEL_74:
            v21 = v19;
            v74 = v19;
            goto LABEL_75;
          }
LABEL_49:
          *(_DWORD *)o__errno_0() = 22;
          invalid_parameter_noinfo();
          goto LABEL_50;
        }
        memcpy_0(v39, v41, v38);
      }
      v42 = v60;
      v43 = v36[4] + 20;
      v36[2] = v43;
      v44 = v36 + 3;
      *v44 = v42;
      v45 = *(_QWORD *)(a3 + 8);
      if ( !v45 )
        v45 = *(_QWORD *)(a3 + 16);
      v46 = ORGetValue(v45, 0, (_DWORD)v16, 0, a6[2] + v43, (__int64)v44);
      v47 = (unsigned int)v46;
      if ( v46 )
      {
        v71[2] = 939;
        v71[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
        v71[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
        v71[3] = "::ORGetValue( Wrapper->GetKey(), nullptr, ValueNameNullTerminated, nullptr, KeyValueInformation->Buffer"
                 " + FullInfo->DataOffset, &FullInfo->DataLength)";
        if ( v46 > 0 )
          v47 = (unsigned __int16)v46 | 0x80070000;
        v19 = ConvertHResultToNtStatus(v47);
        v20 = (const char **)v71;
        goto LABEL_74;
      }
      goto LABEL_83;
    }
LABEL_66:
    v74 = v34;
    if ( v16 )
      CoTaskMemFree(v16);
    v11 = v34;
    goto LABEL_79;
  }
  if ( a5 != 2 )
  {
    v64 = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
    v63 = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
    v20 = &v63;
    v65 = 973;
    v21 = 3221225474LL;
    v66 = 0;
    v74 = -1073741822;
LABEL_75:
    RtlReportErrorOrigination(v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v21);
LABEL_76:
    v56 = v74;
    if ( v16 )
      CoTaskMemFree(v16);
    v11 = v56;
    goto LABEL_79;
  }
  v22 = *a4 + 16LL;
  v23 = v60;
  v24 = v22 + v60;
  if ( v24 < v60 )
  {
    v69[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
    v69[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
    v20 = (const char **)v69;
    v69[2] = 951;
    v69[3] = "BUCL::Rtl::Add<SIZE_T>( sizeof(KEY_VALUE_PARTIAL_INFORMATION), ValueName.Length, ValueSize, PartialInfoLength)";
    v21 = 3221225621LL;
    v74 = -1073741675;
    goto LABEL_75;
  }
  v25 = RtlReallocateLBlob(v22, v22 + v60, a6);
  v26 = v25;
  if ( v25 < 0 )
  {
    v74 = v25;
    if ( v16 )
      CoTaskMemFree(v16);
    v11 = v26;
    goto LABEL_79;
  }
  v27 = (void *)a6[2];
  *a6 = v24;
  memset_0(v27, 0, v24);
  v28 = a6[2];
  *(_DWORD *)(v28 + 4) = v61;
  *(_DWORD *)(v28 + 8) = v23;
  v29 = *(_QWORD *)(a3 + 8);
  if ( !v29 )
    v29 = *(_QWORD *)(a3 + 16);
  v30 = ORGetValue(v29, 0, (_DWORD)v16, 0, v28 + 12, v28 + 8);
  v31 = (unsigned int)v30;
  if ( v30 )
  {
    v68[2] = 968;
    v68[0] = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
    v68[1] = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::SysQueryValueKey";
    v68[3] = "::ORGetValue( Wrapper->GetKey(), nullptr, ValueNameNullTerminated, nullptr, PartialInfo->Data, &PartialInfo->DataLength)";
    if ( v30 > 0 )
      v31 = (unsigned __int16)v30 | 0x80070000;
    v19 = ConvertHResultToNtStatus(v31);
    v20 = (const char **)v68;
    goto LABEL_74;
  }
LABEL_83:
  if ( a7 )
    *a7 = 1;
  v77 = 1;
  if ( v16 )
    CoTaskMemFree(v16);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>(v76);
  return (unsigned int)v74;
}

```

## disassembly

```asm
0x180150390  push    rbp
0x180150392  push    rbx
0x180150393  push    rsi
0x180150394  push    rdi
0x180150395  push    r12
0x180150397  push    r13
0x180150399  push    r14
0x18015039b  push    r15
0x18015039d  lea     rbp, [rsp-248h]
0x1801503a5  sub     rsp, 3A8h
0x1801503ac  mov     rax, cs:__security_cookie
0x1801503b3  xor     rax, rsp
0x1801503b6  mov     [rbp+280h+var_50], rax
0x1801503bd  mov     rdi, [rbp+280h+arg_28]
0x1801503c4  xor     r13d, r13d
0x1801503c7  mov     rsi, [rbp+280h+arg_30]
0x1801503ce  mov     rbx, rcx
0x1801503d1  lea     rcx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x1801503d8  mov     [rbp+280h+var_1D0], r13d
0x1801503df  mov     [rbp+280h+var_198], r13d
0x1801503e6  mov     r14, r9
0x1801503e9  mov     [rbp+280h+var_188], r13b
0x1801503f0  mov     r15, r8
0x1801503f3  mov     [rbp+280h+var_1C8], edx
0x1801503f9  mov     [rbp+280h+var_1B8], 1
0x180150403  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180150408  lea     r12, aWindowsRtlSyst_115; "Windows::Rtl::SystemImplementation::Off"...
0x18015040f  test    al, 0Eh
0x180150411  jz      loc_180150544
0x180150417  mov     [rsp+3E0h+var_308], rsi
0x18015041f  lea     rcx, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180150426  mov     [rsp+3E0h+var_310], rcx
0x18015042e  lea     rax, aDisp; "disp"
0x180150435  mov     [rsp+3E0h+var_318], rax
0x18015043d  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x180150444  mov     [rsp+3E0h+var_320], rdi
0x18015044c  lea     rax, ?RtlTraceFormat_PCLBLOB@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180150453  mov     [rsp+3E0h+var_328], rax
0x18015045b  lea     rdx, [rbp+280h+var_1D0]; int
0x180150462  lea     rax, aKvi; "kvi"
0x180150469  mov     r9, rbx; int
0x18015046c  mov     [rsp+3E0h+var_330], rax
0x180150474  lea     rax, [rbp+280h+arg_20]
0x18015047b  mov     [rsp+3E0h+var_338], rax
0x180150483  lea     rax, aKvic; "kvic"
0x18015048a  mov     [rsp+3E0h+var_340], rcx
0x180150492  mov     [rsp+3E0h+var_348], rax
0x18015049a  lea     rax, ?RtlTraceFormat_PCUNICODE_STRING@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801504a1  mov     [rsp+3E0h+var_350], r14
0x1801504a9  mov     [rsp+3E0h+var_358], rax
0x1801504b1  lea     rax, aVn; "vn"
0x1801504b8  mov     [rsp+3E0h+var_360], rax
0x1801504c0  lea     rax, ?TraceWrapperHandle@OffregRegistryProvider@SystemImplementation@Rtl@Windows@@CAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::OffregRegistryProvider::TraceWrapperHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801504c7  mov     [rsp+3E0h+var_368], r15
0x1801504cc  mov     [rsp+3E0h+var_370], rax
0x1801504d1  lea     rax, aKey; "key"
0x1801504d8  mov     [rsp+3E0h+var_378], rax
0x1801504dd  lea     rax, [rbp+280h+var_1C8]
0x1801504e4  mov     [rsp+3E0h+var_380], rax
0x1801504e9  lea     rax, aFlags; "flags"
0x1801504f0  mov     [rsp+3E0h+var_388], rcx
0x1801504f5  lea     rcx, [rbp+280h+var_1C0]; int
0x1801504fc  mov     [rsp+3E0h+var_390], rax
0x180150501  lea     rax, aKviKviDispDisp; "(kvi = {kvi}, disp = {disp})"
0x180150508  mov     [rsp+3E0h+var_398], 6
0x180150511  mov     [rsp+3E0h+var_3A0], rax; __int64
0x180150516  lea     rax, aFlagsFlagsKeyK_0; "(flags = {flags}, key = {key}, vn = {vn"...
0x18015051d  mov     [rsp+3E0h+var_3A8], rax; __int64
0x180150522  lea     rax, aFlagsFlagsKeyK_6; "(flags = {flags}, key = {key}, vn = {vn"...
0x180150529  mov     qword ptr [rsp+3E0h+var_3B0], rax; unsigned int
0x18015052e  lea     rax, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x180150535  mov     [rsp+3E0h+var_3B8], rax; Windows::WCP::Rtl *
0x18015053a  mov     [rsp+3E0h+var_3C0], r12; __int64
0x18015053f  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$05@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,6>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x180150544  mov     eax, [rbp+280h+var_1C8]
0x18015054a  test    eax, eax
0x18015054c  jz      short loc_180150559
0x18015054e  test    rsi, rsi
0x180150551  jz      loc_180150C02
0x180150557  jmp     short loc_18015055E
0x180150559  test    rsi, rsi
0x18015055c  jz      short loc_180150561
0x18015055e  mov     [rsi], r13d
0x180150561  mov     [rdi], r13
0x180150564  test    al, 4
0x180150566  jz      short loc_1801505C6
0x180150568  test    al, 1
0x18015056a  jz      short loc_180150580
0x18015056c  test    rsi, rsi
0x18015056f  jz      short loc_180150577
0x180150571  mov     dword ptr [rsi], 2
0x180150577  mov     [rbp+280h+var_188], 1
0x18015057e  jmp     short loc_1801505BB
0x180150580  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x180150587  mov     [rbp+280h+var_2C8], r12
0x18015058b  mov     r8d, 0C0000034h
0x180150591  mov     [rbp+280h+var_2D0], rax
0x180150595  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015059c  mov     [rbp+280h+var_2C0], 35Ch
0x1801505a4  lea     rcx, [rbp+280h+var_2D0]
0x1801505a8  mov     [rbp+280h+var_2B8], r13
0x1801505ac  mov     [rbp+280h+var_1D0], 0C0000034h
0x1801505b6  call    RtlReportErrorOrigination
0x1801505bb  mov     ebx, [rbp+280h+var_1D0]
0x1801505c1  jmp     loc_180150B44
0x1801505c6  movzx   r8d, word ptr [r14]
0x1801505ca  lea     rcx, [rbp+280h+pv]
0x1801505ce  mov     rdx, [r14+8]
0x1801505d2  mov     [rbp+280h+pv], r13
0x1801505d6  call    ??$AssignCb@_W@?$AutoNullTerminatedString@VCLPCWSTRTraits@COM@Windows@@V?$Auto@PEB_W@3@@Windows@@QEAAJQEB_W_K@Z; Windows::AutoNullTerminatedString<Windows::COM::CLPCWSTRTraits,Windows::Auto<wchar_t const *>>::AssignCb<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801505db  mov     ebx, eax
0x1801505dd  test    eax, eax
0x1801505df  jns     short loc_180150605
0x1801505e1  mov     rcx, [rbp+280h+pv]; pv
0x1801505e5  mov     [rbp+280h+var_1D0], eax
0x1801505eb  test    rcx, rcx
0x1801505ee  jz      loc_180150B44
0x1801505f4  call    cs:__imp_CoTaskMemFree
0x1801505fb  nop     dword ptr [rax+rax+00h]
0x180150600  jmp     loc_180150B44
0x180150605  mov     rcx, [r15+8]
0x180150609  mov     rbx, [rbp+280h+pv]
0x18015060d  mov     [rbp+280h+var_2FC], r13d
0x180150611  mov     [rbp+280h+var_300], r13d
0x180150615  test    rcx, rcx
0x180150618  jnz     short loc_18015061E
0x18015061a  mov     rcx, [r15+10h]
0x18015061e  lea     rax, [rbp+280h+var_300]
0x180150622  mov     r8, rbx
0x180150625  mov     [rsp+3E0h+var_3B8], rax
0x18015062a  lea     r9, [rbp+280h+var_2FC]
0x18015062e  xor     edx, edx
0x180150630  mov     [rsp+3E0h+var_3C0], r13
0x180150635  call    ORGetValue
0x18015063a  mov     ecx, eax
0x18015063c  test    eax, eax
0x18015063e  jz      short loc_1801506A2
0x180150640  cmp     eax, 2
0x180150643  jz      short loc_180150682
0x180150645  mov     [rbp+280h+var_2E8], r12
0x180150649  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x180150650  mov     [rbp+280h+var_2F0], rax
0x180150654  lea     rax, aOrgetvalueWrap_0; "::ORGetValue( Wrapper->GetKey(), nullpt"...
0x18015065b  mov     [rbp+280h+var_2D8], rax
0x18015065f  mov     [rbp+280h+var_2E0], 36Fh
0x180150667  test    ecx, ecx
0x180150669  jle     short loc_180150674
0x18015066b  movzx   ecx, cx
0x18015066e  or      ecx, 80070000h
0x180150674  call    ConvertHResultToNtStatus
0x180150679  lea     rcx, [rbp+280h+var_2F0]
0x18015067d  jmp     loc_180150B13
0x180150682  test    byte ptr [rbp+280h+var_1C8], 1
0x180150689  jz      short loc_1801506A2
0x18015068b  test    rsi, rsi
0x18015068e  jz      short loc_180150696
0x180150690  mov     dword ptr [rsi], 2
0x180150696  mov     [rbp+280h+var_188], 1
0x18015069d  jmp     loc_180150B28
0x1801506a2  mov     ecx, [rbp+280h+arg_20]
0x1801506a8  test    ecx, ecx
0x1801506aa  jz      loc_180150A00
0x1801506b0  sub     ecx, 1
0x1801506b3  jz      loc_180150823
0x1801506b9  cmp     ecx, 1
0x1801506bc  jz      short loc_1801506F2
0x1801506be  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x1801506c5  mov     [rbp+280h+var_2E8], r12
0x1801506c9  mov     [rbp+280h+var_2F0], rax
0x1801506cd  lea     rcx, [rbp+280h+var_2F0]
0x1801506d1  mov     [rbp+280h+var_2E0], 3CDh
0x1801506d9  mov     r8d, 0C0000002h
0x1801506df  mov     [rbp+280h+var_2D8], r13
0x1801506e3  mov     [rbp+280h+var_1D0], 0C0000002h
0x1801506ed  jmp     loc_180150B1C
0x1801506f2  movzx   ecx, word ptr [r14]
0x1801506f6  add     rcx, 10h
0x1801506fa  cmp     rcx, 10h
0x1801506fe  jb      loc_1801507E8
0x180150704  mov     r13d, [rbp+280h+var_300]
0x180150708  lea     r12, [rcx+r13]
0x18015070c  cmp     r12, r13
0x18015070f  jb      loc_1801507E1
0x180150715  mov     r8, rdi
0x180150718  mov     rdx, r12
0x18015071b  call    RtlReallocateLBlob
0x180150720  mov     r14d, eax
0x180150723  test    eax, eax
0x180150725  jns     short loc_180150749
0x180150727  mov     [rbp+280h+var_1D0], eax
0x18015072d  test    rbx, rbx
0x180150730  jz      short loc_180150741
0x180150732  mov     rcx, rbx; pv
0x180150735  call    cs:__imp_CoTaskMemFree
0x18015073c  nop     dword ptr [rax+rax+00h]
0x180150741  mov     ebx, r14d
0x180150744  jmp     loc_180150B44
0x180150749  mov     rcx, [rdi+10h]; void *
0x18015074d  mov     r8, r12; Size
0x180150750  xor     edx, edx; Val
0x180150752  mov     [rdi], r12
0x180150755  call    memset_0
0x18015075a  mov     rdx, [rdi+10h]
0x18015075e  mov     eax, [rbp+280h+var_2FC]
0x180150761  lea     r8, [rdx+8]
0x180150765  mov     [rdx+4], eax
0x180150768  mov     [r8], r13d
0x18015076b  mov     rcx, [r15+8]
0x18015076f  test    rcx, rcx
0x180150772  jnz     short loc_180150778
0x180150774  mov     rcx, [r15+10h]
0x180150778  lea     rax, [rdx+0Ch]
0x18015077c  mov     [rsp+3E0h+var_3B8], r8
0x180150781  mov     r8, rbx
0x180150784  mov     [rsp+3E0h+var_3C0], rax
0x180150789  xor     edx, edx
0x18015078b  xor     r9d, r9d
0x18015078e  call    ORGetValue
0x180150793  mov     ecx, eax
0x180150795  test    eax, eax
0x180150797  jz      loc_180150B6D
0x18015079d  mov     [rbp+280h+var_2A0], 3C8h
0x1801507a5  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x1801507ac  mov     [rbp+280h+var_2B0], rax
0x1801507b0  lea     rax, aWindowsRtlSyst_115; "Windows::Rtl::SystemImplementation::Off"...
0x1801507b7  mov     [rbp+280h+var_2A8], rax
0x1801507bb  lea     rax, aOrgetvalueWrap; "::ORGetValue( Wrapper->GetKey(), nullpt"...
0x1801507c2  mov     [rbp+280h+var_298], rax
0x1801507c6  test    ecx, ecx
0x1801507c8  jle     short loc_1801507D3
0x1801507ca  movzx   ecx, cx
0x1801507cd  or      ecx, 80070000h
0x1801507d3  call    ConvertHResultToNtStatus
0x1801507d8  lea     rcx, [rbp+280h+var_2B0]
0x1801507dc  jmp     loc_180150B13
0x1801507e1  lea     r12, aWindowsRtlSyst_115; "Windows::Rtl::SystemImplementation::Off"...
0x1801507e8  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x1801507ef  mov     [rbp+280h+var_288], r12
0x1801507f3  mov     [rbp+280h+var_290], rax
0x1801507f7  lea     rcx, [rbp+280h+var_290]
0x1801507fb  lea     rax, aBuclRtlAddSize_13; "BUCL::Rtl::Add<SIZE_T>( sizeof(KEY_VALU"...
0x180150802  mov     [rbp+280h+var_280], 3B7h
0x18015080a  mov     [rbp+280h+var_278], rax
0x18015080e  mov     r8d, 0C0000095h
0x180150814  mov     [rbp+280h+var_1D0], 0C0000095h
0x18015081e  jmp     loc_180150B1C
0x180150823  movzx   ecx, word ptr [r14]
0x180150827  add     rcx, 18h
0x18015082b  cmp     rcx, 18h
0x18015082f  jb      loc_1801509C5
0x180150835  mov     eax, [rbp+280h+var_300]
0x180150838  lea     r13, [rcx+rax]
0x18015083c  cmp     r13, rax
0x18015083f  jb      loc_1801509C5
0x180150845  mov     r8, rdi
0x180150848  mov     rdx, r13
0x18015084b  call    RtlReallocateLBlob
0x180150850  mov     r12d, eax
0x180150853  test    eax, eax
0x180150855  js      loc_180150A61
0x18015085b  mov     rcx, [rdi+10h]; void *
0x18015085f  mov     r8, r13; Size
0x180150862  xor     edx, edx; Val
0x180150864  mov     [rdi], r13
0x180150867  call    memset_0
0x18015086c  mov     r13, [rdi+10h]
0x180150870  mov     eax, [rbp+280h+var_2FC]
0x180150873  mov     [r13+4], eax
0x180150877  movzx   edx, word ptr [r14]
0x18015087b  mov     [r13+10h], edx
0x18015087f  movzx   r12d, word ptr [r14]
0x180150883  test    r12, r12
0x180150886  jz      short loc_1801508FE
0x180150888  lea     rcx, [r13+14h]; void *
0x18015088c  test    rcx, rcx
0x18015088f  jnz     short loc_1801508DD
0x180150891  call    _o__errno_0
0x180150896  mov     dword ptr [rax], 16h
0x18015089c  call    _invalid_parameter_noinfo
0x1801508a1  mov     ecx, 80960016h
0x1801508a6  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x1801508ad  mov     [rbp+280h+var_260], 39Fh
0x1801508b5  mov     [rbp+280h+var_270], rax
0x1801508b9  lea     rax, aWindowsRtlSyst_115; "Windows::Rtl::SystemImplementation::Off"...
0x1801508c0  mov     [rbp+280h+var_268], rax
0x1801508c4  lea     rax, aMemcpySFullinf; "::memcpy_s(FullInfo->Name, FullInfo->Na"...
0x1801508cb  mov     [rbp+280h+var_258], rax
0x1801508cf  call    ConvertHResultToNtStatus
0x1801508d4  lea     rcx, [rbp+280h+var_270]
0x1801508d8  jmp     loc_180150B13
0x1801508dd  mov     r14, [r14+8]
0x1801508e1  test    r14, r14
0x1801508e4  jz      loc_18015098C
0x1801508ea  cmp     rdx, r12
0x1801508ed  jb      loc_18015098C
0x1801508f3  mov     r8, r12; Size
0x1801508f6  mov     rdx, r14; Src
0x1801508f9  call    memcpy_0
0x1801508fe  mov     eax, [r13+10h]
0x180150902  mov     ecx, [rbp+280h+var_300]
  ... truncated ...
```
