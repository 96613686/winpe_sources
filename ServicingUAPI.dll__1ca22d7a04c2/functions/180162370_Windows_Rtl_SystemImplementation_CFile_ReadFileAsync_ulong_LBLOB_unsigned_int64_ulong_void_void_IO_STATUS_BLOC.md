# Windows::Rtl::SystemImplementation::CFile::ReadFileAsync(ulong,_LBLOB *,unsigned __int64 *,ulong,void (*)(void *,_IO_STATUS_BLOCK *,ulong),void *,_IO_STATUS_BLOCK *,ulong *)

- ea: `0x180162370`
- end: `0x1801629a0`
- name: `?ReadFileAsync@CFile@SystemImplementation@Rtl@Windows@@UEAAJKPEAU_LBLOB@@PEA_KKP6AXPEAXPEAU_IO_STATUS_BLOCK@@K@Z23PEAK@Z`
- size: `1584`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFile *__hidden this, unsigned int, struct _LBLOB *, unsigned __int64 *, unsigned int, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x180030b68`
- `0x1800497c0`
- `0x180118530`
- `0x18011a948`
- `0x180162370`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18016281f`
- `ntdll!NtWaitForSingleObject` at `0x18016281f`
- `ntdll!TpCancelAsyncIoOperation` at `0x180162756`
- `ntdll!TpCancelAsyncIoOperation` at `0x18016287e`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801628cd`
- `ntdll!TpCancelAsyncIoOperation` at `0x180162756`
- `ntdll!TpCancelAsyncIoOperation` at `0x18016287e`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801628cd`
- `ntdll!TpStartAsyncIoOperation` at `0x1801626ca`
- `ntdll!TpStartAsyncIoOperation` at `0x1801626ca`
- `ntdll!NtCreateEvent` at `0x180162580`
- `ntdll!NtCreateEvent` at `0x180162580`
- `ntdll!NtClose` at `0x1801625d5`
- `ntdll!NtClose` at `0x180162697`
- `ntdll!NtClose` at `0x18016276c`
- `ntdll!NtClose` at `0x180162894`
- `ntdll!NtClose` at `0x1801628f1`
- `ntdll!NtClose` at `0x1801625d5`
- `ntdll!NtClose` at `0x180162697`
- `ntdll!NtClose` at `0x18016276c`
- `ntdll!NtClose` at `0x180162894`
- `ntdll!NtClose` at `0x1801628f1`

## string_xrefs

