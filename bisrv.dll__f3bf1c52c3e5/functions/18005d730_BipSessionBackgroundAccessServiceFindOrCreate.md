# BipSessionBackgroundAccessServiceFindOrCreate

- ea: `0x18005d730`
- end: `0x18005db73`
- name: `BipSessionBackgroundAccessServiceFindOrCreate`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18005db80`

## callees

- `0x1800066e8`
- `0x180051dfc`
- `0x18005d730`
- `0x18006a8d4`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18005d815`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005d9a5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005d815`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005d9a5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005d7bd`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005d7bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005da5e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005da5e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005dad2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005db45`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005dad2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005db45`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005d93e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005d93e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005da64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005da64`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005d798`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005da41`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005d798`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005da41`

## pseudocode

```c
__int64 __fastcall BipSessionBackgroundAccessServiceFindOrCreate(unsigned int a1, _QWORD *a2)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  int v4; // ebx
  __int64 v6; // r13
  __int64 v7; // rax
  int v8; // edi
  int v9; // r15d
  __int128 *v10; // r12
  int v11; // ebx
  __int64 v13; // rbx
  int v14; // ebx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // ebx
  __int64 v22; // rdi
  int v23; // ebx
  int v24; // [rsp+38h] [rbp-89h] BYREF
  int v25; // [rsp+3Ch] [rbp-85h] BYREF
  _DWORD v26[2]; // [rsp+40h] [rbp-81h] BYREF
  __int128 v27; // [rsp+48h] [rbp-79h] BYREF
  __int64 v28; // [rsp+58h] [rbp-69h]
  __int128 *v29; // [rsp+60h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-49h] BYREF
  char *v32; // [rsp+88h] [rbp-39h]
  int v33; // [rsp+90h] [rbp-31h]
  int v34; // [rsp+94h] [rbp-2Dh]
  _DWORD *v35; // [rsp+98h] [rbp-29h]
  __int64 v36; // [rsp+A0h] [rbp-21h]
  __int128 **v37; // [rsp+A8h] [rbp-19h]
  __int64 v38; // [rsp+B0h] [rbp-11h]
  int *v39; // [rsp+B8h] [rbp-9h]
  __int64 v40; // [rsp+C0h] [rbp-1h]
  int *v41; // [rsp+C8h] [rbp+7h]
  __int64 v42; // [rsp+D0h] [rbp+Fh]

  v28 = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v4 = 1 << dword_1800C46D8;
  v27 = 0;
  v6 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  if ( *(_DWORD *)(v6 + 4) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
  RtlAcquireSRWLockShared(BipSessionLock);
  v7 = qword_1800C4400;
  *(_DWORD *)(v6 + 4) |= v4;
  if ( (__int64 *)v7 == &qword_1800C4400 )
  {
LABEL_7:
    v8 = -1073741275;
    v9 = 1000;
LABEL_8:
    v10 = 0;
    v11 = ~(1 << dword_1800C46D8);
    RtlReleaseSRWLockShared(BipSessionLock);
    *(_DWORD *)(v6 + 4) &= v11;
    goto LABEL_9;
  }
  while ( *(_DWORD *)(v7 + 56) != a1 )
  {
    v7 = *(_QWORD *)v7;
    if ( (__int64 *)v7 == &qword_1800C4400 )
      goto LABEL_7;
  }
  v13 = *(_QWORD *)(v7 + 64);
  if ( v13 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*(_QWORD *)(v7 + 64));
    *a2 = v13;
    v8 = 0;
    v9 = 0;
    goto LABEL_8;
  }
  v14 = ~(1 << dword_1800C46D8);
  RtlReleaseSRWLockShared(BipSessionLock);
  *(_DWORD *)(v6 + 4) &= v14;
  v10 = &v27;
  v8 = BipSystemBackgroundAccessContextAllocateState(&v27, a1);
  if ( v8 >= 0 )
  {
    v24 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)v27 + 152LL))(v27, *((_QWORD *)&v27 + 1), &v24);
    if ( v15 >= 0 )
    {
      LODWORD(v28) = v24;
    }
    else
    {
      v8 = (unsigned __int16)v15;
      v16 = (unsigned __int16)v15 | 0xC0070000;
      if ( v8 )
        v8 = v16;
      if ( v8 < 0 )
      {
        v9 = 3000;
        BipSystemBackgroundAccessContextCleanup(&v27);
        goto LABEL_9;
      }
    }
    v17 = 1 << dword_1800C46D8;
    if ( *(_DWORD *)(v6 + 4) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
      BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
    RtlAcquireSRWLockExclusive(BipSessionLock);
    CurrentThreadId = GetCurrentThreadId();
    *(_DWORD *)(v6 + 4) |= v17;
    dword_1800C46DC = CurrentThreadId;
    v19 = qword_1800C4400;
    *(_DWORD *)(v6 + 8) |= v17;
    v20 = *(unsigned int *)(v6 + 8);
    if ( (__int64 *)v19 == &qword_1800C4400 )
    {
LABEL_30:
      v8 = -1073741275;
      v21 = ~(1 << dword_1800C46D8);
      dword_1800C46DC = 0;
      v9 = 4000;
      *(_DWORD *)(v6 + 8) = v20 & v21;
      RtlReleaseSRWLockExclusive(BipSessionLock);
      *(_DWORD *)(v6 + 4) &= v21;
      BipSystemBackgroundAccessContextCleanup(&v27);
    }
    else
    {
      while ( *(_DWORD *)(v19 + 56) != a1 )
      {
        v19 = *(_QWORD *)v19;
        if ( (__int64 *)v19 == &qword_1800C4400 )
          goto LABEL_30;
      }
      v22 = *(_QWORD *)(v19 + 64);
      if ( !v22 )
      {
        v22 = v27;
        v10 = 0;
        *(_OWORD *)(v19 + 64) = v27;
        *(_QWORD *)(v19 + 80) = v28;
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, v20);
      v23 = ~(1 << dword_1800C46D8);
      dword_1800C46DC = 0;
      *(_DWORD *)(v6 + 8) &= v23;
      RtlReleaseSRWLockExclusive(BipSessionLock);
      *a2 = v22;
      v8 = 0;
      v9 = 0;
      *(_DWORD *)(v6 + 4) &= v23;
      if ( v10 )
        BipSystemBackgroundAccessContextCleanup(v10);
    }
  }
  else
  {
    v9 = 2000;
    BipSystemBackgroundAccessContextCleanup(&v27);
  }
