# Windows::Rtl::SystemImplementation::CFile::WriteFileAsync(ulong,_LBLOB const &,unsigned __int64 *,void (*)(void *,_IO_STATUS_BLOCK *,ulong),void *,_IO_STATUS_BLOCK *,ulong *)

- ea: `0x180163cb0`
- end: `0x1801642fe`
- name: `?WriteFileAsync@CFile@SystemImplementation@Rtl@Windows@@UEAAJKAEBU_LBLOB@@PEA_KP6AXPEAXPEAU_IO_STATUS_BLOCK@@K@Z23PEAK@Z`
- size: `1614`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFile *__hidden this, unsigned int, const struct _LBLOB *, unsigned __int64 *, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, unsigned int *)`
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
- `0x180163cb0`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18016417d`
- `ntdll!NtWaitForSingleObject` at `0x18016417d`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801640dc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801641dc`
- `ntdll!TpCancelAsyncIoOperation` at `0x18016422b`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801640dc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801641dc`
- `ntdll!TpCancelAsyncIoOperation` at `0x18016422b`
- `ntdll!TpStartAsyncIoOperation` at `0x18016404d`
- `ntdll!TpStartAsyncIoOperation` at `0x18016404d`
- `ntdll!NtCreateEvent` at `0x180163e86`
- `ntdll!NtCreateEvent` at `0x180163e86`
- `ntdll!NtClose` at `0x180163edb`
- `ntdll!NtClose` at `0x180163f86`
- `ntdll!NtClose` at `0x18016400e`
- `ntdll!NtClose` at `0x1801640f2`
- `ntdll!NtClose` at `0x1801641f2`
- `ntdll!NtClose` at `0x18016424f`
- `ntdll!NtClose` at `0x180163edb`
- `ntdll!NtClose` at `0x180163f86`
- `ntdll!NtClose` at `0x18016400e`
- `ntdll!NtClose` at `0x1801640f2`
- `ntdll!NtClose` at `0x1801641f2`
- `ntdll!NtClose` at `0x18016424f`

## string_xrefs