- `0x1801625aa`: `::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )`
- `0x180162403`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`
- `0x180162650`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`
- `0x180162841`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CFile::ReadFileAsync(
        Windows::Rtl::SystemImplementation::CFile *this,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        struct _LBLOB *a3,
        unsigned __int64 *a4,
        unsigned int a5,
        void (*a6)(void *, struct _IO_STATUS_BLOCK *, unsigned int),
        void *a7,
        struct _IO_STATUS_BLOCK *a8,
        unsigned int *a9)
{
  __int64 v12; // rdx
  __int64 v13; // r8
  char v14; // cl
  _QWORD *v15; // rcx
  _QWORD *v16; // rsi
  NTSTATUS v17; // eax
  unsigned int v18; // ebx
  char v19; // r12
  unsigned int v20; // ebx
  int v21; // eax
  char v22; // cl
  ULONG_PTR v23; // rax
  ULONG_PTR Information; // rax
  NTSTATUS v25; // eax
  _QWORD v27[4]; // [rsp+C8h] [rbp-68h] BYREF
  _QWORD v28[4]; // [rsp+E8h] [rbp-48h] BYREF
  _QWORD v29[4]; // [rsp+108h] [rbp-28h] BYREF
  _QWORD v30[4]; // [rsp+128h] [rbp-8h] BYREF
  _QWORD v31[4]; // [rsp+148h] [rbp+18h] BYREF
  _QWORD v32[5]; // [rsp+168h] [rbp+38h] BYREF
  unsigned int v33; // [rsp+190h] [rbp+60h] BYREF
  void *EventHandle; // [rsp+198h] [rbp+68h] BYREF
  int v35; // [rsp+1A0h] [rbp+70h] BYREF
  int v36; // [rsp+1A8h] [rbp+78h] BYREF
  unsigned __int64 v37; // [rsp+1B0h] [rbp+80h] BYREF
  _BYTE v38[8]; // [rsp+1C0h] [rbp+90h] BYREF
  int v39; // [rsp+1C8h] [rbp+98h]
  int v40; // [rsp+1E8h] [rbp+B8h]
  char v41; // [rsp+1F8h] [rbp+C8h]

  v32[4] = -2;
  v35 = (int)a2;
  v33 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 1;
  if ( (Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, a2) & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::Arm(
      v38,
      &v33,
      Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      this,
      "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync",
      &Windows::WCP::Rtl::Facility_SIL,
      0,
      "(Flags = {flg}, Buffer = {buf}, Offset = {off}, Disposition = {disp})",
      0,
      4,
      "flg",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      &v35,
      "buf",
      Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength,
      a3,
      "off",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG,
      a4,
      "disp",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      a9);
  if ( !a9 )
  {
    v32[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v32[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
    v32[2] = 1595;
    v32[3] = "Disposition";
    v15 = v32;
    goto LABEL_70;
  }
  *a9 = 0;
  v14 = v35;
  if ( (v35 & 0xFFFFFFF8) != 0 )
  {
    v27[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v27[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
    v27[2] = 1601;
    v27[3] = "Valid flags check failed: Flags";
    v15 = v27;
LABEL_70:
    v33 = -1073741811;
    RtlReportErrorOrigination(v15, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v18 = v33;
LABEL_71:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>(v38);
    return v18;
  }
  if ( (unsigned __int64)a5 > *((_QWORD *)a3 + 1) )
  {
    v28[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v28[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
    v28[2] = 1603;
    v28[3] = "Length <= Buffer->MaximumLength";
    v15 = v28;
    goto LABEL_70;
  }
  *(_QWORD *)a3 = 0;
  v16 = (_QWORD *)((char *)this + 96);
  if ( (v14 & 4) == 0 || *v16 )
  {
    v19 = 0;
    EventHandle = 0;
  }
  else
  {
    EventHandle = 0;
    v17 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    v13 = (unsigned int)v17;
    if ( v17 < 0 )
    {
      v29[0] = "onecore\\base\\wcp\\sil\\file.cpp";
      v29[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
      v29[2] = 1617;
      v29[3] = "::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )";
      v33 = v17;
      RtlReportErrorOrigination(v29, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v17);
      v18 = v33;
      if ( EventHandle )
      {
        if ( NtClose(EventHandle) < 0 )
          __fastfail(7u);
        EventHandle = 0;
      }
      goto LABEL_71;
    }
    v19 = 1;
    v14 = v35;
  }
  v37 = 0;
  v36 = 0;
  v20 = (2 * (v14 & 1) + 8) | 4;
  if ( (v14 & 2) == 0 )
    v20 = 2 * (v14 & 1) + 8;
  if ( a4 )
  {
    if ( *a4 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v30[0] = "onecore\\base\\wcp\\sil\\file.cpp";
      v30[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
      v30[2] = 1636;
      v30[3] = "*Offset <= (0x7fffffffffffffff)";
      v33 = -1073741675;
      RtlReportErrorOrigination(v30, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
      v18 = v33;
      if ( EventHandle )
      {
        if ( NtClose(EventHandle) < 0 )
          __fastfail(7u);
        EventHandle = 0;
      }
      goto LABEL_71;
    }
    v37 = *a4;
  }
  if ( *v16 )
    TpStartAsyncIoOperation(*v16, v12, v13);
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, _QWORD, unsigned int, unsigned __int64, _QWORD, int *))(**((_QWORD **)this + 9) + 120LL))(
          *((_QWORD *)this + 9),
          v20,
          *((_QWORD *)this + 5),
          EventHandle,
          a6,
          a7,
          a8,
          *((_QWORD *)a3 + 2),
          a5,
          (unsigned __int64)&v37 & -(__int64)(a4 != 0),
          0,
          &v36);
  v18 = v21;
  if ( v21 < 0 )
  {
    v33 = v21;
    if ( *v16 )
      TpCancelAsyncIoOperation();
    if ( EventHandle )
    {
      if ( NtClose(EventHandle) < 0 )
        __fastfail(7u);
      EventHandle = 0;
    }
    goto LABEL_71;
  }
  if ( v36 != 1 )
  {
    switch ( v36 )
    {
      case 2:
        if ( (v35 & 1) == 0 )
          goto LABEL_72;
        *a9 = 2;
        break;
      case 3:
        if ( (v35 & 2) == 0 || (Information = a8->Information, Information > *((_QWORD *)a3 + 1)) )
        {
LABEL_72:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x18016299FLL);
        }
        *(_QWORD *)a3 = Information;
        *a9 = 3;
        break;
      case 4:
        if ( !v19 )
        {
          *a9 = 4;
          v41 = 1;
          goto LABEL_64;
        }
        v25 = NtWaitForSingleObject(EventHandle, 0, 0);
        if ( v25 < 0 )
        {
          v31[0] = "onecore\\base\\wcp\\sil\\file.cpp";
          v31[1] = "Windows::Rtl::SystemImplementation::CFile::ReadFileAsync";
          v31[2] = 1702;
          v31[3] = "::NtWaitForSingleObject(WaitEvent, 0 , nullptr)";
          v33 = v25;
          RtlReportErrorOrigination(v31, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v25);
          v18 = v33;
          if ( *v16 )
            TpCancelAsyncIoOperation();
          if ( EventHandle )
          {
            if ( NtClose(EventHandle) < 0 )
              __fastfail(7u);
            EventHandle = 0;
          }
          goto LABEL_71;
        }
        *a9 = 5;
        break;
      default:
        goto LABEL_72;
    }
    v41 = 1;
    goto LABEL_61;
  }
  v22 = *((_BYTE *)this + 104);
  *a9 = 1;
  v23 = a8->Information;
  if ( v23 > *((_QWORD *)a3 + 1) )
    goto LABEL_72;
  *(_QWORD *)a3 = v23;
  v41 = 1;
  if ( v22 )
  {
LABEL_61:
    if ( *v16 )
      TpCancelAsyncIoOperation();
  }
LABEL_64:
  if ( EventHandle )
  {
    if ( NtClose(EventHandle) < 0 )
      __fastfail(7u);
    EventHandle = 0;
  }
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>(v38);
  return v33;
}

```

## disassembly

```asm
0x180162370  push    rbp
0x180162372  push    rbx
0x180162373  push    rsi
0x180162374  push    rdi
0x180162375  push    r12
0x180162377  push    r13
0x180162379  push    r14
0x18016237b  push    r15
0x18016237d  lea     rbp, [rsp-1E8h]
0x180162385  sub     rsp, 318h
0x18016238c  mov     [rbp+220h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x180162394  mov     rax, cs:__security_cookie
0x18016239b  xor     rax, rsp
0x18016239e  mov     [rbp+220h+var_50], rax
0x1801623a5  mov     r13, r9
0x1801623a8  mov     r14, r8
0x1801623ab  mov     r15, rcx
0x1801623ae  mov     [rbp+220h+var_1B0], edx
0x1801623b1  mov     rax, [rbp+220h+arg_28]
0x1801623b8  mov     [rbp+220h+var_290], rax
0x1801623bc  mov     rax, [rbp+220h+arg_30]
0x1801623c3  mov     [rbp+220h+var_298], rax
0x1801623c7  mov     rax, [rbp+220h+arg_38]
0x1801623ce  mov     [rbp+220h+var_2A0], rax
0x1801623d2  mov     rdi, [rbp+220h+arg_40]
0x1801623d9  xor     ebx, ebx
0x1801623db  mov     [rbp+220h+var_1C0], ebx
0x1801623de  mov     [rbp+220h+var_168], ebx
0x1801623e4  mov     [rbp+220h+var_158], bl
0x1801623ea  mov     [rbp+220h+var_188], 1
0x1801623f4  lea     rsi, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x1801623fb  mov     rcx, rsi; this
0x1801623fe  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180162403  lea     r12, aWindowsRtlSyst_82; "Windows::Rtl::SystemImplementation::CFi"...
0x18016240a  test    al, 0Eh
0x18016240c  jz      loc_1801624D8
0x180162412  mov     [rsp+350h+var_2A8], rdi
0x18016241a  lea     rcx, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180162421  mov     [rsp+350h+var_2B0], rcx
0x180162429  lea     rax, aDisp; "disp"
0x180162430  mov     [rsp+350h+var_2B8], rax
0x180162438  mov     [rsp+350h+var_2C0], r13
0x180162440  lea     rax, ?RtlTraceFormat_PCULONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180162447  mov     [rsp+350h+var_2C8], rax
0x18016244f  lea     rax, aOff; "off"
0x180162456  mov     [rsp+350h+var_2D0], rax
0x18016245e  mov     [rsp+350h+var_2D8], r14
0x180162463  lea     rax, ?RtlTraceFormat_PCLBLOB_LimitLength@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18016246a  mov     [rsp+350h+var_2E0], rax
0x18016246f  lea     rax, aBuf; "buf"
0x180162476  mov     [rsp+350h+var_2E8], rax
0x18016247b  lea     rax, [rbp+220h+var_1B0]
0x18016247f  mov     [rsp+350h+var_2F0], rax
0x180162484  mov     [rsp+350h+var_2F8], rcx
0x180162489  lea     rax, aFlg; "flg"
0x180162490  mov     [rsp+350h+var_300], rax
0x180162495  mov     [rsp+350h+var_308], 4
0x18016249e  mov     [rsp+350h+var_310], rbx
0x1801624a3  lea     rax, aFlagsFlgBuffer; "(Flags = {flg}, Buffer = {buf}, Offset "...
0x1801624aa  mov     [rsp+350h+var_318], rax
0x1801624af  mov     [rsp+350h+var_320], rbx
0x1801624b4  mov     [rsp+350h+var_328], rsi
0x1801624b9  mov     qword ptr [rsp+350h+InitialState], r12
0x1801624be  mov     r9, r15
0x1801624c1  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801624c8  lea     rdx, [rbp+220h+var_1C0]
0x1801624cc  lea     rcx, [rbp+220h+var_190]
0x1801624d3  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$03@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1801624d8  test    rdi, rdi
0x1801624db  jz      loc_180162921
0x1801624e1  mov     [rdi], ebx
0x1801624e3  mov     ecx, [rbp+220h+var_1B0]
0x1801624e6  test    ecx, 0FFFFFFF8h
0x1801624ec  jz      short loc_180162519
0x1801624ee  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x1801624f5  mov     [rbp+220h+var_288], rax
0x1801624f9  mov     [rbp+220h+var_280], r12
0x1801624fd  mov     [rbp+220h+var_278], 641h
0x180162505  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x18016250c  mov     [rbp+220h+var_270], rax
0x180162510  lea     rcx, [rbp+220h+var_288]
0x180162514  jmp     loc_180162947
0x180162519  mov     eax, [rbp+220h+arg_20]
0x18016251f  cmp     rax, [r14+8]
0x180162523  jbe     short loc_180162550
0x180162525  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x18016252c  mov     [rbp+220h+var_268], rax
0x180162530  mov     [rbp+220h+var_260], r12
0x180162534  mov     [rbp+220h+var_258], 643h
0x18016253c  lea     rax, aLengthBufferMa; "Length <= Buffer->MaximumLength"
0x180162543  mov     [rbp+220h+var_250], rax
0x180162547  lea     rcx, [rbp+220h+var_268]
0x18016254b  jmp     loc_180162947
0x180162550  mov     [r14], rbx
0x180162553  lea     rsi, [r15+60h]
0x180162557  test    cl, 4
0x18016255a  jz      loc_180162601
0x180162560  cmp     [rsi], rbx
0x180162563  jnz     loc_180162601
0x180162569  mov     [rbp+220h+EventHandle], rbx
0x18016256d  mov     [rsp+350h+InitialState], bl; InitialState
0x180162571  xor     r9d, r9d; EventType
0x180162574  xor     r8d, r8d; ObjectAttributes
0x180162577  mov     edx, 1F0003h; DesiredAccess
0x18016257c  lea     rcx, [rbp+220h+EventHandle]; EventHandle
0x180162580  call    cs:__imp_NtCreateEvent
0x180162587  nop     dword ptr [rax+rax+00h]
0x18016258c  mov     r8d, eax
0x18016258f  test    eax, eax
0x180162591  jns     short loc_1801625F9
0x180162593  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x18016259a  mov     [rbp+220h+var_248], rax
0x18016259e  mov     [rbp+220h+var_240], r12
0x1801625a2  mov     [rbp+220h+var_238], 651h
0x1801625aa  lea     rax, aNtcreateeventW; "::NtCreateEvent( WaitEvent.GetInitPoint"...
0x1801625b1  mov     [rbp+220h+var_230], rax
0x1801625b5  mov     [rbp+220h+var_1C0], r8d
0x1801625b9  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801625c0  lea     rcx, [rbp+220h+var_248]
0x1801625c4  call    RtlReportErrorOrigination
0x1801625c9  mov     ebx, [rbp+220h+var_1C0]
0x1801625cc  mov     rcx, [rbp+220h+EventHandle]; Handle
0x1801625d0  test    rcx, rcx
0x1801625d3  jz      short loc_1801625F4
0x1801625d5  call    cs:__imp_NtClose
0x1801625dc  nop     dword ptr [rax+rax+00h]
0x1801625e1  test    eax, eax
0x1801625e3  jns     short loc_1801625EC
0x1801625e5  mov     ecx, 7
0x1801625ea  int     29h; Win8: RtlFailFast(ecx)
0x1801625ec  mov     [rbp+220h+EventHandle], 0
0x1801625f4  jmp     loc_180162963
0x1801625f9  mov     r12b, 1
0x1801625fc  mov     ecx, [rbp+220h+var_1B0]
0x1801625ff  jmp     short loc_180162608
0x180162601  mov     r12b, bl
0x180162604  mov     [rbp+220h+EventHandle], rbx
0x180162608  mov     [rbp+220h+var_1A0], rbx
0x18016260f  mov     [rbp+220h+var_1A8], ebx
0x180162612  mov     eax, ecx
0x180162614  and     eax, 1
0x180162617  lea     eax, ds:8[rax*2]
0x18016261e  mov     ebx, eax
0x180162620  or      ebx, 4
0x180162623  test    cl, 2
0x180162626  cmovz   ebx, eax
0x180162629  test    r13, r13
0x18016262c  jz      loc_1801626C2
0x180162632  mov     rax, [r13+0]
0x180162636  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180162640  cmp     rax, rcx
0x180162643  jbe     short loc_1801626BB
0x180162645  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x18016264c  mov     [rbp+220h+var_228], rax
0x180162650  lea     rax, aWindowsRtlSyst_82; "Windows::Rtl::SystemImplementation::CFi"...
0x180162657  mov     [rbp+220h+var_220], rax
0x18016265b  mov     [rbp+220h+var_218], 664h
0x180162663  lea     rax, aOffset0x7fffff; "*Offset <= (0x7fffffffffffffff)"
0x18016266a  mov     [rbp+220h+var_210], rax
0x18016266e  mov     [rbp+220h+var_1C0], 0C0000095h
0x180162675  mov     r8d, 0C0000095h
0x18016267b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180162682  lea     rcx, [rbp+220h+var_228]
0x180162686  call    RtlReportErrorOrigination
0x18016268b  mov     ebx, [rbp+220h+var_1C0]
0x18016268e  mov     rcx, [rbp+220h+EventHandle]; Handle
0x180162692  test    rcx, rcx
0x180162695  jz      short loc_1801626B6
0x180162697  call    cs:__imp_NtClose
0x18016269e  nop     dword ptr [rax+rax+00h]
0x1801626a3  test    eax, eax
0x1801626a5  jns     short loc_1801626AE
0x1801626a7  mov     ecx, 7
0x1801626ac  int     29h; Win8: RtlFailFast(ecx)
0x1801626ae  mov     [rbp+220h+EventHandle], 0
0x1801626b6  jmp     loc_180162963
0x1801626bb  mov     [rbp+220h+var_1A0], rax
0x1801626c2  mov     rcx, [rsi]
0x1801626c5  test    rcx, rcx
0x1801626c8  jz      short loc_1801626D6
0x1801626ca  call    cs:__imp_TpStartAsyncIoOperation
0x1801626d1  nop     dword ptr [rax+rax+00h]
0x1801626d6  mov     rcx, [r15+48h]
0x1801626da  mov     rax, [rcx]
0x1801626dd  neg     r13
0x1801626e0  sbb     r8, r8
0x1801626e3  lea     rdx, [rbp+220h+var_1A0]
0x1801626ea  and     r8, rdx
0x1801626ed  lea     rdx, [rbp+220h+var_1A8]
0x1801626f1  mov     [rsp+350h+var_2F8], rdx
0x1801626f6  mov     [rsp+350h+var_300], 0
0x1801626ff  mov     [rsp+350h+var_308], r8
0x180162704  mov     edx, [rbp+220h+arg_20]
0x18016270a  mov     dword ptr [rsp+350h+var_310], edx
0x18016270e  mov     r8, [r14+10h]
0x180162712  mov     [rsp+350h+var_318], r8
0x180162717  mov     r13, [rbp+220h+var_2A0]
0x18016271b  mov     [rsp+350h+var_320], r13
0x180162720  mov     rdx, [rbp+220h+var_298]
0x180162724  mov     [rsp+350h+var_328], rdx
0x180162729  mov     rdx, [rbp+220h+var_290]
0x18016272d  mov     qword ptr [rsp+350h+InitialState], rdx
0x180162732  mov     r9, [rbp+220h+EventHandle]
0x180162736  mov     r8, [r15+28h]
0x18016273a  mov     edx, ebx
0x18016273c  mov     rax, [rax+78h]
0x180162740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162745  mov     ebx, eax
0x180162747  test    eax, eax
0x180162749  jns     short loc_180162790
0x18016274b  mov     [rbp+220h+var_1C0], eax
0x18016274e  mov     rcx, [rsi]
0x180162751  test    rcx, rcx
0x180162754  jz      short loc_180162763
0x180162756  call    cs:__imp_TpCancelAsyncIoOperation
0x18016275d  nop     dword ptr [rax+rax+00h]
0x180162762  nop
0x180162763  mov     rcx, [rbp+220h+EventHandle]; Handle
0x180162767  test    rcx, rcx
0x18016276a  jz      short loc_18016278B
0x18016276c  call    cs:__imp_NtClose
0x180162773  nop     dword ptr [rax+rax+00h]
0x180162778  test    eax, eax
0x18016277a  jns     short loc_180162783
0x18016277c  mov     ecx, 7
0x180162781  int     29h; Win8: RtlFailFast(ecx)
0x180162783  mov     [rbp+220h+EventHandle], 0
0x18016278b  jmp     loc_180162963
0x180162790  mov     eax, [rbp+220h+var_1A8]
0x180162793  cmp     eax, 1
0x180162796  jnz     short loc_1801627C3
0x180162798  mov     cl, [r15+68h]
0x18016279c  mov     [rdi], eax
0x18016279e  mov     rax, [r13+8]
0x1801627a2  cmp     rax, [r14+8]
0x1801627a6  ja      loc_180162995
0x1801627ac  mov     [r14], rax
0x1801627af  mov     [rbp+220h+var_158], 1
0x1801627b6  test    cl, cl
0x1801627b8  jz      loc_1801628E8
0x1801627be  jmp     loc_1801628C5
0x1801627c3  cmp     eax, 2
0x1801627c6  jnz     short loc_1801627D9
0x1801627c8  test    byte ptr [rbp+220h+var_1B0], 1
0x1801627cc  jz      loc_180162995
0x1801627d2  mov     [rdi], eax
0x1801627d4  jmp     loc_1801628BE
0x1801627d9  cmp     eax, 3
0x1801627dc  jnz     short loc_180162804
0x1801627de  test    byte ptr [rbp+220h+var_1B0], 2
0x1801627e2  jz      loc_180162995
0x1801627e8  mov     rax, [r13+8]
0x1801627ec  cmp     rax, [r14+8]
0x1801627f0  ja      loc_180162995
0x1801627f6  mov     [r14], rax
0x1801627f9  mov     dword ptr [rdi], 3
0x1801627ff  jmp     loc_1801628BE
0x180162804  cmp     eax, 4
0x180162807  jnz     loc_180162995
0x18016280d  test    r12b, r12b
0x180162810  jz      loc_1801628DB
0x180162816  xor     r8d, r8d; Timeout
0x180162819  xor     edx, edx; Alertable
0x18016281b  mov     rcx, [rbp+220h+EventHandle]; Handle
0x18016281f  call    cs:__imp_NtWaitForSingleObject
0x180162826  nop     dword ptr [rax+rax+00h]
0x18016282b  mov     r8d, eax
0x18016282e  test    eax, eax
0x180162830  jns     loc_1801628B8
0x180162836  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x18016283d  mov     [rbp+220h+var_208], rax
0x180162841  lea     rax, aWindowsRtlSyst_82; "Windows::Rtl::SystemImplementation::CFi"...
0x180162848  mov     [rbp+220h+var_200], rax
0x18016284c  mov     [rbp+220h+var_1F8], 6A6h
0x180162854  lea     rax, aNtwaitforsingl; "::NtWaitForSingleObject(WaitEvent, 0 , "...
0x18016285b  mov     [rbp+220h+var_1F0], rax
0x18016285f  mov     [rbp+220h+var_1C0], r8d
0x180162863  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18016286a  lea     rcx, [rbp+220h+var_208]
0x18016286e  call    RtlReportErrorOrigination
0x180162873  mov     ebx, [rbp+220h+var_1C0]
0x180162876  mov     rcx, [rsi]
0x180162879  test    rcx, rcx
0x18016287c  jz      short loc_18016288B
0x18016287e  call    cs:__imp_TpCancelAsyncIoOperation
0x180162885  nop     dword ptr [rax+rax+00h]
0x18016288a  nop
0x18016288b  mov     rcx, [rbp+220h+EventHandle]; Handle
0x18016288f  test    rcx, rcx
0x180162892  jz      short loc_1801628B3
0x180162894  call    cs:__imp_NtClose
0x18016289b  nop     dword ptr [rax+rax+00h]
0x1801628a0  test    eax, eax
0x1801628a2  jns     short loc_1801628AB
0x1801628a4  mov     ecx, 7
0x1801628a9  int     29h; Win8: RtlFailFast(ecx)
0x1801628ab  mov     [rbp+220h+EventHandle], 0
0x1801628b3  jmp     loc_180162963
0x1801628b8  mov     dword ptr [rdi], 5
0x1801628be  mov     [rbp+220h+var_158], 1
  ... truncated ...
```
