# SymbolHandler::Load(void)

- ea: `0x1801a3f84`
- end: `0x1801a4222`
- name: `?Load@SymbolHandler@@QEAAXXZ`
- size: `670`
- prototype: `void __fastcall(SymbolHandler *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18011a030`
- `0x18011f54c`
- `0x1801a57b4`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18003104c`
- `0x1801a3f84`
- `0x1801bd010`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x1801a3fd7`
- `ntdll!LdrLoadDll` at `0x1801a4092`
- `ntdll!LdrLoadDll` at `0x1801a3fd7`
- `ntdll!LdrLoadDll` at `0x1801a4092`
- `ntdll!LdrUnloadDll` at `0x1801a4158`
- `ntdll!LdrUnloadDll` at `0x1801a417f`
- `ntdll!LdrUnloadDll` at `0x1801a41d8`
- `ntdll!LdrUnloadDll` at `0x1801a4158`
- `ntdll!LdrUnloadDll` at `0x1801a417f`
- `ntdll!LdrUnloadDll` at `0x1801a41d8`
- `ntdll!LdrGetProcedureAddress` at `0x1801a4004`
- `ntdll!LdrGetProcedureAddress` at `0x1801a4028`
- `ntdll!LdrGetProcedureAddress` at `0x1801a404c`
- `ntdll!LdrGetProcedureAddress` at `0x1801a40b8`
- `ntdll!LdrGetProcedureAddress` at `0x1801a4004`
- `ntdll!LdrGetProcedureAddress` at `0x1801a4028`
- `ntdll!LdrGetProcedureAddress` at `0x1801a404c`
- `ntdll!LdrGetProcedureAddress` at `0x1801a40b8`

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
    if ( qword_1802414C0 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801A4221LL);
    }
    LdrLoadDll(
      0,
      0,
      (PUNICODE_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0EE__0GC__0GH__0GI__0GF__0GM__0HA__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
      &qword_1802414C0);
    if ( qword_1802414C0 )
    {
      LdrGetProcedureAddress(
        qword_1802414C0,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0M_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EG__0HC__0GP__0GN__0EB__0GE__0GE__0HC__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1802414C8);
      LdrGetProcedureAddress(
        qword_1802414C0,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0O_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0EJ__0GO__0GJ__0HE__0GJ__0GB__0GM__0GJ__0HK__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1802414D0);
      LdrGetProcedureAddress(
        qword_1802414C0,
        (PANSI_STRING)&___LiteralObject__2U__BaseLiteralBuffer__0L_U_STRING__D_Details_RtlStringLiterals__3D0FD__0HJ__0GN__0ED__0GM__0GF__0GB__0GO__0HF__0HA__0A_____0A__00_01_02_03_04_05_06_07_08_09_Details_RtlStringLiterals__3U_STRING__B,
        0,
        &qword_1802414D8);
      if ( qword_1802414D0 && qword_1802414C8 && qword_1802414D8 )
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
            &qword_1802414E0);
        if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int64))qword_1802414D0)(-1, 0, 1) )
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
          qword_1802414D0 = 0;
          qword_1802414C8 = 0;
          qword_1802414D8 = 0;
          if ( qword_1802414C0 )
          {
            if ( LdrUnloadDll(qword_1802414C0) < 0 )
              __fastfail(7u);
            qword_1802414C0 = 0;
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
        qword_1802414D0 = 0;
        qword_1802414C8 = 0;
        qword_1802414D8 = 0;
        if ( qword_1802414C0 )
        {
          if ( LdrUnloadDll(qword_1802414C0) < 0 )
            __fastfail(7u);
          qword_1802414C0 = 0;
        }
      }
    }
    ++g_SymbolHandler;
  }
}

