# Controller_WdfEvtDeviceD0EntryPostInterruptsEnabled

- ea: `0x140044260`
- end: `0x1400444b7`
- name: `Controller_WdfEvtDeviceD0EntryPostInterruptsEnabled`
- size: `599`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140004454`
- `0x140019410`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001b9a4`
- `0x14001ca48`
- `0x1400224d0`
- `0x140029168`
- `0x14003242c`
- `0x1400327a4`
- `0x140034404`
- `0x14003508c`
- `0x14003c1d4`
- `0x140044260`
- `0x1400599b0`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x140044350`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x140044350`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceD0EntryPostInterruptsEnabled(__int64 a1, unsigned int a2)
{
  __int64 v4; // rbx
  char v5; // r14
  int v6; // edx
  char PreProcessedSystemPowerAction; // bp
  int v8; // r8d
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  __int64 v12; // r8
  int v13; // edi
  int v14; // r9d
  __int64 v15; // rbp
  unsigned int i; // edi

  v4 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006C2C0)
                 + 8);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 3104))(WdfDriverGlobals, a1);
  PreProcessedSystemPowerAction = Controller_GetPreProcessedSystemPowerAction(v4);
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0pqqh_EtwWriteTransfer(
      *(unsigned __int8 *)(v4 + 868),
      (unsigned int)USBXHCI_ETW_EVENT_CONTROLLER_D0_ENTRY_POST_INTERRUPTS_START,
      v8,
      *(_QWORD *)(v4 + 8),
      a2,
      v5,
      *(_BYTE *)(v4 + 868));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qLLL(
      *(_QWORD *)(v4 + 72),
      v6,
      4,
      76,
      (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
      a1,
      a2,
      PreProcessedSystemPowerAction,
      v5);
  if ( *(_DWORD *)(v4 + 864) && *(_QWORD *)(v4 + 1296) )
    SleepstudyHelper_ComponentInactive();
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qd(
      *(_QWORD *)(v4 + 72),
      v6,
      4,
      126,
      (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids,
      v4,
      a2);
  }
  v9 = Controller_Start(v4);
  v13 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_23;
    v14 = 77;
    goto LABEL_13;
  }
  v15 = *(_QWORD *)(v4 + 152);
  for ( i = 1; i <= *(_DWORD *)(v15 + 16); ++i )
  {
    LOBYTE(v12) = 1;
    RootHub_DetectAndAcknowledgePortResume(v15, i, v12);
  }
  v9 = Command_D0EntryPostInterruptsEnabled(*(_QWORD *)(v4 + 144), a2);
  v13 = v9;
  if ( v9 >= 0 )
  {
    if ( (*(_BYTE *)(v4 + 736) & 0x10) != 0 )
    {
      v13 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(v4 + 72), v10, 4, 80, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
      }
    }
    else
    {
      Wmi_CreateControllerCapabilities(*(_QWORD *)(v4 + 160));
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 79;
LABEL_13:
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v4 + 72), v10, 4, v14, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v9);
  }
