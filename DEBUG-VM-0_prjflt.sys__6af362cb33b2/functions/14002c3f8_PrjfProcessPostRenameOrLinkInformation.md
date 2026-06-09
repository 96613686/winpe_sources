# PrjfProcessPostRenameOrLinkInformation

- ea: `0x14002c3f8`
- end: `0x14002c984`
- name: `PrjfProcessPostRenameOrLinkInformation`
- size: `1420`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14002bd30`

## callees

- `0x140002f3c`
- `0x140003d9c`
- `0x140006570`
- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d5e8`
- `0x14002c3f8`
- `0x14003005c`
- `0x140041e28`
- `0x1400422ec`
- `0x140043844`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002c5f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c5f9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002c717`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002c717`
- `FLTMGR!FltReleaseContext` at `0x14002c848`
- `FLTMGR!FltReleaseContext` at `0x14002c85c`
- `FLTMGR!FltReleaseContext` at `0x14002c848`
- `FLTMGR!FltReleaseContext` at `0x14002c85c`

## pseudocode

```c
__int64 __fastcall PrjfProcessPostRenameOrLinkInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PFLT_CONTEXT v7; // r12
  int Tombstone; // ebx
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int SetContextFileObject; // eax
  int v19; // edx
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  int v25; // r8d
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  PFLT_CONTEXT Context[9]; // [rsp+60h] [rbp-48h] BYREF
  PFLT_CONTEXT v34; // [rsp+C0h] [rbp+18h] BYREF
  int v35; // [rsp+C8h] [rbp+20h]

  v35 = a4;
  Context[0] = 0;
  v34 = 0;
  v7 = 0;
  if ( (_DWORD)a4 == 128 )
  {
    if ( *(_DWORD *)(a1 + 24) )
    {
      LOBYTE(a4) = 1;
      v30 = PrjfCleanUpRenameLinkTargetTombstone(a1, a2, a3, a4);
      Tombstone = v30;
      if ( v30 < 0 )
      {
        if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v31) = BYTE2(xmmword_14001A3D0) & 8;
          LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            531,
            v31,
            v32,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            19,
            26,
            (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
            118,
            v30);
        }
        goto LABEL_46;
      }
    }
    else
    {
      v15 = PrjfCleanUpRenameLinkTargetTombstone(a1, a2, a3, 0);
      Tombstone = v15;
      if ( v15 < 0 )
      {
        if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = BYTE2(xmmword_14001A3D0) & 8;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            531,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            19,
            23,
            (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
            22,
            v15);
        }
        goto LABEL_46;
      }
      if ( *(_QWORD *)(a3 + 24) )
      {
        KeWaitForSingleObject((PVOID)(*(_QWORD *)(a3 + 40) + 288LL), Executive, 0, 0, 0);
        if ( !*(_BYTE *)(*(_QWORD *)(a3 + 40) + 282LL) )
        {
          SetContextFileObject = PrjfGetSetContextFileObject(
                                   *(PFLT_INSTANCE *)(a2 + 24),
                                   *(PFILE_OBJECT *)(a3 + 24),
                                   0x80000000,
                                   0,
                                   0,
                                   0,
                                   0,
                                   Context,
                                   &v34);
          Tombstone = SetContextFileObject;
          if ( SetContextFileObject < 0 )
          {
            if ( (BYTE2(xmmword_14001A3D0) & 8) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v19) = BYTE2(xmmword_14001A3D0) & 8;
              LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                531,
                v19,
                v21,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                19,
                24,
                (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
                62,
                SetContextFileObject);
            }
            v7 = v34;
            goto LABEL_42;
          }
          v7 = v34;
          if ( !*((_BYTE *)v34 + 44) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v20);
          Tombstone = PrjfCreateTombstone(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        (struct _UNICODE_STRING *)(*(_QWORD *)(a3 + 32) + 8LL),
                        *(_BYTE *)(a3 + 48));
          if ( Tombstone == -1073741771 )
          {
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(a3 + 8), (PCUNICODE_STRING)(a3 + 64), 1u) )
            {
              Tombstone = 0;
              goto LABEL_31;
            }
          }
          else if ( Tombstone >= 0 )
          {
            goto LABEL_31;
          }
          if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v22) = BYTE2(xmmword_14001A3D0) & 8;
            LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              531,
              v22,
              v23,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              19,
              25,
              (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
              94,
              Tombstone);
          }
          PrjfTelemetryTombstoneFailureOperation(1, 2, (unsigned int)Tombstone);
          goto LABEL_42;
        }
      }
    }
LABEL_31:
    if ( *(_QWORD *)(a3 + 24) )
    {
      Tombstone = PrjfRemoveInMemoryTombstone(*(PFLT_INSTANCE *)(a2 + 24));
      if ( Tombstone < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = BYTE1(xmmword_14001A3D0) & 0x20;
          LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdd(525, v24, v25, *((_QWORD *)WPP_GLOBAL_Control + 8));
        }
        PrjfTelemetryTombstoneFailureOperation(2, 10, (unsigned int)Tombstone);
      }
    }
    goto LABEL_37;
  }
  if ( (_DWORD)a4 != 256 )
  {
    Tombstone = 0;
    MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected NotificationToSend");
LABEL_37:
    if ( *(int *)(a1 + 24) >= 0 )
    {
      v26 = PrjfNotifyRenameOrLinkOperation(
              a1,
              *(struct _FLT_INSTANCE **)(a2 + 24),
              *(struct _FILE_OBJECT **)(a2 + 32),
              v35,
              (__int128 **)a3);
      Tombstone = v26;
      if ( v26 < 0
        && ((BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v27) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v27,
          v28,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          30,
          (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
          218,
          v26);
      }
    }
LABEL_42:
    if ( Context[0] )
      FltReleaseContext(Context[0]);
    if ( v7 )
      FltReleaseContext(v7);
    goto LABEL_46;
  }
  if ( *(int *)(a1 + 24) >= 0 )
  {
    v12 = PrjfCleanUpRenameLinkTargetTombstone(a1, a2, a3, 0);
    Tombstone = v12;
    if ( v12 >= 0 )
      goto LABEL_37;
    if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v13,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        29,
        (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
        189,
        v12);
    }
  }
  else
  {
    LOBYTE(a4) = 1;
    v9 = PrjfCleanUpRenameLinkTargetTombstone(a1, a2, a3, a4);
    Tombstone = v9;
    if ( v9 >= 0 )
      goto LABEL_37;
    if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        28,
        (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
        172,
        v9);
    }
  }
LABEL_46:
  if ( a3 )
    PrjfReleaseRenameOrLinkCompletionContext((PVOID)a3);
  return (unsigned int)Tombstone;
}

```