```

## disassembly

```asm
0x1801a3f84  mov     [rsp-8+arg_0], rdi
0x1801a3f89  push    rbp
0x1801a3f8a  mov     rbp, rsp
0x1801a3f8d  sub     rsp, 70h
0x1801a3f91  mov     rax, cs:__security_cookie
0x1801a3f98  xor     rax, rsp
0x1801a3f9b  mov     [rbp+var_10], rax
0x1801a3f9f  mov     eax, cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1801a3fa5  xor     edi, edi
0x1801a3fa7  test    eax, eax
0x1801a3fa9  jz      short loc_1801A3FB8
0x1801a3fab  inc     eax
0x1801a3fad  mov     cs:?g_SymbolHandler@@3VSymbolHandler@@A, eax; SymbolHandler g_SymbolHandler
0x1801a3fb3  jmp     loc_1801A41FC
0x1801a3fb8  cmp     cs:qword_1802414C0, rdi
0x1801a3fbf  jnz     loc_1801A4217
0x1801a3fc5  lea     r9, qword_1802414C0; BaseAddress
0x1801a3fcc  xor     edx, edx; LoadFlags
0x1801a3fce  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EE@@0GC@@0GH@@0GI@@0GF@@0GM@@0HA@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1801a3fd5  xor     ecx, ecx; SearchPath
0x1801a3fd7  call    cs:__imp_LdrLoadDll
0x1801a3fde  nop     dword ptr [rax+rax+00h]
0x1801a3fe3  mov     rcx, cs:qword_1802414C0; BaseAddress
0x1801a3fea  test    rcx, rcx
0x1801a3fed  jz      loc_1801A41F6
0x1801a3ff3  lea     r9, qword_1802414C8; ProcedureAddress
0x1801a3ffa  xor     r8d, r8d; Ordinal
0x1801a3ffd  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EG@@0HC@@0GP@@0GN@@0EB@@0GE@@0GE@@0HC@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801a4004  call    cs:__imp_LdrGetProcedureAddress
0x1801a400b  nop     dword ptr [rax+rax+00h]
0x1801a4010  mov     rcx, cs:qword_1802414C0; BaseAddress
0x1801a4017  lea     r9, qword_1802414D0; ProcedureAddress
0x1801a401e  xor     r8d, r8d; Ordinal
0x1801a4021  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0O@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0EJ@@0GO@@0GJ@@0HE@@0GJ@@0GB@@0GM@@0GJ@@0HK@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801a4028  call    cs:__imp_LdrGetProcedureAddress
0x1801a402f  nop     dword ptr [rax+rax+00h]
0x1801a4034  mov     rcx, cs:qword_1802414C0; BaseAddress
0x1801a403b  lea     r9, qword_1802414D8; ProcedureAddress
0x1801a4042  xor     r8d, r8d; Ordinal
0x1801a4045  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0L@U_STRING@@D@Details@RtlStringLiterals@@3D0FD@@0HJ@@0GN@@0ED@@0GM@@0GF@@0GB@@0GO@@0HF@@0HA@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801a404c  call    cs:__imp_LdrGetProcedureAddress
0x1801a4053  nop     dword ptr [rax+rax+00h]
0x1801a4058  cmp     cs:qword_1802414D0, rdi
0x1801a405f  jz      loc_1801A4198
0x1801a4065  cmp     cs:qword_1802414C8, rdi
0x1801a406c  jz      loc_1801A4198
0x1801a4072  cmp     cs:qword_1802414D8, rdi
0x1801a4079  jz      loc_1801A4198
0x1801a407f  lea     r9, [rbp+BaseAddress]; BaseAddress
0x1801a4083  mov     [rbp+BaseAddress], rdi
0x1801a4087  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0GO@@0HE@@0GE@@0GM@@0GM@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B; Name
0x1801a408e  xor     edx, edx; LoadFlags
0x1801a4090  xor     ecx, ecx; SearchPath
0x1801a4092  call    cs:__imp_LdrLoadDll
0x1801a4099  nop     dword ptr [rax+rax+00h]
0x1801a409e  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x1801a40a2  test    rcx, rcx
0x1801a40a5  jz      short loc_1801A40C4
0x1801a40a7  lea     r9, qword_1802414E0; ProcedureAddress
0x1801a40ae  xor     r8d, r8d; Ordinal
0x1801a40b1  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BC@U_STRING@@D@Details@RtlStringLiterals@@3D0EM@@0GE@@0HC@@0EH@@0GF@@0HE@@0EE@@0GM@@0GM@@0EG@@0HF@@0GM@@0GM@@0EO@@0GB@@0GN@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@@Details@RtlStringLiterals@@3U_STRING@@B; Name
0x1801a40b8  call    cs:__imp_LdrGetProcedureAddress
0x1801a40bf  nop     dword ptr [rax+rax+00h]
0x1801a40c4  mov     rax, cs:qword_1802414D0
0x1801a40cb  xor     edx, edx
0x1801a40cd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801a40d1  lea     r8d, [rdx+1]
0x1801a40d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a40da  test    eax, eax
0x1801a40dc  jnz     loc_1801A4176
0x1801a40e2  mov     rax, gs:30h
0x1801a40eb  lea     r9, aSyminitializeF; "++ SymInitialize failed with: {0} - not"...
0x1801a40f2  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801a40f9  mov     [rbp+var_28], rdi
0x1801a40fd  mov     ecx, [rax+68h]
0x1801a4100  lea     rax, [rbp+var_40]
0x1801a4104  mov     [rbp+var_38], rax
0x1801a4108  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU?$FormatWin32ErrorWrapper@K@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801a410f  mov     [rbp+var_20], rax
0x1801a4113  lea     rax, [rbp+var_38]
0x1801a4117  mov     [rbp+var_18], rax
0x1801a411b  lea     rax, [rbp+var_28]
0x1801a411f  mov     dword ptr [rbp+var_40], ecx
0x1801a4122  xor     ecx, ecx; this
0x1801a4124  mov     [rsp+70h+var_48], rax; unsigned __int64
0x1801a4129  mov     [rsp+70h+var_50], 1; char *
0x1801a4132  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801a4137  mov     rcx, cs:qword_1802414C0; BaseAddress
0x1801a413e  mov     cs:qword_1802414D0, rdi
0x1801a4145  mov     cs:qword_1802414C8, rdi
0x1801a414c  mov     cs:qword_1802414D8, rdi
0x1801a4153  test    rcx, rcx
0x1801a4156  jz      short loc_1801A4176
0x1801a4158  call    cs:__imp_LdrUnloadDll
0x1801a415f  nop     dword ptr [rax+rax+00h]
0x1801a4164  test    eax, eax
0x1801a4166  jns     short loc_1801A416F
0x1801a4168  mov     ecx, 7
0x1801a416d  int     29h; Win8: RtlFailFast(ecx)
0x1801a416f  mov     cs:qword_1802414C0, rdi
0x1801a4176  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x1801a417a  test    rcx, rcx
0x1801a417d  jz      short loc_1801A41F6
0x1801a417f  call    cs:__imp_LdrUnloadDll
0x1801a4186  nop     dword ptr [rax+rax+00h]
0x1801a418b  test    eax, eax
0x1801a418d  jns     short loc_1801A41F6
0x1801a418f  mov     ecx, 7
0x1801a4194  int     29h; Win8: RtlFailFast(ecx)
0x1801a4196  jmp     short loc_1801A41F6
0x1801a4198  mov     [rsp+70h+var_48], rdi; unsigned __int64
0x1801a419d  lea     r9, aSymbolFunction; "++ Symbol functions not found - not pre"...
0x1801a41a4  lea     r8, ?Facility_General@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1801a41ab  mov     [rsp+70h+var_50], rdi; char *
0x1801a41b0  xor     ecx, ecx; this
0x1801a41b2  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x1801a41b7  mov     rcx, cs:qword_1802414C0; BaseAddress
0x1801a41be  mov     cs:qword_1802414D0, rdi
0x1801a41c5  mov     cs:qword_1802414C8, rdi
0x1801a41cc  mov     cs:qword_1802414D8, rdi
0x1801a41d3  test    rcx, rcx
0x1801a41d6  jz      short loc_1801A41F6
0x1801a41d8  call    cs:__imp_LdrUnloadDll
0x1801a41df  nop     dword ptr [rax+rax+00h]
0x1801a41e4  test    eax, eax
0x1801a41e6  jns     short loc_1801A41EF
0x1801a41e8  mov     ecx, 7
0x1801a41ed  int     29h; Win8: RtlFailFast(ecx)
0x1801a41ef  mov     cs:qword_1802414C0, rdi
0x1801a41f6  inc     cs:?g_SymbolHandler@@3VSymbolHandler@@A; SymbolHandler g_SymbolHandler
0x1801a41fc  mov     rcx, [rbp+var_10]
0x1801a4200  xor     rcx, rsp; StackCookie
0x1801a4203  call    __security_check_cookie
0x1801a4208  mov     rdi, [rsp+70h+arg_0]
0x1801a4210  add     rsp, 70h
0x1801a4214  pop     rbp
0x1801a4215  retn
0x1801a4217  mov     ecx, 0C00000E5h; int
0x1801a421c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
