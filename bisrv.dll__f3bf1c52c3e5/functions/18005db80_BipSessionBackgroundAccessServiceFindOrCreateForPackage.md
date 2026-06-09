# BipSessionBackgroundAccessServiceFindOrCreateForPackage

- ea: `0x18005db80`
- end: `0x18005ddfd`
- name: `BipSessionBackgroundAccessServiceFindOrCreateForPackage`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180056ff0`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x180013190`
- `0x18005d730`
- `0x18005db80`
- `0x18006a8d4`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18005dc2f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005dc2f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005dc05`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005dc05`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005dc64`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005dc64`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ddce`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ddce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005dbe8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005dbe8`

## pseudocode

```c
__int64 __fastcall BipSessionBackgroundAccessServiceFindOrCreateForPackage(__int64 a1, _QWORD *a2)
{
  int v4; // ebx
  __int64 v5; // r15
  unsigned int ActiveSessionId; // edi
  int v7; // ebx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v8; // rcx
  int v9; // ebx
  int v11; // ebx
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v15; // eax
  __int64 v16; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v18; // [rsp+3Ch] [rbp-4Dh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  __int16 *v21; // [rsp+60h] [rbp-29h]
  int v22; // [rsp+68h] [rbp-21h]
  int v23; // [rsp+6Ch] [rbp-1Dh]
  __int64 *v24; // [rsp+70h] [rbp-19h]
  int v25; // [rsp+78h] [rbp-11h]
  int v26; // [rsp+7Ch] [rbp-Dh]
  unsigned int *v27; // [rsp+80h] [rbp-9h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  int *v29; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]

  v16 = 0;
  BipAcquireGlobalLock();
  v4 = 1 << dword_1800C46D8;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v5 + 4) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
  RtlAcquireSRWLockShared(BipSessionLock);
  *(_DWORD *)(v5 + 4) |= v4;
  ActiveSessionId = BipPackageGetActiveSessionId(a1);
  v7 = ~(1 << dword_1800C46D8);
  RtlReleaseSRWLockShared(BipSessionLock);
  *(_DWORD *)(v5 + 4) &= v7;
  BipLockWatchdogContextDisarmWatchdog(v8);
  v9 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  *(_DWORD *)(v5 + 8) &= v9;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v5 + 4) &= v9;
  if ( ActiveSessionId == -1 )
    return 3221225567LL;
  v11 = BipSessionBackgroundAccessServiceFindOrCreate(ActiveSessionId, &v16);
  if ( v11 < 0 )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v17 = v11;
      v29 = &v17;
      v12 = (__int64 *)(a1 + 416);
      v18 = ActiveSessionId;
      v27 = &v18;
      v30 = 4;
      v28 = 4;
      if ( a1 == -416 )
      {
        v12 = &qword_1800A1670;
        v15 = 2;
      }
      else
      {
        v13 = -1;
        while ( *((_WORD *)v12 + ++v13) != 0 )
          ;
        v15 = 2 * v13 + 2;
      }
      v25 = v15;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v24 = v12;
      v26 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 3;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v21 = word_1800B3ECA;
      UserData.Reserved = 2;
      v22 = 75;
      v23 = 1;
      LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
    return (unsigned int)v11;
  }
  else
  {
    *a2 = v16;
    return 0;
  }
}

```

## disassembly

