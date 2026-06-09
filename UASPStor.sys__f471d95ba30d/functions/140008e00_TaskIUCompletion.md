# TaskIUCompletion

- ea: `0x140008e00`
- end: `0x140009092`
- name: `TaskIUCompletion`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140002964`
- `0x140005744`
- `0x140008348`
- `0x140008e00`
- `0x140009098`
- `0x1400092ec`
- `0x1400093e8`
- `0x1400098a0`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008e89`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008ee0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008f67`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008fc9`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009043`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008e89`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008ee0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008f67`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140008fc9`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009043`

## pseudocode

```c
__int64 __fastcall TaskIUCompletion(__int64 *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rdi
  int v7; // r13d
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  char v12; // si
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  void *v20; // rdx
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rbx
  int v24; // eax
  int v25; // edx
  int Default; // eax
  int v27; // edx
  __int64 v28; // rax

  v4 = a4;
  v7 = *(_DWORD *)(a1[10] + 4);
  *((_DWORD *)a1 + 2) = 3;
  if ( a3 == -1073741536 || v7 == -1073676288 )
  {
    v12 = 2;
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v27) = 4;
      WPP_RECORDER_SF_Di(Default, v27, 3, 42);
    }
    goto LABEL_28;
  }
  if ( !v7 && a3 >= 0 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_Did(v8, v9, v10, v11);
    }
    return QueueUpdateTaskCompletion(a1);
  }
  v12 = 4;
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    WPP_RECORDER_SF_DidD(v13, v14, v15, v16);
    v4 = a4;
    v12 = 4;
  }
  if ( (unsigned int)(v7 + 1073741807) <= 1 || v7 == -1073741820 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = a1[4];
      v24 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v25) = 3;
      WPP_RECORDER_SF_i(v24, v25, 2, 44, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v23);
    }
    v19 = *a1;
    v20 = &ResetPipeWorkItem;
    v21 = v4;
    v22 = 0;
    goto LABEL_24;
  }
  if ( v7 == -1073713152 || a3 == -1073741667 || a3 == -1073741810 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v18) = 3;
      WPP_RECORDER_SF_(v17, v18, 2, 45, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
    }
    v19 = *a1;
    v20 = &BulkResetDeviceWorkItem;
    v21 = 0;
    v22 = *(_QWORD *)(*a1 + 160);
LABEL_24:
    UaspQueueWorkItem(v19, v20, v22, v21);
  }
LABEL_28:
  v28 = a1[4];
  if ( *(_BYTE *)(v28 + 3) <= 1u )
    *(_BYTE *)(v28 + 3) = v12;
  return QueueUpdateTaskCompletion(a1);
}