- `0x180163eb0`: `::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )`
- `0x180163d43`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x180163f3f`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x180163fc7`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x18016419f`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CFile::WriteFileAsync(
        Windows::Rtl::SystemImplementation::CFile *this,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        const struct _LBLOB *a3,
        unsigned __int64 *a4,
        void (*a5)(void *, struct _IO_STATUS_BLOCK *, unsigned int),
        void *a6,
        struct _IO_STATUS_BLOCK *a7,
        unsigned int *a8)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // cl
  _QWORD *v14; // rcx
  _QWORD *v15; // rsi
  NTSTATUS v16; // eax
  unsigned int v17; // ebx
  char v18; // r15
  unsigned int v19; // ebx
  int v20; // eax
  char v21; // al
  NTSTATUS v22; // eax
  _QWORD v24[4]; // [rsp+C8h] [rbp-68h] BYREF
  _QWORD v25[4]; // [rsp+E8h] [rbp-48h] BYREF
  _QWORD v26[4]; // [rsp+108h] [rbp-28h] BYREF
  _QWORD v27[4]; // [rsp+128h] [rbp-8h] BYREF
  _QWORD v28[4]; // [rsp+148h] [rbp+18h] BYREF
  _QWORD v29[5]; // [rsp+168h] [rbp+38h] BYREF
  unsigned int v30; // [rsp+190h] [rbp+60h] BYREF
  void *EventHandle; // [rsp+198h] [rbp+68h] BYREF
  int v32; // [rsp+1A0h] [rbp+70h] BYREF
  int v33; // [rsp+1A8h] [rbp+78h] BYREF
  unsigned __int64 v34; // [rsp+1B0h] [rbp+80h] BYREF
  _BYTE v35[8]; // [rsp+1C0h] [rbp+90h] BYREF
  int v36; // [rsp+1C8h] [rbp+98h]
  int v37; // [rsp+1E8h] [rbp+B8h]
  char v38; // [rsp+1F8h] [rbp+C8h]

  v29[4] = -2;
  v32 = (int)a2;
  v30 = 0;
  v37 = 0;
  v38 = 0;
  v36 = 1;
  if ( (Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, a2) & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::Arm(
      v35,
      &v30,
      Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      this,
      "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync",
      &Windows::WCP::Rtl::Facility_SIL,
      0,
      "(Flags = {flg}, Buffer = {buf}, Offset = {off}, Disposition = {disp})",
      0,
      4,
      "flg",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      &v32,
      "buf",
      Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength,
      a3,
      "off",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG,
      a4,
      "disp",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      a8);
  if ( !a8 )
  {
    v29[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v29[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
    v29[2] = 1758;
    v29[3] = "Disposition";
    v14 = v29;
    goto LABEL_71;
  }
  *a8 = 0;
  v13 = v32;
  if ( (v32 & 0xFFFFFFF8) != 0 )
  {
    v24[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v24[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
    v24[2] = 1764;
    v24[3] = "Valid flags check failed: Flags";
    v14 = v24;
LABEL_71:
    v30 = -1073741811;
    RtlReportErrorOrigination(v14, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v17 = v30;
LABEL_72:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>(v35);
    return v17;
  }
  v15 = (_QWORD *)((char *)this + 96);
  if ( (v32 & 4) == 0 || *v15 )
  {
    v18 = 0;
    EventHandle = 0;
  }
  else
  {
    EventHandle = 0;
    v16 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    v12 = (unsigned int)v16;
    if ( v16 < 0 )
    {
      v25[0] = "onecore\\base\\wcp\\sil\\file.cpp";
      v25[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
      v25[2] = 1776;
      v25[3] = "::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )";
      v30 = v16;
      RtlReportErrorOrigination(v25, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v16);
      v17 = v30;
      if ( EventHandle )
      {
        if ( NtClose(EventHandle) < 0 )
          __fastfail(7u);
        EventHandle = 0;
      }
      goto LABEL_72;
    }
    v18 = 1;
    v13 = v32;
  }
  v33 = 0;
  v34 = 0;
  if ( a4 )
  {
    v11 = 0x7FFFFFFFFFFFFFFFLL;
    if ( *a4 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v26[0] = "onecore\\base\\wcp\\sil\\file.cpp";
      v26[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
      v26[2] = 1785;
      v26[3] = "*Offset <= (0x7fffffffffffffff)";
      v30 = -1073741675;
      RtlReportErrorOrigination(v26, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
      v17 = v30;
      if ( EventHandle )
      {
        if ( NtClose(EventHandle) < 0 )
          __fastfail(7u);
        EventHandle = 0;
      }
      goto LABEL_72;
    }
    v34 = *a4;
  }
  if ( *(_QWORD *)a3 > 0xFFFFFFFF )
  {
    v27[0] = "onecore\\base\\wcp\\sil\\file.cpp";
    v27[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
    v27[2] = 1789;
    v27[3] = "Buffer.Length <= 0xffffffff";
    v30 = -1073741675;
    RtlReportErrorOrigination(v27, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
    v17 = v30;
    if ( EventHandle )
    {
      if ( NtClose(EventHandle) < 0 )
        __fastfail(7u);
      EventHandle = 0;
    }
    goto LABEL_72;
  }
  v19 = ((v13 & 1) + 4) | 2;
  if ( (v13 & 2) == 0 )
    v19 = (v13 & 1) + 4;
  if ( *v15 )
    TpStartAsyncIoOperation(*v15, v11, v12);
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, _QWORD, _DWORD, unsigned __int64, _QWORD, int *))(**((_QWORD **)this + 9) + 128LL))(
          *((_QWORD *)this + 9),
          v19,
          *((_QWORD *)this + 5),
          EventHandle,
          a5,
          a6,
          a7,
          *((_QWORD *)a3 + 2),
          *(_DWORD *)a3,
          (unsigned __int64)&v34 & -(__int64)(a4 != 0),
          0,
          &v33);
  v17 = v20;
  if ( v20 < 0 )
  {
    v30 = v20;
    if ( *v15 )
      TpCancelAsyncIoOperation();
    if ( EventHandle )
    {
      if ( NtClose(EventHandle) < 0 )
        __fastfail(7u);
      EventHandle = 0;
    }
    goto LABEL_72;
  }
  switch ( v33 )
  {
    case 2:
      *a8 = 2;
LABEL_61:
      v38 = 1;
      goto LABEL_62;
    case 3:
      *a8 = 3;
      goto LABEL_61;
    case 1:
      if ( a7->Information == *(_QWORD *)a3 )
      {
        v21 = *((_BYTE *)this + 104);
        *a8 = 1;
        v38 = 1;
        if ( v21 )
        {
LABEL_62:
          if ( *v15 )
            TpCancelAsyncIoOperation();
          goto LABEL_65;
        }
        goto LABEL_65;
      }
LABEL_73:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801642FDLL);
  }
  if ( v33 != 4 )
    goto LABEL_73;
  if ( v18 )
  {
    v22 = NtWaitForSingleObject(EventHandle, 0, 0);
    if ( v22 < 0 )
    {
      v28[0] = "onecore\\base\\wcp\\sil\\file.cpp";
      v28[1] = "Windows::Rtl::SystemImplementation::CFile::WriteFileAsync";
      v28[2] = 1853;
      v28[3] = "::NtWaitForSingleObject(WaitEvent, 0 , nullptr)";
      v30 = v22;
      RtlReportErrorOrigination(v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v22);
      v17 = v30;
      if ( *v15 )
        TpCancelAsyncIoOperation();
      if ( EventHandle )
      {
        if ( NtClose(EventHandle) < 0 )
          __fastfail(7u);
        EventHandle = 0;
      }
      goto LABEL_72;
    }
    *a8 = 5;
    goto LABEL_61;
  }
  *a8 = 4;
  v38 = 1;
LABEL_65:
  if ( EventHandle )
  {
    if ( NtClose(EventHandle) < 0 )
      __fastfail(7u);
    EventHandle = 0;
  }
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>(v35);
  return v30;
}

```

