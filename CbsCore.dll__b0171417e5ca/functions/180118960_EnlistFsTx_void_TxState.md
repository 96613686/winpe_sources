# EnlistFsTx(void *,TxState &)

- ea: `0x180118960`
- end: `0x180118de4`
- name: `?EnlistFsTx@@YAJPEAXAEAW4TxState@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(void *, enum TxState *)`
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1801188a8`
- `0x1801f2d6c`

## callees

- `0x180010cc0`
- `0x180019bdc`
- `0x180056864`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800bca84`
- `0x1800eb920`
- `0x180117788`
- `0x18011792c`
- `0x180117c0c`
- `0x180118960`
- `0x18011944c`
- `0x180119688`
- `0x1801197fc`
- `0x18011a5dc`
- `0x1801f6a64`
- `0x1801f6bd4`
- `0x1801f6dec`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180118aca`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180118aca`
- `ntdll!LdrLoadDll` at `0x180118a07`
- `ntdll!LdrLoadDll` at `0x180118a07`
- `ntdll!LdrGetProcedureAddress` at `0x180118a65`
- `ntdll!LdrGetProcedureAddress` at `0x180118a65`

## string_xrefs

- `0x180118a3c`: `::LdrLoadDll(nullptr, nullptr, &L"ntdll.dll"_US, Ntdll.GetInitPointer())`
- `0x180118b6e`: `pfnLdrGetDllFullName(hModule, FilePath.GetMutablePointer())`
- `0x180118a9a`: `::LdrGetProcedureAddress(Ntdll.Get(), &"LdrGetDllFullName"_ANSI, 0, reinterpret_cast<PVOID*>(&pfnLdrGetDllFullName))`
- `0x180118d4c`: `Default FsTx Session already set`
- `0x180118cf5`: `::FsTxCreateSession2( Windows::StringUtil::c_str(SystemVolumeRootPath), Windows::StringUtil::c_str(SessionMetadataDirRelPath), Flags, nullptr, nullptr, &sessionContext)`

## pseudocode