LABEL_23:
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 8) != 0 )
    McTemplateK0pqqq_EtwWriteTransfer(
      v11,
      (unsigned int)USBXHCI_ETW_EVENT_CONTROLLER_D0_ENTRY_POST_INTERRUPTS_COMPLETE,
      v12,
      *(_QWORD *)(v4 + 8),
      a2,
      v5,
      v13);
  if ( v13 < 0 )
    Etw_ReportFatalError(v11, v4, 0, 4145, v13, 0);
  Etw_ControllerRundown(0, v4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140044260  push    rbx
0x140044262  push    rbp
0x140044263  push    rsi
0x140044264  push    rdi
0x140044265  push    r12
0x140044267  push    r13
0x140044269  push    r14
0x14004426b  push    r15
0x14004426d  sub     rsp, 58h
0x140044271  mov     rax, cs:WdfFunctions_01033
0x140044278  mov     esi, edx
0x14004427a  mov     r8, cs:off_14006C2C0
0x140044281  mov     rdi, rcx
0x140044284  mov     rdx, rcx
0x140044287  mov     rcx, cs:WdfDriverGlobals
0x14004428e  mov     rax, [rax+650h]
0x140044295  call    _guard_dispatch_icall
0x14004429a  mov     rcx, cs:WdfDriverGlobals
0x1400442a1  mov     rdx, rdi
0x1400442a4  mov     rbx, [rax+8]
0x1400442a8  mov     rax, cs:WdfFunctions_01033
0x1400442af  mov     rax, [rax+0C20h]
0x1400442b6  call    _guard_dispatch_icall
0x1400442bb  mov     rcx, rbx
0x1400442be  mov     r14d, eax
0x1400442c1  call    Controller_GetPreProcessedSystemPowerAction
0x1400442c6  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x1400442cd  mov     ebp, eax
0x1400442cf  jz      short loc_1400442F6
0x1400442d1  movzx   ecx, byte ptr [rbx+364h]
0x1400442d8  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_D0_ENTRY_POST_INTERRUPTS_START
0x1400442df  mov     r9, [rbx+8]
0x1400442e3  mov     word ptr [rsp+98h+var_68], cx
0x1400442e8  mov     dword ptr [rsp+98h+var_70], r14d
0x1400442ed  mov     dword ptr [rsp+98h+var_78], esi
0x1400442f1  call    McTemplateK0pqqh_EtwWriteTransfer
0x1400442f6  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400442fd  mov     r12d, 4
0x140044303  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004430a  lea     r13, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140044311  jz      short loc_14004433B
0x140044313  mov     rcx, [rbx+48h]
0x140044317  lea     r9d, [r12+48h]
0x14004431c  mov     [rsp+98h+var_58], r14d
0x140044321  mov     r8d, r12d
0x140044324  mov     [rsp+98h+var_60], ebp
0x140044328  mov     [rsp+98h+var_68], esi
0x14004432c  mov     [rsp+98h+var_70], rdi
0x140044331  mov     [rsp+98h+var_78], r13
0x140044336  call    WPP_RECORDER_SF_qLLL
0x14004433b  cmp     dword ptr [rbx+360h], 0
0x140044342  jz      short loc_14004435C
0x140044344  mov     rcx, [rbx+510h]
0x14004434b  test    rcx, rcx
0x14004434e  jz      short loc_14004435C
0x140044350  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x140044357  nop     dword ptr [rax+rax+00h]
0x14004435c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140044363  jz      short loc_140044388
0x140044365  mov     rcx, [rbx+48h]
0x140044369  mov     r9d, 7Eh ; '~'
0x14004436f  mov     [rsp+98h+var_68], esi
0x140044373  mov     r8d, r12d
0x140044376  mov     [rsp+98h+var_70], rbx
0x14004437b  mov     dl, r12b
0x14004437e  mov     [rsp+98h+var_78], r13
0x140044383  call    WPP_RECORDER_SF_qd
0x140044388  mov     rcx, rbx
0x14004438b  call    Controller_Start
0x140044390  mov     edi, eax
0x140044392  test    eax, eax
0x140044394  jns     short loc_1400443C5
0x140044396  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004439d  jz      loc_14004444D
0x1400443a3  mov     r9d, 4Dh ; 'M'
0x1400443a9  mov     rcx, [rbx+48h]
0x1400443ad  mov     r8d, r12d
0x1400443b0  mov     dword ptr [rsp+98h+var_70], eax
0x1400443b4  mov     dl, 2
0x1400443b6  mov     [rsp+98h+var_78], r13
0x1400443bb  call    WPP_RECORDER_SF_d
0x1400443c0  jmp     loc_14004444D
0x1400443c5  mov     rbp, [rbx+98h]
0x1400443cc  mov     edi, 1
0x1400443d1  cmp     [rbp+10h], edi
0x1400443d4  jb      short loc_1400443EA
0x1400443d6  mov     r8b, 1
0x1400443d9  mov     edx, edi
0x1400443db  mov     rcx, rbp
0x1400443de  call    RootHub_DetectAndAcknowledgePortResume
0x1400443e3  inc     edi
0x1400443e5  cmp     edi, [rbp+10h]
0x1400443e8  jbe     short loc_1400443D6
0x1400443ea  mov     rcx, [rbx+90h]
0x1400443f1  mov     edx, esi
0x1400443f3  call    Command_D0EntryPostInterruptsEnabled
0x1400443f8  mov     edi, eax
0x1400443fa  test    eax, eax
0x1400443fc  jns     short loc_14004440F
0x1400443fe  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140044405  jz      short loc_14004444D
0x140044407  mov     r9d, 4Fh ; 'O'
0x14004440d  jmp     short loc_1400443A9
0x14004440f  test    byte ptr [rbx+2E0h], 10h
0x140044416  jz      short loc_140044441
0x140044418  mov     edi, 0C00000BBh
0x14004441d  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140044424  jz      short loc_14004444D
0x140044426  mov     rcx, [rbx+48h]
0x14004442a  mov     r9d, 50h ; 'P'
0x140044430  mov     r8d, r12d
0x140044433  mov     [rsp+98h+var_78], r13
0x140044438  mov     dl, 2
0x14004443a  call    WPP_RECORDER_SF_
0x14004443f  jmp     short loc_14004444D
0x140044441  mov     rcx, [rbx+0A0h]
0x140044448  call    Wmi_CreateControllerCapabilities
0x14004444d  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 8
0x140044454  jz      short loc_140044473
0x140044456  mov     r9, [rbx+8]
0x14004445a  lea     rdx, USBXHCI_ETW_EVENT_CONTROLLER_D0_ENTRY_POST_INTERRUPTS_COMPLETE
0x140044461  mov     [rsp+98h+var_68], edi
0x140044465  mov     dword ptr [rsp+98h+var_70], r14d
0x14004446a  mov     dword ptr [rsp+98h+var_78], esi
0x14004446e  call    McTemplateK0pqqq_EtwWriteTransfer
0x140044473  test    edi, edi
0x140044475  jns     short loc_140044499
0x140044477  movsxd  rax, edi
0x14004447a  mov     r9d, 1031h
0x140044480  mov     [rsp+98h+var_70], 0
0x140044489  xor     r8d, r8d
0x14004448c  mov     rdx, rbx
0x14004448f  mov     [rsp+98h+var_78], rax
0x140044494  call    Etw_ReportFatalError
0x140044499  mov     rdx, rbx
0x14004449c  xor     ecx, ecx
0x14004449e  call    Etw_ControllerRundown
0x1400444a3  mov     eax, edi
0x1400444a5  add     rsp, 58h
0x1400444a9  pop     r15
0x1400444ab  pop     r14
0x1400444ad  pop     r13
0x1400444af  pop     r12
0x1400444b1  pop     rdi
0x1400444b2  pop     rsi
0x1400444b3  pop     rbp
0x1400444b4  pop     rbx
0x1400444b5  retn
```
