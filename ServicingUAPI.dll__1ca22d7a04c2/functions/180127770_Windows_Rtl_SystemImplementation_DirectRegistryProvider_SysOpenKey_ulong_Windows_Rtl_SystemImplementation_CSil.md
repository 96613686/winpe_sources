# Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x180127770`
- end: `0x180127d5e`
- name: `?SysOpenKey@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x1800031d0`
- `0x180030b68`
- `0x1800497c0`
- `0x1801186bc`
- `0x18011a9ec`
- `0x18011c474`
- `0x18011ccac`
- `0x18011f29c`
- `0x180120970`
- `0x180121cd0`
- `0x180127770`
- `0x18012d3a0`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtOpenKeyTransactedEx` at `0x180127ad7`
- `ntdll!NtOpenKeyTransactedEx` at `0x180127ad7`
- `ntdll!NtOpenKeyEx` at `0x180127ac1`
- `ntdll!NtOpenKeyEx` at `0x180127ac1`
- `ntdll!NtClose` at `0x180127936`
- `ntdll!NtClose` at `0x1801279c3`
- `ntdll!NtClose` at `0x180127a36`
- `ntdll!NtClose` at `0x180127b3c`
- `ntdll!NtClose` at `0x180127c88`
- `ntdll!NtClose` at `0x180127d0f`
- `ntdll!NtClose` at `0x180127936`
- `ntdll!NtClose` at `0x1801279c3`
- `ntdll!NtClose` at `0x180127a36`
- `ntdll!NtClose` at `0x180127b3c`
- `ntdll!NtClose` at `0x180127c88`
- `ntdll!NtClose` at `0x180127d0f`

## string_xrefs

- `0x1801277fb`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey`
- `0x180127cd3`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey`
- `0x180127b9b`: `Transient insufficient resources at NtOpenKey for {oa}`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey(
        __int64 a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  char v8; // r13
  int v9; // ebx
  char FacilityTracingFlags; // al
  Windows::Rtl::SystemImplementation::DirectRegistryProvider *v12; // rcx
  const struct _UNICODE_STRING *v13; // rdx
  int IsUnacceptableKeyPrefix; // eax
  unsigned int v15; // ebx
  HANDLE v16; // rax
  HANDLE v17; // rcx
  void (*v18)(void); // rax
  HANDLE v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  unsigned int v22; // edi
  HANDLE v23; // rcx
  _QWORD *v25; // rax
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  bool v28; // r14
  __int64 v29; // rdx
  int v30; // eax
  bool *v31; // r8
  int v32; // edi
  int v33; // eax
  unsigned int v34; // r14d
  HANDLE v35; // rcx
  __int64 v36; // r9
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  HANDLE v41; // rcx
  HANDLE v42; // rcx
  bool v43[4]; // [rsp+D0h] [rbp-80h] BYREF
  __int128 v44; // [rsp+D8h] [rbp-78h] BYREF
  int v45; // [rsp+E8h] [rbp-68h] BYREF
  const char *v46; // [rsp+F0h] [rbp-60h] BYREF
  const char *v47; // [rsp+F8h] [rbp-58h]
  __int64 v48; // [rsp+100h] [rbp-50h]
  __int64 v49; // [rsp+108h] [rbp-48h]
  __int64 v50; // [rsp+110h] [rbp-40h]
  _OWORD v51[3]; // [rsp+118h] [rbp-38h] BYREF
  int v52; // [rsp+148h] [rbp-8h] BYREF
  HANDLE Handle; // [rsp+150h] [rbp+0h] BYREF
  unsigned int v54; // [rsp+158h] [rbp+8h]
  int v55; // [rsp+160h] [rbp+10h]
  int v56[14]; // [rsp+170h] [rbp+20h] BYREF
  char v57; // [rsp+1A8h] [rbp+58h]

  v8 = 0;
  v9 = a1;
  v50 = a1;
  v55 = (int)a2;
  v54 = a4;
  v52 = 0;
  v44 = 0;
  Handle = 0;
  v56[10] = 0;
  v57 = 0;
  v56[2] = 1;
  FacilityTracingFlags = Windows::WCP::Rtl::RtlGetFacilityTracingFlags(
                           (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
                           a2);
  v12 = (Windows::Rtl::SystemImplementation::DirectRegistryProvider *)Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject;
  if ( (FacilityTracingFlags & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::Arm(
      (int)v56,
      (int)&v52,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      v9,
      (__int64)"Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      (unsigned int)"(flg = {flg}, da = {da}, oa = {oa})",
      (__int64)"(flg = {flg}, key = {key}, da = {da}, oa = {oa}, disp = {disp})",
      (__int64)"(key = {key}, disp = {disp})");
  v13 = *(const struct _UNICODE_STRING **)(a5 + 16);
  v43[0] = 0;
  IsUnacceptableKeyPrefix = Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(
                              v12,
                              v13,
                              v43);
  v15 = IsUnacceptableKeyPrefix;
  if ( IsUnacceptableKeyPrefix < 0 )
  {
    v52 = IsUnacceptableKeyPrefix;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
    v16 = Handle;
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      Handle = 0;
      v17 = v16;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  if ( v43[0] )
  {
    v47 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey";
    v46 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v48 = 5531;
    v49 = 0;
    v52 = -1073741767;
    RtlReportErrorOrigination(&v46, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225529LL);
    v15 = v52;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
    v19 = Handle;
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      Handle = 0;
      NtClose(v19);
    }
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
    if ( (_QWORD)v44 )
    {
      v18 = **(void (***)(void))v44;
LABEL_72:
      v18();
    }
    return v15;
  }
  if ( a7 )
    v20 = *a7;
  else
    v20 = 0;
  v21 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(
          a5,
          v20);
  v22 = v21;
  if ( v21 < 0 )
  {
    v52 = v21;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v23 = Handle;
      Handle = 0;
      NtClose(v23);
    }
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
    if ( (_QWORD)v44 )
      (**(void (__fastcall ***)(_QWORD))v44)(v44);
    return v22;
  }
  if ( a8 )
    *a8 = 0;
  v25 = *(_QWORD **)(a5 + 8);
  v26 = *(_OWORD *)(a5 + 16);
  v27 = *(_OWORD *)(a5 + 32);
  v51[0] = *(_OWORD *)a5;
  v51[1] = v26;
  v51[2] = v27;
  if ( v25 )
    *((_QWORD *)&v51[0] + 1) = *v25;
  v29 = v54;
  v28 = 1;
  LODWORD(v29) = v54 | 0x100;
  v45 = 0;
  v54 |= 0x100u;
  v43[0] = 1;
  while ( 1 )
  {
    if ( a7 )
      v30 = NtOpenKeyTransactedEx(&Handle, v29, v51, a6, *a7);
    else
      v30 = NtOpenKeyEx(&Handle, v29, v51, a6);
    v32 = v30;
    if ( v30 == -1073741670 )
    {
      v33 = Windows::Rtl::SystemImplementation::DelayForInsufficientResources(
              (Windows::Rtl::SystemImplementation *)&v45,
              (unsigned int *)v43,
              v31);
      v34 = v33;
      if ( v33 < 0 )
      {
        v52 = v33;
        Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
        v35 = Handle;
        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          Handle = 0;
          NtClose(v35);
        }
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
        if ( (_QWORD)v44 )
          (**(void (__fastcall ***)(_QWORD))v44)(v44);
        return v34;
      }
      v28 = v43[0];
      v8 = 1;
    }
    if ( !v28 || v32 != -1073741670 )
      break;
    v29 = v54;
  }
  if ( v32 < 0 )
  {
    if ( (v32 == -1073741772 || v32 == -1073741766) && (v55 & 1) != 0 )
    {
      if ( a8 )
        *a8 = 2;
    }
    else
    {
      if ( v32 != -1073741790 || (v55 & 2) == 0 )
      {
        v48 = 5603;
        v46 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v49 = 0;
        v47 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey";
        v52 = v32;
        RtlReportErrorOrigination(&v46, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v32);
        v15 = v52;
        Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
        v42 = Handle;
        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          Handle = 0;
          NtClose(v42);
        }
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
        if ( (_QWORD)v44 )
        {
          v18 = **(void (***)(void))v44;
          goto LABEL_72;
        }
        return v15;
      }
      if ( a8 )
        *a8 = 3;
    }
LABEL_63:
    v57 = 1;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
    v41 = Handle;
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      Handle = 0;
      NtClose(v41);
    }
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
    if ( (_QWORD)v44 )
      (**(void (__fastcall ***)(_QWORD))v44)(v44);
    return (unsigned int)v52;
  }
  if ( v8 )
    Windows::WCP::Rtl::RtlTrace(
      0,
      (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Transient insufficient resources at NtOpenKey for {oa}",
      (const char *const)1,
      (unsigned __int64)"oa",
      Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
      a5);
  if ( a7 )
    v36 = *a7;
  else
    v36 = 0;
  v37 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::Create(
          v50,
          &Handle,
          &v44,
          v36);
  v15 = v37;
  if ( v37 >= 0 )
  {
    if ( a8 )
      *a8 = 1;
    v38 = *((_QWORD *)&v44 + 1);
    *((_QWORD *)&v44 + 1) = a3[1];
    v39 = v44;
    a3[1] = v38;
    v40 = *a3;
    *a3 = v39;
    *(_QWORD *)&v44 = v40;
    goto LABEL_63;
  }
  v52 = v37;
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(v56);
  v17 = Handle;
  if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    goto LABEL_7;
  Handle = 0;
LABEL_6:
  NtClose(v17);
LABEL_7:
  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v44);
  if ( (_QWORD)v44 )
  {
    v18 = **(void (***)(void))v44;
    goto LABEL_72;
  }
  return v15;
}

```

