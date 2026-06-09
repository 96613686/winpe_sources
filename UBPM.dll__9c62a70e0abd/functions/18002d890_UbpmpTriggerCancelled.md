# UbpmpTriggerCancelled

- ea: `0x18002d890`
- end: `0x18002dc17`
- name: `UbpmpTriggerCancelled`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008720`
- `0x180008920`
- `0x18000a940`
- `0x18001af64`
- `0x18002d890`
- `0x1800381e0`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002daf2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002daf2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002d9c2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002d9c2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002d99f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002dbe3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002d99f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002dbe3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002da77`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002da77`

## pseudocode

```c
ULONG __fastcall UbpmpTriggerCancelled(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v7; // rsi
  __int64 *v8; // rcx
  __int64 v9; // rax
  bool v10; // zf
  int v11; // eax
  int v12; // r15d
  unsigned int v13; // edx
  __int64 v14; // r8
  unsigned __int16 v15; // di
  unsigned int i; // ebx
  __int64 v17; // r14
  __int64 v18; // r8
  __int64 v19; // r9
  ULONG result; // eax
  __int64 v21; // rax
  __int64 *v22; // rcx
  int v23; // esi
  unsigned int v24; // [rsp+30h] [rbp-61h] BYREF
  __int64 v25; // [rsp+38h] [rbp-59h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-51h] BYREF
  __int64 Source1; // [rsp+50h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-31h] BYREF
  int *v29; // [rsp+70h] [rbp-21h]
  int v30; // [rsp+78h] [rbp-19h]
  int v31; // [rsp+7Ch] [rbp-15h]
  __int64 *v32; // [rsp+80h] [rbp-11h]
  int v33; // [rsp+88h] [rbp-9h]
  int v34; // [rsp+8Ch] [rbp-5h]
  unsigned int *v35; // [rsp+90h] [rbp-1h]
  __int64 v36; // [rsp+98h] [rbp+7h]

  Source1 = a2;
  v25 = a4;
  v7 = -1;
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v8 = *(__int64 **)(*(_QWORD *)(a3 + 24) + 8LL);
    if ( v8 )
    {
      v9 = -1;
      do
        v10 = *((_WORD *)v8 + ++v9) == 0;
      while ( !v10 );
      v11 = 2 * v9 + 2;
    }
    else
    {
      v8 = &qword_1800439C0;
      v11 = 2;
    }
    v33 = v11;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v32 = v8;
    v34 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v29 = &dword_1800461A4;
    UserData.Reserved = 2;
    v30 = 31;
    v31 = 1;
    v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v12 = UbpmConsumerIncPendingActions(a3);
  if ( !v12 )
  {
    RtlAcquireSRWLockShared(a3 + 48);
    if ( (*(_BYTE *)(a3 + 41) & 1) != 0 )
    {
      v13 = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 20LL);
      if ( v13 )
      {
        v14 = *(_QWORD *)(a3 + 32);
        v15 = 0;
        while ( *(_QWORD *)(v14 + 40LL * v15 + 8) != a1 && *(_QWORD *)(v14 + 40LL * v15) != a1 )
        {
          if ( ++v15 >= v13 )
            goto LABEL_27;
        }
        for ( i = 0; i < 5; ++i )
        {
          v17 = 28LL * i;
          if ( RtlCompareMemory(&Source1, (char *)&g_CSebConditions + v17 + 20, 8u) == 8 )
          {
            v12 = 0;
            UbpmpActionTerminatesOnConstraint(
              (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)a3,
              v15,
              *(_DWORD *)((char *)&g_CSebConditions + v17 + 16));
            goto LABEL_27;
          }
        }
        v12 = 1168;
        v18 = v25 + 16;
        v19 = a5 - 20;
        if ( !v25 )
        {
          v19 = a5;
          v18 = 0;
        }
        UbpmpCancelTriggerActions(a3, v15, v18, v19);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL),
          0);
      v12 = 1223;
    }