```asm
0x18005db80  mov     [rsp-8+arg_10], rbx
0x18005db85  push    rbp
0x18005db86  push    rsi
0x18005db87  push    rdi
0x18005db88  push    r12
0x18005db8a  push    r13
0x18005db8c  push    r14
0x18005db8e  push    r15
0x18005db90  lea     rbp, [rsp-27h]
0x18005db95  sub     rsp, 0B0h
0x18005db9c  mov     rax, cs:__security_cookie
0x18005dba3  xor     rax, rsp
0x18005dba6  mov     [rbp+57h+var_40], rax
0x18005dbaa  xor     r13d, r13d
0x18005dbad  mov     rsi, rdx
0x18005dbb0  mov     [rbp+57h+var_B0], r13
0x18005dbb4  mov     r14, rcx
0x18005dbb7  call    BipAcquireGlobalLock
0x18005dbbc  mov     edx, cs:_tls_index
0x18005dbc2  mov     ebx, 1
0x18005dbc7  mov     rax, gs:58h
0x18005dbd0  mov     ecx, cs:dword_1800C46D8
0x18005dbd6  mov     r12d, 4
0x18005dbdc  shl     ebx, cl
0x18005dbde  mov     r15, [rax+rdx*8]
0x18005dbe2  cmp     [r12+r15], ebx
0x18005dbe6  jb      short loc_18005DBFE
0x18005dbe8  call    cs:__imp_IsDebuggerPresent
0x18005dbee  test    eax, eax
0x18005dbf0  jz      short loc_18005DBFE
0x18005dbf2  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x18005dbf9  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18005dbfe  lea     rcx, BipSessionLock
0x18005dc05  call    cs:__imp_RtlAcquireSRWLockShared
0x18005dc0b  or      [r12+r15], ebx
0x18005dc0f  mov     rcx, r14
0x18005dc12  call    BipPackageGetActiveSessionId
0x18005dc17  mov     ecx, cs:dword_1800C46D8
0x18005dc1d  mov     ebx, 1
0x18005dc22  shl     ebx, cl
0x18005dc24  mov     edi, eax
0x18005dc26  lea     rcx, BipSessionLock
0x18005dc2d  not     ebx
0x18005dc2f  call    cs:__imp_RtlReleaseSRWLockShared
0x18005dc35  and     [r12+r15], ebx
0x18005dc39  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005dc3e  mov     ecx, cs:dword_1800C3CB0
0x18005dc44  mov     ebx, 1
0x18005dc49  shl     ebx, cl
0x18005dc4b  lea     rcx, BipGlobalLock
0x18005dc52  mov     eax, 8
0x18005dc57  not     ebx
0x18005dc59  mov     cs:dword_1800C3CB4, r13d
0x18005dc60  and     [rax+r15], ebx
0x18005dc64  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005dc6a  and     [r12+r15], ebx
0x18005dc6e  cmp     edi, 0FFFFFFFFh
0x18005dc71  jnz     short loc_18005DC7D
0x18005dc73  mov     eax, 0C000005Fh
0x18005dc78  jmp     loc_18005DDD6
0x18005dc7d  lea     rdx, [rbp+57h+var_B0]
0x18005dc81  mov     ecx, edi
0x18005dc83  call    BipSessionBackgroundAccessServiceFindOrCreate
0x18005dc88  mov     ebx, eax
0x18005dc8a  test    eax, eax
0x18005dc8c  js      short loc_18005DC9D
0x18005dc8e  mov     rax, [rbp+57h+var_B0]
0x18005dc92  mov     [rsi], rax
0x18005dc95  mov     eax, r13d
0x18005dc98  jmp     loc_18005DDD6
0x18005dc9d  mov     rcx, [rbp+57h+var_B0]
0x18005dca1  test    rcx, rcx
0x18005dca4  jz      short loc_18005DCB2
0x18005dca6  mov     rax, [rcx]
0x18005dca9  mov     rax, [rax+10h]
0x18005dcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcb2  mov     eax, cs:dword_1800C3098
0x18005dcb8  cmp     eax, 2
0x18005dcbb  jbe     loc_18005DDD4
0x18005dcc1  mov     rcx, cs:qword_1800C30B0
0x18005dcc8  mov     rax, cs:qword_1800C30A8
0x18005dccf  test    al, 3
0x18005dcd1  jz      loc_18005DDD4
0x18005dcd7  mov     rax, rcx
0x18005dcda  and     eax, 3
0x18005dcdd  cmp     rax, rcx
0x18005dce0  jnz     loc_18005DDD4
0x18005dce6  lea     rax, [rbp+57h+var_A8]
0x18005dcea  mov     [rbp+57h+var_A8], ebx
0x18005dced  mov     [rbp+57h+var_50], rax
0x18005dcf1  lea     rcx, [r14+1A0h]
0x18005dcf8  mov     [rbp+57h+var_A4], edi
0x18005dcfb  lea     rax, [rbp+57h+var_A4]
0x18005dcff  mov     [rbp+57h+var_60], rax
0x18005dd03  mov     [rbp+57h+var_48], 4
0x18005dd0b  mov     [rbp+57h+var_58], 4
0x18005dd13  test    rcx, rcx
0x18005dd16  jz      short loc_18005DD35
0x18005dd18  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005dd1f  nop
0x18005dd20  cmp     [rcx+rax*2+2], r13w
0x18005dd26  lea     rax, [rax+1]
0x18005dd2a  jnz     short loc_18005DD20
0x18005dd2c  lea     eax, ds:2[rax*2]
0x18005dd33  jmp     short loc_18005DD41
0x18005dd35  lea     rcx, qword_1800A1670
0x18005dd3c  mov     eax, 2
0x18005dd41  mov     [rbp+57h+var_68], eax
0x18005dd44  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18005dd48  movzx   eax, cs:word_1800B3EC0
0x18005dd4f  xor     r9d, r9d; RelatedActivityId
0x18005dd52  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18005dd55  xor     r8d, r8d; ActivityId
0x18005dd58  mov     rax, cs:off_1800C30A0
0x18005dd5f  mov     [rbp+57h+var_90.Ptr], rax
0x18005dd63  mov     [rbp+57h+var_70], rcx
0x18005dd67  lea     rcx, _TraceLoggingMetadata
0x18005dd6e  mov     [rbp+57h+var_64], r13d
0x18005dd72  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18005dd79  mov     [rbp+57h+EventDescriptor.Keyword], 3
0x18005dd81  movzx   eax, word ptr [rax]
0x18005dd84  mov     [rbp+57h+var_90.Size], eax
0x18005dd87  lea     rax, word_1800B3ECA
0x18005dd8e  mov     [rbp+57h+var_80], rax
0x18005dd92  lea     rax, _TraceLoggingMetadataEnd
0x18005dd99  sub     eax, ecx
0x18005dd9b  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18005dda2  mov     [rbp+57h+var_78], 4Bh ; 'K'
0x18005dda9  mov     [rbp+57h+var_74], 1
0x18005ddb0  mov     dword ptr [rbp+57h+var_B0], eax
0x18005ddb3  mov     eax, dword ptr [rbp+57h+var_B0]
0x18005ddb6  mov     rcx, cs:RegHandle; RegHandle
0x18005ddbd  lea     rax, [rbp+57h+var_90]
0x18005ddc1  mov     [rsp+0E0h+UserData], rax; UserData
0x18005ddc6  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x18005ddce  call    cs:__imp_EventWriteTransfer
0x18005ddd4  mov     eax, ebx
0x18005ddd6  mov     rcx, [rbp+57h+var_40]
0x18005ddda  xor     rcx, rsp; StackCookie
0x18005dddd  call    __security_check_cookie
0x18005dde2  mov     rbx, [rsp+0E0h+arg_10]
0x18005ddea  add     rsp, 0B0h
0x18005ddf1  pop     r15
0x18005ddf3  pop     r14
0x18005ddf5  pop     r13
0x18005ddf7  pop     r12
0x18005ddf9  pop     rdi
0x18005ddfa  pop     rsi
0x18005ddfb  pop     rbp
0x18005ddfc  retn
```
