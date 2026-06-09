# ReadyIUCompletion

- ea: `0x14000a450`
- end: `0x14000a7b6`
- name: `ReadyIUCompletion`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000a7bc`

## callees

- `0x140002964`
- `0x140005744`
- `0x1400081dc`
- `0x1400098a0`
- `0x140009fe0`
- `0x14000a450`
- `0x14000b4d0`
- `0x14000b59c`
- `0x14000b710`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a4ff`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a557`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a5e8`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a655`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a74a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a4ff`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a557`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a5e8`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a655`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a74a`

## string_xrefs

- `0x14000a496`: `ReadReadyIU`
- `0x14000a4a7`: `WriteReadyIU`

## pseudocode

```c
__int64 __fastcall ReadyIUCompletion(__int64 *a1, _BYTE *a2, int a3, __int64 a4)
{
  __int64 v5; // rcx
  int v8; // r14d
  char v9; // bp
  int Default; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rbx
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  void *v20; // rdx
  __int64 v21; // r9
  __int64 v22; // r8
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  __int64 result; // rax
  __int64 v27; // rbx
  int v28; // eax
  int v29; // edx
  __int64 v30; // rax

  v5 = a1[13];
  v8 = *(_DWORD *)(v5 + 4);
  *((_DWORD *)a1 + 5) = 3;
  *((_BYTE *)a1 + 203) = 0;
  if ( *a2 != 6 && *a2 != 7 )
  {
    v9 = 4;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_DD(WPP_GLOBAL_Control->DeviceExtension, 0, a3, 13);
    goto LABEL_10;
  }
  if ( a3 == -1073741536 || v8 == -1073676288 )
  {
    if ( !*(_DWORD *)(v5 + 36) )
    {
      v9 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_SDi(WPP_GLOBAL_Control->DeviceExtension, 0, a3, 14);
      goto LABEL_10;
    }
  }
  else if ( v8 || a3 < 0 )
  {
    v9 = 4;
    if ( !gTracingEnabled )
      goto LABEL_13;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_SDiD(Default, v11, v12, v13);
    }
LABEL_10:
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = a1[4];
      v15 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v16) = 3;
      WPP_RECORDER_SF_i(v15, v16, 2, 17, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v14);
    }
LABEL_13:
    *((_DWORD *)a1 + 3) = 3;
    if ( (unsigned int)(v8 + 1073741807) <= 1 || v8 == -1073741820 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = a1[4];
        v28 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v29) = 3;
        WPP_RECORDER_SF_i(v28, v29, 2, 18, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v27);
      }
      v19 = *a1;
      v20 = &ResetPipeWorkItem;
      v21 = a4;
      v22 = 0;
    }
    else
    {
      if ( v8 != -1073713152 && a3 != -1073741667 && a3 != -1073741810 )
      {
LABEL_39:
        v30 = a1[4];
        if ( *(_BYTE *)(v30 + 3) <= 1u )
          *(_BYTE *)(v30 + 3) = v9;
        return QueueUpdateCompletion(a1);
      }
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v17 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v18) = 3;
        WPP_RECORDER_SF_(v17, v18, 2, 19, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids);
      }
      v19 = *a1;
      v20 = &BulkResetDeviceWorkItem;
      v21 = 0;
      v22 = *(_QWORD *)(*a1 + 160);
    }
    UaspQueueWorkItem(v19, v20, v22, v21);
    goto LABEL_39;
  }
  v9 = 4;
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v24) = 4;
    WPP_RECORDER_SF_SDi(v23, v24, v25, 16);
  }
  result = IssueDataTransferRequest(a1);
  if ( (int)result < 0 )
    goto LABEL_10;
  return result;
}

```

## disassembly

