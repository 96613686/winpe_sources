# BipPackageEnsureIsRegistered

- ea: `0x180037500`
- end: `0x18003785e`
- name: `BipPackageEnsureIsRegistered`
- size: `862`
- prototype: `__int64 __fastcall(ULONG SessionId, PSID Sid1)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058370`
- `0x18005df20`
- `0x180065f80`
- `0x18007fdf8`

## callees

- `0x180006aa0`
- `0x18002d280`
- `0x180037500`
- `0x180052400`
- `0x18006a8d4`
- `0x18006d364`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180037690`
- `ntdll!RtlReleaseSRWLockShared` at `0x180037690`
- `ntdll!RtlAcquireSRWLockShared` at `0x180037667`
- `ntdll!RtlAcquireSRWLockShared` at `0x180037667`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800375f8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180037833`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800375f8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180037833`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003764a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003764a`

## pseudocode

```c
__int64 __fastcall BipPackageEnsureIsRegistered(ULONG SessionId, PSID Sid1, const WCHAR *a3)
{
  int v6; // ebx
  _DWORD *v7; // r14
  int v8; // ebx
  int IsRegistered; // ebx
  __int64 *v10; // rax
  __int64 v11; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rbx
  unsigned int v19; // [rsp+30h] [rbp-99h] BYREF
  __int64 v20; // [rsp+38h] [rbp-91h] BYREF
  int v21; // [rsp+40h] [rbp-89h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-71h] BYREF
  char *v24; // [rsp+68h] [rbp-61h]
  int v25; // [rsp+70h] [rbp-59h]
  int v26; // [rsp+74h] [rbp-55h]
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+80h] [rbp-49h] BYREF
  char *v28; // [rsp+90h] [rbp-39h]
  int v29; // [rsp+98h] [rbp-31h]
  int v30; // [rsp+9Ch] [rbp-2Dh]
  unsigned int *v31; // [rsp+A0h] [rbp-29h]
  __int64 v32; // [rsp+A8h] [rbp-21h]
  __int64 *v33; // [rsp+B0h] [rbp-19h]
  int v34; // [rsp+B8h] [rbp-11h]
  int v35; // [rsp+BCh] [rbp-Dh]
  const WCHAR *v36; // [rsp+C0h] [rbp-9h]
  int v37; // [rsp+C8h] [rbp-1h]
  int v38; // [rsp+CCh] [rbp+3h]
  int *v39; // [rsp+D0h] [rbp+7h]
  __int64 v40; // [rsp+D8h] [rbp+Fh]

  v20 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v24 = byte_1800AF789;
    UserData.Reserved = 2;
    v25 = 40;
    v26 = 1;
    v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( SessionId != -1 )
    goto LABEL_20;
  v6 = 1 << dword_1800C46D8;
  v7 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
  if ( *v7 >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
  RtlAcquireSRWLockShared(BipSessionLock);
  *v7 |= v6;
  SessionId = BipUserInfoGetSessionIdBySid(Sid1);
  v8 = ~(1 << dword_1800C46D8);
  RtlReleaseSRWLockShared(BipSessionLock);
  *v7 &= v8;
  if ( SessionId == -1 )
  {
    IsRegistered = -1073741729;
  }
  else
  {
LABEL_20:
    IsRegistered = BipSystemUserQueryUserContextToken(SessionId, Sid1, &v20);
    if ( IsRegistered >= 0 )
    {
      v17 = v20;
      if ( v20 == 0xFFFFFFFFLL )
        MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
      IsRegistered = BipSystemPackageEnsureIsRegistered(v17, a3);
      if ( IsRegistered >= 0 )
        IsRegistered = 0;
    }
  }
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v19 = SessionId;
    v31 = &v19;
    v10 = &BipTraceLoggingNullSid;
    v32 = 4;
    if ( Sid1 )
      v10 = (__int64 *)Sid1;
    v35 = 0;
    v33 = v10;
    v34 = 4 * *((unsigned __int8 *)v10 + 1) + 8;
    if ( a3 )
    {
      v11 = -1;
      while ( a3[++v11] != 0 )
        ;
      v13 = 2 * v11 + 2;
    }
    else
    {
      a3 = (const WCHAR *)&qword_1800A1670;
      v13 = 2;
    }
    v37 = v13;
    v38 = 0;
    v39 = &v21;
    *(_DWORD *)&EventDescriptor.Level = 516;
    v27.Ptr = (ULONGLONG)off_1800C30A0;
    v36 = a3;
    v21 = IsRegistered;
    v40 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    v27.Size = *(unsigned __int16 *)off_1800C30A0;
    v28 = byte_1800AF7BD;
    v27.Reserved = 2;
    v29 = 75;
    v30 = 1;
    LODWORD(v20) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &v27);
  }
  return (unsigned int)IsRegistered;
}

```

## disassembly