## disassembly

```asm
0x180127770  push    rbp
0x180127772  push    rbx
0x180127773  push    rsi
0x180127774  push    rdi
0x180127775  push    r12
0x180127777  push    r13
0x180127779  push    r14
0x18012777b  push    r15
0x18012777d  lea     rbp, [rsp-188h]
0x180127785  sub     rsp, 2D8h
0x18012778c  mov     rax, cs:__security_cookie
0x180127793  xor     rax, rsp
0x180127796  mov     [rbp+1C0h+var_50], rax
0x18012779d  mov     r15, [rbp+1C0h+arg_20]
0x1801277a4  lea     r14, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x1801277ab  mov     rsi, [rbp+1C0h+arg_38]
0x1801277b2  xor     r13d, r13d
0x1801277b5  mov     rbx, rcx
0x1801277b8  mov     [rbp+1C0h+var_200], rcx
0x1801277bc  xorps   xmm0, xmm0
0x1801277bf  mov     [rbp+1C0h+var_1B0], edx
0x1801277c2  mov     rcx, r14; this
0x1801277c5  mov     [rbp+1C0h+var_1B8], r9d
0x1801277c9  mov     r12, r8
0x1801277cc  mov     [rbp+1C0h+var_1C8], r13d
0x1801277d0  movdqu  [rbp+1C0h+var_238], xmm0
0x1801277d5  mov     [rbp+1C0h+Handle], r13
0x1801277d9  mov     [rbp+1C0h+var_178], r13d
0x1801277dd  mov     [rbp+1C0h+var_168], r13b
0x1801277e1  mov     [rbp+1C0h+var_198], 1
0x1801277e8  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1801277ed  lea     rcx, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801277f4  lea     rdx, aOa; "oa"
0x1801277fb  lea     rdi, aWindowsRtlSyst_306; "Windows::Rtl::SystemImplementation::Dir"...
0x180127802  test    al, 0Eh
0x180127804  jz      loc_1801278FE
0x18012780a  mov     [rsp+310h+var_250], rsi
0x180127812  lea     rax, ?Format_PCULONG_AsSysOpenKeyDisposition@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysOpenKeyDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180127819  mov     [rsp+310h+var_258], rax
0x180127821  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x180127828  lea     rax, aDisp; "disp"
0x18012782f  mov     r9, rbx; int
0x180127832  mov     [rsp+310h+var_260], rax
0x18012783a  lea     rax, [rbp+1C0h+var_1B8]
0x18012783e  mov     [rsp+310h+var_268], r15
0x180127846  mov     [rsp+310h+var_270], rcx
0x18012784e  lea     rcx, [rbp+1C0h+var_1A0]; int
0x180127852  mov     [rsp+310h+var_278], rdx
0x18012785a  lea     rdx, [rbp+1C0h+var_1C8]; int
0x18012785e  mov     [rsp+310h+var_280], rax
0x180127866  lea     rax, ?RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012786d  mov     [rsp+310h+var_288], rax
0x180127875  lea     rax, aDa; "da"
0x18012787c  mov     [rsp+310h+var_290], rax
0x180127884  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012788b  mov     [rsp+310h+var_298], r12
0x180127890  mov     [rsp+310h+var_2A0], rax
0x180127895  lea     rax, aKey; "key"
0x18012789c  mov     [rsp+310h+var_2A8], rax
0x1801278a1  lea     rax, [rbp+1C0h+var_1B0]
0x1801278a5  mov     [rsp+310h+var_2B0], rax
0x1801278aa  lea     rax, ?Format_PCULONG_AsSysOpenKeyFlags@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysOpenKeyFlags(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801278b1  mov     [rsp+310h+var_2B8], rax
0x1801278b6  lea     rax, aFlg; "flg"
0x1801278bd  mov     [rsp+310h+var_2C0], rax
0x1801278c2  lea     rax, aKeyKeyDispDisp; "(key = {key}, disp = {disp})"
0x1801278c9  mov     [rsp+310h+var_2C8], 5
0x1801278d2  mov     [rsp+310h+var_2D0], rax; __int64
0x1801278d7  lea     rax, aFlgFlgKeyKeyDa; "(flg = {flg}, key = {key}, da = {da}, o"...
0x1801278de  mov     [rsp+310h+var_2D8], rax; __int64
0x1801278e3  lea     rax, aFlgFlgDaDaOaOa; "(flg = {flg}, da = {da}, oa = {oa})"
0x1801278ea  mov     qword ptr [rsp+310h+var_2E0], rax; unsigned int
0x1801278ef  mov     [rsp+310h+var_2E8], r14; Windows::WCP::Rtl *
0x1801278f4  mov     [rsp+310h+var_2F0], rdi; __int64
0x1801278f9  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1801278fe  mov     rdx, [r15+10h]; struct _UNICODE_STRING *
0x180127902  lea     r8, [rbp+1C0h+var_240]; bool *
0x180127906  mov     [rbp+1C0h+var_240], r13b
0x18012790a  call    ?IsUnacceptableKeyPrefix@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@PEA_N@Z; Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(_UNICODE_STRING const &,bool *)
0x18012790f  mov     ebx, eax
0x180127911  test    eax, eax
0x180127913  jns     short loc_180127963
0x180127915  lea     rcx, [rbp+1C0h+var_1A0]
0x180127919  mov     [rbp+1C0h+var_1C8], eax
0x18012791c  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x180127921  mov     rax, [rbp+1C0h+Handle]
0x180127925  lea     rcx, [rax-1]
0x180127929  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18012792d  ja      short loc_180127942
0x18012792f  mov     [rbp+1C0h+Handle], r13
0x180127933  mov     rcx, rax; Handle
0x180127936  call    cs:__imp_NtClose
0x18012793d  nop     dword ptr [rax+rax+00h]
0x180127942  lea     rcx, [rbp+1C0h+var_238]; this
0x180127946  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18012794b  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x18012794f  test    rcx, rcx
0x180127952  jz      loc_180127D38
0x180127958  mov     rax, [rcx]
0x18012795b  mov     rax, [rax]
0x18012795e  jmp     loc_180127D33
0x180127963  cmp     [rbp+1C0h+var_240], r13b
0x180127967  jz      loc_1801279F3
0x18012796d  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180127974  mov     [rbp+1C0h+var_218], rdi
0x180127978  mov     r8d, 0C0000039h
0x18012797e  mov     [rbp+1C0h+var_220], rax
0x180127982  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180127989  mov     [rbp+1C0h+var_210], 159Bh
0x180127991  lea     rcx, [rbp+1C0h+var_220]
0x180127995  mov     [rbp+1C0h+var_208], r13
0x180127999  mov     [rbp+1C0h+var_1C8], 0C0000039h
0x1801279a0  call    RtlReportErrorOrigination
0x1801279a5  mov     ebx, [rbp+1C0h+var_1C8]
0x1801279a8  lea     rcx, [rbp+1C0h+var_1A0]
0x1801279ac  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x1801279b1  mov     rcx, [rbp+1C0h+Handle]; Handle
0x1801279b5  lea     rax, [rcx-1]
0x1801279b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801279bd  ja      short loc_1801279CF
0x1801279bf  mov     [rbp+1C0h+Handle], r13
0x1801279c3  call    cs:__imp_NtClose
0x1801279ca  nop     dword ptr [rax+rax+00h]
0x1801279cf  lea     rcx, [rbp+1C0h+var_238]; this
0x1801279d3  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801279d8  mov     rdx, qword ptr [rbp+1C0h+var_238]
0x1801279dc  test    rdx, rdx
0x1801279df  jz      loc_180127D38
0x1801279e5  mov     rcx, [rdx]
0x1801279e8  mov     rax, [rcx]
0x1801279eb  mov     rcx, rdx
0x1801279ee  jmp     loc_180127D33
0x1801279f3  mov     rbx, [rbp+1C0h+arg_30]
0x1801279fa  test    rbx, rbx
0x1801279fd  jz      short loc_180127A04
0x1801279ff  mov     rdx, [rbx]
0x180127a02  jmp     short loc_180127A07
0x180127a04  mov     rdx, r13
0x180127a07  mov     rcx, r15
0x180127a0a  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x180127a0f  mov     edi, eax
0x180127a11  test    eax, eax
0x180127a13  jns     short loc_180127A66
0x180127a15  lea     rcx, [rbp+1C0h+var_1A0]
0x180127a19  mov     [rbp+1C0h+var_1C8], eax
0x180127a1c  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x180127a21  mov     rax, [rbp+1C0h+Handle]
0x180127a25  lea     rcx, [rax-1]
0x180127a29  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180127a2d  ja      short loc_180127A42
0x180127a2f  mov     rcx, rax; Handle
0x180127a32  mov     [rbp+1C0h+Handle], r13
0x180127a36  call    cs:__imp_NtClose
0x180127a3d  nop     dword ptr [rax+rax+00h]
0x180127a42  lea     rcx, [rbp+1C0h+var_238]; this
0x180127a46  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180127a4b  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x180127a4f  test    rcx, rcx
0x180127a52  jz      short loc_180127A5F
0x180127a54  mov     rax, [rcx]
0x180127a57  mov     rax, [rax]
0x180127a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127a5f  mov     eax, edi
0x180127a61  jmp     loc_180127D3A
0x180127a66  test    rsi, rsi
0x180127a69  jz      short loc_180127A6E
0x180127a6b  mov     [rsi], r13d
0x180127a6e  movups  xmm2, xmmword ptr [r15]
0x180127a72  mov     rax, [r15+8]
0x180127a76  movups  xmm0, xmmword ptr [r15+10h]
0x180127a7b  movups  xmm1, xmmword ptr [r15+20h]
0x180127a80  movups  [rbp+1C0h+var_1F8], xmm2
0x180127a84  movups  [rbp+1C0h+var_1E8], xmm0
0x180127a88  movups  [rbp+1C0h+var_1D8], xmm1
0x180127a8c  test    rax, rax
0x180127a8f  jz      short loc_180127A98
0x180127a91  mov     rax, [rax]
0x180127a94  mov     qword ptr [rbp+1C0h+var_1F8+8], rax
0x180127a98  mov     edx, [rbp+1C0h+var_1B8]
0x180127a9b  mov     r14b, 1
0x180127a9e  bts     edx, 8
0x180127aa2  mov     [rbp+1C0h+var_228], r13d
0x180127aa6  mov     [rbp+1C0h+var_1B8], edx
0x180127aa9  mov     [rbp+1C0h+var_240], r14b
0x180127aad  mov     r9d, [rbp+1C0h+arg_28]
0x180127ab4  lea     r8, [rbp+1C0h+var_1F8]
0x180127ab8  lea     rcx, [rbp+1C0h+Handle]
0x180127abc  test    rbx, rbx
0x180127abf  jnz     short loc_180127ACF
0x180127ac1  call    cs:__imp_NtOpenKeyEx
0x180127ac8  nop     dword ptr [rax+rax+00h]
0x180127acd  jmp     short loc_180127AE3
0x180127acf  mov     rax, [rbx]
0x180127ad2  mov     [rsp+310h+var_2F0], rax
0x180127ad7  call    cs:__imp_NtOpenKeyTransactedEx
0x180127ade  nop     dword ptr [rax+rax+00h]
0x180127ae3  mov     edi, eax
0x180127ae5  cmp     eax, 0C000009Ah
0x180127aea  jnz     short loc_180127B07
0x180127aec  lea     rdx, [rbp+1C0h+var_240]; unsigned int *
0x180127af0  lea     rcx, [rbp+1C0h+var_228]; this
0x180127af4  call    ?DelayForInsufficientResources@SystemImplementation@Rtl@Windows@@YAJPEAKPEA_N@Z; Windows::Rtl::SystemImplementation::DelayForInsufficientResources(ulong *,bool *)
0x180127af9  mov     r14d, eax
0x180127afc  test    eax, eax
0x180127afe  js      short loc_180127B19
0x180127b00  mov     r14b, [rbp+1C0h+var_240]
0x180127b04  mov     r13b, 1
0x180127b07  test    r14b, r14b
0x180127b0a  jz      short loc_180127B6D
0x180127b0c  cmp     edi, 0C000009Ah
0x180127b12  jnz     short loc_180127B6D
0x180127b14  mov     edx, [rbp+1C0h+var_1B8]
0x180127b17  jmp     short loc_180127AAD
0x180127b19  lea     rcx, [rbp+1C0h+var_1A0]
0x180127b1d  mov     [rbp+1C0h+var_1C8], r14d
0x180127b21  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x180127b26  mov     rcx, [rbp+1C0h+Handle]; Handle
0x180127b2a  lea     rax, [rcx-1]
0x180127b2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180127b32  ja      short loc_180127B48
0x180127b34  mov     [rbp+1C0h+Handle], 0
0x180127b3c  call    cs:__imp_NtClose
0x180127b43  nop     dword ptr [rax+rax+00h]
0x180127b48  lea     rcx, [rbp+1C0h+var_238]; this
0x180127b4c  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180127b51  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x180127b55  test    rcx, rcx
0x180127b58  jz      short loc_180127B65
0x180127b5a  mov     rax, [rcx]
0x180127b5d  mov     rax, [rax]
0x180127b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127b65  mov     eax, r14d
0x180127b68  jmp     loc_180127D3A
0x180127b6d  xor     r14d, r14d
0x180127b70  test    edi, edi
0x180127b72  js      loc_180127C2D
0x180127b78  test    r13b, r13b
0x180127b7b  jz      short loc_180127BB3
0x180127b7d  lea     rax, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180127b84  mov     qword ptr [rsp+310h+var_2E0], r15
0x180127b89  mov     [rsp+310h+var_2E8], rax
0x180127b8e  lea     r9d, [r14+1]; char *
0x180127b92  lea     rax, aOa; "oa"
0x180127b99  xor     ecx, ecx; this
0x180127b9b  lea     r8, aTransientInsuf; "Transient insufficient resources at NtO"...
0x180127ba2  mov     [rsp+310h+var_2F0], rax; unsigned __int64
0x180127ba7  lea     rdx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180127bae  call    ?RtlTrace@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@QEBD_KZZ; Windows::WCP::Rtl::RtlTrace(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,...)
0x180127bb3  test    rbx, rbx
0x180127bb6  jz      short loc_180127BBD
0x180127bb8  mov     r9, [rbx]
0x180127bbb  jmp     short loc_180127BC0
0x180127bbd  mov     r9, r14
0x180127bc0  mov     rcx, [rbp+1C0h+var_200]
0x180127bc4  lea     r8, [rbp+1C0h+var_238]
0x180127bc8  lea     rdx, [rbp+1C0h+Handle]
0x180127bcc  call    ?Create@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJPEAVIRtlObjectProvider@234@$$QEAV?$Auto@PEAX@4@PEAVCSilHandle@234@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::Create(Windows::Rtl::SystemImplementation::IRtlObjectProvider *,Windows::Auto<void *> &&,Windows::Rtl::SystemImplementation::CSilHandle *,void *)
0x180127bd1  mov     ebx, eax
0x180127bd3  test    eax, eax
0x180127bd5  jns     short loc_180127BFE
0x180127bd7  lea     rcx, [rbp+1C0h+var_1A0]
0x180127bdb  mov     [rbp+1C0h+var_1C8], eax
0x180127bde  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x180127be3  mov     rcx, [rbp+1C0h+Handle]
0x180127be7  lea     rdx, [rcx-1]
0x180127beb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180127bef  ja      loc_180127942
0x180127bf5  mov     [rbp+1C0h+Handle], r14
0x180127bf9  jmp     loc_180127936
0x180127bfe  test    rsi, rsi
0x180127c01  jz      short loc_180127C09
0x180127c03  mov     dword ptr [rsi], 1
0x180127c09  mov     rcx, qword ptr [rbp+1C0h+var_238+8]
0x180127c0d  mov     rax, [r12+8]
0x180127c12  mov     qword ptr [rbp+1C0h+var_238+8], rax
0x180127c16  mov     rax, qword ptr [rbp+1C0h+var_238]
0x180127c1a  mov     [r12+8], rcx
0x180127c1f  mov     rcx, [r12]
0x180127c23  mov     [r12], rax
0x180127c27  mov     qword ptr [rbp+1C0h+var_238], rcx
0x180127c2b  jmp     short loc_180127C69
0x180127c2d  cmp     edi, 0C0000034h
0x180127c33  jz      short loc_180127C3D
0x180127c35  cmp     edi, 0C000003Ah
0x180127c3b  jnz     short loc_180127C50
0x180127c3d  test    byte ptr [rbp+1C0h+var_1B0], 1
0x180127c41  jz      short loc_180127C50
0x180127c43  test    rsi, rsi
0x180127c46  jz      short loc_180127C69
0x180127c48  mov     dword ptr [rsi], 2
0x180127c4e  jmp     short loc_180127C69
0x180127c50  cmp     edi, 0C0000022h
0x180127c56  jnz     short loc_180127CB9
0x180127c58  test    byte ptr [rbp+1C0h+var_1B0], 2
0x180127c5c  jz      short loc_180127CB9
0x180127c5e  test    rsi, rsi
0x180127c61  jz      short loc_180127C69
0x180127c63  mov     dword ptr [rsi], 3
0x180127c69  lea     rcx, [rbp+1C0h+var_1A0]
0x180127c6d  mov     [rbp+1C0h+var_168], 1
  ... truncated ...
```
