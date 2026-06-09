# Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x18018aa60`
- end: `0x18018b04e`
- name: `?SysOpenKey@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x1800059d0`
- `0x18017b8ec`
- `0x18017db9c`
- `0x18017f6c4`
- `0x18017ffa4`
- `0x18018258c`
- `0x180183c60`
- `0x180184fc0`
- `0x18018aa60`
- `0x180190700`
- `0x1801e4d48`
- `0x1801efdc0`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtOpenKeyTransactedEx` at `0x18018adc7`
- `ntdll!NtOpenKeyTransactedEx` at `0x18018adc7`
- `ntdll!NtOpenKeyEx` at `0x18018adb1`
- `ntdll!NtOpenKeyEx` at `0x18018adb1`
- `ntdll!NtClose` at `0x18018ac26`
- `ntdll!NtClose` at `0x18018acb3`
- `ntdll!NtClose` at `0x18018ad26`
- `ntdll!NtClose` at `0x18018ae2c`
- `ntdll!NtClose` at `0x18018af78`
- `ntdll!NtClose` at `0x18018afff`
- `ntdll!NtClose` at `0x18018ac26`
- `ntdll!NtClose` at `0x18018acb3`
- `ntdll!NtClose` at `0x18018ad26`
- `ntdll!NtClose` at `0x18018ae2c`
- `ntdll!NtClose` at `0x18018af78`
- `ntdll!NtClose` at `0x18018afff`

## string_xrefs

- `0x18018ae8b`: `Transient insufficient resources at NtOpenKey for {oa}`
- `0x18018aaeb`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey`
- `0x18018afc3`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysOpenKey`

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
0x18018aa60  push    rbp
0x18018aa62  push    rbx
0x18018aa63  push    rsi
0x18018aa64  push    rdi
0x18018aa65  push    r12
0x18018aa67  push    r13
0x18018aa69  push    r14
0x18018aa6b  push    r15
0x18018aa6d  lea     rbp, [rsp-188h]
0x18018aa75  sub     rsp, 2D8h
0x18018aa7c  mov     rax, cs:__security_cookie
0x18018aa83  xor     rax, rsp
0x18018aa86  mov     [rbp+1C0h+var_50], rax
0x18018aa8d  mov     r15, [rbp+1C0h+arg_20]
0x18018aa94  lea     r14, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18018aa9b  mov     rsi, [rbp+1C0h+arg_38]
0x18018aaa2  xor     r13d, r13d
0x18018aaa5  mov     rbx, rcx
0x18018aaa8  mov     [rbp+1C0h+var_200], rcx
0x18018aaac  xorps   xmm0, xmm0
0x18018aaaf  mov     [rbp+1C0h+var_1B0], edx
0x18018aab2  mov     rcx, r14; this
0x18018aab5  mov     [rbp+1C0h+var_1B8], r9d
0x18018aab9  mov     r12, r8
0x18018aabc  mov     [rbp+1C0h+var_1C8], r13d
0x18018aac0  movdqu  [rbp+1C0h+var_238], xmm0
0x18018aac5  mov     [rbp+1C0h+Handle], r13
0x18018aac9  mov     [rbp+1C0h+var_178], r13d
0x18018aacd  mov     [rbp+1C0h+var_168], r13b
0x18018aad1  mov     [rbp+1C0h+var_198], 1
0x18018aad8  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18018aadd  lea     rcx, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018aae4  lea     rdx, aOa; "oa"
0x18018aaeb  lea     rdi, aWindowsRtlSyst_306; "Windows::Rtl::SystemImplementation::Dir"...
0x18018aaf2  test    al, 0Eh
0x18018aaf4  jz      loc_18018ABEE
0x18018aafa  mov     [rsp+310h+var_250], rsi
0x18018ab02  lea     rax, ?Format_PCULONG_AsSysOpenKeyDisposition@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysOpenKeyDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018ab09  mov     [rsp+310h+var_258], rax
0x18018ab11  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x18018ab18  lea     rax, aDisp; "disp"
0x18018ab1f  mov     r9, rbx; int
0x18018ab22  mov     [rsp+310h+var_260], rax
0x18018ab2a  lea     rax, [rbp+1C0h+var_1B8]
0x18018ab2e  mov     [rsp+310h+var_268], r15
0x18018ab36  mov     [rsp+310h+var_270], rcx
0x18018ab3e  lea     rcx, [rbp+1C0h+var_1A0]; int
0x18018ab42  mov     [rsp+310h+var_278], rdx
0x18018ab4a  lea     rdx, [rbp+1C0h+var_1C8]; int
0x18018ab4e  mov     [rsp+310h+var_280], rax
0x18018ab56  lea     rax, ?RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018ab5d  mov     [rsp+310h+var_288], rax
0x18018ab65  lea     rax, aDa; "da"
0x18018ab6c  mov     [rsp+310h+var_290], rax
0x18018ab74  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018ab7b  mov     [rsp+310h+var_298], r12
0x18018ab80  mov     [rsp+310h+var_2A0], rax
0x18018ab85  lea     rax, aKey; "key"
0x18018ab8c  mov     [rsp+310h+var_2A8], rax
0x18018ab91  lea     rax, [rbp+1C0h+var_1B0]
0x18018ab95  mov     [rsp+310h+var_2B0], rax
0x18018ab9a  lea     rax, ?Format_PCULONG_AsSysOpenKeyFlags@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysOpenKeyFlags(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018aba1  mov     [rsp+310h+var_2B8], rax
0x18018aba6  lea     rax, aFlg; "flg"
0x18018abad  mov     [rsp+310h+var_2C0], rax
0x18018abb2  lea     rax, aKeyKeyDispDisp; "(key = {key}, disp = {disp})"
0x18018abb9  mov     [rsp+310h+var_2C8], 5
0x18018abc2  mov     [rsp+310h+var_2D0], rax; __int64
0x18018abc7  lea     rax, aFlgFlgKeyKeyDa; "(flg = {flg}, key = {key}, da = {da}, o"...
0x18018abce  mov     [rsp+310h+var_2D8], rax; __int64
0x18018abd3  lea     rax, aFlgFlgDaDaOaOa; "(flg = {flg}, da = {da}, oa = {oa})"
0x18018abda  mov     qword ptr [rsp+310h+var_2E0], rax; unsigned int
0x18018abdf  mov     [rsp+310h+var_2E8], r14; Windows::WCP::Rtl *
0x18018abe4  mov     [rsp+310h+var_2F0], rdi; __int64
0x18018abe9  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18018abee  mov     rdx, [r15+10h]; struct _UNICODE_STRING *
0x18018abf2  lea     r8, [rbp+1C0h+var_240]; bool *
0x18018abf6  mov     [rbp+1C0h+var_240], r13b
0x18018abfa  call    ?IsUnacceptableKeyPrefix@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@PEA_N@Z; Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(_UNICODE_STRING const &,bool *)
0x18018abff  mov     ebx, eax
0x18018ac01  test    eax, eax
0x18018ac03  jns     short loc_18018AC53
0x18018ac05  lea     rcx, [rbp+1C0h+var_1A0]
0x18018ac09  mov     [rbp+1C0h+var_1C8], eax
0x18018ac0c  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x18018ac11  mov     rax, [rbp+1C0h+Handle]
0x18018ac15  lea     rcx, [rax-1]
0x18018ac19  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018ac1d  ja      short loc_18018AC32
0x18018ac1f  mov     [rbp+1C0h+Handle], r13
0x18018ac23  mov     rcx, rax; Handle
0x18018ac26  call    cs:__imp_NtClose
0x18018ac2d  nop     dword ptr [rax+rax+00h]
0x18018ac32  lea     rcx, [rbp+1C0h+var_238]; this
0x18018ac36  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18018ac3b  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x18018ac3f  test    rcx, rcx
0x18018ac42  jz      loc_18018B028
0x18018ac48  mov     rax, [rcx]
0x18018ac4b  mov     rax, [rax]
0x18018ac4e  jmp     loc_18018B023
0x18018ac53  cmp     [rbp+1C0h+var_240], r13b
0x18018ac57  jz      loc_18018ACE3
0x18018ac5d  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18018ac64  mov     [rbp+1C0h+var_218], rdi
0x18018ac68  mov     r8d, 0C0000039h
0x18018ac6e  mov     [rbp+1C0h+var_220], rax
0x18018ac72  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18018ac79  mov     [rbp+1C0h+var_210], 159Bh
0x18018ac81  lea     rcx, [rbp+1C0h+var_220]
0x18018ac85  mov     [rbp+1C0h+var_208], r13
0x18018ac89  mov     [rbp+1C0h+var_1C8], 0C0000039h
0x18018ac90  call    RtlReportErrorOrigination
0x18018ac95  mov     ebx, [rbp+1C0h+var_1C8]
0x18018ac98  lea     rcx, [rbp+1C0h+var_1A0]
0x18018ac9c  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x18018aca1  mov     rcx, [rbp+1C0h+Handle]; Handle
0x18018aca5  lea     rax, [rcx-1]
0x18018aca9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018acad  ja      short loc_18018ACBF
0x18018acaf  mov     [rbp+1C0h+Handle], r13
0x18018acb3  call    cs:__imp_NtClose
0x18018acba  nop     dword ptr [rax+rax+00h]
0x18018acbf  lea     rcx, [rbp+1C0h+var_238]; this
0x18018acc3  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18018acc8  mov     rdx, qword ptr [rbp+1C0h+var_238]
0x18018accc  test    rdx, rdx
0x18018accf  jz      loc_18018B028
0x18018acd5  mov     rcx, [rdx]
0x18018acd8  mov     rax, [rcx]
0x18018acdb  mov     rcx, rdx
0x18018acde  jmp     loc_18018B023
0x18018ace3  mov     rbx, [rbp+1C0h+arg_30]
0x18018acea  test    rbx, rbx
0x18018aced  jz      short loc_18018ACF4
0x18018acef  mov     rdx, [rbx]
0x18018acf2  jmp     short loc_18018ACF7
0x18018acf4  mov     rdx, r13
0x18018acf7  mov     rcx, r15
0x18018acfa  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x18018acff  mov     edi, eax
0x18018ad01  test    eax, eax
0x18018ad03  jns     short loc_18018AD56
0x18018ad05  lea     rcx, [rbp+1C0h+var_1A0]
0x18018ad09  mov     [rbp+1C0h+var_1C8], eax
0x18018ad0c  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x18018ad11  mov     rax, [rbp+1C0h+Handle]
0x18018ad15  lea     rcx, [rax-1]
0x18018ad19  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018ad1d  ja      short loc_18018AD32
0x18018ad1f  mov     rcx, rax; Handle
0x18018ad22  mov     [rbp+1C0h+Handle], r13
0x18018ad26  call    cs:__imp_NtClose
0x18018ad2d  nop     dword ptr [rax+rax+00h]
0x18018ad32  lea     rcx, [rbp+1C0h+var_238]; this
0x18018ad36  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18018ad3b  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x18018ad3f  test    rcx, rcx
0x18018ad42  jz      short loc_18018AD4F
0x18018ad44  mov     rax, [rcx]
0x18018ad47  mov     rax, [rax]
0x18018ad4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ad4f  mov     eax, edi
0x18018ad51  jmp     loc_18018B02A
0x18018ad56  test    rsi, rsi
0x18018ad59  jz      short loc_18018AD5E
0x18018ad5b  mov     [rsi], r13d
0x18018ad5e  movups  xmm2, xmmword ptr [r15]
0x18018ad62  mov     rax, [r15+8]
0x18018ad66  movups  xmm0, xmmword ptr [r15+10h]
0x18018ad6b  movups  xmm1, xmmword ptr [r15+20h]
0x18018ad70  movups  [rbp+1C0h+var_1F8], xmm2
0x18018ad74  movups  [rbp+1C0h+var_1E8], xmm0
0x18018ad78  movups  [rbp+1C0h+var_1D8], xmm1
0x18018ad7c  test    rax, rax
0x18018ad7f  jz      short loc_18018AD88
0x18018ad81  mov     rax, [rax]
0x18018ad84  mov     qword ptr [rbp+1C0h+var_1F8+8], rax
0x18018ad88  mov     edx, [rbp+1C0h+var_1B8]
0x18018ad8b  mov     r14b, 1
0x18018ad8e  bts     edx, 8
0x18018ad92  mov     [rbp+1C0h+var_228], r13d
0x18018ad96  mov     [rbp+1C0h+var_1B8], edx
0x18018ad99  mov     [rbp+1C0h+var_240], r14b
0x18018ad9d  mov     r9d, [rbp+1C0h+arg_28]
0x18018ada4  lea     r8, [rbp+1C0h+var_1F8]
0x18018ada8  lea     rcx, [rbp+1C0h+Handle]
0x18018adac  test    rbx, rbx
0x18018adaf  jnz     short loc_18018ADBF
0x18018adb1  call    cs:__imp_NtOpenKeyEx
0x18018adb8  nop     dword ptr [rax+rax+00h]
0x18018adbd  jmp     short loc_18018ADD3
0x18018adbf  mov     rax, [rbx]
0x18018adc2  mov     [rsp+310h+var_2F0], rax
0x18018adc7  call    cs:__imp_NtOpenKeyTransactedEx
0x18018adce  nop     dword ptr [rax+rax+00h]
0x18018add3  mov     edi, eax
0x18018add5  cmp     eax, 0C000009Ah
0x18018adda  jnz     short loc_18018ADF7
0x18018addc  lea     rdx, [rbp+1C0h+var_240]; unsigned int *
0x18018ade0  lea     rcx, [rbp+1C0h+var_228]; this
0x18018ade4  call    ?DelayForInsufficientResources@SystemImplementation@Rtl@Windows@@YAJPEAKPEA_N@Z; Windows::Rtl::SystemImplementation::DelayForInsufficientResources(ulong *,bool *)
0x18018ade9  mov     r14d, eax
0x18018adec  test    eax, eax
0x18018adee  js      short loc_18018AE09
0x18018adf0  mov     r14b, [rbp+1C0h+var_240]
0x18018adf4  mov     r13b, 1
0x18018adf7  test    r14b, r14b
0x18018adfa  jz      short loc_18018AE5D
0x18018adfc  cmp     edi, 0C000009Ah
0x18018ae02  jnz     short loc_18018AE5D
0x18018ae04  mov     edx, [rbp+1C0h+var_1B8]
0x18018ae07  jmp     short loc_18018AD9D
0x18018ae09  lea     rcx, [rbp+1C0h+var_1A0]
0x18018ae0d  mov     [rbp+1C0h+var_1C8], r14d
0x18018ae11  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x18018ae16  mov     rcx, [rbp+1C0h+Handle]; Handle
0x18018ae1a  lea     rax, [rcx-1]
0x18018ae1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018ae22  ja      short loc_18018AE38
0x18018ae24  mov     [rbp+1C0h+Handle], 0
0x18018ae2c  call    cs:__imp_NtClose
0x18018ae33  nop     dword ptr [rax+rax+00h]
0x18018ae38  lea     rcx, [rbp+1C0h+var_238]; this
0x18018ae3c  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18018ae41  mov     rcx, qword ptr [rbp+1C0h+var_238]
0x18018ae45  test    rcx, rcx
0x18018ae48  jz      short loc_18018AE55
0x18018ae4a  mov     rax, [rcx]
0x18018ae4d  mov     rax, [rax]
0x18018ae50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ae55  mov     eax, r14d
0x18018ae58  jmp     loc_18018B02A
0x18018ae5d  xor     r14d, r14d
0x18018ae60  test    edi, edi
0x18018ae62  js      loc_18018AF1D
0x18018ae68  test    r13b, r13b
0x18018ae6b  jz      short loc_18018AEA3
0x18018ae6d  lea     rax, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018ae74  mov     qword ptr [rsp+310h+var_2E0], r15
0x18018ae79  mov     [rsp+310h+var_2E8], rax
0x18018ae7e  lea     r9d, [r14+1]; char *
0x18018ae82  lea     rax, aOa; "oa"
0x18018ae89  xor     ecx, ecx; this
0x18018ae8b  lea     r8, aTransientInsuf; "Transient insufficient resources at NtO"...
0x18018ae92  mov     [rsp+310h+var_2F0], rax; unsigned __int64
0x18018ae97  lea     rdx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x18018ae9e  call    ?RtlTrace@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@QEBD_KZZ; Windows::WCP::Rtl::RtlTrace(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,...)
0x18018aea3  test    rbx, rbx
0x18018aea6  jz      short loc_18018AEAD
0x18018aea8  mov     r9, [rbx]
0x18018aeab  jmp     short loc_18018AEB0
0x18018aead  mov     r9, r14
0x18018aeb0  mov     rcx, [rbp+1C0h+var_200]
0x18018aeb4  lea     r8, [rbp+1C0h+var_238]
0x18018aeb8  lea     rdx, [rbp+1C0h+Handle]
0x18018aebc  call    ?Create@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJPEAVIRtlObjectProvider@234@$$QEAV?$Auto@PEAX@4@PEAVCSilHandle@234@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::Create(Windows::Rtl::SystemImplementation::IRtlObjectProvider *,Windows::Auto<void *> &&,Windows::Rtl::SystemImplementation::CSilHandle *,void *)
0x18018aec1  mov     ebx, eax
0x18018aec3  test    eax, eax
0x18018aec5  jns     short loc_18018AEEE
0x18018aec7  lea     rcx, [rbp+1C0h+var_1A0]
0x18018aecb  mov     [rbp+1C0h+var_1C8], eax
0x18018aece  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$04@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,5>(void)
0x18018aed3  mov     rcx, [rbp+1C0h+Handle]
0x18018aed7  lea     rdx, [rcx-1]
0x18018aedb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18018aedf  ja      loc_18018AC32
0x18018aee5  mov     [rbp+1C0h+Handle], r14
0x18018aee9  jmp     loc_18018AC26
0x18018aeee  test    rsi, rsi
0x18018aef1  jz      short loc_18018AEF9
0x18018aef3  mov     dword ptr [rsi], 1
0x18018aef9  mov     rcx, qword ptr [rbp+1C0h+var_238+8]
0x18018aefd  mov     rax, [r12+8]
0x18018af02  mov     qword ptr [rbp+1C0h+var_238+8], rax
0x18018af06  mov     rax, qword ptr [rbp+1C0h+var_238]
0x18018af0a  mov     [r12+8], rcx
0x18018af0f  mov     rcx, [r12]
0x18018af13  mov     [r12], rax
0x18018af17  mov     qword ptr [rbp+1C0h+var_238], rcx
0x18018af1b  jmp     short loc_18018AF59
0x18018af1d  cmp     edi, 0C0000034h
0x18018af23  jz      short loc_18018AF2D
0x18018af25  cmp     edi, 0C000003Ah
0x18018af2b  jnz     short loc_18018AF40
0x18018af2d  test    byte ptr [rbp+1C0h+var_1B0], 1
0x18018af31  jz      short loc_18018AF40
0x18018af33  test    rsi, rsi
0x18018af36  jz      short loc_18018AF59
0x18018af38  mov     dword ptr [rsi], 2
0x18018af3e  jmp     short loc_18018AF59
0x18018af40  cmp     edi, 0C0000022h
0x18018af46  jnz     short loc_18018AFA9
0x18018af48  test    byte ptr [rbp+1C0h+var_1B0], 2
0x18018af4c  jz      short loc_18018AFA9
0x18018af4e  test    rsi, rsi
0x18018af51  jz      short loc_18018AF59
0x18018af53  mov     dword ptr [rsi], 3
0x18018af59  lea     rcx, [rbp+1C0h+var_1A0]
0x18018af5d  mov     [rbp+1C0h+var_168], 1
  ... truncated ...
```
