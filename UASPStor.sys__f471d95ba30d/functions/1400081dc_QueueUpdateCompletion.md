# QueueUpdateCompletion

- ea: `0x1400081dc`
- end: `0x140008342`
- name: `QueueUpdateCompletion`
- size: `358`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007010`
- `0x1400072c0`
- `0x140008720`
- `0x14000a450`

## callees

- `0x140002070`
- `0x140004adc`
- `0x140007ee4`
- `0x1400081dc`
- `0x140009620`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400082f6`
- `ntoskrnl!KeSetEvent` at `0x1400082f6`
- `storport!StorPortNotification` at `0x14000831c`
- `storport!StorPortNotification` at `0x14000831c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008226`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000829a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008226`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000829a`

## pseudocode

```c
__int64 __fastcall QueueUpdateCompletion(_QWORD *a1)
{
  __int64 v1; // r15
  int Default; // eax
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  __int64 result; // rax
  bool v8; // zf
  char v9; // bl
  int v10; // eax
  int v11; // edx

  v1 = a1[4];
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    WPP_RECORDER_SF_PDddd(Default, v4, v5, v6);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)a1 + 6, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v8 = gTracingEnabled == 0;
    *(_QWORD *)((char *)a1 + 12) = 0;
    *((_DWORD *)a1 + 2) = 0;
    *((_DWORD *)a1 + 5) = 0;
    if ( !v8 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *(_BYTE *)(v1 + 3);
      v10 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_iD(v10, v11, 5, 14, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v1, v9);
    }
    if ( *(_BYTE *)(v1 + 3) == 1 )
      UaspPostProcessSrb(*a1, a1[4]);
    if ( *((_BYTE *)a1 + 200) )
    {
      KeSetEvent((PRKEVENT)a1[24], 0, 0);
      return QueueReleaseEntry(a1);
    }
    else
    {
      QueueReleaseEntry(a1);
      return StorPortNotification(0, *a1, v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400081dc  mov     [rsp+arg_8], rbx
0x1400081e1  mov     [rsp+arg_10], rbp
0x1400081e6  push    rsi
0x1400081e7  push    rdi
0x1400081e8  push    r13
0x1400081ea  push    r14
0x1400081ec  push    r15
0x1400081ee  sub     rsp, 50h
0x1400081f2  cmp     cs:gTracingEnabled, 0
0x1400081f9  lea     r13, WPP_RECORDER_INITIALIZED
0x140008200  mov     r15, [rcx+20h]
0x140008204  mov     r14, rcx
0x140008207  jz      short loc_14000824F
0x140008209  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140008210  jz      short loc_14000824F
0x140008212  mov     ebx, [rcx+10h]
0x140008215  mov     edi, [rcx+0Ch]
0x140008218  mov     esi, [rcx+8]
0x14000821b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008222  mov     ebp, [r15+0Ch]
0x140008226  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000822d  nop     dword ptr [rax+rax+00h]
0x140008232  mov     [rsp+78h+var_30], ebx
0x140008236  mov     rcx, rax
0x140008239  mov     [rsp+78h+var_38], edi
0x14000823d  mov     [rsp+78h+var_40], esi
0x140008241  mov     [rsp+78h+var_48], ebp
0x140008245  mov     [rsp+78h+var_50], r15
0x14000824a  call    WPP_RECORDER_SF_PDddd
0x14000824f  or      eax, 0FFFFFFFFh
0x140008252  lock xadd [r14+18h], eax
0x140008258  cmp     eax, 1
0x14000825b  jnz     loc_140008328
0x140008261  cmp     cs:gTracingEnabled, 0
0x140008268  mov     qword ptr [r14+0Ch], 0
0x140008270  mov     dword ptr [r14+8], 0
0x140008278  mov     dword ptr [r14+14h], 0
0x140008280  jz      short loc_1400082CD
0x140008282  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140008289  jz      short loc_1400082CD
0x14000828b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008292  lea     edi, [rax+0Dh]
0x140008295  movzx   ebx, byte ptr [r15+3]
0x14000829a  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400082a1  nop     dword ptr [rax+rax+00h]
0x1400082a6  mov     [rsp+78h+var_48], ebx
0x1400082aa  lea     r8d, [rdi-9]
0x1400082ae  mov     rcx, rax
0x1400082b1  mov     [rsp+78h+var_50], r15
0x1400082b6  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x1400082bd  movzx   r9d, di
0x1400082c1  mov     dl, 4
0x1400082c3  mov     [rsp+78h+var_58], rax
0x1400082c8  call    WPP_RECORDER_SF_iD
0x1400082cd  cmp     byte ptr [r15+3], 1
0x1400082d2  jnz     short loc_1400082E0
0x1400082d4  mov     rdx, [r14+20h]
0x1400082d8  mov     rcx, [r14]
0x1400082db  call    UaspPostProcessSrb
0x1400082e0  cmp     byte ptr [r14+0C8h], 0
0x1400082e8  jz      short loc_14000830C
0x1400082ea  mov     rcx, [r14+0C0h]; Event
0x1400082f1  xor     r8d, r8d; Wait
0x1400082f4  xor     edx, edx; Increment
0x1400082f6  call    cs:__imp_KeSetEvent
0x1400082fd  nop     dword ptr [rax+rax+00h]
0x140008302  mov     rcx, r14
0x140008305  call    QueueReleaseEntry
0x14000830a  jmp     short loc_140008328
0x14000830c  mov     rcx, r14
0x14000830f  call    QueueReleaseEntry
0x140008314  mov     rdx, [r14]
0x140008317  mov     r8, r15
0x14000831a  xor     ecx, ecx
0x14000831c  call    cs:__imp_StorPortNotification
0x140008323  nop     dword ptr [rax+rax+00h]
0x140008328  lea     r11, [rsp+78h+var_28]
0x14000832d  mov     rbx, [r11+38h]
0x140008331  mov     rbp, [r11+40h]
0x140008335  mov     rsp, r11
0x140008338  pop     r15
0x14000833a  pop     r14
0x14000833c  pop     r13
0x14000833e  pop     rdi
0x14000833f  pop     rsi
0x140008340  retn
```
