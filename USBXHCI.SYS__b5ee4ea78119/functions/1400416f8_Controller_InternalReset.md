# Controller_InternalReset

- ea: `0x1400416f8`
- end: `0x140041c05`
- name: `Controller_InternalReset`
- size: `1293`
- prototype: ``
- caller_count: `3`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x14003c354`
- `0x14004132c`
- `0x140043660`

## callees

- `0x14000c264`
- `0x14001795c`
- `0x140017adc`
- `0x140019828`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001b3b8`
- `0x14001bd04`
- `0x14001ca48`
- `0x14001cf48`
- `0x14001fb30`
- `0x1400218a0`
- `0x1400219b0`
- `0x14002792c`
- `0x14002b300`
- `0x14002e028`
- `0x14002e9b0`
- `0x140033bcc`
- `0x140035d64`
- `0x14003d1f8`
- `0x14003d8a4`
- `0x14003d970`
- `0x140040eb4`
- `0x1400416f8`
- `0x14004620c`
- `0x140049644`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140041778`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140041778`

## string_xrefs

- `0x140041977`: `During controller reset recovery, controller stop timed out`
- `0x140041a5e`: `During controller reset recovery, controller reset timed out`
- `0x140041af9`: `During controller reset recovery, controller start timed out`

## pseudocode

