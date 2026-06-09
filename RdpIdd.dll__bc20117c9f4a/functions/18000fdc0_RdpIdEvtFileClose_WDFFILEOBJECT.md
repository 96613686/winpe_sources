# RdpIdEvtFileClose(WDFFILEOBJECT__ *)

- ea: `0x18000fdc0`
- end: `0x18000ff9c`
- name: `?RdpIdEvtFileClose@@YAXPEAUWDFFILEOBJECT__@@@Z`
- size: `476`
- prototype: `void __fastcall(struct WDFFILEOBJECT__ *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18000fdc0`
- `0x180017b74`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff25`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ff66`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ff66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RdpIdEvtFileClose(struct WDFFILEOBJECT__ *a1)
{
  char v2; // di
  bool v3; // bl
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  struct RDPIDD_FILEOBJECT_CONTEXT *v8; // rbx
  __int64 v9; // rax
  CRdpIdAdapter **v10; // rax
  bool v11; // bl
  char v12; // al
  int v13; // r8d
  int v14; // edx
  const char *v15; // r9
  int v16; // [rsp+20h] [rbp-78h]
  int v17; // [rsp+28h] [rbp-70h]
  GUID ActivityId; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      18,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  try
  {
    v8 = (struct RDPIDD_FILEOBJECT_CONTEXT *)(*(__int64 (**)(void))(WdfFunctions_02025 + 984))();
    v9 = (*(__int64 (__fastcall **)(__int64, struct WDFFILEOBJECT__ *))(WdfFunctions_02025 + 552))(WdfDriverGlobals, a1);
    v10 = (CRdpIdAdapter **)(*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
                              WdfDriverGlobals,
                              v9,
                              off_180057078);
    CRdpIdAdapter::OnFileClosed(*v10, v8);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = GetCurrentThreadId();
      LOBYTE(v13) = v11;
      LOBYTE(v14) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        19,
        &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
        v12);
    }
    EventActivityIdControl(2u, &ActivityId);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp",
      v15);
  }
}

