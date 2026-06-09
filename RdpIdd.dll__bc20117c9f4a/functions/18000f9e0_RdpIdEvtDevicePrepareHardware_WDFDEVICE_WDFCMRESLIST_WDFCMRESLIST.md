# RdpIdEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)

- ea: `0x18000f9e0`
- end: `0x18000fb84`
- name: `?RdpIdEvtDevicePrepareHardware@@YAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z`
- size: `420`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, struct WDFCMRESLIST__ *, struct WDFCMRESLIST__ *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18000f9e0`
- `0x180017954`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb08`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fb48`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fb48`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RdpIdEvtDevicePrepareHardware(
        struct WDFDEVICE__ *a1,
        struct WDFCMRESLIST__ *a2,
        struct WDFCMRESLIST__ *a3)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  CRdpIdAdapter **v10; // rax
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  const char *v15; // r9
  __int64 result; // rax
  int v17; // [rsp+20h] [rbp-78h]
  int v18; // [rsp+28h] [rbp-70h]
  GUID ActivityId; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v17,
      v18,
      12,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  if ( byte_180057E4A )
    __debugbreak();
  try
  {
    v10 = (CRdpIdAdapter **)(*(__int64 (__fastcall **)(__int64, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_02025
                                                                                                + 984))(
                              WdfDriverGlobals,
                              a1,
                              off_180057078);
    CRdpIdAdapter::InitAdapter(*v10);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = GetCurrentThreadId();
      LOBYTE(v13) = v11;
      LOBYTE(v14) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v17,
        v18,
        13,
        &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
        v12);
    }
    EventActivityIdControl(2u, &ActivityId);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Nt_Return_CaughtException(
                           retaddr,
                           (void *)0xD1,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18000f9e0  mov     [rsp+arg_8], rbx
0x18000f9e5  mov     [rsp+arg_10], rsi
0x18000f9ea  push    rdi
0x18000f9eb  push    r12
0x18000f9ed  push    r13
0x18000f9ef  push    r14
0x18000f9f1  push    r15
0x18000f9f3  sub     rsp, 70h
0x18000f9f7  mov     rax, cs:__security_cookie
0x18000f9fe  xor     rax, rsp
0x18000fa01  mov     [rsp+98h+var_30], rax
0x18000fa06  mov     r15, rcx
0x18000fa09  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18000fa10  lea     rcx, [rsp+98h+ActivityId]; ActivityId
0x18000fa15  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000fa1a  nop
0x18000fa1b  lea     r12, WPP_GLOBAL_Control
0x18000fa22  mov     rax, cs:WPP_GLOBAL_Control
0x18000fa29  mov     bl, 1
0x18000fa2b  cmp     rax, r12
0x18000fa2e  jz      short loc_18000FA40
0x18000fa30  test    [rax+1Ch], bl
0x18000fa33  jz      short loc_18000FA40
0x18000fa35  cmp     byte ptr [rax+19h], 4
0x18000fa39  jb      short loc_18000FA40
0x18000fa3b  mov     dil, bl
0x18000fa3e  jmp     short loc_18000FA43
0x18000fa40  xor     dil, dil
0x18000fa43  lea     r13, WPP_RECORDER_INITIALIZED
0x18000fa4a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000fa51  setnz   sil
0x18000fa55  test    dil, dil
0x18000fa58  jnz     short loc_18000FA68
0x18000fa5a  test    sil, sil
0x18000fa5d  jnz     short loc_18000FA68
0x18000fa5f  lea     r14, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fa66  jmp     short loc_18000FAA5
0x18000fa68  call    cs:__imp_GetCurrentThreadId
0x18000fa6f  nop     dword ptr [rax+rax+00h]
0x18000fa74  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000fa78  lea     r14, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fa7f  mov     [rsp+98h+MessageGuid], r14; MessageGuid
0x18000fa84  mov     [rsp+98h+var_68], 0Ch; __int16
0x18000fa8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa92  mov     r9, [rcx+28h]; int
0x18000fa96  mov     r8b, sil; int
0x18000fa99  mov     dl, dil; int
0x18000fa9c  mov     rcx, [rcx+10h]; int
0x18000faa0  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000faa5  cmp     cs:byte_180057E4A, 0
0x18000faac  jz      short loc_18000FAAF
0x18000faae  int     3; Trap to Debugger
0x18000faaf  mov     rax, cs:WdfFunctions_02025
0x18000fab6  mov     r8, cs:off_180057078
0x18000fabd  mov     rdx, r15
0x18000fac0  mov     rcx, cs:WdfDriverGlobals
0x18000fac7  mov     rax, [rax+3D8h]
0x18000face  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad3  mov     rcx, [rax]; this
0x18000fad6  call    ?InitAdapter@CRdpIdAdapter@@QEAAXXZ; CRdpIdAdapter::InitAdapter(void)
0x18000fadb  mov     rax, cs:WPP_GLOBAL_Control
0x18000fae2  cmp     rax, r12
0x18000fae5  jz      short loc_18000FAF2
0x18000fae7  test    [rax+1Ch], bl
0x18000faea  jz      short loc_18000FAF2
0x18000faec  cmp     byte ptr [rax+19h], 4
0x18000faf0  jnb     short loc_18000FAF4
0x18000faf2  xor     bl, bl
0x18000faf4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000fafb  setnz   dil
0x18000faff  test    bl, bl
0x18000fb01  jnz     short loc_18000FB08
0x18000fb03  test    dil, dil
0x18000fb06  jz      short loc_18000FB3E
0x18000fb08  call    cs:__imp_GetCurrentThreadId
0x18000fb0f  nop     dword ptr [rax+rax+00h]
0x18000fb14  mov     dword ptr [rsp+98h+var_58], eax; char
0x18000fb18  mov     [rsp+98h+MessageGuid], r14; MessageGuid
0x18000fb1d  mov     [rsp+98h+var_68], 0Dh; __int16
0x18000fb24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb2b  mov     r9, [rcx+28h]; int
0x18000fb2f  mov     r8b, dil; int
0x18000fb32  mov     dl, bl; int
0x18000fb34  mov     rcx, [rcx+10h]; int
0x18000fb38  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000fb3d  nop
0x18000fb3e  lea     rdx, [rsp+98h+ActivityId]; ActivityId
0x18000fb43  mov     ecx, 2; ControlCode
0x18000fb48  call    cs:__imp_EventActivityIdControl
0x18000fb4f  nop     dword ptr [rax+rax+00h]
0x18000fb54  xor     eax, eax
0x18000fb56  jmp     short loc_18000FB5C
0x18000fb58  mov     eax, [rsp+98h+var_48]
0x18000fb5c  mov     rcx, [rsp+98h+var_30]
0x18000fb61  xor     rcx, rsp; StackCookie
0x18000fb64  call    __security_check_cookie
0x18000fb69  lea     r11, [rsp+98h+var_28]
0x18000fb6e  mov     rbx, [r11+38h]
0x18000fb72  mov     rsi, [r11+40h]
0x18000fb76  mov     rsp, r11
0x18000fb79  pop     r15
0x18000fb7b  pop     r14
0x18000fb7d  pop     r13
0x18000fb7f  pop     r12
0x18000fb81  pop     rdi
0x18000fb82  retn
```