## disassembly

```asm
0x180163cb0  push    rbp
0x180163cb2  push    rbx
0x180163cb3  push    rsi
0x180163cb4  push    rdi
0x180163cb5  push    r12
0x180163cb7  push    r13
0x180163cb9  push    r14
0x180163cbb  push    r15
0x180163cbd  lea     rbp, [rsp-1E8h]
0x180163cc5  sub     rsp, 318h
0x180163ccc  mov     [rbp+220h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x180163cd4  mov     rax, cs:__security_cookie
0x180163cdb  xor     rax, rsp
0x180163cde  mov     [rbp+220h+var_50], rax
0x180163ce5  mov     r13, r9
0x180163ce8  mov     r12, r8
0x180163ceb  mov     r14, rcx
0x180163cee  mov     [rbp+220h+var_1B0], edx
0x180163cf1  mov     rax, [rbp+220h+arg_20]
0x180163cf8  mov     [rbp+220h+var_290], rax
0x180163cfc  mov     rax, [rbp+220h+arg_28]
0x180163d03  mov     [rbp+220h+var_298], rax
0x180163d07  mov     rax, [rbp+220h+arg_30]
0x180163d0e  mov     [rbp+220h+var_2A0], rax
0x180163d12  mov     rdi, [rbp+220h+arg_38]
0x180163d19  xor     ebx, ebx
0x180163d1b  mov     [rbp+220h+var_1C0], ebx
0x180163d1e  mov     [rbp+220h+var_168], ebx
0x180163d24  mov     [rbp+220h+var_158], bl
0x180163d2a  mov     [rbp+220h+var_188], 1
0x180163d34  lea     rsi, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x180163d3b  mov     rcx, rsi; this
0x180163d3e  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180163d43  lea     r15, aWindowsRtlSyst_301; "Windows::Rtl::SystemImplementation::CFi"...
0x180163d4a  test    al, 0Eh
0x180163d4c  jz      loc_180163E18
0x180163d52  mov     [rsp+350h+var_2A8], rdi
0x180163d5a  lea     rcx, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180163d61  mov     [rsp+350h+var_2B0], rcx
0x180163d69  lea     rax, aDisp; "disp"
0x180163d70  mov     [rsp+350h+var_2B8], rax
0x180163d78  mov     [rsp+350h+var_2C0], r13
0x180163d80  lea     rax, ?RtlTraceFormat_PCULONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180163d87  mov     [rsp+350h+var_2C8], rax
0x180163d8f  lea     rax, aOff; "off"
0x180163d96  mov     [rsp+350h+var_2D0], rax
0x180163d9e  mov     [rsp+350h+var_2D8], r12
0x180163da3  lea     rax, ?RtlTraceFormat_PCLBLOB_LimitLength@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCLBLOB_LimitLength(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180163daa  mov     [rsp+350h+var_2E0], rax
0x180163daf  lea     rax, aBuf; "buf"
0x180163db6  mov     [rsp+350h+var_2E8], rax
0x180163dbb  lea     rax, [rbp+220h+var_1B0]
0x180163dbf  mov     [rsp+350h+var_2F0], rax
0x180163dc4  mov     [rsp+350h+var_2F8], rcx
0x180163dc9  lea     rax, aFlg; "flg"
0x180163dd0  mov     [rsp+350h+var_300], rax
0x180163dd5  mov     [rsp+350h+var_308], 4
0x180163dde  mov     [rsp+350h+var_310], rbx
0x180163de3  lea     rax, aFlagsFlgBuffer; "(Flags = {flg}, Buffer = {buf}, Offset "...
0x180163dea  mov     [rsp+350h+var_318], rax
0x180163def  mov     [rsp+350h+var_320], rbx
0x180163df4  mov     [rsp+350h+var_328], rsi
0x180163df9  mov     qword ptr [rsp+350h+InitialState], r15
0x180163dfe  mov     r9, r14
0x180163e01  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180163e08  lea     rdx, [rbp+220h+var_1C0]
0x180163e0c  lea     rcx, [rbp+220h+var_190]
0x180163e13  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$03@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,4>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x180163e18  test    rdi, rdi
0x180163e1b  jz      loc_18016427F
0x180163e21  mov     [rdi], ebx
0x180163e23  mov     ecx, [rbp+220h+var_1B0]
0x180163e26  test    ecx, 0FFFFFFF8h
0x180163e2c  jz      short loc_180163E59
0x180163e2e  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180163e35  mov     [rbp+220h+var_288], rax
0x180163e39  mov     [rbp+220h+var_280], r15
0x180163e3d  mov     [rbp+220h+var_278], 6E4h
0x180163e45  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x180163e4c  mov     [rbp+220h+var_270], rax
0x180163e50  lea     rcx, [rbp+220h+var_288]
0x180163e54  jmp     loc_1801642A5
0x180163e59  lea     rsi, [r14+60h]
0x180163e5d  test    cl, 4
0x180163e60  jz      loc_180163F07
0x180163e66  cmp     [rsi], rbx
0x180163e69  jnz     loc_180163F07
0x180163e6f  mov     [rbp+220h+EventHandle], rbx
0x180163e73  mov     [rsp+350h+InitialState], bl; InitialState
0x180163e77  xor     r9d, r9d; EventType
0x180163e7a  xor     r8d, r8d; ObjectAttributes
0x180163e7d  mov     edx, 1F0003h; DesiredAccess
0x180163e82  lea     rcx, [rbp+220h+EventHandle]; EventHandle
0x180163e86  call    cs:__imp_NtCreateEvent
0x180163e8d  nop     dword ptr [rax+rax+00h]
0x180163e92  mov     r8d, eax
0x180163e95  test    eax, eax
0x180163e97  jns     short loc_180163EFF
0x180163e99  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180163ea0  mov     [rbp+220h+var_268], rax
0x180163ea4  mov     [rbp+220h+var_260], r15
0x180163ea8  mov     [rbp+220h+var_258], 6F0h
0x180163eb0  lea     rax, aNtcreateeventW; "::NtCreateEvent( WaitEvent.GetInitPoint"...
0x180163eb7  mov     [rbp+220h+var_250], rax
0x180163ebb  mov     [rbp+220h+var_1C0], r8d
0x180163ebf  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180163ec6  lea     rcx, [rbp+220h+var_268]
0x180163eca  call    RtlReportErrorOrigination
0x180163ecf  mov     ebx, [rbp+220h+var_1C0]
0x180163ed2  mov     rcx, [rbp+220h+EventHandle]; Handle
0x180163ed6  test    rcx, rcx
0x180163ed9  jz      short loc_180163EFA
0x180163edb  call    cs:__imp_NtClose
0x180163ee2  nop     dword ptr [rax+rax+00h]
0x180163ee7  test    eax, eax
0x180163ee9  jns     short loc_180163EF2
0x180163eeb  mov     ecx, 7
0x180163ef0  int     29h; Win8: RtlFailFast(ecx)
0x180163ef2  mov     [rbp+220h+EventHandle], 0
0x180163efa  jmp     loc_1801642C1
0x180163eff  mov     r15b, 1
0x180163f02  mov     ecx, [rbp+220h+var_1B0]
0x180163f05  jmp     short loc_180163F0E
0x180163f07  mov     r15b, bl
0x180163f0a  mov     [rbp+220h+EventHandle], rbx
0x180163f0e  mov     [rbp+220h+var_1A8], ebx
0x180163f11  mov     [rbp+220h+var_1A0], rbx
0x180163f18  test    r13, r13
0x180163f1b  jz      loc_180163FB1
0x180163f21  mov     rax, [r13+0]
0x180163f25  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180163f2f  cmp     rax, rdx
0x180163f32  jbe     short loc_180163FAA
0x180163f34  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180163f3b  mov     [rbp+220h+var_248], rax
0x180163f3f  lea     rax, aWindowsRtlSyst_301; "Windows::Rtl::SystemImplementation::CFi"...
0x180163f46  mov     [rbp+220h+var_240], rax
0x180163f4a  mov     [rbp+220h+var_238], 6F9h
0x180163f52  lea     rax, aOffset0x7fffff; "*Offset <= (0x7fffffffffffffff)"
0x180163f59  mov     [rbp+220h+var_230], rax
0x180163f5d  mov     [rbp+220h+var_1C0], 0C0000095h
0x180163f64  mov     r8d, 0C0000095h
0x180163f6a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180163f71  lea     rcx, [rbp+220h+var_248]
0x180163f75  call    RtlReportErrorOrigination
0x180163f7a  mov     ebx, [rbp+220h+var_1C0]
0x180163f7d  mov     rcx, [rbp+220h+EventHandle]; Handle
0x180163f81  test    rcx, rcx
0x180163f84  jz      short loc_180163FA5
0x180163f86  call    cs:__imp_NtClose
0x180163f8d  nop     dword ptr [rax+rax+00h]
0x180163f92  test    eax, eax
0x180163f94  jns     short loc_180163F9D
0x180163f96  mov     ecx, 7
0x180163f9b  int     29h; Win8: RtlFailFast(ecx)
0x180163f9d  mov     [rbp+220h+EventHandle], 0
0x180163fa5  jmp     loc_1801642C1
0x180163faa  mov     [rbp+220h+var_1A0], rax
0x180163fb1  mov     eax, 0FFFFFFFFh
0x180163fb6  cmp     [r12], rax
0x180163fba  jbe     short loc_180164032
0x180163fbc  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x180163fc3  mov     [rbp+220h+var_228], rax
0x180163fc7  lea     rax, aWindowsRtlSyst_301; "Windows::Rtl::SystemImplementation::CFi"...
0x180163fce  mov     [rbp+220h+var_220], rax
0x180163fd2  mov     [rbp+220h+var_218], 6FDh
0x180163fda  lea     rax, aBufferLength0x; "Buffer.Length <= 0xffffffff"
0x180163fe1  mov     [rbp+220h+var_210], rax
0x180163fe5  mov     [rbp+220h+var_1C0], 0C0000095h
0x180163fec  mov     r8d, 0C0000095h
0x180163ff2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180163ff9  lea     rcx, [rbp+220h+var_228]
0x180163ffd  call    RtlReportErrorOrigination
0x180164002  mov     ebx, [rbp+220h+var_1C0]
0x180164005  mov     rcx, [rbp+220h+EventHandle]; Handle
0x180164009  test    rcx, rcx
0x18016400c  jz      short loc_18016402D
0x18016400e  call    cs:__imp_NtClose
0x180164015  nop     dword ptr [rax+rax+00h]
0x18016401a  test    eax, eax
0x18016401c  jns     short loc_180164025
0x18016401e  mov     ecx, 7
0x180164023  int     29h; Win8: RtlFailFast(ecx)
0x180164025  mov     [rbp+220h+EventHandle], 0
0x18016402d  jmp     loc_1801642C1
0x180164032  mov     eax, ecx
0x180164034  and     eax, 1
0x180164037  add     eax, 4
0x18016403a  mov     ebx, eax
0x18016403c  or      ebx, 2
0x18016403f  test    cl, 2
0x180164042  cmovz   ebx, eax
0x180164045  mov     rcx, [rsi]
0x180164048  test    rcx, rcx
0x18016404b  jz      short loc_180164059
0x18016404d  call    cs:__imp_TpStartAsyncIoOperation
0x180164054  nop     dword ptr [rax+rax+00h]
0x180164059  mov     rcx, [r14+48h]
0x18016405d  mov     rax, [rcx]
0x180164060  neg     r13
0x180164063  sbb     r8, r8
0x180164066  lea     rdx, [rbp+220h+var_1A0]
0x18016406d  and     r8, rdx
0x180164070  lea     rdx, [rbp+220h+var_1A8]
0x180164074  mov     [rsp+350h+var_2F8], rdx
0x180164079  mov     [rsp+350h+var_300], 0
0x180164082  mov     [rsp+350h+var_308], r8
0x180164087  mov     r8d, [r12]
0x18016408b  mov     dword ptr [rsp+350h+var_310], r8d
0x180164090  mov     r8, [r12+10h]
0x180164095  mov     [rsp+350h+var_318], r8
0x18016409a  mov     r13, [rbp+220h+var_2A0]
0x18016409e  mov     [rsp+350h+var_320], r13
0x1801640a3  mov     rdx, [rbp+220h+var_298]
0x1801640a7  mov     [rsp+350h+var_328], rdx
0x1801640ac  mov     rdx, [rbp+220h+var_290]
0x1801640b0  mov     qword ptr [rsp+350h+InitialState], rdx
0x1801640b5  mov     r9, [rbp+220h+EventHandle]
0x1801640b9  mov     r8, [r14+28h]
0x1801640bd  mov     edx, ebx
0x1801640bf  mov     rax, [rax+80h]
0x1801640c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801640cb  mov     ebx, eax
0x1801640cd  test    eax, eax
0x1801640cf  jns     short loc_180164116
0x1801640d1  mov     [rbp+220h+var_1C0], eax
0x1801640d4  mov     rcx, [rsi]
0x1801640d7  test    rcx, rcx
0x1801640da  jz      short loc_1801640E9
0x1801640dc  call    cs:__imp_TpCancelAsyncIoOperation
0x1801640e3  nop     dword ptr [rax+rax+00h]
0x1801640e8  nop
0x1801640e9  mov     rcx, [rbp+220h+EventHandle]; Handle
0x1801640ed  test    rcx, rcx
0x1801640f0  jz      short loc_180164111
0x1801640f2  call    cs:__imp_NtClose
0x1801640f9  nop     dword ptr [rax+rax+00h]
0x1801640fe  test    eax, eax
0x180164100  jns     short loc_180164109
0x180164102  mov     ecx, 7
0x180164107  int     29h; Win8: RtlFailFast(ecx)
0x180164109  mov     [rbp+220h+EventHandle], 0
0x180164111  jmp     loc_1801642C1
0x180164116  mov     eax, [rbp+220h+var_1A8]
0x180164119  cmp     eax, 2
0x18016411c  jnz     short loc_180164125
0x18016411e  mov     [rdi], eax
0x180164120  jmp     loc_18016421C
0x180164125  cmp     eax, 3
0x180164128  jnz     short loc_180164131
0x18016412a  mov     [rdi], eax
0x18016412c  jmp     loc_18016421C
0x180164131  cmp     eax, 1
0x180164134  jnz     short loc_180164162
0x180164136  mov     rax, [r12]
0x18016413a  cmp     [r13+8], rax
0x18016413e  jnz     loc_1801642F3
0x180164144  mov     al, [r14+68h]
0x180164148  mov     dword ptr [rdi], 1
0x18016414e  mov     [rbp+220h+var_158], 1
0x180164155  test    al, al
0x180164157  jz      loc_180164246
0x18016415d  jmp     loc_180164223
0x180164162  cmp     eax, 4
0x180164165  jnz     loc_1801642F3
0x18016416b  test    r15b, r15b
0x18016416e  jz      loc_180164239
0x180164174  xor     r8d, r8d; Timeout
0x180164177  xor     edx, edx; Alertable
0x180164179  mov     rcx, [rbp+220h+EventHandle]; Handle
0x18016417d  call    cs:__imp_NtWaitForSingleObject
0x180164184  nop     dword ptr [rax+rax+00h]
0x180164189  mov     r8d, eax
0x18016418c  test    eax, eax
0x18016418e  jns     loc_180164216
0x180164194  lea     rax, aOnecoreBaseWcp_49; "onecore\\base\\wcp\\sil\\file.cpp"
0x18016419b  mov     [rbp+220h+var_208], rax
0x18016419f  lea     rax, aWindowsRtlSyst_301; "Windows::Rtl::SystemImplementation::CFi"...
0x1801641a6  mov     [rbp+220h+var_200], rax
0x1801641aa  mov     [rbp+220h+var_1F8], 73Dh
0x1801641b2  lea     rax, aNtwaitforsingl; "::NtWaitForSingleObject(WaitEvent, 0 , "...
0x1801641b9  mov     [rbp+220h+var_1F0], rax
0x1801641bd  mov     [rbp+220h+var_1C0], r8d
0x1801641c1  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801641c8  lea     rcx, [rbp+220h+var_208]
0x1801641cc  call    RtlReportErrorOrigination
0x1801641d1  mov     ebx, [rbp+220h+var_1C0]
0x1801641d4  mov     rcx, [rsi]
0x1801641d7  test    rcx, rcx
0x1801641da  jz      short loc_1801641E9
0x1801641dc  call    cs:__imp_TpCancelAsyncIoOperation
0x1801641e3  nop     dword ptr [rax+rax+00h]
0x1801641e8  nop
0x1801641e9  mov     rcx, [rbp+220h+EventHandle]; Handle
0x1801641ed  test    rcx, rcx
0x1801641f0  jz      short loc_180164211
0x1801641f2  call    cs:__imp_NtClose
0x1801641f9  nop     dword ptr [rax+rax+00h]
0x1801641fe  test    eax, eax
0x180164200  jns     short loc_180164209
  ... truncated ...
```