```asm
0x180037500  push    rbp
0x180037502  push    rsi
0x180037503  push    rdi
0x180037504  push    r12
0x180037506  push    r15
0x180037508  lea     rbp, [rsp-37h]
0x18003750d  sub     rsp, 100h
0x180037514  mov     rax, cs:__security_cookie
0x18003751b  xor     rax, rsp
0x18003751e  mov     [rbp+57h+var_40], rax
0x180037522  mov     eax, cs:dword_1800C3098
0x180037528  lea     r12, _TraceLoggingMetadataEnd
0x18003752f  mov     [rsp+120h+var_28], r13
0x180037537  mov     r15, rdx
0x18003753a  mov     [rsp+120h+var_E8], 0
0x180037543  mov     rdi, r8
0x180037546  lea     rdx, _TraceLoggingMetadata
0x18003754d  mov     esi, ecx
0x18003754f  cmp     eax, 5
0x180037552  jbe     loc_1800375FE
0x180037558  mov     rcx, cs:qword_1800C30B0
0x18003755f  mov     rax, cs:qword_1800C30A8
0x180037566  test    al, 2
0x180037568  jz      loc_1800375FE
0x18003756e  mov     rax, rcx
0x180037571  and     eax, 2
0x180037574  cmp     rax, rcx
0x180037577  jnz     loc_1800375FE
0x18003757d  movzx   eax, cs:word_1800AF77F
0x180037584  xor     r9d, r9d; RelatedActivityId
0x180037587  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18003758a  xor     r8d, r8d; ActivityId
0x18003758d  mov     rax, cs:off_1800C30A0
0x180037594  mov     [rbp+57h+var_C8.Ptr], rax
0x180037598  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1800375a0  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x1800375a8  movzx   eax, word ptr [rax]
0x1800375ab  mov     [rbp+57h+var_C8.Size], eax
0x1800375ae  lea     rax, byte_1800AF789
0x1800375b5  mov     [rbp+57h+var_B8], rax
0x1800375b9  mov     rax, r12
0x1800375bc  sub     eax, edx
0x1800375be  mov     dword ptr [rbp+57h+var_C8.0Ch], 2
0x1800375c5  mov     [rbp+57h+var_B0], 28h ; '('
0x1800375cc  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800375d1  mov     [rbp+57h+var_AC], 1
0x1800375d8  mov     [rsp+120h+var_F0], eax
0x1800375dc  mov     eax, [rsp+120h+var_F0]
0x1800375e0  mov     rcx, cs:RegHandle; RegHandle
0x1800375e7  lea     rax, [rbp+57h+var_C8]
0x1800375eb  mov     [rsp+120h+UserData], rax; UserData
0x1800375f0  mov     [rsp+120h+UserDataCount], 2; UserDataCount
0x1800375f8  call    cs:__imp_EventWriteTransfer
0x1800375fe  mov     r13d, 0FFFFFFFFh
0x180037604  mov     [rsp+120h+arg_18], rbx
0x18003760c  cmp     esi, r13d
0x18003760f  jnz     loc_180037746
0x180037615  mov     ecx, cs:dword_1800C46D8
0x18003761b  mov     ebx, 1
0x180037620  mov     rax, gs:58h
0x180037629  shl     ebx, cl
0x18003762b  mov     ecx, cs:_tls_index
0x180037631  mov     [rsp+120h+var_30], r14
0x180037639  mov     edx, 4
0x18003763e  mov     r14, [rax+rcx*8]
0x180037642  add     r14, rdx
0x180037645  cmp     [r14], ebx
0x180037648  jb      short loc_180037660
0x18003764a  call    cs:__imp_IsDebuggerPresent
0x180037650  test    eax, eax
0x180037652  jz      short loc_180037660
0x180037654  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x18003765b  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180037660  lea     rcx, BipSessionLock
0x180037667  call    cs:__imp_RtlAcquireSRWLockShared
0x18003766d  or      [r14], ebx
0x180037670  mov     rcx, r15; Sid2
0x180037673  call    BipUserInfoGetSessionIdBySid
0x180037678  mov     ecx, cs:dword_1800C46D8
0x18003767e  mov     ebx, 1
0x180037683  shl     ebx, cl
0x180037685  mov     esi, eax
0x180037687  lea     rcx, BipSessionLock
0x18003768e  not     ebx
0x180037690  call    cs:__imp_RtlReleaseSRWLockShared
0x180037696  and     [r14], ebx
0x180037699  mov     r14, [rsp+120h+var_30]
0x1800376a1  cmp     esi, r13d
0x1800376a4  jnz     loc_180037746
0x1800376aa  mov     ebx, 0C000005Fh
0x1800376af  xor     edx, edx
0x1800376b1  mov     eax, cs:dword_1800C3098
0x1800376b7  mov     r13, [rsp+120h+var_28]
0x1800376bf  cmp     eax, 4
0x1800376c2  jbe     loc_180037839
0x1800376c8  mov     rcx, cs:qword_1800C30B0
0x1800376cf  mov     rax, cs:qword_1800C30A8
0x1800376d6  test    al, 3
0x1800376d8  jz      loc_180037839
0x1800376de  mov     rax, rcx
0x1800376e1  and     eax, 3
0x1800376e4  cmp     rax, rcx
0x1800376e7  jnz     loc_180037839
0x1800376ed  lea     rax, [rsp+120h+var_F0]
0x1800376f2  mov     [rsp+120h+var_F0], esi
0x1800376f6  mov     [rbp+57h+var_80], rax
0x1800376fa  test    r15, r15
0x1800376fd  lea     rax, BipTraceLoggingNullSid
0x180037704  mov     [rbp+57h+var_78], 4
0x18003770c  cmovnz  rax, r15
0x180037710  mov     [rbp+57h+var_64], edx
0x180037713  mov     [rbp+57h+var_70], rax
0x180037717  movzx   eax, byte ptr [rax+1]
0x18003771b  lea     eax, ds:8[rax*4]
0x180037722  mov     [rbp+57h+var_68], eax
0x180037725  test    rdi, rdi
0x180037728  jz      short loc_180037787
0x18003772a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180037731  cmp     word ptr [rdi+rax*2+2], 0
0x180037737  lea     rax, [rax+1]
0x18003773b  jnz     short loc_180037731
0x18003773d  lea     eax, ds:2[rax*2]
0x180037744  jmp     short loc_180037793
0x180037746  lea     r8, [rsp+120h+var_E8]
0x18003774b  mov     rdx, r15; Sid1
0x18003774e  mov     ecx, esi; SessionId
0x180037750  call    BipSystemUserQueryUserContextToken
0x180037755  mov     ebx, eax
0x180037757  test    eax, eax
0x180037759  js      loc_1800376AF
0x18003775f  mov     rbx, [rsp+120h+var_E8]
0x180037764  cmp     rbx, r13
0x180037767  jnz     short loc_18003776E
0x180037769  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003776e  mov     rdx, rdi
0x180037771  mov     rcx, rbx
0x180037774  call    BipSystemPackageEnsureIsRegistered
0x180037779  xor     edx, edx
0x18003777b  mov     ebx, eax
0x18003777d  test    eax, eax
0x18003777f  cmovns  ebx, edx
0x180037782  jmp     loc_1800376B1
0x180037787  lea     rdi, qword_1800A1670
0x18003778e  mov     eax, 2
0x180037793  mov     [rbp+57h+var_58], eax
0x180037796  xor     r9d, r9d; RelatedActivityId
0x180037799  mov     [rbp+57h+var_54], edx
0x18003779c  lea     rax, [rsp+120h+var_E0]
0x1800377a1  mov     [rbp+57h+var_50], rax
0x1800377a5  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800377aa  movzx   eax, cs:word_1800AF7B3
0x1800377b1  xor     r8d, r8d; ActivityId
0x1800377b4  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800377b7  mov     rax, cs:off_1800C30A0
0x1800377be  mov     [rbp+57h+var_A0.Ptr], rax
0x1800377c2  mov     [rbp+57h+var_60], rdi
0x1800377c6  mov     [rsp+120h+var_E0], ebx
0x1800377ca  mov     [rbp+57h+var_48], 4
0x1800377d2  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1800377da  mov     [rbp+57h+EventDescriptor.Keyword], 3
0x1800377e2  movzx   eax, word ptr [rax]
0x1800377e5  mov     [rbp+57h+var_A0.Size], eax
0x1800377e8  lea     rax, byte_1800AF7BD
0x1800377ef  mov     [rbp+57h+var_90], rax
0x1800377f3  lea     rax, _TraceLoggingMetadata
0x1800377fa  sub     r12d, eax
0x1800377fd  mov     dword ptr [rbp+57h+var_A0.0Ch], 2
0x180037804  mov     [rbp+57h+var_88], 4Bh ; 'K'
0x18003780b  mov     [rbp+57h+var_84], 1
0x180037812  mov     dword ptr [rsp+120h+var_E8], r12d
0x180037817  mov     eax, dword ptr [rsp+120h+var_E8]
0x18003781b  mov     rcx, cs:RegHandle; RegHandle
0x180037822  lea     rax, [rbp+57h+var_A0]
0x180037826  mov     [rsp+120h+UserData], rax; UserData
0x18003782b  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x180037833  call    cs:__imp_EventWriteTransfer
0x180037839  mov     eax, ebx
0x18003783b  mov     rbx, [rsp+120h+arg_18]
0x180037843  mov     rcx, [rbp+57h+var_40]
0x180037847  xor     rcx, rsp; StackCookie
0x18003784a  call    __security_check_cookie
0x18003784f  add     rsp, 100h
0x180037856  pop     r15
0x180037858  pop     r12
0x18003785a  pop     rdi
0x18003785b  pop     rsi
0x18003785c  pop     rbp
0x18003785d  retn
```