```c
__int64 __fastcall Controller_InternalReset(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r14
  unsigned int i; // esi
  __int64 v8; // rbp
  __int64 j; // rbx
  __int64 v10; // rcx
  __int64 v11; // rbx
  int v12; // edx
  int v13; // esi
  int v14; // eax
  int v15; // edx
  int v16; // edx
  __int64 v17; // rbx
  int v18; // edx
  unsigned int k; // ebp
  __int64 v20; // rcx
  int v21; // eax
  int v22; // edx
  _QWORD *v23; // rsi
  __int64 result; // rax
  int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // r8

  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 2) != 0 )
    McTemplateK0p_EtwWriteTransfer(a1, USBXHCI_ETW_EVENT_CONTROLLER_INTERNAL_RESET_START, a3, *(_QWORD *)(a1 + 8));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 196, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 816)) != 1 && !KdRefreshDebuggerNotPresent() )
    __debugbreak();
  _InterlockedAdd((volatile signed __int32 *)(a1 + 804), 1u);
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1308), 0, 1)
    && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1304), 0, 0) )
  {
    ++*(_DWORD *)(a1 + 876);
    ++*(_DWORD *)(a1 + 944);
    *(_BYTE *)(a1 + 872) = 1;
    _InterlockedAdd((volatile signed __int32 *)(a1 + 808), 1u);
  }
  LOBYTE(a3) = 1;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01033 + 2560))(
    WdfDriverGlobals,
    *(_QWORD *)(a1 + 760),
    a3);
  v4 = *(_QWORD *)(a1 + 144);
  DynamicLock_Acquire(*(_QWORD *)(v4 + 112));
  v5 = *(_QWORD *)(v4 + 112);
  *(_DWORD *)(v4 + 36) = 3;
  *(_BYTE *)(v4 + 121) = 0;
  DynamicLock_Release(v5);
  v6 = *(_QWORD *)(a1 + 136);
  for ( i = 1; i <= *(_DWORD *)(v6 + 96); ++i )
  {
    v8 = *(_QWORD *)(XilDeviceSlot_GetUsbDeviceHandleArray(v6) + 8LL * i);
    if ( v8 )
    {
      for ( j = 1; j != 32; ++j )
      {
        v10 = *(_QWORD *)(v8 + 8 * j + 176);
        if ( v10 )
          ESM_AddEsmEvent(v10, 15);
      }
    }
  }
  Interrupter_FlushPendingDpcOrWorkItemPreReset(*(_QWORD *)(a1 + 128));
  v11 = (int)Register_ControllerStop(*(_QWORD *)(a1 + 88));
  Interrupter_FlushPendingDpcOrWorkItemPreReset(*(_QWORD *)(a1 + 128));
  if ( (int)v11 >= 0 )
  {
    v14 = Register_ControllerReset(*(_QWORD *)(a1 + 88), 1);
    v13 = v14;
    if ( v14 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 72),
        v15,
        4,
        198,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v14);
    }
  }
  else
  {
    v13 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 72),
        v12,
        4,
        197,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v11);
    }
    Controller_DisableController(a1);
  }
  Command_ControllerResetPostReset(*(_QWORD *)(a1 + 144));
  if ( *(_QWORD *)(a1 + 120) )
    CommonBuffer_FlushWorkItems();
  DeviceSlot_ControllerResetPostReset(*(_QWORD *)(a1 + 136));
  RootHub_D0Entry(*(_QWORD *)(a1 + 152));
  if ( (int)v11 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 72),
        v16,
        4,
        199,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v11);
    }
    Controller_HwVerifierBreakIfEnabled(
      a1,
      0,
      0,
      8,
      (__int64)"During controller reset recovery, controller stop timed out",
      0,
      0);
    Controller_ReportFatalErrorEx(a1, 4, 4107, 0, v11, 0, 0, 0);
LABEL_45:
    Command_FailAllCommands(*(_QWORD *)(a1 + 144));
    v23 = (_QWORD *)(a1 + 8);
    result = ((__int64 (__fastcall *)(__int64, _QWORD))qword_14006CCE0)(UcxDriverGlobals, *(_QWORD *)(a1 + 8));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = 2;
      result = WPP_RECORDER_SF_d(
                 *(_QWORD *)(a1 + 72),
                 v25,
                 4,
                 203,
                 (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
                 v11);
    }
    goto LABEL_50;
  }
  v17 = *(_QWORD *)(a1 + 128);
  if ( (unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(v17 + 8)) )
  {
    Interrupter_Initialize(v17);
    Interrupter_InterrupterRegisterIntialize(v17);
    for ( k = 0; k < *(_DWORD *)(v17 + 92); ++k )
    {
      v20 = *(_QWORD *)(*(_QWORD *)(v17 + 32) + 8LL * k);
      if ( v20 )
      {
        *(_DWORD *)(v20 + 112) &= ~0x10u;
        if ( (*(_DWORD *)(v20 + 112) & 4) != 0 )
          Interrupter_InterruptEnable();
      }
    }
  }
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 72),
        v18,
        4,
        200,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v13);
    }
    Controller_HwVerifierBreakIfEnabled(
      a1,
      0,
      0,
      16,
      (__int64)"During controller reset recovery, controller reset timed out",
      0,
      0);
    Controller_ReportFatalErrorEx(a1, 4, 4103, 0, v13, 0, 0, 0);
    LODWORD(v11) = v13;
    goto LABEL_45;
  }
  v21 = Controller_Start(a1);
  v11 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 72),
        v22,
        4,
        201,
        (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
        v21);
    }
    Controller_HwVerifierBreakIfEnabled(
      a1,
      0,
      0,
      32,
      (__int64)"During controller reset recovery, controller start timed out",
      0,
      0);
    Controller_ReportFatalErrorEx(a1, 4, 4104, 0, v11, 0, 0, 0);
    goto LABEL_45;
  }
  result = Command_ControllerResetPostResetSuccess(*(_QWORD *)(a1 + 144));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    result = WPP_RECORDER_SF_(*(_QWORD *)(a1 + 72), 4, 4, 202, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
  v23 = (_QWORD *)(a1 + 8);
  LODWORD(v11) = 0;
LABEL_50:
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 2) != 0 )
    result = McTemplateK0pq_EtwWriteTransfer(v26, USBXHCI_ETW_EVENT_CONTROLLER_INTERNAL_RESET_COMPLETE, v27, *v23, v11);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 816));
  return result;
}

```

