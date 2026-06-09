# RMContext::Initialize(ulong,bool *)

- ea: `0x1802bf654`
- end: `0x1802bf8d9`
- name: `?Initialize@RMContext@@QEAAJKPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(RMContext *__hidden this, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1802c3d80`

## callees

- `0x1800aa134`
- `0x1800eb50c`
- `0x1800eb920`
- `0x180219834`
- `0x1802bf654`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x1802bf6fc`
- `ntdll!LdrLoadDll` at `0x1802bf6fc`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf736`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf767`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf798`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf7c9`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf7fa`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf82b`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf736`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf767`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf798`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf7c9`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf7fa`
- `ntdll!LdrGetProcedureAddress` at `0x1802bf82b`

## pseudocode

```c
__int64 __fastcall RMContext::Initialize(RMContext *this, __int64 a2, bool *a3)
{
  _QWORD *v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  PVOID v9; // rcx
  struct _UNICODE_STRING Name; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  int v14; // [rsp+40h] [rbp-10h] BYREF

  *a3 = 0;
  v14 = 0;
  if ( *(_QWORD *)this )
    goto LABEL_21;
  v5 = operator new[](0x170u);
  if ( v5 )
  {
    v6 = 0;
    *v5 = 5;
    do
    {
      v7 = 9 * v6++;
      LODWORD(v5[v7 + 1]) = -1;
    }
    while ( v6 < 5 );
    v8 = v5 + 1;
    if ( v8 )
    {
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = 5;
    }
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
LABEL_21:
    v12 = 152;
    *(_QWORD *)&Name.Length = "onecore\\base\\wcp\\poq\\RMHelper.h";
    Name.Buffer = (PWSTR)"RMContext::Initialize";
    v13 = "m_RMHandles.Allocate(Capacity)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
             &v14,
             &Name);
  }
  else
  {
    v9 = RMContext::s_hRstrtMgr;
    if ( RMContext::s_hRstrtMgr
      || (Name = *(struct _UNICODE_STRING *)&___LiteralObject__2U__BaseLiteralBuffer__0N_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0HC__0HD__0HE__0HC__0HE__0GN__0GH__0HC__0CO__0GE__0GM__0GM__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
          LdrLoadDll(0, 0, &Name, &RMContext::s_hRstrtMgr),
          (v9 = RMContext::s_hRstrtMgr) != 0) )
    {
      *(_QWORD *)&Name.Length = 983054;
      Name.Buffer = (PWSTR)"RmStartSession";
      LdrGetProcedureAddress(v9, (PANSI_STRING)&Name, 0, (PVOID *)this + 3);
      Name.Buffer = (PWSTR)"RmRegisterResources";
      *(_QWORD *)&Name.Length = 1310739;
      LdrGetProcedureAddress(RMContext::s_hRstrtMgr, (PANSI_STRING)&Name, 0, (PVOID *)this + 4);
      Name.Buffer = (PWSTR)"RmGetList";
      *(_QWORD *)&Name.Length = 655369;
      LdrGetProcedureAddress(RMContext::s_hRstrtMgr, (PANSI_STRING)&Name, 0, (PVOID *)this + 5);
      Name.Buffer = (PWSTR)"RmShutdown";
      *(_QWORD *)&Name.Length = 720906;
      LdrGetProcedureAddress(RMContext::s_hRstrtMgr, (PANSI_STRING)&Name, 0, (PVOID *)this + 6);
      Name.Buffer = (PWSTR)"RmRestart";
      *(_QWORD *)&Name.Length = 655369;
      LdrGetProcedureAddress(RMContext::s_hRstrtMgr, (PANSI_STRING)&Name, 0, (PVOID *)this + 7);
      Name.Buffer = (PWSTR)"RmEndSession";
      *(_QWORD *)&Name.Length = 851980;
      LdrGetProcedureAddress(RMContext::s_hRstrtMgr, (PANSI_STRING)&Name, 0, (PVOID *)this + 8);
      if ( *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 4)
          && *((_QWORD *)this + 5)
          && *((_QWORD *)this + 6)
          && *((_QWORD *)this + 7)
          && *((_QWORD *)this + 8) )
        {
          *a3 = 1;
        }
      }
    }
    if ( !*a3 )
      Windows::WCP::Rtl::RtlTrace(
        0,
        (unsigned int)&Windows::WCP::Rtl::Facility_POQ,
        (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Unable to successfully initialize RMContext, not using RestartMgr.",
        0,
        *(unsigned __int64 *)&Name.Length);
    return 0;
  }
}

```

## disassembly