LABEL_9:
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v24 = v9;
    v41 = &v24;
    v25 = v8;
    v39 = &v25;
    v29 = v10;
    v37 = &v29;
    v26[0] = a1;
    v35 = v26;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v42 = 4;
    v40 = 4;
    v38 = 8;
    v36 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v32 = byte_1800B3F21;
    UserData.Reserved = 2;
    v33 = 81;
    v34 = 1;
    v26[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005d730  mov     r11, rsp
0x18005d733  push    rbp
0x18005d734  push    rsi
0x18005d735  push    rdi
0x18005d736  push    r14
0x18005d738  push    r15
0x18005d73a  lea     rbp, [r11-5Fh]
0x18005d73e  sub     rsp, 0F0h
0x18005d745  mov     rax, cs:__security_cookie
0x18005d74c  xor     rax, rsp
0x18005d74f  mov     [rbp+57h+var_40], rax
0x18005d753  mov     [r11+18h], rbx
0x18005d757  xor     eax, eax
0x18005d759  mov     esi, ecx
0x18005d75b  mov     [rbp+57h+var_C0], rax
0x18005d75f  mov     ecx, cs:dword_1800C46D8
0x18005d765  mov     ebx, 1
0x18005d76a  mov     rax, gs:58h
0x18005d773  xorps   xmm0, xmm0
0x18005d776  shl     ebx, cl
0x18005d778  mov     r15, rdx
0x18005d77b  mov     ecx, cs:_tls_index
0x18005d781  mov     [r11-38h], r13
0x18005d785  mov     edi, 4
0x18005d78a  movups  [rbp+57h+var_D0], xmm0
0x18005d78e  mov     r13, [rax+rcx*8]
0x18005d792  cmp     [rdi+r13], ebx
0x18005d796  jb      short loc_18005D7AE
0x18005d798  call    cs:__imp_IsDebuggerPresent
0x18005d79e  test    eax, eax
0x18005d7a0  jz      short loc_18005D7AE
0x18005d7a2  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x18005d7a9  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18005d7ae  lea     rcx, BipSessionLock
0x18005d7b5  mov     [rsp+0E8h], r12
0x18005d7bd  call    cs:__imp_RtlAcquireSRWLockShared
0x18005d7c3  mov     rax, cs:qword_1800C4400
0x18005d7ca  lea     rcx, qword_1800C4400
0x18005d7d1  or      [rdi+r13], ebx
0x18005d7d5  xor     r14d, r14d
0x18005d7d8  cmp     rax, rcx
0x18005d7db  jz      short loc_18005D7F1
0x18005d7dd  nop     dword ptr [rax]
0x18005d7e0  cmp     [rax+38h], esi
0x18005d7e3  jz      loc_18005D969
0x18005d7e9  mov     rax, [rax]
0x18005d7ec  cmp     rax, rcx
0x18005d7ef  jnz     short loc_18005D7E0
0x18005d7f1  mov     edi, 0C0000225h
0x18005d7f6  mov     r15d, 3E8h
0x18005d7fc  mov     ecx, cs:dword_1800C46D8
0x18005d802  mov     ebx, 1
0x18005d807  shl     ebx, cl
0x18005d809  mov     r12, r14
0x18005d80c  lea     rcx, BipSessionLock
0x18005d813  not     ebx
0x18005d815  call    cs:__imp_RtlReleaseSRWLockShared
0x18005d81b  mov     eax, 4
0x18005d820  and     [rax+r13], ebx
0x18005d824  mov     eax, cs:dword_1800C3098
0x18005d82a  mov     r13, [rsp+110h+var_30]
0x18005d832  mov     rbx, [rsp+110h+arg_10]
0x18005d83a  cmp     eax, 5
0x18005d83d  jbe     loc_18005D944
0x18005d843  mov     rcx, cs:qword_1800C30B0
0x18005d84a  mov     rax, cs:qword_1800C30A8
0x18005d851  test    al, 2
0x18005d853  jz      loc_18005D944
0x18005d859  mov     rax, rcx
0x18005d85c  and     eax, 2
0x18005d85f  cmp     rax, rcx
0x18005d862  jnz     loc_18005D944
0x18005d868  mov     [rsp+110h+var_E0], r15d
0x18005d86d  lea     rax, [rsp+110h+var_E0]
0x18005d872  mov     [rbp+57h+var_50], rax
0x18005d876  lea     rcx, _TraceLoggingMetadata
0x18005d87d  mov     [rsp+110h+var_DC], edi
0x18005d881  lea     rax, [rsp+110h+var_DC]
0x18005d886  mov     [rbp+57h+var_60], rax
0x18005d88a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18005d88e  mov     [rbp+57h+var_B8], r12
0x18005d892  lea     rax, [rbp+57h+var_B8]
0x18005d896  mov     [rbp+57h+var_70], rax
0x18005d89a  xor     r9d, r9d; RelatedActivityId
0x18005d89d  lea     rax, [rsp+38h]
0x18005d8a2  mov     [rsp+38h], esi
0x18005d8a6  mov     [rbp+57h+var_80], rax
0x18005d8aa  xor     r8d, r8d; ActivityId
0x18005d8ad  movzx   eax, cs:word_1800B3F17
0x18005d8b4  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18005d8b7  mov     rax, cs:off_1800C30A0
0x18005d8be  mov     [rbp+57h+var_A0.Ptr], rax
0x18005d8c2  mov     [rbp+57h+var_48], 4
0x18005d8ca  mov     [rbp+57h+var_58], 4
0x18005d8d2  mov     [rbp+57h+var_68], 8
0x18005d8da  mov     [rbp+57h+var_78], 4
0x18005d8e2  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18005d8e9  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x18005d8f1  movzx   eax, word ptr [rax]
0x18005d8f4  mov     [rbp+57h+var_A0.Size], eax
0x18005d8f7  lea     rax, byte_1800B3F21
0x18005d8fe  mov     [rbp+57h+var_90], rax
0x18005d902  lea     rax, _TraceLoggingMetadataEnd
0x18005d909  sub     eax, ecx
0x18005d90b  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x18005d912  mov     [rbp+57h+var_88], 51h ; 'Q'
0x18005d919  mov     [rbp+57h+var_84], 1
0x18005d920  mov     [rbp+57h+var_D4], eax
0x18005d923  mov     eax, [rbp+57h+var_D4]
0x18005d926  mov     rcx, cs:RegHandle; RegHandle
0x18005d92d  lea     rax, [rbp+57h+var_A0]
0x18005d931  mov     [rsp+110h+UserData], rax; UserData
0x18005d936  mov     [rsp+110h+UserDataCount], 6; UserDataCount
0x18005d93e  call    cs:__imp_EventWriteTransfer
0x18005d944  mov     r12, [rsp+0E8h]
0x18005d94c  mov     eax, edi
0x18005d94e  mov     rcx, [rbp+57h+var_40]
0x18005d952  xor     rcx, rsp; StackCookie
0x18005d955  call    __security_check_cookie
0x18005d95a  add     rsp, 0F0h
0x18005d961  pop     r15
0x18005d963  pop     r14
0x18005d965  pop     rdi
0x18005d966  pop     rsi
0x18005d967  pop     rbp
0x18005d968  retn
0x18005d969  mov     rbx, [rax+40h]
0x18005d96d  test    rbx, rbx
0x18005d970  jz      short loc_18005D98F
0x18005d972  mov     rax, [rbx]
0x18005d975  mov     rcx, rbx
0x18005d978  mov     rax, [rax+8]
0x18005d97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d981  mov     [r15], rbx
0x18005d984  mov     edi, r14d
0x18005d987  mov     r15d, r14d
0x18005d98a  jmp     loc_18005D7FC
0x18005d98f  mov     ecx, cs:dword_1800C46D8
0x18005d995  mov     ebx, 1
0x18005d99a  shl     ebx, cl
0x18005d99c  lea     rcx, BipSessionLock
0x18005d9a3  not     ebx
0x18005d9a5  call    cs:__imp_RtlReleaseSRWLockShared
0x18005d9ab  and     [rdi+r13], ebx
0x18005d9af  lea     rcx, [rbp+57h+var_D0]
0x18005d9b3  mov     edx, esi
0x18005d9b5  lea     r12, [rbp+57h+var_D0]
0x18005d9b9  call    BipSystemBackgroundAccessContextAllocateState
0x18005d9be  mov     edi, eax
0x18005d9c0  test    eax, eax
0x18005d9c2  jns     short loc_18005D9D7
0x18005d9c4  mov     rcx, r12
0x18005d9c7  mov     r15d, 7D0h
0x18005d9cd  call    BipSystemBackgroundAccessContextCleanup
0x18005d9d2  jmp     loc_18005D824
0x18005d9d7  mov     rcx, qword ptr [rbp+57h+var_D0]
0x18005d9db  lea     r8, [rsp+110h+var_E0]
0x18005d9e0  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x18005d9e4  mov     [rsp+110h+var_E0], r14d
0x18005d9e9  mov     rax, [rcx]
0x18005d9ec  mov     rax, [rax+98h]
0x18005d9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9f8  test    eax, eax
0x18005d9fa  jns     short loc_18005DA22
0x18005d9fc  movzx   edi, ax
0x18005d9ff  mov     eax, edi
0x18005da01  or      eax, 0C0070000h
0x18005da06  test    edi, edi
0x18005da08  cmovnz  edi, eax
0x18005da0b  test    edi, edi
0x18005da0d  jns     short loc_18005DA29
0x18005da0f  mov     rcx, r12
0x18005da12  mov     r15d, 0BB8h
0x18005da18  call    BipSystemBackgroundAccessContextCleanup
0x18005da1d  jmp     loc_18005D824
0x18005da22  mov     eax, [rsp+110h+var_E0]
0x18005da26  mov     dword ptr [rbp+57h+var_C0], eax
0x18005da29  mov     ecx, cs:dword_1800C46D8
0x18005da2f  mov     ebx, 1
0x18005da34  mov     edi, 4
0x18005da39  shl     ebx, cl
0x18005da3b  cmp     [rdi+r13], ebx
0x18005da3f  jb      short loc_18005DA57
0x18005da41  call    cs:__imp_IsDebuggerPresent
0x18005da47  test    eax, eax
0x18005da49  jz      short loc_18005DA57
0x18005da4b  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x18005da52  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18005da57  lea     rcx, BipSessionLock
0x18005da5e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005da64  call    cs:__imp_GetCurrentThreadId
0x18005da6a  or      [rdi+r13], ebx
0x18005da6e  lea     rcx, qword_1800C4400
0x18005da75  mov     r8d, 8
0x18005da7b  mov     cs:dword_1800C46DC, eax
0x18005da81  mov     rax, cs:qword_1800C4400
0x18005da88  or      [r8+r13], ebx
0x18005da8c  mov     edx, [r8+r13]
0x18005da90  cmp     rax, rcx
0x18005da93  jz      short loc_18005DAA2
0x18005da95  cmp     [rax+38h], esi
0x18005da98  jz      short loc_18005DAEE
0x18005da9a  mov     rax, [rax]
0x18005da9d  cmp     rax, rcx
0x18005daa0  jnz     short loc_18005DA95
0x18005daa2  mov     ecx, cs:dword_1800C46D8
0x18005daa8  mov     ebx, 1
0x18005daad  shl     ebx, cl
0x18005daaf  mov     edi, 0C0000225h
0x18005dab4  not     ebx
0x18005dab6  mov     cs:dword_1800C46DC, r14d
0x18005dabd  mov     eax, ebx
0x18005dabf  lea     rcx, BipSessionLock
0x18005dac6  and     eax, edx
0x18005dac8  mov     r15d, 0FA0h
0x18005dace  mov     [r8+r13], eax
0x18005dad2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005dad8  mov     eax, 4
0x18005dadd  mov     rcx, r12
0x18005dae0  and     [rax+r13], ebx
0x18005dae4  call    BipSystemBackgroundAccessContextCleanup
0x18005dae9  jmp     loc_18005D824
0x18005daee  mov     rdi, [rax+40h]
0x18005daf2  test    rdi, rdi
0x18005daf5  jnz     short loc_18005DB10
0x18005daf7  movups  xmm0, [rbp+57h+var_D0]
0x18005dafb  mov     rdi, qword ptr [rbp+57h+var_D0]
0x18005daff  mov     r12, r14
0x18005db02  movups  xmmword ptr [rax+40h], xmm0
0x18005db06  movsd   xmm1, [rbp+57h+var_C0]
0x18005db0b  movsd   qword ptr [rax+50h], xmm1
0x18005db10  mov     rax, [rdi]
0x18005db13  mov     rcx, rdi
0x18005db16  mov     rax, [rax+8]
0x18005db1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db1f  mov     ecx, cs:dword_1800C46D8
0x18005db25  mov     ebx, 1
0x18005db2a  shl     ebx, cl
0x18005db2c  lea     rcx, BipSessionLock
0x18005db33  mov     eax, 8
0x18005db38  not     ebx
0x18005db3a  mov     cs:dword_1800C46DC, r14d
0x18005db41  and     [rax+r13], ebx
0x18005db45  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005db4b  mov     [r15], rdi
0x18005db4e  mov     edi, r14d
0x18005db51  mov     eax, 4
0x18005db56  mov     r15d, r14d
0x18005db59  and     [rax+r13], ebx
0x18005db5d  test    r12, r12
0x18005db60  jz      loc_18005D824
0x18005db66  mov     rcx, r12
0x18005db69  call    BipSystemBackgroundAccessContextCleanup
0x18005db6e  jmp     loc_18005D824
```