LABEL_27:
    RtlReleaseSRWLockShared(a3 + 48);
    UbpmConsumerDecPendingActions(a3);
  }
  result = dword_18004F0F0;
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v21 = *(_QWORD *)(a3 + 24);
    v24 = v12;
    v36 = 4;
    v22 = *(__int64 **)(v21 + 8);
    v35 = &v24;
    if ( v22 )
    {
      do
        v10 = *((_WORD *)v22 + ++v7) == 0;
      while ( !v10 );
      v23 = 2 * v7 + 2;
    }
    else
    {
      v22 = &qword_1800439C0;
      v23 = 2;
    }
    *(_DWORD *)&EventDescriptor.Level = 516;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v32 = v22;
    v33 = v23;
    v34 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v29 = (int *)byte_180046145;
    UserData.Reserved = 2;
    v30 = 42;
    v31 = 1;
    LODWORD(v25) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18002d890  mov     [rsp-8+arg_0], rbx
0x18002d895  push    rbp
0x18002d896  push    rsi
0x18002d897  push    rdi
0x18002d898  push    r12
0x18002d89a  push    r13
0x18002d89c  push    r14
0x18002d89e  push    r15
0x18002d8a0  lea     rbp, [rsp-1Fh]
0x18002d8a5  sub     rsp, 0B0h
0x18002d8ac  mov     rax, cs:__security_cookie
0x18002d8b3  xor     rax, rsp
0x18002d8b6  mov     [rbp+4Fh+var_40], rax
0x18002d8ba  mov     eax, cs:dword_18004F0F0
0x18002d8c0  lea     rdi, _TraceLoggingMetadataEnd
0x18002d8c7  xor     r14d, r14d
0x18002d8ca  mov     [rbp+4Fh+Source1], rdx
0x18002d8ce  mov     [rbp+4Fh+var_A8], r9
0x18002d8d2  mov     r13, r8
0x18002d8d5  lea     rdx, _TraceLoggingMetadata
0x18002d8dc  mov     rbx, rcx
0x18002d8df  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002d8e6  cmp     eax, 4
0x18002d8e9  jbe     loc_18002D9AB
0x18002d8ef  mov     rax, [r8+18h]
0x18002d8f3  mov     rcx, [rax+8]
0x18002d8f7  test    rcx, rcx
0x18002d8fa  jz      short loc_18002D915
0x18002d8fc  mov     rax, rsi
0x18002d8ff  nop
0x18002d900  cmp     [rcx+rax*2+2], r14w
0x18002d906  lea     rax, [rax+1]
0x18002d90a  jnz     short loc_18002D900
0x18002d90c  lea     eax, ds:2[rax*2]
0x18002d913  jmp     short loc_18002D921
0x18002d915  lea     rcx, qword_1800439C0
0x18002d91c  mov     eax, 2
0x18002d921  mov     [rbp+4Fh+var_58], eax
0x18002d924  xor     r9d, r9d; RelatedActivityId
0x18002d927  movzx   eax, cs:word_18004619A
0x18002d92e  xor     r8d, r8d; ActivityId
0x18002d931  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18002d934  mov     rax, cs:off_18004F0F8
0x18002d93b  mov     [rbp+4Fh+var_80.Ptr], rax
0x18002d93f  mov     [rbp+4Fh+var_60], rcx
0x18002d943  mov     [rbp+4Fh+var_54], r14d
0x18002d947  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18002d94e  mov     [rbp+4Fh+EventDescriptor.Keyword], r14
0x18002d952  movzx   eax, word ptr [rax]
0x18002d955  mov     [rbp+4Fh+var_80.Size], eax
0x18002d958  lea     rax, dword_1800461A4
0x18002d95f  mov     [rbp+4Fh+var_70], rax
0x18002d963  mov     rax, rdi
0x18002d966  sub     eax, edx
0x18002d968  mov     dword ptr [rbp+4Fh+var_80.0Ch], 2
0x18002d96f  mov     [rbp+4Fh+var_68], 1Fh
0x18002d976  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18002d97a  mov     [rbp+4Fh+var_64], 1
0x18002d981  mov     [rbp+4Fh+var_B0], eax
0x18002d984  mov     eax, [rbp+4Fh+var_B0]
0x18002d987  mov     rcx, cs:RegHandle; RegHandle
0x18002d98e  lea     rax, [rbp+4Fh+var_80]
0x18002d992  mov     [rsp+0E0h+UserData], rax; UserData
0x18002d997  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x18002d99f  call    cs:__imp_EventWriteTransfer
0x18002d9a6  nop     dword ptr [rax+rax+00h]
0x18002d9ab  mov     rcx, r13
0x18002d9ae  call    UbpmConsumerIncPendingActions
0x18002d9b3  mov     r15d, eax
0x18002d9b6  test    eax, eax
0x18002d9b8  jnz     loc_18002DB06
0x18002d9be  lea     rcx, [r13+30h]
0x18002d9c2  call    cs:__imp_RtlAcquireSRWLockShared
0x18002d9c9  nop     dword ptr [rax+rax+00h]
0x18002d9ce  test    byte ptr [r13+29h], 1
0x18002d9d3  jnz     short loc_18002DA1B
0x18002d9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9dc  lea     rax, WPP_GLOBAL_Control
0x18002d9e3  cmp     rcx, rax
0x18002d9e6  jz      short loc_18002DA10
0x18002d9e8  test    byte ptr [rcx+1Ch], 1
0x18002d9ec  jz      short loc_18002DA10
0x18002d9ee  mov     r9, [r13+18h]
0x18002d9f2  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002d9f9  mov     rcx, [rcx+10h]
0x18002d9fd  mov     edx, 3Eh ; '>'
0x18002da02  mov     [rsp+0E0h+UserDataCount], r14d
0x18002da07  mov     r9, [r9+8]
0x18002da0b  call    WPP_SF_Sd
0x18002da10  mov     r15d, 4C7h
0x18002da16  jmp     loc_18002DAEE
0x18002da1b  mov     rax, [r13+18h]
0x18002da1f  mov     edx, [rax+14h]
0x18002da22  test    edx, edx
0x18002da24  jz      loc_18002DAEE
0x18002da2a  mov     r8, [r13+20h]
0x18002da2e  mov     edi, r14d
0x18002da31  movzx   eax, di
0x18002da34  lea     rcx, [rax+rax*4]
0x18002da38  cmp     [r8+rcx*8+8], rbx
0x18002da3d  jz      short loc_18002DA54
0x18002da3f  cmp     [r8+rcx*8], rbx
0x18002da43  jz      short loc_18002DA54
0x18002da45  inc     di
0x18002da48  movzx   eax, di
0x18002da4b  cmp     eax, edx
0x18002da4d  jb      short loc_18002DA31
0x18002da4f  jmp     loc_18002DAE7
0x18002da54  mov     ebx, r14d
0x18002da57  lea     rcx, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002da5e  xchg    ax, ax
0x18002da60  lea     rdx, [rcx+14h]
0x18002da64  mov     eax, ebx
0x18002da66  imul    r14, rax, 1Ch
0x18002da6a  mov     r8d, 8; Length
0x18002da70  lea     rcx, [rbp+4Fh+Source1]; Source1
0x18002da74  add     rdx, r14; Source2
0x18002da77  call    cs:__imp_RtlCompareMemory
0x18002da7e  nop     dword ptr [rax+rax+00h]
0x18002da83  cmp     rax, 8
0x18002da87  jz      short loc_18002DACA
0x18002da89  inc     ebx
0x18002da8b  lea     rcx, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002da92  cmp     ebx, 5
0x18002da95  jb      short loc_18002DA60
0x18002da97  mov     rcx, [rbp+4Fh+var_A8]
0x18002da9b  movzx   edx, di
0x18002da9e  mov     eax, [rbp+4Fh+arg_20]
0x18002daa1  test    rcx, rcx
0x18002daa4  mov     r15d, 490h
0x18002daaa  lea     r8, [rcx+10h]
0x18002daae  lea     r9d, [rax-14h]
0x18002dab2  cmovz   r9d, eax
0x18002dab6  xor     r14d, r14d
0x18002dab9  test    rcx, rcx
0x18002dabc  mov     rcx, r13
0x18002dabf  cmovz   r8, r14
0x18002dac3  call    UbpmpCancelTriggerActions
0x18002dac8  jmp     short loc_18002DAE7
0x18002daca  lea     r8, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002dad1  movzx   edx, di; unsigned int
0x18002dad4  mov     r8d, [r14+r8+10h]; unsigned int
0x18002dad9  mov     rcx, r13; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18002dadc  xor     r15d, r15d
0x18002dadf  call    UbpmpActionTerminatesOnConstraint
0x18002dae4  xor     r14d, r14d
0x18002dae7  lea     rdi, _TraceLoggingMetadataEnd
0x18002daee  lea     rcx, [r13+30h]
0x18002daf2  call    cs:__imp_RtlReleaseSRWLockShared
0x18002daf9  nop     dword ptr [rax+rax+00h]
0x18002dafe  mov     rcx, r13
0x18002db01  call    UbpmConsumerDecPendingActions
0x18002db06  mov     eax, cs:dword_18004F0F0
0x18002db0c  cmp     eax, 4
0x18002db0f  jbe     loc_18002DBEF
0x18002db15  mov     rax, [r13+18h]
0x18002db19  mov     [rbp+4Fh+var_B0], r15d
0x18002db1d  mov     [rbp+4Fh+var_48], 4
0x18002db25  mov     rcx, [rax+8]
0x18002db29  lea     rax, [rbp+4Fh+var_B0]
0x18002db2d  mov     [rbp+4Fh+var_50], rax
0x18002db31  test    rcx, rcx
0x18002db34  jz      short loc_18002DB55
0x18002db36  nop     word ptr [rax+rax+00000000h]
0x18002db40  cmp     word ptr [rcx+rsi*2+2], 0
0x18002db46  lea     rsi, [rsi+1]
0x18002db4a  jnz     short loc_18002DB40
0x18002db4c  lea     esi, ds:2[rsi*2]
0x18002db53  jmp     short loc_18002DB61
0x18002db55  lea     rcx, qword_1800439C0
0x18002db5c  mov     esi, 2
0x18002db61  movzx   eax, cs:word_18004613B
0x18002db68  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x18002db6c  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18002db6f  xor     r9d, r9d; RelatedActivityId
0x18002db72  mov     rax, cs:off_18004F0F8
0x18002db79  xor     r8d, r8d; ActivityId
0x18002db7c  mov     [rbp+4Fh+var_80.Ptr], rax
0x18002db80  mov     [rbp+4Fh+var_60], rcx
0x18002db84  mov     [rbp+4Fh+var_58], esi
0x18002db87  mov     [rbp+4Fh+var_54], r14d
0x18002db8b  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x18002db92  mov     [rbp+4Fh+EventDescriptor.Keyword], r14
0x18002db96  movzx   eax, word ptr [rax]
0x18002db99  mov     [rbp+4Fh+var_80.Size], eax
0x18002db9c  lea     rax, byte_180046145
0x18002dba3  mov     [rbp+4Fh+var_70], rax
0x18002dba7  lea     rax, _TraceLoggingMetadata
0x18002dbae  sub     edi, eax
0x18002dbb0  mov     dword ptr [rbp+4Fh+var_80.0Ch], 2
0x18002dbb7  mov     [rbp+4Fh+var_68], 2Ah ; '*'
0x18002dbbe  mov     [rbp+4Fh+var_64], 1
0x18002dbc5  mov     dword ptr [rbp+4Fh+var_A8], edi
0x18002dbc8  mov     eax, dword ptr [rbp+4Fh+var_A8]
0x18002dbcb  mov     rcx, cs:RegHandle; RegHandle
0x18002dbd2  lea     rax, [rbp+4Fh+var_80]
0x18002dbd6  mov     [rsp+0E0h+UserData], rax; UserData
0x18002dbdb  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x18002dbe3  call    cs:__imp_EventWriteTransfer
0x18002dbea  nop     dword ptr [rax+rax+00h]
0x18002dbef  mov     rcx, [rbp+4Fh+var_40]
0x18002dbf3  xor     rcx, rsp; StackCookie
0x18002dbf6  call    __security_check_cookie
0x18002dbfb  mov     rbx, [rsp+0E0h+arg_0]
0x18002dc03  add     rsp, 0B0h
0x18002dc0a  pop     r15
0x18002dc0c  pop     r14
0x18002dc0e  pop     r13
0x18002dc10  pop     r12
0x18002dc12  pop     rdi
0x18002dc13  pop     rsi
0x18002dc14  pop     rbp
0x18002dc15  retn
```