## disassembly

```asm
0x14002c3f8  mov     r11, rsp
0x14002c3fb  mov     [r11+8], rbx
0x14002c3ff  mov     [r11+20h], r9d
0x14002c403  push    rbp
0x14002c404  push    rsi
0x14002c405  push    rdi
0x14002c406  push    r12
0x14002c408  push    r13
0x14002c40a  push    r14
0x14002c40c  push    r15
0x14002c40e  sub     rsp, 70h
0x14002c412  mov     r15, rcx
0x14002c415  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c41c  xor     ecx, ecx
0x14002c41e  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c425  mov     [r11-48h], rcx
0x14002c429  mov     eax, r9d
0x14002c42c  mov     [r11+18h], rcx
0x14002c430  mov     rsi, r8
0x14002c433  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c43a  mov     r13, rdx
0x14002c43d  mov     r12d, ecx
0x14002c440  cmp     r9d, 80h
0x14002c447  jz      loc_14002C566
0x14002c44d  cmp     eax, 100h
0x14002c452  jz      short loc_14002C467
0x14002c454  mov     ebx, ecx
0x14002c456  lea     rcx, aUnexpectedNoti; "Unexpected NotificationToSend"
0x14002c45d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002c462  jmp     loc_14002C7BA
0x14002c467  cmp     [r15+18h], ecx
0x14002c46b  mov     rcx, r15
0x14002c46e  jge     loc_14002C4FE
0x14002c474  mov     r9b, 1
0x14002c477  call    PrjfCleanUpRenameLinkTargetTombstone
0x14002c47c  mov     ebx, eax
0x14002c47e  test    eax, eax
0x14002c480  jns     loc_14002C7BA
0x14002c486  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c48c  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c493  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c49a  setnz   r8b
0x14002c49e  and     dl, 8
0x14002c4a1  jnz     short loc_14002C4AC
0x14002c4a3  test    r8b, r8b
0x14002c4a6  jz      loc_14002C868
0x14002c4ac  mov     [rsp+0A8h+var_58], eax
0x14002c4b0  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c4b7  mov     [rsp+0A8h+var_60], 2ACh
0x14002c4bf  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c4c6  mov     [rsp+0A8h+var_68], rbp
0x14002c4cb  mov     [rsp+0A8h+var_70], r14
0x14002c4d0  mov     word ptr [rsp+0A8h+var_78], 1Ch
0x14002c4d7  mov     r9, cs:WPP_GLOBAL_Control
0x14002c4de  mov     ecx, 213h
0x14002c4e3  mov     dword ptr [rsp+0A8h+var_80], 13h
0x14002c4eb  mov     byte ptr [rsp+0A8h+Timeout], 2
0x14002c4f0  mov     r9, [r9+40h]
0x14002c4f4  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c4f9  jmp     loc_14002C868
0x14002c4fe  xor     r9d, r9d
0x14002c501  call    PrjfCleanUpRenameLinkTargetTombstone
0x14002c506  mov     ebx, eax
0x14002c508  test    eax, eax
0x14002c50a  jns     loc_14002C7BA
0x14002c510  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c516  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c51d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c524  setnz   r8b
0x14002c528  and     dl, 8
0x14002c52b  jnz     short loc_14002C536
0x14002c52d  test    r8b, r8b
0x14002c530  jz      loc_14002C868
0x14002c536  mov     [rsp+0A8h+var_58], eax
0x14002c53a  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c541  mov     [rsp+0A8h+var_60], 2BDh
0x14002c549  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c550  mov     [rsp+0A8h+var_68], rbp
0x14002c555  mov     [rsp+0A8h+var_70], r14
0x14002c55a  mov     word ptr [rsp+0A8h+var_78], 1Dh
0x14002c561  jmp     loc_14002C4D7
0x14002c566  cmp     [r15+18h], ecx
0x14002c56a  mov     rcx, r15
0x14002c56d  jnz     loc_14002C91C
0x14002c573  xor     r9d, r9d
0x14002c576  call    PrjfCleanUpRenameLinkTargetTombstone
0x14002c57b  mov     ebx, eax
0x14002c57d  test    eax, eax
0x14002c57f  jns     short loc_14002C5D7
0x14002c581  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c587  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c58e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c595  setnz   r8b
0x14002c599  and     dl, 8
0x14002c59c  jnz     short loc_14002C5A7
0x14002c59e  test    r8b, r8b
0x14002c5a1  jz      loc_14002C868
0x14002c5a7  mov     [rsp+0A8h+var_58], eax
0x14002c5ab  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c5b2  mov     [rsp+0A8h+var_60], 216h
0x14002c5ba  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c5c1  mov     [rsp+0A8h+var_68], rbp
0x14002c5c6  mov     [rsp+0A8h+var_70], r14
0x14002c5cb  mov     word ptr [rsp+0A8h+var_78], 17h
0x14002c5d2  jmp     loc_14002C4D7
0x14002c5d7  cmp     [rsi+18h], r12
0x14002c5db  jz      loc_14002C72D
0x14002c5e1  mov     rcx, [rsi+28h]
0x14002c5e5  xor     r9d, r9d; Alertable
0x14002c5e8  add     rcx, 120h; Object
0x14002c5ef  mov     [rsp+0A8h+Timeout], r12; Timeout
0x14002c5f4  xor     r8d, r8d; WaitMode
0x14002c5f7  xor     edx, edx; WaitReason
0x14002c5f9  call    cs:__imp_KeWaitForSingleObject
0x14002c600  nop     dword ptr [rax+rax+00h]
0x14002c605  mov     rax, [rsi+28h]
0x14002c609  mov     cl, [rax+11Ah]
0x14002c60f  test    cl, cl
0x14002c611  jnz     loc_14002C72D
0x14002c617  mov     rdx, [rsi+18h]; FileObject
0x14002c61b  lea     rax, [rsp+0A8h+arg_10]
0x14002c623  mov     rcx, [r13+18h]; Instance
0x14002c627  xor     r9d, r9d
0x14002c62a  mov     [rsp+0A8h+var_68], rax; __int64
0x14002c62f  mov     r8d, 80000000h
0x14002c635  lea     rax, [rsp+0A8h+Context]
0x14002c63a  mov     [rsp+0A8h+var_70], rax; __int64
0x14002c63f  mov     [rsp+0A8h+var_78], r12; __int64
0x14002c644  mov     [rsp+0A8h+var_80], r12; __int64
0x14002c649  mov     byte ptr [rsp+0A8h+Timeout], r12b; char
0x14002c64e  call    PrjfGetSetContextFileObject
0x14002c653  mov     ebx, eax
0x14002c655  test    eax, eax
0x14002c657  jns     short loc_14002C6D5
0x14002c659  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c65f  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c666  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c66d  setnz   r8b
0x14002c671  and     dl, 8
0x14002c674  jnz     short loc_14002C67B
0x14002c676  test    r8b, r8b
0x14002c679  jz      short loc_14002C6C8
0x14002c67b  mov     r9, cs:WPP_GLOBAL_Control
0x14002c682  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c689  mov     [rsp+0A8h+var_58], eax
0x14002c68d  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c694  mov     [rsp+0A8h+var_60], 23Eh
0x14002c69c  mov     ecx, 213h
0x14002c6a1  mov     [rsp+0A8h+var_68], rbp
0x14002c6a6  mov     r9, [r9+40h]
0x14002c6aa  mov     [rsp+0A8h+var_70], r14
0x14002c6af  mov     word ptr [rsp+0A8h+var_78], 18h
0x14002c6b6  mov     dword ptr [rsp+0A8h+var_80], 13h
0x14002c6be  mov     byte ptr [rsp+0A8h+Timeout], 2
0x14002c6c3  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c6c8  mov     r12, [rsp+0A8h+arg_10]
0x14002c6d0  jmp     loc_14002C83E
0x14002c6d5  mov     r12, [rsp+0A8h+arg_10]
0x14002c6dd  cmp     byte ptr [r12+2Ch], 0
0x14002c6e3  jnz     short loc_14002C6EA
0x14002c6e5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002c6ea  mov     rdx, [rsi+20h]
0x14002c6ee  mov     r8b, [rsi+30h]
0x14002c6f2  add     rdx, 8
0x14002c6f6  mov     rcx, [r13+18h]; Instance
0x14002c6fa  call    PrjfCreateTombstone
0x14002c6ff  mov     ebx, eax
0x14002c701  cmp     eax, 0C0000035h
0x14002c706  jnz     loc_14002C890
0x14002c70c  lea     rdx, [rsi+40h]; String2
0x14002c710  mov     r8b, 1; CaseInSensitive
0x14002c713  lea     rcx, [rsi+8]; String1
0x14002c717  call    cs:__imp_RtlCompareUnicodeString
0x14002c71e  nop     dword ptr [rax+rax+00h]
0x14002c723  test    eax, eax
0x14002c725  jnz     loc_14002C898
0x14002c72b  xor     ebx, ebx
0x14002c72d  mov     r8, [rsi+18h]
0x14002c731  test    r8, r8
0x14002c734  jz      loc_14002C7BA
0x14002c73a  mov     rdx, [rsi+20h]
0x14002c73e  mov     rcx, [r13+18h]; Instance
0x14002c742  call    PrjfRemoveInMemoryTombstone
0x14002c747  mov     ebx, eax
0x14002c749  test    eax, eax
0x14002c74b  jns     short loc_14002C7BA
0x14002c74d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c754  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002c75a  setnz   r8b
0x14002c75e  and     dl, 20h
0x14002c761  jnz     short loc_14002C768
0x14002c763  test    r8b, r8b
0x14002c766  jz      short loc_14002C7AA
0x14002c768  mov     eax, [r15+18h]
0x14002c76c  mov     ecx, 20Dh
0x14002c771  mov     r9, cs:WPP_GLOBAL_Control
0x14002c778  mov     [rsp+0A8h+var_50], eax
0x14002c77c  mov     [rsp+0A8h+var_58], ebx
0x14002c780  mov     [rsp+0A8h+var_60], 28Eh
0x14002c788  mov     r9, [r9+40h]
0x14002c78c  mov     [rsp+0A8h+var_68], rbp
0x14002c791  mov     [rsp+0A8h+var_70], r14
0x14002c796  mov     word ptr [rsp+0A8h+var_78], 1Bh
0x14002c79d  mov     dword ptr [rsp+0A8h+var_80], 0Dh
0x14002c7a5  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x14002c7aa  mov     edx, 0Ah
0x14002c7af  mov     r8d, ebx
0x14002c7b2  lea     ecx, [rdx-8]
0x14002c7b5  call    PrjfTelemetryTombstoneFailureOperation
0x14002c7ba  cmp     dword ptr [r15+18h], 0
0x14002c7bf  jl      short loc_14002C83E
0x14002c7c1  mov     r9d, [rsp+0A8h+arg_18]
0x14002c7c9  mov     rcx, r15
0x14002c7cc  mov     r8, [r13+20h]
0x14002c7d0  mov     rdx, [r13+18h]
0x14002c7d4  mov     [rsp+0A8h+Timeout], rsi
0x14002c7d9  call    PrjfNotifyRenameOrLinkOperation
0x14002c7de  mov     ebx, eax
0x14002c7e0  test    eax, eax
0x14002c7e2  jns     short loc_14002C83E
0x14002c7e4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c7eb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002c7f1  setnz   r8b
0x14002c7f5  and     dl, 20h
0x14002c7f8  jnz     short loc_14002C7FF
0x14002c7fa  test    r8b, r8b
0x14002c7fd  jz      short loc_14002C83E
0x14002c7ff  mov     r9, cs:WPP_GLOBAL_Control
0x14002c806  mov     ecx, 20Dh
0x14002c80b  mov     [rsp+0A8h+var_58], eax
0x14002c80f  mov     [rsp+0A8h+var_60], 2DAh
0x14002c817  mov     [rsp+0A8h+var_68], rbp
0x14002c81c  mov     r9, [r9+40h]
0x14002c820  mov     [rsp+0A8h+var_70], r14
0x14002c825  mov     word ptr [rsp+0A8h+var_78], 1Eh
0x14002c82c  mov     dword ptr [rsp+0A8h+var_80], 0Dh
0x14002c834  mov     byte ptr [rsp+0A8h+Timeout], 2
0x14002c839  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c83e  mov     rcx, [rsp+0A8h+Context]; Context
0x14002c843  test    rcx, rcx
0x14002c846  jz      short loc_14002C854
0x14002c848  call    cs:__imp_FltReleaseContext
0x14002c84f  nop     dword ptr [rax+rax+00h]
0x14002c854  test    r12, r12
0x14002c857  jz      short loc_14002C868
0x14002c859  mov     rcx, r12; Context
0x14002c85c  call    cs:__imp_FltReleaseContext
0x14002c863  nop     dword ptr [rax+rax+00h]
0x14002c868  test    rsi, rsi
0x14002c86b  jz      short loc_14002C875
0x14002c86d  mov     rcx, rsi; Entry
0x14002c870  call    PrjfReleaseRenameOrLinkCompletionContext
0x14002c875  mov     eax, ebx
0x14002c877  mov     rbx, [rsp+0A8h+arg_0]
0x14002c87f  add     rsp, 70h
0x14002c883  pop     r15
0x14002c885  pop     r14
0x14002c887  pop     r13
0x14002c889  pop     r12
0x14002c88b  pop     rdi
0x14002c88c  pop     rsi
0x14002c88d  pop     rbp
0x14002c88e  retn
0x14002c890  test    ebx, ebx
0x14002c892  jns     loc_14002C72D
0x14002c898  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c89e  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c8a5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c8ac  setnz   r8b
0x14002c8b0  and     dl, 8
0x14002c8b3  jnz     short loc_14002C8BA
0x14002c8b5  test    r8b, r8b
0x14002c8b8  jz      short loc_14002C907
0x14002c8ba  mov     r9, cs:WPP_GLOBAL_Control
0x14002c8c1  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c8c8  mov     [rsp+0A8h+var_58], ebx
0x14002c8cc  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c8d3  mov     [rsp+0A8h+var_60], 25Eh
0x14002c8db  mov     ecx, 213h
0x14002c8e0  mov     [rsp+0A8h+var_68], rbp
0x14002c8e5  mov     r9, [r9+40h]
0x14002c8e9  mov     [rsp+0A8h+var_70], r14
0x14002c8ee  mov     word ptr [rsp+0A8h+var_78], 19h
0x14002c8f5  mov     dword ptr [rsp+0A8h+var_80], 13h
0x14002c8fd  mov     byte ptr [rsp+0A8h+Timeout], 2
0x14002c902  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002c907  mov     edx, 2
0x14002c90c  mov     r8d, ebx
0x14002c90f  lea     ecx, [rdx-1]
0x14002c912  call    PrjfTelemetryTombstoneFailureOperation
0x14002c917  jmp     loc_14002C83E
0x14002c91c  mov     r9b, 1
0x14002c91f  call    PrjfCleanUpRenameLinkTargetTombstone
0x14002c924  mov     ebx, eax
0x14002c926  test    eax, eax
0x14002c928  jns     loc_14002C72D
0x14002c92e  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14002c934  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002c93b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002c942  setnz   r8b
  ... truncated ...
```