```asm
0x14000a450  push    rbx
0x14000a452  push    rbp
0x14000a453  push    rsi
0x14000a454  push    rdi
0x14000a455  push    r12
0x14000a457  push    r13
0x14000a459  push    r14
0x14000a45b  push    r15
0x14000a45d  sub     rsp, 58h
0x14000a461  mov     rsi, rcx
0x14000a464  lea     r15, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a46b  mov     rcx, [rcx+68h]
0x14000a46f  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a476  xor     ebx, ebx
0x14000a478  mov     r13, r9
0x14000a47b  mov     r12d, r8d
0x14000a47e  mov     r14d, [rcx+4]
0x14000a482  mov     dword ptr [rsi+14h], 3
0x14000a489  mov     [rsi+0CBh], bl
0x14000a48f  movzx   eax, byte ptr [rdx]
0x14000a492  cmp     al, 6
0x14000a494  jnz     short loc_14000A49F
0x14000a496  lea     r15, aReadreadyiu; "ReadReadyIU"
0x14000a49d  jmp     short loc_14000A4AE
0x14000a49f  cmp     al, 7
0x14000a4a1  jnz     loc_14000A6E6
0x14000a4a7  lea     r15, aWritereadyiu; "WriteReadyIU"
0x14000a4ae  cmp     r12d, 0C0000120h
0x14000a4b5  jz      loc_14000A62B
0x14000a4bb  cmp     r14d, 0C0010000h
0x14000a4c2  jz      loc_14000A62B
0x14000a4c8  test    r14d, r14d
0x14000a4cb  jnz     short loc_14000A4D6
0x14000a4cd  test    r12d, r12d
0x14000a4d0  jns     loc_14000A630
0x14000a4d6  cmp     cs:gTracingEnabled, bl
0x14000a4dc  mov     bpl, 4
0x14000a4df  jz      loc_14000A588
0x14000a4e5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a4ec  jz      short loc_14000A528
0x14000a4ee  movzx   ebx, word ptr [rsi+28h]
0x14000a4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4f9  dec     ebx
0x14000a4fb  mov     rdi, [rsi+20h]
0x14000a4ff  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a506  nop     dword ptr [rax+rax+00h]
0x14000a50b  mov     [rsp+98h+var_58], r14d
0x14000a510  mov     rcx, rax
0x14000a513  mov     [rsp+98h+var_60], rdi
0x14000a518  mov     [rsp+98h+var_68], ebx
0x14000a51c  mov     [rsp+98h+var_70], r15
0x14000a521  call    WPP_RECORDER_SF_SDiD
0x14000a526  xor     ebx, ebx
0x14000a528  lea     r15, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a52f  cmp     cs:gTracingEnabled, bl
0x14000a535  jz      short loc_14000A581
0x14000a537  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a53e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a545  jz      short loc_14000A588
0x14000a547  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a54e  mov     edi, 11h
0x14000a553  mov     rbx, [rsi+20h]
0x14000a557  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a55e  nop     dword ptr [rax+rax+00h]
0x14000a563  mov     [rsp+98h+var_70], rbx
0x14000a568  lea     r8d, [rdi-0Fh]
0x14000a56c  mov     rcx, rax
0x14000a56f  mov     [rsp+98h+var_78], r15
0x14000a574  movzx   r9d, di
0x14000a578  mov     dl, 3
0x14000a57a  call    WPP_RECORDER_SF_i
0x14000a57f  xor     ebx, ebx
0x14000a581  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000a588  lea     eax, [r14+3FFFFFEFh]
0x14000a58f  mov     dword ptr [rsi+0Ch], 3
0x14000a596  cmp     eax, 1
0x14000a599  jbe     loc_14000A729
0x14000a59f  cmp     r14d, 0C0000004h
0x14000a5a6  jz      loc_14000A729
0x14000a5ac  cmp     r14d, 0C0007000h
0x14000a5b3  jz      short loc_14000A5CB
0x14000a5b5  cmp     r12d, 0C000009Dh
0x14000a5bc  jz      short loc_14000A5CB
0x14000a5be  cmp     r12d, 0C000000Eh
0x14000a5c5  jnz     loc_14000A78E
0x14000a5cb  cmp     cs:gTracingEnabled, bl
0x14000a5d1  jz      short loc_14000A612
0x14000a5d3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a5da  jz      short loc_14000A612
0x14000a5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5e3  mov     ebx, 13h
0x14000a5e8  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a5ef  nop     dword ptr [rax+rax+00h]
0x14000a5f4  movzx   r9d, bx
0x14000a5f8  lea     r8d, [rbx-11h]
0x14000a5fc  mov     rcx, rax
0x14000a5ff  mov     dl, 3
0x14000a601  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a608  mov     [rsp+98h+var_78], rax
0x14000a60d  call    WPP_RECORDER_SF_
0x14000a612  mov     rcx, [rsi]
0x14000a615  lea     rdx, BulkResetDeviceWorkItem
0x14000a61c  xor     r9d, r9d
0x14000a61f  mov     r8, [rcx+0A0h]
0x14000a626  jmp     loc_14000A789
0x14000a62b  cmp     [rcx+24h], ebx
0x14000a62e  jz      short loc_14000A697
0x14000a630  cmp     cs:gTracingEnabled, bl
0x14000a636  mov     bpl, 4
0x14000a639  jz      short loc_14000A682
0x14000a63b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a642  jz      short loc_14000A682
0x14000a644  movzx   ebx, word ptr [rsi+28h]
0x14000a648  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a64f  dec     ebx
0x14000a651  mov     rdi, [rsi+20h]
0x14000a655  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a65c  nop     dword ptr [rax+rax+00h]
0x14000a661  mov     [rsp+98h+var_60], rdi
0x14000a666  mov     r9d, 10h
0x14000a66c  mov     rcx, rax
0x14000a66f  mov     [rsp+98h+var_68], ebx
0x14000a673  mov     dl, bpl
0x14000a676  mov     [rsp+98h+var_70], r15
0x14000a67b  call    WPP_RECORDER_SF_SDi
0x14000a680  xor     ebx, ebx
0x14000a682  mov     rcx, rsi
0x14000a685  call    IssueDataTransferRequest
0x14000a68a  test    eax, eax
0x14000a68c  jns     loc_14000A7A4
0x14000a692  jmp     loc_14000A528
0x14000a697  mov     bpl, 2
0x14000a69a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a6a1  jz      loc_14000A528
0x14000a6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6ae  cmp     [rcx+48h], bx
0x14000a6b2  jz      loc_14000A528
0x14000a6b8  movzx   edx, word ptr [rsi+28h]
0x14000a6bc  mov     r9d, 0Eh
0x14000a6c2  mov     rax, [rsi+20h]
0x14000a6c6  dec     edx
0x14000a6c8  mov     rcx, [rcx+40h]
0x14000a6cc  mov     [rsp+98h+var_60], rax
0x14000a6d1  mov     [rsp+98h+var_68], edx
0x14000a6d5  xor     edx, edx
0x14000a6d7  mov     [rsp+98h+var_70], r15
0x14000a6dc  call    WPP_RECORDER_SF_SDi
0x14000a6e1  jmp     loc_14000A528
0x14000a6e6  mov     bpl, 4
0x14000a6e9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a6f0  jz      loc_14000A52F
0x14000a6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6fd  cmp     [rcx+48h], bx
0x14000a701  jz      loc_14000A52F
0x14000a707  movzx   edx, word ptr [rsi+28h]
0x14000a70b  mov     r9d, 0Dh
0x14000a711  mov     rcx, [rcx+40h]
0x14000a715  mov     [rsp+98h+var_68], eax
0x14000a719  mov     dword ptr [rsp+98h+var_70], edx
0x14000a71d  xor     edx, edx
0x14000a71f  call    WPP_RECORDER_SF_DD
0x14000a724  jmp     loc_14000A52F
0x14000a729  cmp     cs:gTracingEnabled, bl
0x14000a72f  jz      short loc_14000A779
0x14000a731  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000a738  jz      short loc_14000A779
0x14000a73a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a741  mov     edi, 12h
0x14000a746  mov     rbx, [rsi+20h]
0x14000a74a  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a751  nop     dword ptr [rax+rax+00h]
0x14000a756  mov     [rsp+98h+var_70], rbx
0x14000a75b  lea     r8d, [rdi-10h]
0x14000a75f  mov     rcx, rax
0x14000a762  movzx   r9d, di
0x14000a766  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a76d  mov     dl, 3
0x14000a76f  mov     [rsp+98h+var_78], rax
0x14000a774  call    WPP_RECORDER_SF_i
0x14000a779  mov     rcx, [rsi]
0x14000a77c  lea     rdx, ResetPipeWorkItem
0x14000a783  mov     r9, r13
0x14000a786  xor     r8d, r8d
0x14000a789  call    UaspQueueWorkItem
0x14000a78e  mov     rax, [rsi+20h]
0x14000a792  cmp     byte ptr [rax+3], 1
0x14000a796  ja      short loc_14000A79C
0x14000a798  mov     [rax+3], bpl
0x14000a79c  mov     rcx, rsi
0x14000a79f  call    QueueUpdateCompletion
0x14000a7a4  add     rsp, 58h
0x14000a7a8  pop     r15
0x14000a7aa  pop     r14
0x14000a7ac  pop     r13
0x14000a7ae  pop     r12
0x14000a7b0  pop     rdi
0x14000a7b1  pop     rsi
0x14000a7b2  pop     rbp
0x14000a7b3  pop     rbx
0x14000a7b4  retn
```