## disassembly

```asm
0x1400416f8  push    rbx
0x1400416fa  push    rbp
0x1400416fb  push    rsi
0x1400416fc  push    rdi
0x1400416fd  push    r12
0x1400416ff  push    r13
0x140041701  push    r14
0x140041703  push    r15
0x140041705  sub     rsp, 48h
0x140041709  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 2
0x140041710  mov     rdi, rcx
0x140041713  jz      short loc_140041725
0x140041715  mov     r9, [rcx+8]
0x140041719  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_INTERNAL_RESET_START
0x140041720  call    McTemplateK0p_EtwWriteTransfer
0x140041725  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004172c  mov     r13d, 4
0x140041732  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041739  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041740  jz      short loc_14004175C
0x140041742  mov     rcx, [rdi+48h]
0x140041746  mov     r9d, 0C4h
0x14004174c  mov     r8d, r13d
0x14004174f  mov     [rsp+88h+var_68], rbp
0x140041754  mov     dl, r13b
0x140041757  call    WPP_RECORDER_SF_
0x14004175c  mov     r12d, 1
0x140041762  mov     eax, r12d
0x140041765  lock xadd [rdi+330h], eax
0x14004176d  add     eax, r12d
0x140041770  xor     r15d, r15d
0x140041773  cmp     eax, r12d
0x140041776  jz      short loc_140041789
0x140041778  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14004177f  nop     dword ptr [rax+rax+00h]
0x140041784  test    al, al
0x140041786  jnz     short loc_140041789
0x140041788  int     3; Trap to Debugger
0x140041789  lock add [rdi+324h], r12d
0x140041791  mov     ecx, r15d
0x140041794  mov     eax, r12d
0x140041797  lock cmpxchg [rdi+51Ch], ecx
0x14004179f  test    eax, eax
0x1400417a1  jnz     short loc_1400417CA
0x1400417a3  lock cmpxchg [rdi+518h], ecx
0x1400417ab  jnz     short loc_1400417CA
0x1400417ad  add     [rdi+36Ch], r12d
0x1400417b4  add     [rdi+3B0h], r12d
0x1400417bb  mov     [rdi+368h], r12b
0x1400417c2  lock add [rdi+328h], r12d
0x1400417ca  mov     rax, cs:WdfFunctions_01033
0x1400417d1  mov     r8b, r12b
0x1400417d4  mov     rdx, [rdi+2F8h]
0x1400417db  mov     rcx, cs:WdfDriverGlobals
0x1400417e2  mov     rax, [rax+0A00h]
0x1400417e9  call    _guard_dispatch_icall
0x1400417ee  mov     rbx, [rdi+90h]
0x1400417f5  mov     rcx, [rbx+70h]
0x1400417f9  call    DynamicLock_Acquire
0x1400417fe  mov     rcx, [rbx+70h]
0x140041802  mov     dword ptr [rbx+24h], 3
0x140041809  mov     [rbx+79h], r15b
0x14004180d  call    DynamicLock_Release
0x140041812  mov     r14, [rdi+88h]
0x140041819  mov     esi, r12d
0x14004181c  cmp     [r14+60h], r12d
0x140041820  jb      short loc_140041868
0x140041822  mov     rcx, r14
0x140041825  call    XilDeviceSlot_GetUsbDeviceHandleArray
0x14004182a  mov     ecx, esi
0x14004182c  mov     rbp, [rax+rcx*8]
0x140041830  test    rbp, rbp
0x140041833  jz      short loc_140041858
0x140041835  mov     rbx, r12
0x140041838  mov     rcx, [rbp+rbx*8+0B0h]
0x140041840  test    rcx, rcx
0x140041843  jz      short loc_14004184F
0x140041845  mov     edx, 0Fh
0x14004184a  call    ESM_AddEsmEvent
0x14004184f  add     rbx, r12
0x140041852  cmp     rbx, 20h ; ' '
0x140041856  jnz     short loc_140041838
0x140041858  add     esi, r12d
0x14004185b  cmp     esi, [r14+60h]
0x14004185f  jbe     short loc_140041822
0x140041861  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041868  mov     rcx, [rdi+80h]
0x14004186f  call    Interrupter_FlushPendingDpcOrWorkItemPreReset
0x140041874  mov     rcx, [rdi+58h]
0x140041878  call    Register_ControllerStop
0x14004187d  mov     rcx, [rdi+80h]
0x140041884  movsxd  rbx, eax
0x140041887  call    Interrupter_FlushPendingDpcOrWorkItemPreReset
0x14004188c  test    ebx, ebx
0x14004188e  jns     short loc_1400418CA
0x140041890  mov     esi, r15d
0x140041893  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004189a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400418a1  jz      short loc_1400418C0
0x1400418a3  mov     rcx, [rdi+48h]
0x1400418a7  mov     r9d, 0C5h
0x1400418ad  mov     dword ptr [rsp+88h+var_60], ebx
0x1400418b1  mov     r8d, r13d
0x1400418b4  mov     dl, 2
0x1400418b6  mov     [rsp+88h+var_68], rbp
0x1400418bb  call    WPP_RECORDER_SF_d
0x1400418c0  mov     rcx, rdi
0x1400418c3  call    Controller_DisableController
0x1400418c8  jmp     short loc_140041912
0x1400418ca  mov     rcx, [rdi+58h]
0x1400418ce  mov     dl, r12b
0x1400418d1  call    Register_ControllerReset
0x1400418d6  mov     esi, eax
0x1400418d8  test    eax, eax
0x1400418da  jns     short loc_14004190B
0x1400418dc  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400418e3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400418ea  jz      short loc_140041912
0x1400418ec  mov     rcx, [rdi+48h]
0x1400418f0  mov     r9d, 0C6h
0x1400418f6  mov     dword ptr [rsp+88h+var_60], eax
0x1400418fa  mov     r8d, r13d
0x1400418fd  mov     dl, 2
0x1400418ff  mov     [rsp+88h+var_68], rbp
0x140041904  call    WPP_RECORDER_SF_d
0x140041909  jmp     short loc_140041912
0x14004190b  lea     r14, WPP_RECORDER_INITIALIZED
0x140041912  mov     rcx, [rdi+90h]
0x140041919  call    Command_ControllerResetPostReset
0x14004191e  mov     rcx, [rdi+78h]
0x140041922  test    rcx, rcx
0x140041925  jz      short loc_14004192C
0x140041927  call    CommonBuffer_FlushWorkItems
0x14004192c  mov     rcx, [rdi+88h]
0x140041933  call    DeviceSlot_ControllerResetPostReset
0x140041938  mov     rcx, [rdi+98h]
0x14004193f  call    RootHub_D0Entry
0x140041944  test    ebx, ebx
0x140041946  jns     loc_1400419CF
0x14004194c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140041953  jz      short loc_140041972
0x140041955  mov     rcx, [rdi+48h]
0x140041959  mov     r9d, 0C7h
0x14004195f  mov     dword ptr [rsp+88h+var_60], ebx
0x140041963  mov     r8d, r13d
0x140041966  mov     dl, 2
0x140041968  mov     [rsp+88h+var_68], rbp
0x14004196d  call    WPP_RECORDER_SF_d
0x140041972  mov     [rsp+88h+var_58], r15
0x140041977  lea     rax, aDuringControll_0; "During controller reset recovery, contr"...
0x14004197e  mov     [rsp+88h+var_60], r15
0x140041983  mov     r9d, 8
0x140041989  xor     r8d, r8d
0x14004198c  mov     [rsp+88h+var_68], rax
0x140041991  xor     edx, edx
0x140041993  mov     rcx, rdi
0x140041996  call    Controller_HwVerifierBreakIfEnabled
0x14004199b  mov     [rsp+88h+var_50], r15
0x1400419a0  xor     r9d, r9d
0x1400419a3  mov     [rsp+88h+var_58], r15
0x1400419a8  mov     r8d, 100Bh
0x1400419ae  mov     [rsp+88h+var_60], r15
0x1400419b3  mov     edx, r13d
0x1400419b6  mov     rcx, rdi
0x1400419b9  mov     [rsp+88h+var_68], rbx
0x1400419be  call    Controller_ReportFatalErrorEx
0x1400419c3  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400419ca  jmp     loc_140041B45
0x1400419cf  mov     rbx, [rdi+80h]
0x1400419d6  mov     rcx, [rbx+8]
0x1400419da  call    Controller_IsControllerAccessible
0x1400419df  test    al, al
0x1400419e1  jz      short loc_140041A24
0x1400419e3  mov     rcx, rbx
0x1400419e6  call    Interrupter_Initialize
0x1400419eb  mov     rcx, rbx
0x1400419ee  call    Interrupter_InterrupterRegisterIntialize
0x1400419f3  mov     ebp, r15d
0x1400419f6  cmp     [rbx+5Ch], r15d
0x1400419fa  jbe     short loc_140041A24
0x1400419fc  mov     rax, [rbx+20h]
0x140041a00  mov     ecx, ebp
0x140041a02  mov     rcx, [rax+rcx*8]
0x140041a06  test    rcx, rcx
0x140041a09  jz      short loc_140041A1C
0x140041a0b  and     dword ptr [rcx+70h], 0FFFFFFEFh
0x140041a0f  mov     eax, [rcx+70h]
0x140041a12  test    r13b, al
0x140041a15  jz      short loc_140041A1C
0x140041a17  call    Interrupter_InterruptEnable
0x140041a1c  add     ebp, r12d
0x140041a1f  cmp     ebp, [rbx+5Ch]
0x140041a22  jb      short loc_1400419FC
0x140041a24  test    esi, esi
0x140041a26  jns     loc_140041AB4
0x140041a2c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140041a33  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041a3a  jz      short loc_140041A59
0x140041a3c  mov     rcx, [rdi+48h]
0x140041a40  mov     r9d, 0C8h
0x140041a46  mov     dword ptr [rsp+88h+var_60], esi
0x140041a4a  mov     r8d, r13d
0x140041a4d  mov     dl, 2
0x140041a4f  mov     [rsp+88h+var_68], rbp
0x140041a54  call    WPP_RECORDER_SF_d
0x140041a59  mov     [rsp+88h+var_58], r15
0x140041a5e  lea     rax, aDuringControll_1; "During controller reset recovery, contr"...
0x140041a65  mov     [rsp+88h+var_60], r15
0x140041a6a  mov     r9d, 10h
0x140041a70  xor     r8d, r8d
0x140041a73  mov     [rsp+88h+var_68], rax
0x140041a78  xor     edx, edx
0x140041a7a  mov     rcx, rdi
0x140041a7d  call    Controller_HwVerifierBreakIfEnabled
0x140041a82  mov     [rsp+88h+var_50], r15
0x140041a87  xor     r9d, r9d
0x140041a8a  movsxd  rax, esi
0x140041a8d  mov     r8d, 1007h
0x140041a93  mov     [rsp+88h+var_58], r15
0x140041a98  mov     edx, r13d
0x140041a9b  mov     [rsp+88h+var_60], r15
0x140041aa0  mov     rcx, rdi
0x140041aa3  mov     [rsp+88h+var_68], rax
0x140041aa8  call    Controller_ReportFatalErrorEx
0x140041aad  mov     ebx, esi
0x140041aaf  jmp     loc_140041B45
0x140041ab4  mov     rcx, rdi
0x140041ab7  call    Controller_Start
0x140041abc  movsxd  rbx, eax
0x140041abf  test    eax, eax
0x140041ac1  jns     loc_140041B93
0x140041ac7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140041ace  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041ad5  jz      short loc_140041AF4
0x140041ad7  mov     rcx, [rdi+48h]
0x140041adb  mov     r9d, 0C9h
0x140041ae1  mov     dword ptr [rsp+88h+var_60], ebx
0x140041ae5  mov     r8d, r13d
0x140041ae8  mov     dl, 2
0x140041aea  mov     [rsp+88h+var_68], rbp
0x140041aef  call    WPP_RECORDER_SF_d
0x140041af4  mov     [rsp+88h+var_58], r15
0x140041af9  lea     rax, aDuringControll; "During controller reset recovery, contr"...
0x140041b00  mov     [rsp+88h+var_60], r15
0x140041b05  mov     r9d, 20h ; ' '
0x140041b0b  xor     r8d, r8d
0x140041b0e  mov     [rsp+88h+var_68], rax
0x140041b13  xor     edx, edx
0x140041b15  mov     rcx, rdi
0x140041b18  call    Controller_HwVerifierBreakIfEnabled
0x140041b1d  mov     [rsp+88h+var_50], r15
0x140041b22  xor     r9d, r9d
0x140041b25  mov     [rsp+88h+var_58], r15
0x140041b2a  mov     r8d, 1008h
0x140041b30  mov     [rsp+88h+var_60], r15
0x140041b35  mov     edx, r13d
0x140041b38  mov     rcx, rdi
0x140041b3b  mov     [rsp+88h+var_68], rbx
0x140041b40  call    Controller_ReportFatalErrorEx
0x140041b45  mov     rcx, [rdi+90h]
0x140041b4c  call    Command_FailAllCommands
0x140041b51  mov     rax, cs:qword_14006CCE0
0x140041b58  lea     rsi, [rdi+8]
0x140041b5c  mov     rdx, [rsi]
0x140041b5f  mov     rcx, cs:UcxDriverGlobals
0x140041b66  call    _guard_dispatch_icall
0x140041b6b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140041b72  jz      short loc_140041BD0
0x140041b74  mov     rcx, [rdi+48h]
0x140041b78  mov     r9d, 0CBh
0x140041b7e  mov     dword ptr [rsp+88h+var_60], ebx
0x140041b82  mov     r8d, r13d
0x140041b85  mov     dl, 2
0x140041b87  mov     [rsp+88h+var_68], rbp
0x140041b8c  call    WPP_RECORDER_SF_d
0x140041b91  jmp     short loc_140041BD0
0x140041b93  mov     rcx, [rdi+90h]
0x140041b9a  call    Command_ControllerResetPostResetSuccess
0x140041b9f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140041ba6  jz      short loc_140041BC9
0x140041ba8  mov     rcx, [rdi+48h]
0x140041bac  lea     rbp, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041bb3  mov     r9d, 0CAh
0x140041bb9  mov     [rsp+88h+var_68], rbp
0x140041bbe  mov     r8d, r13d
0x140041bc1  mov     dl, r13b
0x140041bc4  call    WPP_RECORDER_SF_
0x140041bc9  lea     rsi, [rdi+8]
0x140041bcd  mov     ebx, r15d
0x140041bd0  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 2
0x140041bd7  jz      short loc_140041BEC
0x140041bd9  mov     r9, [rsi]
0x140041bdc  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_INTERNAL_RESET_COMPLETE
0x140041be3  mov     dword ptr [rsp+88h+var_68], ebx
0x140041be7  call    McTemplateK0pq_EtwWriteTransfer
0x140041bec  lock dec dword ptr [rdi+330h]
0x140041bf3  add     rsp, 48h
0x140041bf7  pop     r15
0x140041bf9  pop     r14
0x140041bfb  pop     r13
  ... truncated ...
```
