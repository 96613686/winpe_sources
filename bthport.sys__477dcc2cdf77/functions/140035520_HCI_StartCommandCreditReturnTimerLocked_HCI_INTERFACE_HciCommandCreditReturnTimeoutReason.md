# HCI_StartCommandCreditReturnTimerLocked(HCI_INTERFACE *,HciCommandCreditReturnTimeoutReason)

- ea: `0x140035520`
- end: `0x140035658`
- name: `?HCI_StartCommandCreditReturnTimerLocked@@YAXPEAUHCI_INTERFACE@@W4HciCommandCreditReturnTimeoutReason@@@Z`
- size: `312`
- prototype: `void __fastcall(struct HCI_INTERFACE *, enum HciCommandCreditReturnTimeoutReason)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140034a04`
- `0x140034ac4`
- `0x140034e48`

## callees

- `0x140005608`
- `0x140035520`
- `0x14015ce04`
- `0x14015ce38`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003563b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14003563b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400355f9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400355f9`
- `ntoskrnl!KeSetTimer` at `0x140035616`
- `ntoskrnl!KeSetTimer` at `0x140035616`

## string_xrefs

- `0x1400355d8`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`
- `0x14003553f`: `Unrecognized command credit timeout reason.`
- `0x1400355c5`: `Starting command credit return timer when command credits are still available.`

## pseudocode

```c
void __fastcall HCI_StartCommandCreditReturnTimerLocked(struct HCI_INTERFACE *a1, __int64 a2)
{
  HciCommandCreditReturnTimeoutReason v2; // edi
  LARGE_INTEGER v4; // rsi
  bool v5; // zf

  v2 = (int)a2;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
    {
      v4.QuadPart = -10000000;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredArgsMsgKM("bthport.sys", a2, 0, "Unrecognized command credit timeout reason.");
      v4.QuadPart = 0;
    }
  }
  else
  {
    v4.QuadPart = -300000000;
  }
  v5 = a1->CommandPacketsAllowed == 0;
  a1->CommandCreditReturnTimeoutReason = v2;
  if ( !v5 )
  {
    LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      1,
      a1->IfrLog,
      2,
      2,
      19,
      (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids);
    MicrosoftTelemetryAssertTriggeredMsgKM("Starting command credit return timer when command credits are still available.");
  }
  IoAcquireRemoveLockEx(
    &a1->DevExt->RemoveLock,
    HCI_StartCommandCreditReturnTimerLocked,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcicommand.cpp",
    0x606u,
    0x20u);
  if ( KeSetTimer(&a1->CommandCreditReturnTimer, v4, &a1->CommandCreditReturnTimerDpc) )
    IoReleaseRemoveLockEx(&a1->DevExt->RemoveLock, HCI_StartCommandCreditReturnTimerLocked, 0x20u);
}

```

## disassembly

```asm
0x140035520  mov     [rsp+arg_0], rbx
0x140035525  mov     [rsp+arg_8], rsi
0x14003552a  push    rdi
0x14003552b  sub     rsp, 40h
0x14003552f  mov     edi, edx
0x140035531  mov     rbx, rcx
0x140035534  mov     eax, edx
0x140035536  test    edx, edx
0x140035538  jz      short loc_140035562
0x14003553a  cmp     eax, 1
0x14003553d  jz      short loc_140035559
0x14003553f  lea     r9, aUnrecognizedCo; __annotation("Debug", "TelemetryAssert", "false", "Unrecognized command credit timeout reason.")
0x140035546  xor     r8d, r8d
0x140035549  lea     rcx, aBthportSys; "bthport.sys"
0x140035550  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140035555  xor     esi, esi
0x140035557  jmp     short loc_140035569
0x140035559  mov     rsi, 0FFFFFFFFFF676980h
0x140035560  jmp     short loc_140035569
0x140035562  mov     rsi, 0FFFFFFFFEE1E5D00h
0x140035569  cmp     byte ptr [rbx+0C32h], 0
0x140035570  mov     [rbx+0CB8h], edi
0x140035576  jz      short loc_1400355D1
0x140035578  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003557f  mov     eax, [rcx+2Ch]
0x140035582  test    al, 2
0x140035584  jz      short loc_140035590
0x140035586  cmp     byte ptr [rcx+29h], 2
0x14003558a  jb      short loc_140035590
0x14003558c  mov     dl, 1
0x14003558e  jmp     short loc_140035592
0x140035590  xor     dl, dl
0x140035592  mov     r9, [rbx+10B0h]
0x140035599  lea     rax, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x1400355a0  mov     rcx, [rcx+18h]
0x1400355a4  mov     r8b, 1
0x1400355a7  mov     [rsp+48h+var_10], rax
0x1400355ac  mov     [rsp+48h+var_18], 13h
0x1400355b3  mov     [rsp+48h+var_20], 2
0x1400355bb  mov     byte ptr [rsp+48h+RemlockSize], 2
0x1400355c0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400355c5  lea     rcx, aStartingComman; __annotation("Debug", "TelemetryAssert", "false", "Starting command credit return timer when command credits are still available.")
0x1400355cc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400355d1  mov     rcx, [rbx+4A8h]
0x1400355d8  lea     r8, aOnecoreDrivers_61; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400355df  mov     edi, 20h ; ' '
0x1400355e4  lea     rdx, ?HCI_StartCommandCreditReturnTimerLocked@@YAXPEAUHCI_INTERFACE@@W4HciCommandCreditReturnTimeoutReason@@@Z; Tag
0x1400355eb  add     rcx, 38h ; '8'; RemoveLock
0x1400355ef  mov     [rsp+48h+RemlockSize], edi; RemlockSize
0x1400355f3  mov     r9d, 606h; Line
0x1400355f9  call    cs:__imp_IoAcquireRemoveLockEx
0x140035600  nop     dword ptr [rax+rax+00h]
0x140035605  lea     r8, [rbx+0C78h]; Dpc
0x14003560c  mov     rdx, rsi; DueTime
0x14003560f  lea     rcx, [rbx+0C38h]; Timer
0x140035616  call    cs:__imp_KeSetTimer
0x14003561d  nop     dword ptr [rax+rax+00h]
0x140035622  test    al, al
0x140035624  jz      short loc_140035647
0x140035626  mov     rcx, [rbx+4A8h]
0x14003562d  lea     rdx, ?HCI_StartCommandCreditReturnTimerLocked@@YAXPEAUHCI_INTERFACE@@W4HciCommandCreditReturnTimeoutReason@@@Z; Tag
0x140035634  add     rcx, 38h ; '8'; RemoveLock
0x140035638  mov     r8d, edi; RemlockSize
0x14003563b  call    cs:__imp_IoReleaseRemoveLockEx
0x140035642  nop     dword ptr [rax+rax+00h]
0x140035647  mov     rbx, [rsp+48h+arg_0]
0x14003564c  mov     rsi, [rsp+48h+arg_8]
0x140035651  add     rsp, 40h
0x140035655  pop     rdi
0x140035656  retn
```