```

## disassembly

```asm
0x140008e00  mov     [rsp+arg_18], r9
0x140008e05  push    rbx
0x140008e06  push    rbp
0x140008e07  push    rsi
0x140008e08  push    rdi
0x140008e09  push    r12
0x140008e0b  push    r13
0x140008e0d  push    r14
0x140008e0f  push    r15
0x140008e11  sub     rsp, 58h
0x140008e15  mov     rax, [rcx+50h]
0x140008e19  mov     rdi, r9
0x140008e1c  mov     r12d, r8d
0x140008e1f  mov     r14, rcx
0x140008e22  mov     r13d, [rax+4]
0x140008e26  mov     dword ptr [rcx+8], 3
0x140008e2d  cmp     r8d, 0C0000120h
0x140008e34  jz      loc_14000900F
0x140008e3a  cmp     r13d, 0C0010000h
0x140008e41  jz      loc_14000900F
0x140008e47  xor     ebp, ebp
0x140008e49  test    r13d, r13d
0x140008e4c  jnz     short loc_140008EAF
0x140008e4e  test    r8d, r8d
0x140008e51  js      short loc_140008EAF
0x140008e53  cmp     cs:gTracingEnabled, bpl
0x140008e5a  jz      loc_140009078
0x140008e60  lea     r15, WPP_RECORDER_INITIALIZED
0x140008e67  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008e6e  jz      loc_140009078
0x140008e74  movzx   ebx, word ptr [rcx+28h]
0x140008e78  mov     rsi, [rcx+20h]
0x140008e7c  dec     ebx
0x140008e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e85  movzx   edi, byte ptr [rdx+4]
0x140008e89  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008e90  nop     dword ptr [rax+rax+00h]
0x140008e95  mov     [rsp+98h+var_60], edi
0x140008e99  mov     rcx, rax
0x140008e9c  mov     [rsp+98h+var_68], rsi
0x140008ea1  mov     dword ptr [rsp+98h+var_70], ebx
0x140008ea5  call    WPP_RECORDER_SF_Did
0x140008eaa  jmp     loc_140009078
0x140008eaf  cmp     cs:gTracingEnabled, bpl
0x140008eb6  lea     r15, WPP_RECORDER_INITIALIZED
0x140008ebd  mov     sil, 4
0x140008ec0  jz      short loc_140008F11
0x140008ec2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008ec9  jz      short loc_140008F11
0x140008ecb  movzx   ebx, word ptr [rcx+28h]
0x140008ecf  mov     rsi, [rcx+20h]
0x140008ed3  dec     ebx
0x140008ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x140008edc  movzx   edi, byte ptr [rdx+4]
0x140008ee0  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008ee7  nop     dword ptr [rax+rax+00h]
0x140008eec  mov     [rsp+98h+var_58], r13d
0x140008ef1  mov     rcx, rax
0x140008ef4  mov     [rsp+98h+var_60], edi
0x140008ef8  mov     [rsp+98h+var_68], rsi
0x140008efd  mov     dword ptr [rsp+98h+var_70], ebx
0x140008f01  call    WPP_RECORDER_SF_DidD
0x140008f06  mov     rdi, [rsp+98h+arg_18]
0x140008f0e  mov     sil, 4
0x140008f11  lea     eax, [r13+3FFFFFEFh]
0x140008f18  cmp     eax, 1
0x140008f1b  jbe     loc_140008FA7
0x140008f21  cmp     r13d, 0C0000004h
0x140008f28  jz      short loc_140008FA7
0x140008f2a  cmp     r13d, 0C0007000h
0x140008f31  jz      short loc_140008F49
0x140008f33  cmp     r12d, 0C000009Dh
0x140008f3a  jz      short loc_140008F49
0x140008f3c  cmp     r12d, 0C000000Eh
0x140008f43  jnz     loc_14000906A
0x140008f49  cmp     cs:gTracingEnabled, bpl
0x140008f50  jz      short loc_140008F91
0x140008f52  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008f59  jz      short loc_140008F91
0x140008f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f62  mov     ebx, 2Dh ; '-'
0x140008f67  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008f6e  nop     dword ptr [rax+rax+00h]
0x140008f73  movzx   r9d, bx
0x140008f77  lea     r8d, [rbx-2Bh]
0x140008f7b  mov     rcx, rax
0x140008f7e  mov     dl, 3
0x140008f80  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008f87  mov     [rsp+98h+var_78], rax
0x140008f8c  call    WPP_RECORDER_SF_
0x140008f91  mov     rcx, [r14]
0x140008f94  lea     rdx, BulkResetDeviceWorkItem
0x140008f9b  xor     r9d, r9d
0x140008f9e  mov     r8, [rcx+0A0h]
0x140008fa5  jmp     short loc_140009008
0x140008fa7  cmp     cs:gTracingEnabled, bpl
0x140008fae  jz      short loc_140008FF8
0x140008fb0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008fb7  jz      short loc_140008FF8
0x140008fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fc0  mov     ebp, 2Ch ; ','
0x140008fc5  mov     rbx, [r14+20h]
0x140008fc9  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140008fd0  nop     dword ptr [rax+rax+00h]
0x140008fd5  mov     [rsp+98h+var_70], rbx
0x140008fda  lea     r8d, [rbp-2Ah]
0x140008fde  mov     rcx, rax
0x140008fe1  movzx   r9d, bp
0x140008fe5  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140008fec  mov     dl, 3
0x140008fee  mov     [rsp+98h+var_78], rax
0x140008ff3  call    WPP_RECORDER_SF_i
0x140008ff8  mov     rcx, [r14]
0x140008ffb  lea     rdx, ResetPipeWorkItem
0x140009002  mov     r9, rdi
0x140009005  xor     r8d, r8d
0x140009008  call    UaspQueueWorkItem
0x14000900d  jmp     short loc_14000906A
0x14000900f  xor     ebp, ebp
0x140009011  mov     sil, 2
0x140009014  cmp     cs:gTracingEnabled, bpl
0x14000901b  jz      short loc_14000906A
0x14000901d  lea     r15, WPP_RECORDER_INITIALIZED
0x140009024  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000902b  jz      short loc_14000906A
0x14000902d  movzx   ebx, word ptr [rcx+28h]
0x140009031  mov     ebp, 2Ah ; '*'
0x140009036  mov     rdi, [rcx+20h]
0x14000903a  dec     ebx
0x14000903c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009043  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000904a  nop     dword ptr [rax+rax+00h]
0x14000904f  mov     [rsp+98h+var_68], rdi
0x140009054  lea     r8d, [rbp-27h]
0x140009058  mov     rcx, rax
0x14000905b  mov     dword ptr [rsp+98h+var_70], ebx
0x14000905f  movzx   r9d, bp
0x140009063  mov     dl, 4
0x140009065  call    WPP_RECORDER_SF_Di
0x14000906a  mov     rax, [r14+20h]
0x14000906e  cmp     byte ptr [rax+3], 1
0x140009072  ja      short loc_140009078
0x140009074  mov     [rax+3], sil
0x140009078  mov     rcx, r14
0x14000907b  call    QueueUpdateTaskCompletion
0x140009080  add     rsp, 58h
0x140009084  pop     r15
0x140009086  pop     r14
0x140009088  pop     r13
0x14000908a  pop     r12
0x14000908c  pop     rdi
0x14000908d  pop     rsi
0x14000908e  pop     rbp
0x14000908f  pop     rbx
0x140009090  retn
```
