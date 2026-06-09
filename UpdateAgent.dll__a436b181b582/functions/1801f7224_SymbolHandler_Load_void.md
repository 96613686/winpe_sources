# SymbolHandler::Load(void)

- ea: `0x1801f7224`
- end: `0x1801f74c2`
- name: `?Load@SymbolHandler@@QEAAXXZ`
- size: `670`
- prototype: `void __fastcall(SymbolHandler *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18017d1e0`
- `0x18018283c`
- `0x1801f8a54`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x1801e51c4`
- `0x1801f7224`
- `0x1802b1010`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x1801f7277`
- `ntdll!LdrLoadDll` at `0x1801f7332`
- `ntdll!LdrLoadDll` at `0x1801f7277`
- `ntdll!LdrLoadDll` at `0x1801f7332`
- `ntdll!LdrUnloadDll` at `0x1801f73f8`
- `ntdll!LdrUnloadDll` at `0x1801f741f`
- `ntdll!LdrUnloadDll` at `0x1801f7478`
- `ntdll!LdrUnloadDll` at `0x1801f73f8`
- `ntdll!LdrUnloadDll` at `0x1801f741f`
- `ntdll!LdrUnloadDll` at `0x1801f7478`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72a4`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72c8`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72ec`
- `ntdll!LdrGetProcedureAddress` at `0x1801f7358`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72a4`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72c8`
- `ntdll!LdrGetProcedureAddress` at `0x1801f72ec`
- `ntdll!LdrGetProcedureAddress` at `0x1801f7358`

## pseudocode

```c
void __fastcall SymbolHandler::Load(SymbolHandler *this)
{
  unsigned int v1; // edx
  unsigned int v2; // edx
  ULONG LastErrorValue; // ecx
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v4; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER **v5; // [rsp+38h] [rbp-38h] BYREF
  PVOID BaseAddress; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v7[3]; // [rsp+48h] [rbp-28h] BYREF

  if ( g_SymbolHandler )
  {
    ++g_SymbolHandler;
  }
  else
  {
    if ( qword_1803ACC40 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801F74C1LL);
    }
    LdrLoadDll(
      0,
      0,
      (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0EE__0GC__0GH__0GI__0GF__0GM__0HA__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
      &qword_1803ACC40);
    if ( qword_1803ACC40 )
    {
      LdrGetProcedureAddress(
        qword_1803ACC40,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EG__0HC__0GP__0GN__0EB__0GE__0GE__0HC__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803ACC48);
      LdrGetProcedureAddress(
        qword_1803ACC40,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0O_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EJ__0GO__0GJ__0HE__0GJ__0GB__0GM__0GJ__0HK__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803ACC50);
      LdrGetProcedureAddress(
        qword_1803ACC40,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0L_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0ED__0GM__0GF__0GB__0GO__0HF__0HA__0A_____0A__00_01_02_03_04_05_06_07_08_09_Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1803ACC58);
      if ( qword_1803ACC50 && qword_1803ACC48 && qword_1803ACC58 )
      {
        BaseAddress = 0;
        LdrLoadDll(
          0,
          0,
          (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__09U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0GO__0HE__0GE__0GM__0GM__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_Details_RtlStringLiterals__3U_UNICODE_STRING__B,
          &BaseAddress);
        if ( BaseAddress )
          LdrGetProcedureAddress(
            BaseAddress,
            (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0BC_U_STRING__D_Details_RtlStringLiterals__3D0EM__0GE__0HC__0EH__0GF__0HE__0EE__0GM__0GM__0EG__0HF__0GM__0GM__0EO__0GB__0GN__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__Details_RtlStringLiterals__3U_STRING__B,
            0,
            &qword_1803ACC60);
        if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64))qword_1803ACC50)(-1, 0, 1) )
        {
          v7[0] = 0;
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v5 = &v4;
          v7[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
          v7[2] = (unsigned __int64)&v5;
          LODWORD(v4) = LastErrorValue;
          Windows::WCP::Rtl::RtlTraceFromParameterList(
            0,
            v2,
            (unsigned int)&Windows::WCP::Rtl::Facility_General,
            (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"++ SymInitialize failed with: {0} - not pretty printing backtrace",
            (const char *const)1,
            (unsigned __int64)v7,
            v4);
          qword_1803ACC50 = 0;
          qword_1803ACC48 = 0;
          qword_1803ACC58 = 0;
          if ( qword_1803ACC40 )
          {
            if ( LdrUnloadDll(qword_1803ACC40) < 0 )
              __fastfail(7u);
            qword_1803ACC40 = 0;
          }
        }
        if ( BaseAddress )
        {
          if ( LdrUnloadDll(BaseAddress) < 0 )
            __fastfail(7u);
        }
      }
      else
      {
        Windows::WCP::Rtl::RtlTraceFromParameterList(
          0,
          v1,
          (unsigned int)&Windows::WCP::Rtl::Facility_General,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"++ Symbol functions not found - not pretty printing backtrace",
          0,
          0,
          v4);
        qword_1803ACC50 = 0;
        qword_1803ACC48 = 0;
        qword_1803ACC58 = 0;
        if ( qword_1803ACC40 )
        {
          if ( LdrUnloadDll(qword_1803ACC40) < 0 )
            __fastfail(7u);
          qword_1803ACC40 = 0;
        }
      }
    }
    ++g_SymbolHandler;
  }
}