```asm
0x1802bf654  mov     [rsp-38h+arg_8], rbx
0x1802bf659  push    rbp
0x1802bf65a  push    rsi
0x1802bf65b  push    rdi
0x1802bf65c  push    r12
0x1802bf65e  push    r13
0x1802bf660  push    r14
0x1802bf662  push    r15
0x1802bf664  mov     rbp, rsp
0x1802bf667  sub     rsp, 50h
0x1802bf66b  mov     rax, cs:__security_cookie
0x1802bf672  xor     rax, rsp
0x1802bf675  mov     [rbp+var_8], rax
0x1802bf679  xor     ebx, ebx
0x1802bf67b  mov     rsi, r8
0x1802bf67e  mov     [r8], bl
0x1802bf681  mov     rdi, rcx
0x1802bf684  mov     [rbp+var_10], ebx
0x1802bf687  cmp     [rcx], rbx
0x1802bf68a  jnz     loc_1802BF87E
0x1802bf690  mov     ecx, 170h; unsigned __int64
0x1802bf695  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1802bf69a  test    rax, rax
0x1802bf69d  jz      short loc_1802BF6CB
0x1802bf69f  lea     r8d, [rbx+5]
0x1802bf6a3  mov     edx, ebx
0x1802bf6a5  mov     [rax], r8
0x1802bf6a8  lea     rcx, [rdx+rdx*8]
0x1802bf6ac  inc     rdx
0x1802bf6af  mov     dword ptr [rax+rcx*8+8], 0FFFFFFFFh
0x1802bf6b7  cmp     rdx, r8
0x1802bf6ba  jb      short loc_1802BF6A8
0x1802bf6bc  add     rax, 8
0x1802bf6c0  jz      short loc_1802BF6CE
0x1802bf6c2  mov     [rdi], rax
0x1802bf6c5  mov     [rdi+8], r8
0x1802bf6c9  jmp     short loc_1802BF6CE
0x1802bf6cb  mov     rax, rbx
0x1802bf6ce  test    rax, rax
0x1802bf6d1  jz      loc_1802BF87E
0x1802bf6d7  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; SearchPath
0x1802bf6de  test    rcx, rcx
0x1802bf6e1  jnz     short loc_1802BF718
0x1802bf6e3  movups  xmm0, xmmword ptr cs:??$LiteralObject@$2U?$BaseLiteralBuffer@$0N@U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0HC@@0HD@@0HE@@0HC@@0HE@@0GN@@0GH@@0HC@@0CO@@0GE@@0GM@@0GM@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@@Details@RtlStringLiterals@@3U_UNICODE_STRING@@B
0x1802bf6ea  lea     r9, ?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf6f1  xor     edx, edx; LoadFlags
0x1802bf6f3  lea     r8, [rbp+Name]; Name
0x1802bf6f7  movdqu  xmmword ptr [rbp+Name.Length], xmm0
0x1802bf6fc  call    cs:__imp_LdrLoadDll
0x1802bf703  nop     dword ptr [rax+rax+00h]
0x1802bf708  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf70f  test    rcx, rcx
0x1802bf712  jz      loc_1802BF85E
0x1802bf718  lea     rax, aRmstartsession; "RmStartSession"
0x1802bf71f  mov     qword ptr [rbp+Name.Length], 0F000Eh
0x1802bf727  lea     r9, [rdi+18h]; ProcedureAddress
0x1802bf72b  mov     [rbp+Name.Buffer], rax
0x1802bf72f  xor     r8d, r8d; Ordinal
0x1802bf732  lea     rdx, [rbp+Name]; Name
0x1802bf736  call    cs:__imp_LdrGetProcedureAddress
0x1802bf73d  nop     dword ptr [rax+rax+00h]
0x1802bf742  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf749  lea     rax, aRmregisterreso; "RmRegisterResources"
0x1802bf750  lea     r9, [rdi+20h]; ProcedureAddress
0x1802bf754  mov     [rbp+Name.Buffer], rax
0x1802bf758  xor     r8d, r8d; Ordinal
0x1802bf75b  mov     qword ptr [rbp+Name.Length], 140013h
0x1802bf763  lea     rdx, [rbp+Name]; Name
0x1802bf767  call    cs:__imp_LdrGetProcedureAddress
0x1802bf76e  nop     dword ptr [rax+rax+00h]
0x1802bf773  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf77a  lea     rax, aRmgetlist; "RmGetList"
0x1802bf781  lea     r9, [rdi+28h]; ProcedureAddress
0x1802bf785  mov     [rbp+Name.Buffer], rax
0x1802bf789  xor     r8d, r8d; Ordinal
0x1802bf78c  mov     qword ptr [rbp+Name.Length], 0A0009h
0x1802bf794  lea     rdx, [rbp+Name]; Name
0x1802bf798  call    cs:__imp_LdrGetProcedureAddress
0x1802bf79f  nop     dword ptr [rax+rax+00h]
0x1802bf7a4  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf7ab  lea     rax, aRmshutdown; "RmShutdown"
0x1802bf7b2  lea     r9, [rdi+30h]; ProcedureAddress
0x1802bf7b6  mov     [rbp+Name.Buffer], rax
0x1802bf7ba  xor     r8d, r8d; Ordinal
0x1802bf7bd  mov     qword ptr [rbp+Name.Length], 0B000Ah
0x1802bf7c5  lea     rdx, [rbp+Name]; Name
0x1802bf7c9  call    cs:__imp_LdrGetProcedureAddress
0x1802bf7d0  nop     dword ptr [rax+rax+00h]
0x1802bf7d5  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf7dc  lea     rax, aRmrestart; "RmRestart"
0x1802bf7e3  lea     r9, [rdi+38h]; ProcedureAddress
0x1802bf7e7  mov     [rbp+Name.Buffer], rax
0x1802bf7eb  xor     r8d, r8d; Ordinal
0x1802bf7ee  mov     qword ptr [rbp+Name.Length], 0A0009h
0x1802bf7f6  lea     rdx, [rbp+Name]; Name
0x1802bf7fa  call    cs:__imp_LdrGetProcedureAddress
0x1802bf801  nop     dword ptr [rax+rax+00h]
0x1802bf806  mov     rcx, cs:?s_hRstrtMgr@RMContext@@2PEAUHINSTANCE__@@EA; BaseAddress
0x1802bf80d  lea     rax, aRmendsession; "RmEndSession"
0x1802bf814  lea     r9, [rdi+40h]; ProcedureAddress
0x1802bf818  mov     [rbp+Name.Buffer], rax
0x1802bf81c  xor     r8d, r8d; Ordinal
0x1802bf81f  mov     qword ptr [rbp+Name.Length], 0D000Ch
0x1802bf827  lea     rdx, [rbp+Name]; Name
0x1802bf82b  call    cs:__imp_LdrGetProcedureAddress
0x1802bf832  nop     dword ptr [rax+rax+00h]
0x1802bf837  cmp     [rdi+18h], rbx
0x1802bf83b  jz      short loc_1802BF85E
0x1802bf83d  cmp     [rdi+20h], rbx
0x1802bf841  jz      short loc_1802BF85E
0x1802bf843  cmp     [rdi+28h], rbx
0x1802bf847  jz      short loc_1802BF85E
0x1802bf849  cmp     [rdi+30h], rbx
0x1802bf84d  jz      short loc_1802BF85E
0x1802bf84f  cmp     [rdi+38h], rbx
0x1802bf853  jz      short loc_1802BF85E
0x1802bf855  cmp     [rdi+40h], rbx
0x1802bf859  jz      short loc_1802BF85E
0x1802bf85b  mov     byte ptr [rsi], 1
0x1802bf85e  cmp     [rsi], bl
0x1802bf860  jnz     short loc_1802BF87A
0x1802bf862  xor     r9d, r9d; char *
0x1802bf865  lea     r8, aUnableToSucces; "Unable to successfully initialize RMCon"...
0x1802bf86c  lea     rdx, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x1802bf873  xor     ecx, ecx; this
0x1802bf875  call    ?RtlTrace@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@123@QEBD_KZZ; Windows::WCP::Rtl::RtlTrace(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,...)
0x1802bf87a  xor     eax, eax
0x1802bf87c  jmp     short loc_1802BF8B4
0x1802bf87e  lea     rax, aOnecoreBaseWcp_33; "onecore\\base\\wcp\\poq\\RMHelper.h"
0x1802bf885  mov     [rbp+var_20], 98h
0x1802bf88d  mov     qword ptr [rbp+Name.Length], rax
0x1802bf891  lea     rdx, [rbp+Name]
0x1802bf895  lea     rax, aRmcontextIniti; "RMContext::Initialize"
0x1802bf89c  mov     [rbp+Name.Buffer], rax
0x1802bf8a0  lea     rcx, [rbp+var_10]
0x1802bf8a4  lea     rax, aMRmhandlesAllo; "m_RMHandles.Allocate(Capacity)"
0x1802bf8ab  mov     [rbp+var_18], rax
0x1802bf8af  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802bf8b4  mov     rcx, [rbp+var_8]
0x1802bf8b8  xor     rcx, rsp; StackCookie
0x1802bf8bb  call    __security_check_cookie
0x1802bf8c0  mov     rbx, [rsp+50h+arg_8]
0x1802bf8c8  add     rsp, 50h
0x1802bf8cc  pop     r15
0x1802bf8ce  pop     r14
0x1802bf8d0  pop     r13
0x1802bf8d2  pop     r12
0x1802bf8d4  pop     rdi
0x1802bf8d5  pop     rsi
0x1802bf8d6  pop     rbp
0x1802bf8d7  retn
```
