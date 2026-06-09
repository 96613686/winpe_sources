# RdpIdEvtDeviceReleaseHardware(WDFDEVICE__ *,WDFCMRESLIST__ *)

- ea: `0x18000fb90`
- end: `0x18000fdaf`
- name: `?RdpIdEvtDeviceReleaseHardware@@YAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, struct WDFCMRESLIST__ *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e8f4`
- `0x18000e978`
- `0x18000ebb4`
- `0x18000fb90`
- `0x18001d810`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fc1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd25`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fd70`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fd70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RdpIdEvtDeviceReleaseHardware(struct WDFDEVICE__ *a1, struct WDFCMRESLIST__ *a2)
{
  char v3; // bl
  bool v4; // di
  bool v5; // si
  char CurrentThreadId; // al
  int v7; // r8d
  int v8; // edx
  __int64 v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rdx
  bool v12; // di
  char v13; // al
  int v14; // r8d
  int v15; // edx
  int v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+28h] [rbp-80h]
  _BYTE v19[16]; // [rsp+58h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-40h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v3 = 1;
  v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v7) = v5;
    LOBYTE(v8) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v17,
      v18,
      14,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  if ( byte_180057E4B )
    __debugbreak();
  v9 = (*(__int64 (__fastcall **)(__int64, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         a1,
         off_180057078);
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v19,
    *(_QWORD *)(v9 + 24));
  CRdpIdAdapter::StopAdapter(*(CRdpIdAdapter **)v9);
  v10 = (*(__int64 (__fastcall **)(__int64, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_180057078);
  v11 = *(_QWORD *)(v10 + 16);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(WdfFunctions_02025 + 784))(WdfDriverGlobals, v11, 0, 0);
    *(_QWORD *)(v10 + 16) = 0;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v3 = 0;
  }
  v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = GetCurrentThreadId();
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v17,
      v18,
      15,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      v13);
  }
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v19);
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x18000fb90  mov     [rsp+arg_8], rbx
0x18000fb95  mov     [rsp+arg_10], rsi
0x18000fb9a  push    rdi
0x18000fb9b  push    r12
0x18000fb9d  push    r13
0x18000fb9f  push    r14
0x18000fba1  push    r15
0x18000fba3  sub     rsp, 80h
0x18000fbaa  mov     rax, cs:__security_cookie
0x18000fbb1  xor     rax, rsp
0x18000fbb4  mov     [rsp+0A8h+var_30], rax
0x18000fbb9  mov     r15, rcx
0x18000fbbc  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18000fbc3  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x18000fbc8  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000fbcd  nop
0x18000fbce  lea     r12, WPP_GLOBAL_Control
0x18000fbd5  mov     rax, cs:WPP_GLOBAL_Control
0x18000fbdc  mov     bl, 1
0x18000fbde  cmp     rax, r12
0x18000fbe1  jz      short loc_18000FBF3
0x18000fbe3  test    [rax+1Ch], bl
0x18000fbe6  jz      short loc_18000FBF3
0x18000fbe8  cmp     byte ptr [rax+19h], 4
0x18000fbec  jb      short loc_18000FBF3
0x18000fbee  mov     dil, bl
0x18000fbf1  jmp     short loc_18000FBF6
0x18000fbf3  xor     dil, dil
0x18000fbf6  lea     r13, WPP_RECORDER_INITIALIZED
0x18000fbfd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000fc04  setnz   sil
0x18000fc08  test    dil, dil
0x18000fc0b  jnz     short loc_18000FC1B
0x18000fc0d  test    sil, sil
0x18000fc10  jnz     short loc_18000FC1B
0x18000fc12  lea     r14, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fc19  jmp     short loc_18000FC58
0x18000fc1b  call    cs:__imp_GetCurrentThreadId
0x18000fc22  nop     dword ptr [rax+rax+00h]
0x18000fc27  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18000fc2b  lea     r14, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000fc32  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18000fc37  mov     [rsp+0A8h+var_78], 0Eh; __int16
0x18000fc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc45  mov     r9, [rcx+28h]; int
0x18000fc49  mov     r8b, sil; int
0x18000fc4c  mov     dl, dil; int
0x18000fc4f  mov     rcx, [rcx+10h]; int
0x18000fc53  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000fc58  cmp     cs:byte_180057E4B, 0
0x18000fc5f  jz      short loc_18000FC62
0x18000fc61  int     3; Trap to Debugger
0x18000fc62  mov     rax, cs:WdfFunctions_02025
0x18000fc69  mov     r8, cs:off_180057078
0x18000fc70  mov     rdx, r15
0x18000fc73  mov     rcx, cs:WdfDriverGlobals
0x18000fc7a  mov     rax, [rax+3D8h]
0x18000fc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc86  mov     rdi, rax
0x18000fc89  mov     rdx, [rax+18h]
0x18000fc8d  lea     rcx, [rsp+0A8h+var_50]
0x18000fc92  call    ??0?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &)
0x18000fc97  nop
0x18000fc98  mov     rcx, [rdi]; this
0x18000fc9b  call    ?StopAdapter@CRdpIdAdapter@@QEAAXXZ; CRdpIdAdapter::StopAdapter(void)
0x18000fca0  mov     rax, cs:WdfFunctions_02025
0x18000fca7  mov     r8, cs:off_180057078
0x18000fcae  mov     rdx, r15
0x18000fcb1  mov     rcx, cs:WdfDriverGlobals
0x18000fcb8  mov     rax, [rax+3D8h]
0x18000fcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc4  mov     rdi, rax
0x18000fcc7  mov     rdx, [rax+10h]
0x18000fccb  test    rdx, rdx
0x18000fcce  jz      short loc_18000FCF8
0x18000fcd0  mov     rcx, cs:WdfFunctions_02025
0x18000fcd7  mov     rax, [rcx+310h]
0x18000fcde  xor     r9d, r9d
0x18000fce1  xor     r8d, r8d
0x18000fce4  mov     rcx, cs:WdfDriverGlobals
0x18000fceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf0  mov     qword ptr [rdi+10h], 0
0x18000fcf8  mov     rax, cs:WPP_GLOBAL_Control
0x18000fcff  cmp     rax, r12
0x18000fd02  jz      short loc_18000FD0F
0x18000fd04  test    [rax+1Ch], bl
0x18000fd07  jz      short loc_18000FD0F
0x18000fd09  cmp     byte ptr [rax+19h], 4
0x18000fd0d  jnb     short loc_18000FD11
0x18000fd0f  xor     bl, bl
0x18000fd11  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000fd18  setnz   dil
0x18000fd1c  test    bl, bl
0x18000fd1e  jnz     short loc_18000FD25
0x18000fd20  test    dil, dil
0x18000fd23  jz      short loc_18000FD5B
0x18000fd25  call    cs:__imp_GetCurrentThreadId
0x18000fd2c  nop     dword ptr [rax+rax+00h]
0x18000fd31  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18000fd35  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18000fd3a  mov     [rsp+0A8h+var_78], 0Fh; __int16
0x18000fd41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd48  mov     r9, [rcx+28h]; int
0x18000fd4c  mov     r8b, dil; int
0x18000fd4f  mov     dl, bl; int
0x18000fd51  mov     rcx, [rcx+10h]; int
0x18000fd55  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000fd5a  nop
0x18000fd5b  lea     rcx, [rsp+0A8h+var_50]
0x18000fd60  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18000fd65  nop
0x18000fd66  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x18000fd6b  mov     ecx, 2; ControlCode
0x18000fd70  call    cs:__imp_EventActivityIdControl
0x18000fd77  nop     dword ptr [rax+rax+00h]
0x18000fd7c  xor     eax, eax
0x18000fd7e  jmp     short loc_18000FD84
0x18000fd80  mov     eax, [rsp+0A8h+var_58]
0x18000fd84  mov     rcx, [rsp+0A8h+var_30]
0x18000fd89  xor     rcx, rsp; StackCookie
0x18000fd8c  call    __security_check_cookie
0x18000fd91  lea     r11, [rsp+0A8h+var_28]
0x18000fd99  mov     rbx, [r11+38h]
0x18000fd9d  mov     rsi, [r11+40h]
0x18000fda1  mov     rsp, r11
0x18000fda4  pop     r15
0x18000fda6  pop     r14
0x18000fda8  pop     r13
0x18000fdaa  pop     r12
0x18000fdac  pop     rdi
0x18000fdad  retn
```