```

## disassembly

```asm
0x1801f7224  mov     [rsp-8+arg_0], rdi
0x1801f7229  push    rbp
0x1801f722a  mov     rbp, rsp
0x1801f722d  sub     rsp, 70h
0x1801f7231  mov     rax, cs:__security_cookie
0x1801f7238  xor     rax, rsp
0x1801f723b  mov     [rbp+var_10], rax
0x1801f723f  mov     eax, cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1801f7245  xor     edi, edi
0x1801f7247  test    eax, eax
0x1801f7249  jz      short loc_1801F7258
0x1801f724b  inc     eax
0x1801f724d  mov     cs:?g_SymbolHandler@@3VSymbolHandler@@A, eax; SymbolHandler g_SymbolHandler
0x1801f7253  jmp     loc_1801F749C
0x1801f7258  cmp     cs:qword_1803ACC40, rdi
0x1801f725f  jnz     loc_1801F74B7
0x1801f7265  lea     r9, qword_1803ACC40; BaseAddress
0x1801f726c  xor     edx, edx; LoadFlags
0x1801f726e  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EE@@0GC@@0GH@@0GI@@0GF@@0GM@@0HA@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1801f7275  xor     ecx, ecx; SearchPath
0x1801f7277  call    cs:__imp_LdrLoadDll
0x1801f727e  nop     dword ptr [rax+rax+00h]
0x1801f7283  mov     rcx, cs:qword_1803ACC40; BaseAddress
0x1801f728a  test    rcx, rcx
0x1801f728d  jz      loc_1801F7496
0x1801f7293  lea     r9, qword_1803ACC48; ProcedureAddress
0x1801f729a  xor     r8d, r8d; Ordinal
0x1801f729d  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EG@@0HC@@0GP@@0GN@@0EB@@0GE@@0GE@@0HC@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801f72a4  call    cs:__imp_LdrGetProcedureAddress
0x1801f72ab  nop     dword ptr [rax+rax+00h]
0x1801f72b0  mov     rcx, cs:qword_1803ACC40; BaseAddress
0x1801f72b7  lea     r9, qword_1803ACC50; ProcedureAddress
0x1801f72be  xor     r8d, r8d; Ordinal
0x1801f72c1  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0O@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EJ@@0GO@@0GJ@@0HE@@0GJ@@0GB@@0GM@@0GJ@@0HK@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801f72c8  call    cs:__imp_LdrGetProcedureAddress
0x1801f72cf  nop     dword ptr [rax+rax+00h]
0x1801f72d4  mov     rcx, cs:qword_1803ACC40; BaseAddress
0x1801f72db  lea     r9, qword_1803ACC58; ProcedureAddress
0x1801f72e2  xor     r8d, r8d; Ordinal
0x1801f72e5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0L@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0ED@@0GM@@0GF@@0GB@@0GO@@0HF@@0HA@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801f72ec  call    cs:__imp_LdrGetProcedureAddress
0x1801f72f3  nop     dword ptr [rax+rax+00h]
0x1801f72f8  cmp     cs:qword_1803ACC50, rdi
0x1801f72ff  jz      loc_1801F7438
0x1801f7305  cmp     cs:qword_1803ACC48, rdi
0x1801f730c  jz      loc_1801F7438
0x1801f7312  cmp     cs:qword_1803ACC58, rdi
0x1801f7319  jz      loc_1801F7438
0x1801f731f  lea     r9, [rbp+BaseAddress]; BaseAddress
0x1801f7323  mov     [rbp+BaseAddress], rdi
0x1801f7327  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0GO@@0HE@@0GE@@0GM@@0GM@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1801f732e  xor     edx, edx; LoadFlags
0x1801f7330  xor     ecx, ecx; SearchPath
0x1801f7332  call    cs:__imp_LdrLoadDll
0x1801f7339  nop     dword ptr [rax+rax+00h]
0x1801f733e  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x1801f7342  test    rcx, rcx
0x1801f7345  jz      short loc_1801F7364
0x1801f7347  lea     r9, qword_1803ACC60; ProcedureAddress
0x1801f734e  xor     r8d, r8d; Ordinal
0x1801f7351  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BC@U_STRING@@D@Details@RtlStringLiterals@@3D0EM@@0GE@@0HC@@0EH@@0GF@@0HE@@0EE@@0GM@@0GM@@0EG@@0HF@@0GM@@0GM@@0EO@@0GB@@0GN@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801f7358  call    cs:__imp_LdrGetProcedureAddress
0x1801f735f  nop     dword ptr [rax+rax+00h]
0x1801f7364  mov     rax, cs:qword_1803ACC50
0x1801f736b  xor     edx, edx
0x1801f736d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801f7371  lea     r8d, [rdx+1]
0x1801f7375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f737a  test    eax, eax
0x1801f737c  jnz     loc_1801F7416
0x1801f7382  mov     rax, gs:30h
0x1801f738b  lea     r9, aSyminitializeF; "++ SymInitialize failed with: {0} - not"...
0x1801f7392  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801f7399  mov     [rbp+var_28], rdi
0x1801f739d  mov     ecx, [rax+68h]
0x1801f73a0  lea     rax, [rbp+var_40]
0x1801f73a4  mov     [rbp+var_38], rax
0x1801f73a8  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU?$FormatWin32ErrorWrapper@K@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801f73af  mov     [rbp+var_20], rax
0x1801f73b3  lea     rax, [rbp+var_38]
0x1801f73b7  mov     [rbp+var_18], rax
0x1801f73bb  lea     rax, [rbp+var_28]
0x1801f73bf  mov     dword ptr [rbp+var_40], ecx
0x1801f73c2  xor     ecx, ecx; this
0x1801f73c4  mov     [rsp+70h+var_48], rax; unsigned __int64
0x1801f73c9  mov     [rsp+70h+var_50], 1; char *
0x1801f73d2  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801f73d7  mov     rcx, cs:qword_1803ACC40; BaseAddress
0x1801f73de  mov     cs:qword_1803ACC50, rdi
0x1801f73e5  mov     cs:qword_1803ACC48, rdi
0x1801f73ec  mov     cs:qword_1803ACC58, rdi
0x1801f73f3  test    rcx, rcx
0x1801f73f6  jz      short loc_1801F7416
0x1801f73f8  call    cs:__imp_LdrUnloadDll
0x1801f73ff  nop     dword ptr [rax+rax+00h]
0x1801f7404  test    eax, eax
0x1801f7406  jns     short loc_1801F740F
0x1801f7408  mov     ecx, 7
0x1801f740d  int     29h; Win8: RtlFailFast(ecx)
0x1801f740f  mov     cs:qword_1803ACC40, rdi
0x1801f7416  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x1801f741a  test    rcx, rcx
0x1801f741d  jz      short loc_1801F7496
0x1801f741f  call    cs:__imp_LdrUnloadDll
0x1801f7426  nop     dword ptr [rax+rax+00h]
0x1801f742b  test    eax, eax
0x1801f742d  jns     short loc_1801F7496
0x1801f742f  mov     ecx, 7
0x1801f7434  int     29h; Win8: RtlFailFast(ecx)
0x1801f7436  jmp     short loc_1801F7496
0x1801f7438  mov     [rsp+70h+var_48], rdi; unsigned __int64
0x1801f743d  lea     r9, aSymbolFunction; "++ Symbol functions not found - not pre"...
0x1801f7444  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801f744b  mov     [rsp+70h+var_50], rdi; char *
0x1801f7450  xor     ecx, ecx; this
0x1801f7452  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801f7457  mov     rcx, cs:qword_1803ACC40; BaseAddress
0x1801f745e  mov     cs:qword_1803ACC50, rdi
0x1801f7465  mov     cs:qword_1803ACC48, rdi
0x1801f746c  mov     cs:qword_1803ACC58, rdi
0x1801f7473  test    rcx, rcx
0x1801f7476  jz      short loc_1801F7496
0x1801f7478  call    cs:__imp_LdrUnloadDll
0x1801f747f  nop     dword ptr [rax+rax+00h]
0x1801f7484  test    eax, eax
0x1801f7486  jns     short loc_1801F748F
0x1801f7488  mov     ecx, 7
0x1801f748d  int     29h; Win8: RtlFailFast(ecx)
0x1801f748f  mov     cs:qword_1803ACC40, rdi
0x1801f7496  inc     cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1801f749c  mov     rcx, [rbp+var_10]
0x1801f74a0  xor     rcx, rsp; StackCookie
0x1801f74a3  call    __security_check_cookie
0x1801f74a8  mov     rdi, [rsp+70h+arg_0]
0x1801f74b0  add     rsp, 70h
0x1801f74b4  pop     rbp
0x1801f74b5  retn
0x1801f74b7  mov     ecx, 0C00000E5h; int
0x1801f74bc  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
