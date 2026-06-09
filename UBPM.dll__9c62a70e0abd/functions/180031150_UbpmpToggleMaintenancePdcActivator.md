# UbpmpToggleMaintenancePdcActivator

- ea: `0x180031150`
- end: `0x180031767`
- name: `UbpmpToggleMaintenancePdcActivator`
- size: `1559`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002d770`

## callees

- `0x180002cc4`
- `0x18002fc2c`
- `0x180030ea4`
- `0x180031150`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800315ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x180031635`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800315ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x180031635`
- `ntdll!RtlAcquireSRWLockShared` at `0x18003134f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18003134f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180031183`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180031374`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800313b7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180031183`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180031374`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800313b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800312fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180031592`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800315bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800312fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180031592`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800315bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800312dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003156d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031737`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800312dc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003156d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180031737`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003160a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003160a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003118f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800313c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003118f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800313c3`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180031462`
- `UMPDC!SleepstudyHelperBlockerActiveDereference` at `0x180031462`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180031471`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x180031471`

## pseudocode

```c
int __fastcall UbpmpToggleMaintenancePdcActivator(int a1)
{
  unsigned int v2; // esi
  unsigned __int8 v3; // cl
  int v4; // r12d
  _QWORD *v5; // r14
  char *v6; // r13
  char *v7; // rbx
  _QWORD *v8; // rdi
  _QWORD *v9; // rdx
  __int64 v10; // rsi
  __int64 *v11; // rbx
  __int64 v12; // rax
  bool v13; // zf
  unsigned int v14; // eax
  __int64 *Value; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned int v19; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-65h]
  int v21; // [rsp+38h] [rbp-61h] BYREF
  int v22; // [rsp+3Ch] [rbp-5Dh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+50h] [rbp-49h] BYREF
  __int128 v25; // [rsp+60h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-29h] BYREF
  __int16 *v27; // [rsp+80h] [rbp-19h]
  int v28; // [rsp+88h] [rbp-11h]
  int v29; // [rsp+8Ch] [rbp-Dh]
  int *v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h]
  int *v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]
  unsigned int *v34; // [rsp+B0h] [rbp+17h]
  __int64 v35; // [rsp+B8h] [rbp+1Fh]

  RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
  dword_18004FFE8 = GetCurrentThreadId();
  v20 = 0;
  v2 = 0;
  v24 = 0;
  if ( a1 )
  {
    v3 = 0;
  }
  else
  {
    if ( !(dword_18004FC7C + dword_18004FCBC + dword_18004FCFC + dword_18004FD3C + dword_18004FD7C) )
      goto LABEL_6;
    v3 = 1;
  }
  UbpmTakeMaintenancePdcReference(v3);
LABEL_6:
  if ( (unsigned int)dword_18004F0F0 > 5 && (qword_18004F100 & 4) != 0 && (qword_18004F108 & 4) == qword_18004F108 )
  {
    v32 = &v21;
    v30 = &v22;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18004F0F8;
    v21 = dword_18004FC7C + dword_18004FCBC + dword_18004FCFC + dword_18004FD3C + dword_18004FD7C;
    v22 = a1;
    v33 = 4;
    v31 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 4;
    UserData.Size = *(unsigned __int16 *)off_18004F0F8;
    v27 = &word_180046FE6;
    UserData.Reserved = 2;
    v28 = 76;
    v29 = 1;
    v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  dword_18004FFE8 = 0;
  RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
  if ( !qword_18004FC48 )
  {
    v4 = 10;
    goto LABEL_44;
  }
  UbpmpAcquireListLockShared();
  v5 = g_leConsumerListHead;
  if ( g_leConsumerListHead == (_UNKNOWN *)&g_leConsumerListHead )
    goto LABEL_38;
  do
  {
    v6 = (char *)(v5 + 5);
    RtlAcquireSRWLockShared(v5 + 5);
    if ( !*(_QWORD *)(v5[2] + 48LL) )
      goto LABEL_36;
    v7 = (char *)(v5 + 25);
    RtlAcquireSRWLockExclusive(v5 + 25);
    *((_DWORD *)v5 + 52) = GetCurrentThreadId();
    v8 = (_QWORD *)v5[27];
    if ( v8 == v5 + 27 )
      goto LABEL_35;
    do
    {
      RtlAcquireSRWLockExclusive(&g_MaintenanceLaunchLock);
      dword_18004FFE8 = GetCurrentThreadId();
      if ( !qword_18004FC38 )
        goto LABEL_33;
      if ( byte_18004FC40 == 1 )
      {
        if ( v8[2] )
          goto LABEL_33;
        v9 = (_QWORD *)v5[2];
        v25 = *(_OWORD *)((char *)v8 + 52);
        if ( (int)UbpmpSleepStudyStartReportingBlocker(qword_18004FC48, *v9, v9[1], &v25, &v24) >= 0 )
        {
          v8[2] = v24;
          v24 = 0;
        }
        else
        {
          v20 = 10;
        }
      }
      if ( !byte_18004FC40 )
      {
        v10 = v8[2];
        if ( v10 )
        {
          v11 = *(__int64 **)(v5[2] + 8LL);
          SleepstudyHelperBlockerActiveDereference(v8[2]);
          SleepstudyHelperDestroyBlocker(v10);
          if ( (unsigned int)dword_18004F0F0 > 5
            && (qword_18004F100 & 4) != 0
            && (qword_18004F108 & 4) == qword_18004F108 )
          {
            if ( v11 )
            {
              v12 = -1;
              do
                v13 = *((_WORD *)v11 + ++v12) == 0;
              while ( !v13 );
              v14 = 2 * v12 + 2;
            }
            else
            {
              v11 = &qword_1800439C0;
              v14 = 2;
            }
            v31 = v14;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_18004F0F8;
            v30 = (int *)v11;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 4;
            UserData.Size = *(unsigned __int16 *)off_18004F0F8;
            v27 = (__int16 *)byte_180046FAD;
            UserData.Reserved = 2;
            v28 = 45;
            v29 = 1;
            v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
          }
          v8[2] = 0;
        }
      }
LABEL_33:
      dword_18004FFE8 = 0;
      RtlReleaseSRWLockExclusive(&g_MaintenanceLaunchLock);
      v8 = (_QWORD *)*v8;
    }
    while ( v8 != v5 + 27 );
    v6 = (char *)(v5 + 5);
    v7 = (char *)(v5 + 25);
LABEL_35:
    *((_DWORD *)v7 + 2) = 0;
    RtlReleaseSRWLockExclusive(v7);
LABEL_36:
    RtlReleaseSRWLockShared(v6);
    v5 = (_QWORD *)*v5;
  }
  while ( v5 != &g_leConsumerListHead );
  v2 = v20;
LABEL_38:
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = (__int64 *)TlsGetValue(UbpmpLockTrackerId);
    v16 = *Value;
    if ( (*Value & 2) == 0 )
      __int2c();
    v13 = Value[2]-- == 1;
    if ( v13 )
      *Value = v16 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  RtlReleaseSRWLockShared(&g_ConsumerListLock);
  v4 = 0;
LABEL_44:
  LODWORD(v17) = dword_18004F0F0;
  if ( (unsigned int)dword_18004F0F0 > 5 )
  {
    LODWORD(v17) = qword_18004F100;
    if ( (qword_18004F100 & 4) != 0 )
    {
      v17 = qword_18004F108 & 4;
      if ( v17 == qword_18004F108 )
      {
        v19 = v2;
        v34 = &v19;
        v22 = 0;
        v32 = &v22;
        v21 = v4;
        v30 = &v21;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18004F0F8;
        v35 = 4;
        v33 = 4;
        v31 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 4;
        UserData.Size = *(unsigned __int16 *)off_18004F0F8;
        v27 = word_18004728A;
        UserData.Reserved = 2;
        v28 = 88;
        v29 = 1;
        v20 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v17) = EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x180031150  push    rbp
0x180031152  push    rsi
0x180031153  push    rdi
0x180031154  push    r14
0x180031156  push    r15
0x180031158  lea     rbp, [rsp-37h]
0x18003115d  sub     rsp, 0D0h
0x180031164  mov     rax, cs:__security_cookie
0x18003116b  xor     rax, rsp
0x18003116e  mov     [rbp+57h+var_30], rax
0x180031172  mov     [rsp+0F0h+arg_0], rbx
0x18003117a  mov     ebx, ecx
0x18003117c  lea     rcx, g_MaintenanceLaunchLock
0x180031183  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003118a  nop     dword ptr [rax+rax+00h]
0x18003118f  call    cs:__imp_GetCurrentThreadId
0x180031196  nop     dword ptr [rax+rax+00h]
0x18003119b  xor     r15d, r15d
0x18003119e  mov     cs:dword_18004FFE8, eax
0x1800311a4  mov     [rbp+57h+var_BC], r15d
0x1800311a8  mov     esi, r15d
0x1800311ab  mov     [rbp+57h+var_A0], r15
0x1800311af  test    ebx, ebx
0x1800311b1  jz      short loc_1800311B7
0x1800311b3  xor     ecx, ecx
0x1800311b5  jmp     short loc_1800311D9
0x1800311b7  mov     edx, cs:dword_18004FD7C
0x1800311bd  add     edx, cs:dword_18004FD3C
0x1800311c3  add     edx, cs:dword_18004FCFC
0x1800311c9  add     edx, cs:dword_18004FCBC
0x1800311cf  add     edx, cs:dword_18004FC7C
0x1800311d5  jz      short loc_1800311DE
0x1800311d7  mov     cl, 1; unsigned __int8
0x1800311d9  call    ?UbpmTakeMaintenancePdcReference@@YAXE@Z; UbpmTakeMaintenancePdcReference(uchar)
0x1800311de  mov     eax, cs:dword_18004F0F0
0x1800311e4  lea     rdi, _TraceLoggingMetadataEnd
0x1800311eb  lea     r14, _TraceLoggingMetadata
0x1800311f2  cmp     eax, 5
0x1800311f5  jbe     loc_1800312E8
0x1800311fb  mov     rcx, cs:qword_18004F108
0x180031202  mov     rax, cs:qword_18004F100
0x180031209  test    al, 4
0x18003120b  jz      loc_1800312E8
0x180031211  mov     rax, rcx
0x180031214  and     eax, 4
0x180031217  cmp     rax, rcx
0x18003121a  jnz     loc_1800312E8
0x180031220  mov     edx, cs:dword_18004FD7C
0x180031226  lea     rax, [rbp+57h+var_B8]
0x18003122a  add     edx, cs:dword_18004FD3C
0x180031230  xor     r9d, r9d; RelatedActivityId
0x180031233  add     edx, cs:dword_18004FCFC
0x180031239  xor     r8d, r8d; ActivityId
0x18003123c  add     edx, cs:dword_18004FCBC
0x180031242  add     edx, cs:dword_18004FC7C
0x180031248  mov     [rbp+57h+var_50], rax
0x18003124c  lea     rax, [rbp+57h+var_B4]
0x180031250  mov     [rbp+57h+var_60], rax
0x180031254  movzx   eax, cs:word_180046FDC
0x18003125b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18003125e  mov     rax, cs:off_18004F0F8
0x180031265  mov     [rbp+57h+var_80.Ptr], rax
0x180031269  mov     [rbp+57h+var_B8], edx
0x18003126c  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180031270  mov     [rbp+57h+var_B4], ebx
0x180031273  mov     [rbp+57h+var_48], 4
0x18003127b  mov     [rbp+57h+var_58], 4
0x180031283  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18003128a  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x180031292  movzx   eax, word ptr [rax]
0x180031295  mov     [rbp+57h+var_80.Size], eax
0x180031298  lea     rax, word_180046FE6
0x18003129f  mov     [rbp+57h+var_70], rax
0x1800312a3  mov     rax, rdi
0x1800312a6  sub     eax, r14d
0x1800312a9  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x1800312b0  mov     [rbp+57h+var_68], 4Ch ; 'L'
0x1800312b7  mov     [rbp+57h+var_64], 1
0x1800312be  mov     [rbp+57h+var_C0], eax
0x1800312c1  mov     eax, [rbp+57h+var_C0]
0x1800312c4  mov     rcx, cs:RegHandle; RegHandle
0x1800312cb  lea     rax, [rbp+57h+var_80]
0x1800312cf  mov     [rsp+0F0h+UserData], rax; UserData
0x1800312d4  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x1800312dc  call    cs:__imp_EventWriteTransfer
0x1800312e3  nop     dword ptr [rax+rax+00h]
0x1800312e8  lea     rcx, g_MaintenanceLaunchLock
0x1800312ef  mov     [rsp+0F0h+arg_8], r12
0x1800312f7  mov     cs:dword_18004FFE8, r15d
0x1800312fe  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180031305  nop     dword ptr [rax+rax+00h]
0x18003130a  cmp     cs:qword_18004FC48, rsi
0x180031311  jnz     short loc_18003131E
0x180031313  mov     r12d, 0Ah
0x180031319  jmp     loc_18003164B
0x18003131e  call    UbpmpAcquireListLockShared
0x180031323  mov     r14, cs:g_leConsumerListHead
0x18003132a  lea     rax, g_leConsumerListHead
0x180031331  cmp     r14, rax
0x180031334  jz      loc_1800315FF
0x18003133a  mov     [rsp+0F0h+arg_10], r13
0x180031342  mov     r12d, 0Ah
0x180031348  lea     r13, [r14+28h]
0x18003134c  mov     rcx, r13
0x18003134f  call    cs:__imp_RtlAcquireSRWLockShared
0x180031356  nop     dword ptr [rax+rax+00h]
0x18003135b  mov     rax, [r14+10h]
0x18003135f  cmp     qword ptr [rax+30h], 0
0x180031364  jz      loc_1800315CB
0x18003136a  lea     rbx, [r14+0C8h]
0x180031371  mov     rcx, rbx
0x180031374  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003137b  nop     dword ptr [rax+rax+00h]
0x180031380  call    cs:__imp_GetCurrentThreadId
0x180031387  nop     dword ptr [rax+rax+00h]
0x18003138c  lea     r15, [r14+0D8h]
0x180031393  mov     [rbx+8], eax
0x180031396  mov     rdi, [r15]
0x180031399  cmp     rdi, r15
0x18003139c  jz      loc_1800315B5
0x1800313a2  lea     r13, _TraceLoggingMetadataEnd
0x1800313a9  nop     dword ptr [rax+00000000h]
0x1800313b0  lea     rcx, g_MaintenanceLaunchLock
0x1800313b7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800313be  nop     dword ptr [rax+rax+00h]
0x1800313c3  call    cs:__imp_GetCurrentThreadId
0x1800313ca  nop     dword ptr [rax+rax+00h]
0x1800313cf  cmp     cs:qword_18004FC38, 0
0x1800313d7  mov     cs:dword_18004FFE8, eax
0x1800313dd  jz      loc_180031581
0x1800313e3  cmp     cs:byte_18004FC40, 1
0x1800313ea  jnz     short loc_18003143D
0x1800313ec  cmp     qword ptr [rdi+10h], 0
0x1800313f1  jnz     loc_180031581
0x1800313f7  mov     rdx, [r14+10h]
0x1800313fb  lea     rax, [rbp+57h+var_A0]
0x1800313ff  movups  xmm0, xmmword ptr [rdi+34h]
0x180031403  mov     rcx, cs:qword_18004FC48
0x18003140a  lea     r9, [rbp+57h+var_90]
0x18003140e  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x180031413  movaps  [rbp+57h+var_90], xmm0
0x180031417  mov     r8, [rdx+8]
0x18003141b  mov     rdx, [rdx]
0x18003141e  call    UbpmpSleepStudyStartReportingBlocker
0x180031423  test    eax, eax
0x180031425  jns     short loc_18003142D
0x180031427  mov     [rbp+57h+var_BC], r12d
0x18003142b  jmp     short loc_18003143D
0x18003142d  mov     rax, [rbp+57h+var_A0]
0x180031431  mov     [rdi+10h], rax
0x180031435  mov     [rbp+57h+var_A0], 0
0x18003143d  cmp     cs:byte_18004FC40, 0
0x180031444  jnz     loc_180031581
0x18003144a  mov     rsi, [rdi+10h]
0x18003144e  test    rsi, rsi
0x180031451  jz      loc_180031581
0x180031457  mov     rax, [r14+10h]
0x18003145b  mov     rcx, rsi
0x18003145e  mov     rbx, [rax+8]
0x180031462  call    cs:__imp_SleepstudyHelperBlockerActiveDereference
0x180031469  nop     dword ptr [rax+rax+00h]
0x18003146e  mov     rcx, rsi
0x180031471  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x180031478  nop     dword ptr [rax+rax+00h]
0x18003147d  mov     eax, cs:dword_18004F0F0
0x180031483  cmp     eax, 5
0x180031486  jbe     loc_180031579
0x18003148c  mov     rcx, cs:qword_18004F108
0x180031493  mov     rax, cs:qword_18004F100
0x18003149a  test    al, 4
0x18003149c  jz      loc_180031579
0x1800314a2  mov     rax, rcx
0x1800314a5  and     eax, 4
0x1800314a8  cmp     rax, rcx
0x1800314ab  jnz     loc_180031579
0x1800314b1  test    rbx, rbx
0x1800314b4  jz      short loc_1800314D5
0x1800314b6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800314bd  nop     dword ptr [rax]
0x1800314c0  cmp     word ptr [rbx+rax*2+2], 0
0x1800314c6  lea     rax, [rax+1]
0x1800314ca  jnz     short loc_1800314C0
0x1800314cc  lea     eax, ds:2[rax*2]
0x1800314d3  jmp     short loc_1800314E1
0x1800314d5  lea     rbx, qword_1800439C0
0x1800314dc  mov     eax, 2
0x1800314e1  mov     dword ptr [rbp+57h+var_58], eax
0x1800314e4  lea     rcx, _TraceLoggingMetadata
0x1800314eb  movzx   eax, cs:word_180046FA3
0x1800314f2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800314f6  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800314f9  xor     r9d, r9d; RelatedActivityId
0x1800314fc  mov     rax, cs:off_18004F0F8
0x180031503  xor     r8d, r8d; ActivityId
0x180031506  mov     [rbp+57h+var_80.Ptr], rax
0x18003150a  mov     [rbp+57h+var_60], rbx
0x18003150e  mov     dword ptr [rbp+57h+var_58+4], 0
0x180031515  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18003151c  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x180031524  movzx   eax, word ptr [rax]
0x180031527  mov     [rbp+57h+var_80.Size], eax
0x18003152a  lea     rax, byte_180046FAD
0x180031531  mov     [rbp+57h+var_70], rax
0x180031535  mov     rax, r13
0x180031538  sub     eax, ecx
0x18003153a  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180031541  mov     [rbp+57h+var_68], 2Dh ; '-'
0x180031548  mov     [rbp+57h+var_64], 1
0x18003154f  mov     [rbp+57h+var_C0], eax
0x180031552  mov     eax, [rbp+57h+var_C0]
0x180031555  mov     rcx, cs:RegHandle; RegHandle
0x18003155c  lea     rax, [rbp+57h+var_80]
0x180031560  mov     [rsp+0F0h+UserData], rax; UserData
0x180031565  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x18003156d  call    cs:__imp_EventWriteTransfer
0x180031574  nop     dword ptr [rax+rax+00h]
0x180031579  mov     qword ptr [rdi+10h], 0
0x180031581  lea     rcx, g_MaintenanceLaunchLock
0x180031588  mov     cs:dword_18004FFE8, 0
0x180031592  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180031599  nop     dword ptr [rax+rax+00h]
0x18003159e  mov     rdi, [rdi]
0x1800315a1  cmp     rdi, r15
0x1800315a4  jnz     loc_1800313B0
0x1800315aa  lea     r13, [r14+28h]
0x1800315ae  lea     rbx, [r14+0C8h]
0x1800315b5  xor     r15d, r15d
0x1800315b8  mov     rcx, rbx
0x1800315bb  mov     [rbx+8], r15d
0x1800315bf  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800315c6  nop     dword ptr [rax+rax+00h]
0x1800315cb  mov     rcx, r13
0x1800315ce  call    cs:__imp_RtlReleaseSRWLockShared
0x1800315d5  nop     dword ptr [rax+rax+00h]
0x1800315da  mov     r14, [r14]
0x1800315dd  lea     rax, g_leConsumerListHead
0x1800315e4  cmp     r14, rax
0x1800315e7  jnz     loc_180031348
0x1800315ed  mov     r13, [rsp+0F0h+arg_10]
0x1800315f5  lea     rdi, _TraceLoggingMetadataEnd
0x1800315fc  mov     esi, [rbp+57h+var_BC]
0x1800315ff  mov     ecx, cs:UbpmpLockTrackerId; dwTlsIndex
0x180031605  cmp     ecx, 0FFFFFFFFh
0x180031608  jz      short loc_18003162E
0x18003160a  call    cs:__imp_TlsGetValue
0x180031611  nop     dword ptr [rax+rax+00h]
0x180031616  mov     rdx, [rax]
0x180031619  test    dl, 2
0x18003161c  jnz     short loc_180031620
0x18003161e  int     2Ch; Windows NT - assertion failure
0x180031620  sub     qword ptr [rax+10h], 1
0x180031625  jnz     short loc_18003162E
0x180031627  and     rdx, 0FFFFFFFFFFFFFFFDh
0x18003162b  mov     [rax], rdx
0x18003162e  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x180031635  call    cs:__imp_RtlReleaseSRWLockShared
0x18003163c  nop     dword ptr [rax+rax+00h]
0x180031641  mov     r12d, r15d
0x180031644  lea     r14, _TraceLoggingMetadata
0x18003164b  mov     eax, cs:dword_18004F0F0
0x180031651  mov     rbx, [rsp+0F0h+arg_0]
0x180031659  cmp     eax, 5
0x18003165c  jbe     loc_180031743
0x180031662  mov     rcx, cs:qword_18004F108
0x180031669  mov     rax, cs:qword_18004F100
0x180031670  test    al, 4
0x180031672  jz      loc_180031743
0x180031678  mov     rax, rcx
0x18003167b  and     eax, 4
0x18003167e  cmp     rax, rcx
0x180031681  jnz     loc_180031743
0x180031687  mov     [rbp+57h+var_C0], esi
0x18003168a  lea     rax, [rbp+57h+var_C0]
0x18003168e  mov     [rbp+57h+var_40], rax
0x180031692  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180031696  mov     [rbp+57h+var_B4], r15d
0x18003169a  lea     rax, [rbp+57h+var_B4]
0x18003169e  mov     [rbp+57h+var_50], rax
0x1800316a2  sub     edi, r14d
0x1800316a5  lea     rax, [rbp+57h+var_B8]
0x1800316a9  mov     [rbp+57h+var_B8], r12d
0x1800316ad  mov     [rbp+57h+var_60], rax
0x1800316b1  xor     r9d, r9d; RelatedActivityId
0x1800316b4  movzx   eax, cs:word_180047280
0x1800316bb  xor     r8d, r8d; ActivityId
0x1800316be  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800316c1  mov     rax, cs:off_18004F0F8
0x1800316c8  mov     [rbp+57h+var_80.Ptr], rax
0x1800316cc  mov     [rbp+57h+var_38], 4
0x1800316d4  mov     [rbp+57h+var_48], 4
0x1800316dc  mov     [rbp+57h+var_58], 4
0x1800316e4  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800316eb  mov     [rbp+57h+EventDescriptor.Keyword], 4
0x1800316f3  movzx   eax, word ptr [rax]
0x1800316f6  mov     [rbp+57h+var_80.Size], eax
0x1800316f9  lea     rax, word_18004728A
0x180031700  mov     [rbp+57h+var_70], rax
0x180031704  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18003170b  mov     [rbp+57h+var_68], 58h ; 'X'
0x180031712  mov     [rbp+57h+var_64], 1
  ... truncated ...
```