```

## disassembly

```asm
0x18000fdc0  mov     [rsp+arg_8], rbx
0x18000fdc5  mov     [rsp+arg_10], rsi
0x18000fdca  push    rdi
0x18000fdcb  push    r12
0x18000fdcd  push    r13
0x18000fdcf  push    r14
0x18000fdd1  push    r15
0x18000fdd3  sub     rsp, 70h
0x18000fdd7  mov     rax, cs:__security_cookie
0x18000fdde  xor     rax, rsp
0x18000fde1  mov     [rsp+98h+var_38], rax
0x18000fde6  mov     r15, rcx
0x18000fde9  lea     r12, WPP_GLOBAL_Control
0x18000fdf0  mov     rax, cs:WPP_GLOBAL_Control
0x18000fdf7  mov     dil, 1
0x18000fdfa  cmp     rax, r12
0x18000fdfd  jz      short loc_18000FE10
0x18000fdff  test    [rax+1Ch], dil
0x18000fe03  jz      short loc_18000FE10
0x18000fe05  cmp     byte ptr [rax+19h], 4
0x18000fe09  jb      short loc_18000FE10
0x18000fe0b  mov     bl, dil
0x18000fe0e  jmp     short loc_18000FE12
0x18000fe10  xor     bl, bl
0x18000fe12  lea     r13, WPP_RECORDER_INITIALIZED
0x18000fe19  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000fe20  setnz   r14b
0x18000fe24  test    bl, bl
0x18000fe26  jnz     short loc_18000FE36
0x18000fe28  test    r14b, r14b
0x18000fe2b  jnz     short loc_18000FE36
0x18000fe2d  lea     rsi, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fe34  jmp     short loc_18000FE72
0x18000fe36  call    cs:__imp_GetCurrentThreadId
0x18000fe3d  nop     dword ptr [rax+rax+00h]
0x18000fe42  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000fe46  lea     rsi, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fe4d  mov     [rsp+98h+MessageGuid], rsi; MessageGuid
0x18000fe52  mov     [rsp+98h+var_68], 12h; __int16
0x18000fe59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe60  mov     r9, [rcx+28h]; int
0x18000fe64  mov     r8b, r14b; int
0x18000fe67  mov     dl, bl; int
0x18000fe69  mov     rcx, [rcx+10h]; int
0x18000fe6d  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000fe72  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18000fe79  lea     rcx, [rsp+98h+ActivityId]; ActivityId
0x18000fe7e  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000fe83  nop
0x18000fe84  mov     rax, cs:WdfFunctions_02025
0x18000fe8b  mov     r8, cs:off_180057020
0x18000fe92  mov     rdx, r15
0x18000fe95  mov     rcx, cs:WdfDriverGlobals
0x18000fe9c  mov     rax, [rax+3D8h]
0x18000fea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fea8  mov     rbx, rax
0x18000feab  mov     rcx, cs:WdfFunctions_02025
0x18000feb2  mov     rax, [rcx+228h]
0x18000feb9  mov     rdx, r15
0x18000febc  mov     rcx, cs:WdfDriverGlobals
0x18000fec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec8  mov     rdx, rax
0x18000fecb  mov     rcx, cs:WdfFunctions_02025
0x18000fed2  mov     rax, [rcx+3D8h]
0x18000fed9  mov     r8, cs:off_180057078
0x18000fee0  mov     rcx, cs:WdfDriverGlobals
0x18000fee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feec  mov     rdx, rbx; struct RDPIDD_FILEOBJECT_CONTEXT *
0x18000feef  mov     rcx, [rax]; this
0x18000fef2  call    ?OnFileClosed@CRdpIdAdapter@@QEAAXPEAURDPIDD_FILEOBJECT_CONTEXT@@@Z; CRdpIdAdapter::OnFileClosed(RDPIDD_FILEOBJECT_CONTEXT *)
0x18000fef7  mov     rax, cs:WPP_GLOBAL_Control
0x18000fefe  cmp     rax, r12
0x18000ff01  jz      short loc_18000FF0F
0x18000ff03  test    [rax+1Ch], dil
0x18000ff07  jz      short loc_18000FF0F
0x18000ff09  cmp     byte ptr [rax+19h], 4
0x18000ff0d  jnb     short loc_18000FF12
0x18000ff0f  xor     dil, dil
0x18000ff12  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000ff19  setnz   bl
0x18000ff1c  test    dil, dil
0x18000ff1f  jnz     short loc_18000FF25
0x18000ff21  test    bl, bl
0x18000ff23  jz      short loc_18000FF5C
0x18000ff25  call    cs:__imp_GetCurrentThreadId
0x18000ff2c  nop     dword ptr [rax+rax+00h]
0x18000ff31  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000ff35  mov     [rsp+98h+MessageGuid], rsi; MessageGuid
0x18000ff3a  mov     [rsp+98h+var_68], 13h; __int16
0x18000ff41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff48  mov     r9, [rcx+28h]; int
0x18000ff4c  mov     r8b, bl; int
0x18000ff4f  mov     dl, dil; int
0x18000ff52  mov     rcx, [rcx+10h]; int
0x18000ff56  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000ff5b  nop
0x18000ff5c  lea     rdx, [rsp+98h+ActivityId]; ActivityId
0x18000ff61  mov     ecx, 2; ControlCode
0x18000ff66  call    cs:__imp_EventActivityIdControl
0x18000ff6d  nop     dword ptr [rax+rax+00h]
0x18000ff72  jmp     short $+2
0x18000ff74  mov     rcx, [rsp+98h+var_38]
0x18000ff79  xor     rcx, rsp; StackCookie
0x18000ff7c  call    __security_check_cookie
0x18000ff81  lea     r11, [rsp+98h+var_28]
0x18000ff86  mov     rbx, [r11+38h]
0x18000ff8a  mov     rsi, [r11+40h]
0x18000ff8e  mov     rsp, r11
0x18000ff91  pop     r15
0x18000ff93  pop     r14
0x18000ff95  pop     r13
0x18000ff97  pop     r12
0x18000ff99  pop     rdi
0x18000ff9a  retn
```