```c
__int64 __fastcall EnlistFsTx(void *a1, enum TxState *a2)
{
  bool v2; // zf
  PVOID *InitPointer; // rax
  NTSTATUS Dll; // eax
  __int64 v8; // r8
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **v9; // rdx
  NTSTATUS v10; // eax
  int v11; // eax
  int FsTx; // ebx
  int v13; // eax
  __int64 v14; // rdx
  const wchar_t *v15; // rax
  unsigned int v16; // edx
  int v17; // edi
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // r9d
  int Session2; // eax
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // r8
  int v27; // [rsp+20h] [rbp-E0h]
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v28; // [rsp+30h] [rbp-D0h] BYREF
  const char *v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  const char *v31; // [rsp+48h] [rbp-B8h]
  _QWORD v32[4]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID ProcedureAddress; // [rsp+70h] [rbp-90h] BYREF
  PVOID BaseOfImage; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  const char *v38; // [rsp+A0h] [rbp-60h]
  PVOID BaseAddress; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v40; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h]
  const char *v42; // [rsp+C8h] [rbp-38h]
  _BYTE v43[1024]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[2]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v2 = *(_DWORD *)a2 == 0;
  v35 = 0;
  if ( !v2 )
  {
    v37 = 394;
    *(_QWORD *)&v36 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    *((_QWORD *)&v36 + 1) = "EnlistFsTx";
    v38 = "State == TxState::None";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v35,
             &v36);
  }
  if ( !(unsigned __int8)IsFsTxLoaded() )
  {
    BaseAddress = 0;
    InitPointer = (PVOID *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&BaseAddress);
    Dll = LdrLoadDll(
            0,
            0,
            (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__09U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0GO__0HE__0GE__0GM__0GM__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_Details_RtlStringLiterals__3U_UNICODE_STRING__B,
            InitPointer);
    v8 = (unsigned int)Dll;
    if ( Dll < 0 )
    {
      v37 = 400;
      *(_QWORD *)&v36 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v9 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **)&v36;
      *((_QWORD *)&v36 + 1) = "EnlistFsTx";
      v38 = "::LdrLoadDll(nullptr, nullptr, &L\"ntdll.dll\"_US, Ntdll.GetInitPointer())";
LABEL_8:
      v11 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v35,
              v9,
              v8);
LABEL_9:
      FsTx = v11;
LABEL_18:
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&BaseAddress);
      return (unsigned int)FsTx;
    }
    ProcedureAddress = 0;
    v10 = LdrGetProcedureAddress(
            BaseAddress,
            (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0BC_U_STRING__D_Details_RtlStringLiterals__3D0EM__0GE__0HC__0EH__0GF__0HE__0EE__0GM__0GM__0EG__0HF__0GM__0GM__0EO__0GB__0GN__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__Details_RtlStringLiterals__3U_STRING__B,
            0,
            &ProcedureAddress);
    v8 = (unsigned int)v10;
    if ( v10 < 0 )
    {
      v41 = 404;
      *(_QWORD *)&v40 = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v9 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **)&v40;
      *((_QWORD *)&v40 + 1) = "EnlistFsTx";
      v42 = "::LdrGetProcedureAddress(Ntdll.Get(), &\"LdrGetDllFullName\"_ANSI, 0, reinterpret_cast<PVOID*>(&pfnLdrGetDllFullName))";
      goto LABEL_8;
    }
    BaseOfImage = 0;
    if ( !RtlPcToFileHeader(EnlistFsTx, &BaseOfImage) )
    {
      v32[2] = 407;
      v32[0] = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v9 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **)v32;
      v8 = 3221225781LL;
      v32[1] = "EnlistFsTx";
      v32[3] = "::RtlPcToFileHeader(EnlistFsTx, reinterpret_cast<PVOID*>(&hModule))";
      goto LABEL_8;
    }
    v44[1] = v43;
    v44[0] = 0x4000000;
    v13 = ((__int64 (__fastcall *)(PVOID, _QWORD *))ProcedureAddress)(BaseOfImage, v44);
    v8 = (unsigned int)v13;
    if ( v13 < 0 )
    {
      v30 = 410;
      v28 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)"onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v9 = &v28;
      v29 = "EnlistFsTx";
      v31 = "pfnLdrGetDllFullName(hModule, FilePath.GetMutablePointer())";
      goto LABEL_8;
    }
    v40 = 0;
    v11 = Windows::StringUtil::Rtl::SplitNtPath<RtlString::FixedString<_UNICODE_STRING,512>>(
            v43,
            &v40,
            (unsigned int)v13);
    if ( v11 < 0 )
      goto LABEL_9;
    v36 = 0;
    v37 = 0;
    FsTx = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<_UNICODE_STRING,wchar_t [9]>(
             (__int64)&v40,
             v14,
             (__int64)&v36);
    if ( FsTx < 0
      || (v15 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v36),
          FsTx = LoadFsTx(v15),
          FsTx < 0) )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v36);
      goto LABEL_18;
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v36);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&BaseAddress);
  }
  if ( (unsigned int)FsTxIsDefaultSessionContextSet() )
  {
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      v16,
      (unsigned int)&Windows::WCP::Rtl::Facility_General,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Default FsTx Session already set",
      0,
      0,
      v28);
  }
  else
  {
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      v16,
      (unsigned int)&Windows::WCP::Rtl::Facility_General,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Creating FsTx Session",
      0,
      0,
      v28);
    v40 = 0;
    v41 = 0;
    v17 = 1;
    v37 = 0;
    v36 = 0;
    if ( g_TestMode )
    {
      ProcedureAddress = &v40;
      FsTx = RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
               ___LiteralObject__2U__BaseLiteralBuffer__0BK_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FE__0EF__0FD__0FE__0FP__0EG__0FD__0FE__0FI__0FP__0FG__0EP__0EM__0FF__0EN__0EF__0FP__0EP__0FG__0EF__0FC__0FC__0EJ__0EE__0EF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
               &ProcedureAddress);
      if ( FsTx < 0 )
      {
LABEL_31:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v36);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v40);
        return (unsigned int)FsTx;
      }
      ProcedureAddress = &v36;
      v18 = RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
              ___LiteralObject__2U__BaseLiteralBuffer__0BI_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FE__0EF__0FD__0FE__0FP__0EG__0FD__0FE__0FI__0FP__0FA__0EB__0FE__0EI__0FP__0EP__0FG__0EF__0FC__0FC__0EJ__0EE__0EF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
              &ProcedureAddress);
      if ( v18 < 0 )
      {
LABEL_30:
        FsTx = v18;
        goto LABEL_31;
      }
      v17 = 9;
    }
    BaseOfImage = 0;
    v19 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v36);
    v20 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v40);
    Session2 = FsTxCreateSession2(v20, v19, v17, v21, v27, (__int64)&BaseOfImage);
    v23 = (unsigned int)Session2;
    if ( Session2 )
    {
      v30 = 446;
      v28 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)"onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v29 = "EnlistFsTx";
      v31 = "::FsTxCreateSession2( Windows::StringUtil::c_str(SystemVolumeRootPath), Windows::StringUtil::c_str(SessionMe"
            "tadataDirRelPath), Flags, nullptr, nullptr, &sessionContext)";
      if ( Session2 > 0 )
        v23 = (unsigned __int16)Session2 | 0x80070000;
      v18 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
              &v35,
              &v28,
              v23);
      goto LABEL_30;
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v36);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v40);
  }
  v25 = FsTxEnlistTransaction(v24, a1);
  v26 = (unsigned int)v25;
  if ( v25 )
  {
    v30 = 460;
    v28 = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)"onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
    v29 = "EnlistFsTx";
    v31 = "::FsTxEnlistTransaction( nullptr, Tx, 0x00000001)";
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
             &v35,
             &v28,
             v26);
  }
  else
  {
    *(_DWORD *)a2 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180118960  mov     [rsp-8+arg_10], rbx
0x180118965  mov     [rsp-8+arg_18], rsi
0x18011896a  push    rbp
0x18011896b  push    rdi
0x18011896c  push    r14
0x18011896e  lea     rbp, [rsp-3F0h]
0x180118976  sub     rsp, 4F0h
0x18011897d  mov     rax, cs:__security_cookie
0x180118984  xor     rax, rsp
0x180118987  mov     [rbp+400h+var_20], rax
0x18011898e  cmp     dword ptr [rdx], 0
0x180118991  mov     rsi, rdx
0x180118994  mov     r14, rcx
0x180118997  mov     [rbp+400h+var_480], 0
0x18011899e  jz      short loc_1801189DB
0x1801189a0  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x1801189a7  mov     [rbp+400h+var_468], 18Ah
0x1801189af  mov     qword ptr [rbp+400h+var_478], rax
0x1801189b3  lea     rdx, [rbp+400h+var_478]
0x1801189b7  lea     rax, aEnlistfstx; "EnlistFsTx"
0x1801189be  mov     qword ptr [rbp+400h+var_478+8], rax
0x1801189c2  lea     rcx, [rbp+400h+var_480]
0x1801189c6  lea     rax, aStateTxstateNo; "State == TxState::None"
0x1801189cd  mov     [rbp+400h+var_460], rax
0x1801189d1  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1801189d6  jmp     loc_180118DBC
0x1801189db  call    IsFsTxLoaded
0x1801189e0  test    al, al
0x1801189e2  jnz     loc_180118BF9
0x1801189e8  lea     rcx, [rbp+400h+BaseAddress]
0x1801189ec  mov     [rbp+400h+BaseAddress], 0
0x1801189f4  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801189f9  mov     r9, rax; BaseAddress
0x1801189fc  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0GO@@0HE@@0GE@@0GM@@0GM@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x180118a03  xor     edx, edx; LoadFlags
0x180118a05  xor     ecx, ecx; SearchPath
0x180118a07  call    cs:__imp_LdrLoadDll
0x180118a0e  nop     dword ptr [rax+rax+00h]
0x180118a13  mov     r8d, eax
0x180118a16  test    eax, eax
0x180118a18  jns     short loc_180118A49
0x180118a1a  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118a21  mov     [rbp+400h+var_468], 190h
0x180118a29  mov     qword ptr [rbp+400h+var_478], rax
0x180118a2d  lea     rdx, [rbp+400h+var_478]
0x180118a31  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118a38  mov     qword ptr [rbp+400h+var_478+8], rax
0x180118a3c  lea     rax, aLdrloaddllNull_0; "::LdrLoadDll(nullptr, nullptr, &L\"ntdl"...
0x180118a43  mov     [rbp+400h+var_460], rax
0x180118a47  jmp     short loc_180118AA5
0x180118a49  mov     rcx, [rbp+400h+BaseAddress]; BaseAddress
0x180118a4d  lea     r9, [rsp+500h+ProcedureAddress]; ProcedureAddress
0x180118a52  xor     r8d, r8d; Ordinal
0x180118a55  mov     [rsp+500h+ProcedureAddress], 0
0x180118a5e  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BC@U_STRING@@D@Details@RtlStringLiterals@@3D0EM@@0GE@@0HC@@0EH@@0GF@@0HE@@0EE@@0GM@@0GM@@0EG@@0HF@@0GM@@0GM@@0EO@@0GB@@0GN@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x180118a65  call    cs:__imp_LdrGetProcedureAddress
0x180118a6c  nop     dword ptr [rax+rax+00h]
0x180118a71  mov     r8d, eax
0x180118a74  test    eax, eax
0x180118a76  jns     short loc_180118AB5
0x180118a78  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118a7f  mov     [rbp+400h+var_440], 194h
0x180118a87  mov     qword ptr [rbp+400h+var_450], rax
0x180118a8b  lea     rdx, [rbp+400h+var_450]
0x180118a8f  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118a96  mov     qword ptr [rbp+400h+var_450+8], rax
0x180118a9a  lea     rax, aLdrgetprocedur_0; "::LdrGetProcedureAddress(Ntdll.Get(), &"...
0x180118aa1  mov     [rbp+400h+var_438], rax
0x180118aa5  lea     rcx, [rbp+400h+var_480]
0x180118aa9  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180118aae  mov     ebx, eax
0x180118ab0  jmp     loc_180118BDB
0x180118ab5  lea     rdx, [rsp+500h+BaseOfImage]; BaseOfImage
0x180118aba  mov     [rsp+500h+BaseOfImage], 0
0x180118ac3  lea     rcx, ?EnlistFsTx@@YAJPEAXAEAW4TxState@@@Z; PcValue
0x180118aca  call    cs:__imp_RtlPcToFileHeader
0x180118ad1  nop     dword ptr [rax+rax+00h]
0x180118ad6  test    rax, rax
0x180118ad9  jnz     short loc_180118B15
0x180118adb  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118ae2  mov     [rsp+500h+var_4A0], 197h
0x180118aeb  mov     [rsp+500h+var_4B0], rax
0x180118af0  lea     rdx, [rsp+500h+var_4B0]
0x180118af5  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118afc  mov     r8d, 0C0000135h
0x180118b02  mov     [rsp+500h+var_4A8], rax
0x180118b07  lea     rax, aRtlpctofilehea; "::RtlPcToFileHeader(EnlistFsTx, reinter"...
0x180118b0e  mov     [rsp+500h+var_498], rax
0x180118b13  jmp     short loc_180118AA5
0x180118b15  mov     rcx, [rsp+500h+BaseOfImage]
0x180118b1a  lea     rax, [rbp+400h+var_430]
0x180118b1e  mov     [rbp+400h+var_28], rax
0x180118b25  lea     rdx, [rbp+400h+var_30]
0x180118b2c  mov     rax, [rsp+500h+ProcedureAddress]
0x180118b31  mov     [rbp+400h+var_30], 4000000h
0x180118b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b41  mov     r8d, eax
0x180118b44  test    eax, eax
0x180118b46  jns     short loc_180118B7F
0x180118b48  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118b4f  mov     [rsp+500h+var_4C0], 19Ah
0x180118b58  mov     [rsp+500h+var_4D0], rax
0x180118b5d  lea     rdx, [rsp+500h+var_4D0]
0x180118b62  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118b69  mov     [rsp+500h+var_4C8], rax
0x180118b6e  lea     rax, aPfnldrgetdllfu; "pfnLdrGetDllFullName(hModule, FilePath."...
0x180118b75  mov     [rsp+500h+var_4B8], rax
0x180118b7a  jmp     loc_180118AA5
0x180118b7f  xorps   xmm0, xmm0
0x180118b82  lea     rdx, [rbp+400h+var_450]
0x180118b86  lea     rcx, [rbp+400h+var_430]
0x180118b8a  movups  [rbp+400h+var_450], xmm0
0x180118b8e  call    ??$SplitNtPath@V?$FixedString@U_UNICODE_STRING@@$0CAA@@RtlString@@@Rtl@StringUtil@Windows@@YAJAEBV?$FixedString@U_UNICODE_STRING@@$0CAA@@RtlString@@PEAU_UNICODE_STRING@@1@Z; Windows::StringUtil::Rtl::SplitNtPath<RtlString::FixedString<_UNICODE_STRING,512>>(RtlString::FixedString<_UNICODE_STRING,512> const &,_UNICODE_STRING *,_UNICODE_STRING *)
0x180118b93  test    eax, eax
0x180118b95  js      loc_180118AAE
0x180118b9b  xorps   xmm0, xmm0
0x180118b9e  lea     r8, [rbp+400h+var_478]
0x180118ba2  xor     eax, eax
0x180118ba4  lea     rcx, [rbp+400h+var_450]
0x180118ba8  movups  [rbp+400h+var_478], xmm0
0x180118bac  mov     [rbp+400h+var_468], rax
0x180118bb0  call    ??$CombineAndNullTerminateWin32Paths@U_UNICODE_STRING@@$$BY08_W@Rtl@StringUtil@Windows@@YAJAEBU_UNICODE_STRING@@AEAY08$$CB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<_UNICODE_STRING,wchar_t [9]>(_UNICODE_STRING const &,wchar_t const (&)[9],Windows::Auto<_LUNICODE_STRING> *)
0x180118bb5  lea     rcx, [rbp+400h+var_478]
0x180118bb9  mov     ebx, eax
0x180118bbb  test    eax, eax
0x180118bbd  js      short loc_180118BD6
0x180118bbf  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180118bc4  mov     rcx, rax; wchar_t *
0x180118bc7  call    ?LoadFsTx@@YAJPEB_W@Z; LoadFsTx(wchar_t const *)
0x180118bcc  lea     rcx, [rbp+400h+var_478]
0x180118bd0  mov     ebx, eax
0x180118bd2  test    eax, eax
0x180118bd4  jns     short loc_180118BEB
0x180118bd6  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118bdb  lea     rcx, [rbp+400h+BaseAddress]
0x180118bdf  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x180118be4  mov     eax, ebx
0x180118be6  jmp     loc_180118DBC
0x180118beb  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118bf0  lea     rcx, [rbp+400h+BaseAddress]
0x180118bf4  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x180118bf9  call    FsTxIsDefaultSessionContextSet
0x180118bfe  xor     ecx, ecx; this
0x180118c00  mov     [rsp+500h+var_4D8], 0; unsigned __int64
0x180118c09  mov     [rsp+500h+var_4E0], rcx; char *
0x180118c0e  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180118c15  test    eax, eax
0x180118c17  jnz     loc_180118D4C
0x180118c1d  lea     r9, aCreatingFstxSe; "Creating FsTx Session"
0x180118c24  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180118c29  xor     eax, eax
0x180118c2b  xorps   xmm0, xmm0
0x180118c2e  cmp     cs:?g_TestMode@@3_NA, al; bool g_TestMode
0x180118c34  xorps   xmm1, xmm1
0x180118c37  movups  [rbp+400h+var_450], xmm0
0x180118c3b  mov     [rbp+400h+var_440], rax
0x180118c3f  lea     edi, [rax+1]
0x180118c42  mov     [rbp+400h+var_468], rax
0x180118c46  movups  [rbp+400h+var_478], xmm1
0x180118c4a  jz      short loc_180118C97
0x180118c4c  lea     rax, [rbp+400h+var_450]
0x180118c50  lea     rdx, [rsp+500h+ProcedureAddress]
0x180118c55  mov     [rsp+500h+ProcedureAddress], rax
0x180118c5a  lea     rcx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BK@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FE@@0EF@@0FD@@0FE@@0FP@@0EG@@0FD@@0FE@@0FI@@0FP@@0FG@@0EP@@0EM@@0FF@@0EN@@0EF@@0FP@@0EP@@0FG@@0EF@@0FC@@0FC@@0EJ@@0EE@@0EF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@$0BD@$0BE@$0BF@$0BG@$0BH@$0BI@$0BJ@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180118c61  call    ??$QueryNullTerminatedEnvironmentValue@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@RtlSystemUtil@@YAJAEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(_LUNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180118c66  mov     ebx, eax
0x180118c68  test    eax, eax
0x180118c6a  js      loc_180118D21
0x180118c70  lea     rax, [rbp+400h+var_478]
0x180118c74  lea     rdx, [rsp+500h+ProcedureAddress]
0x180118c79  mov     [rsp+500h+ProcedureAddress], rax
0x180118c7e  lea     rcx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BI@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FE@@0EF@@0FD@@0FE@@0FP@@0EG@@0FD@@0FE@@0FI@@0FP@@0FA@@0EB@@0FE@@0EI@@0FP@@0EP@@0FG@@0EF@@0FC@@0FC@@0EJ@@0EE@@0EF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@$0BD@$0BE@$0BF@$0BG@$0BH@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180118c85  call    ??$QueryNullTerminatedEnvironmentValue@U_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@RtlSystemUtil@@YAJAEBU_LUNICODE_STRING@@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@Z; RtlSystemUtil::QueryNullTerminatedEnvironmentValue<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(_LUNICODE_STRING const &,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180118c8a  test    eax, eax
0x180118c8c  js      loc_180118D1F
0x180118c92  mov     edi, 9
0x180118c97  lea     rcx, [rbp+400h+var_478]
0x180118c9b  mov     [rsp+500h+BaseOfImage], 0
0x180118ca4  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180118ca9  lea     rcx, [rbp+400h+var_450]
0x180118cad  mov     rbx, rax
0x180118cb0  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180118cb5  lea     rcx, [rsp+500h+BaseOfImage]
0x180118cba  mov     r8d, edi
0x180118cbd  mov     [rsp+500h+var_4D8], rcx
0x180118cc2  mov     rdx, rbx
0x180118cc5  mov     rcx, rax
0x180118cc8  call    FsTxCreateSession2
0x180118ccd  mov     r8d, eax
0x180118cd0  test    eax, eax
0x180118cd2  jz      short loc_180118D38
0x180118cd4  mov     [rsp+500h+var_4C0], 1BEh
0x180118cdd  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118ce4  mov     [rsp+500h+var_4D0], rax
0x180118ce9  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118cf0  mov     [rsp+500h+var_4C8], rax
0x180118cf5  lea     rax, aFstxcreatesess; "::FsTxCreateSession2( Windows::StringUt"...
0x180118cfc  mov     [rsp+500h+var_4B8], rax
0x180118d01  test    r8d, r8d
0x180118d04  jle     short loc_180118D11
0x180118d06  movzx   r8d, r8w
0x180118d0a  or      r8d, 80070000h
0x180118d11  lea     rdx, [rsp+500h+var_4D0]
0x180118d16  lea     rcx, [rbp+400h+var_480]
0x180118d1a  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180118d1f  mov     ebx, eax
0x180118d21  lea     rcx, [rbp+400h+var_478]
0x180118d25  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118d2a  lea     rcx, [rbp+400h+var_450]
0x180118d2e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118d33  jmp     loc_180118BE4
0x180118d38  lea     rcx, [rbp+400h+var_478]
0x180118d3c  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118d41  lea     rcx, [rbp+400h+var_450]
0x180118d45  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180118d4a  jmp     short loc_180118D58
0x180118d4c  lea     r9, aDefaultFstxSes; "Default FsTx Session already set"
0x180118d53  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180118d58  mov     rdx, r14
0x180118d5b  call    FsTxEnlistTransaction
0x180118d60  mov     r8d, eax
0x180118d63  test    eax, eax
0x180118d65  jz      short loc_180118DB4
0x180118d67  mov     [rsp+500h+var_4C0], 1CCh
0x180118d70  lea     rax, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118d77  mov     [rsp+500h+var_4D0], rax
0x180118d7c  lea     rax, aEnlistfstx; "EnlistFsTx"
0x180118d83  mov     [rsp+500h+var_4C8], rax
0x180118d88  lea     rax, aFstxenlisttran; "::FsTxEnlistTransaction( nullptr, Tx, 0"...
0x180118d8f  mov     [rsp+500h+var_4B8], rax
0x180118d94  test    r8d, r8d
0x180118d97  jle     short loc_180118DA4
0x180118d99  movzx   r8d, r8w
0x180118d9d  or      r8d, 80070000h
0x180118da4  lea     rdx, [rsp+500h+var_4D0]
0x180118da9  lea     rcx, [rbp+400h+var_480]
0x180118dad  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180118db2  jmp     short loc_180118DBC
0x180118db4  mov     dword ptr [rsi], 1
0x180118dba  xor     eax, eax
0x180118dbc  mov     rcx, [rbp+400h+var_20]
0x180118dc3  xor     rcx, rsp; StackCookie
0x180118dc6  call    __security_check_cookie
0x180118dcb  lea     r11, [rsp+500h+var_10]
0x180118dd3  mov     rbx, [r11+30h]
0x180118dd7  mov     rsi, [r11+38h]
0x180118ddb  mov     rsp, r11
0x180118dde  pop     r14
0x180118de0  pop     rdi
0x180118de1  pop     rbp
0x180118de2  retn
```
