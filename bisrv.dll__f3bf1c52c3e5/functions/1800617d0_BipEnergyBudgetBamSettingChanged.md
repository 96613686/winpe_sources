# BipEnergyBudgetBamSettingChanged

- ea: `0x1800617d0`
- end: `0x180061bb1`
- name: `BipEnergyBudgetBamSettingChanged`
- size: `993`
- prototype: `__int64 __fastcall(struct _BI_LOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180056ff0`

## callees

- `0x180023bf0`
- `0x18002b320`
- `0x1800617d0`
- `0x18006a8d4`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x1800619f6`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800619f6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180061861`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180061861`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180061a56`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180061a56`
- `ntdll!RtlEqualSid` at `0x180061a0b`
- `ntdll!RtlEqualSid` at `0x180061a0b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006199c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180061b84`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006199c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180061b84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061867`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061867`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006184c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006184c`

## pseudocode

```c
int __fastcall BipEnergyBudgetBamSettingChanged(struct _BI_LOCK *a1, __int64 *a2, void *a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 *v5; // rdi
  unsigned int v7; // r14d
  __int64 v8; // r15
  _DWORD *v9; // r12
  DWORD CurrentThreadId; // eax
  __int64 *v11; // r14
  __int64 *v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  __int64 *v16; // rax
  __int64 BudgetForPackage; // rax
  int v18; // r15d
  _QWORD *v19; // r12
  _QWORD *v20; // r14
  _QWORD *v21; // r15
  __int64 v22; // r9
  _QWORD *v23; // r8
  _DWORD *v24; // rax
  int v25; // ebx
  __int64 v26; // rax
  int v27; // esi
  int v28; // eax
  ULONG UserDataCount; // [rsp+20h] [rbp-79h]
  unsigned int v31; // [rsp+30h] [rbp-69h] BYREF
  PSID Sid2; // [rsp+38h] [rbp-61h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-59h] BYREF
  _DWORD *v34; // [rsp+50h] [rbp-49h]
  _DWORD *v35; // [rsp+58h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  char *v37; // [rsp+70h] [rbp-29h]
  int v38; // [rsp+78h] [rbp-21h]
  int v39; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v40; // [rsp+80h] [rbp-19h]
  int v41; // [rsp+88h] [rbp-11h]
  int v42; // [rsp+8Ch] [rbp-Dh]
  __int64 *v43; // [rsp+90h] [rbp-9h]
  int v44; // [rsp+98h] [rbp-1h]
  int v45; // [rsp+9Ch] [rbp+3h]
  unsigned int *v46; // [rsp+A0h] [rbp+7h]
  __int64 v47; // [rsp+A8h] [rbp+Fh]

  v3 = -1;
  Sid2 = a3;
  v4 = -1;
  v5 = a2;
  do
    ++v4;
  while ( *((_WORD *)a2 + v4) );
  v7 = 1 << *((_DWORD *)a1 + 2);
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v9 = (_DWORD *)(v8 + 4);
  v34 = (_DWORD *)(v8 + 4);
  if ( *(_DWORD *)(v8 + 4) >= v7 && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug(a1);
  RtlAcquireSRWLockExclusive(a1);
  CurrentThreadId = GetCurrentThreadId();
  *v9 |= v7;
  *((_DWORD *)a1 + 3) = CurrentThreadId;
  v35 = (_DWORD *)(v8 + 8);
  *(_DWORD *)(v8 + 8) |= v7;
  v11 = &BipTraceLoggingNullSid;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    if ( v5 )
    {
      v12 = v5;
      v13 = -1;
      do
        v14 = *((_WORD *)v5 + ++v13) == 0;
      while ( !v14 );
      v15 = 2 * v13 + 2;
    }
    else
    {
      v12 = &qword_1800A1670;
      v15 = 2;
    }
    v41 = v15;
    v16 = &BipTraceLoggingNullSid;
    v40 = v12;
    v42 = 0;
    v45 = 0;
    if ( Sid2 )
      v16 = (__int64 *)Sid2;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v43 = v16;
    EventDescriptor.Keyword = 2;
    v44 = 4 * *((unsigned __int8 *)v16 + 1) + 8;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v37 = byte_1800B13BD;
    UserData.Reserved = 2;
    v38 = 72;
    v39 = 1;
    v31 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  BudgetForPackage = BipEnergyBudgetGetBudgetForPackage(a1, v5, 0);
  v18 = 0;
  if ( BudgetForPackage )
  {
    v19 = (_QWORD *)(BudgetForPackage + 352);
    v20 = *(_QWORD **)(BudgetForPackage + 352);
    while ( 1 )
    {
      v18 = 0;
      if ( v20 == v19 )
        break;
      v21 = v20;
      v22 = -1;
      v20 = (_QWORD *)*v20;
      v23 = v21 + 2;
      do
        ++v22;
      while ( *((_WORD *)v23 + v22) );
      LOBYTE(UserDataCount) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(v5, v4, v23, v22, UserDataCount) && RtlEqualSid((PSID)v21[51], Sid2) )
      {
        *((_DWORD *)v21 + 116) = -1;
        BipPackageImportanceUpdateScoreForPackage(a1, v21);
        v18 = 1;
        break;
      }
    }
    v9 = v34;
    v11 = &BipTraceLoggingNullSid;
  }
  v24 = v35;
  v25 = ~(1 << *((_DWORD *)a1 + 2));
  *((_DWORD *)a1 + 3) = 0;
  *v24 &= v25;
  RtlReleaseSRWLockExclusive(a1);
  *v9 &= v25;
  LODWORD(v26) = dword_1800C3098;
  if ( (unsigned int)dword_1800C3098 > 4 )
  {
    LODWORD(v26) = qword_1800C30A8;
    if ( (qword_1800C30A8 & 3) != 0 )
    {
      v26 = qword_1800C30B0 & 3;
      if ( v26 == qword_1800C30B0 )
      {
        if ( v5 )
        {
          do
            v14 = *((_WORD *)v5 + ++v3) == 0;
          while ( !v14 );
          v27 = 2 * v3 + 2;
        }
        else
        {
          v5 = &qword_1800A1670;
          v27 = 2;
        }
        v40 = v5;
        v42 = 0;
        v45 = 0;
        if ( Sid2 )
          v11 = (__int64 *)Sid2;
        v41 = v27;
        v43 = v11;
        v31 = v18;
        v47 = 4;
        v28 = *((unsigned __int8 *)v11 + 1);
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 3;
        v44 = 4 * v28 + 8;
        v46 = &v31;
        *(_DWORD *)&EventDescriptor.Level = 516;
        UserData.Ptr = (ULONGLONG)off_1800C30A0;
        UserData.Size = *(unsigned __int16 *)off_1800C30A0;
        v37 = byte_1800B1411;
        UserData.Reserved = 2;
        v38 = 86;
        v39 = 1;
        LODWORD(Sid2) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v26) = EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
  return v26;
}

```

## disassembly

```asm
0x1800617d0  mov     [rsp-8+arg_18], rbx
0x1800617d5  push    rbp
0x1800617d6  push    rsi
0x1800617d7  push    rdi
0x1800617d8  push    r12
0x1800617da  push    r13
0x1800617dc  push    r14
0x1800617de  push    r15
0x1800617e0  lea     rbp, [rsp-27h]
0x1800617e5  sub     rsp, 0C0h
0x1800617ec  mov     rax, cs:__security_cookie
0x1800617f3  xor     rax, rsp
0x1800617f6  mov     [rbp+57h+var_40], rax
0x1800617fa  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180061801  mov     [rbp+57h+Sid2], r8
0x180061805  mov     rbx, rsi
0x180061808  mov     rdi, rdx
0x18006180b  mov     r13, rcx
0x18006180e  xchg    ax, ax
0x180061810  inc     rbx
0x180061813  cmp     word ptr [rdx+rbx*2], 0
0x180061818  jnz     short loc_180061810
0x18006181a  mov     ecx, [rcx+8]
0x18006181d  mov     r14d, 1
0x180061823  mov     rax, gs:58h
0x18006182c  shl     r14d, cl
0x18006182f  mov     ecx, cs:_tls_index
0x180061835  mov     r12d, 4
0x18006183b  mov     r15, [rax+rcx*8]
0x18006183f  add     r12, r15
0x180061842  mov     [rbp+57h+var_A0], r12
0x180061846  cmp     [r12], r14d
0x18006184a  jb      short loc_18006185E
0x18006184c  call    cs:__imp_IsDebuggerPresent
0x180061852  test    eax, eax
0x180061854  jz      short loc_18006185E
0x180061856  mov     rcx, r13; struct _BI_LOCK *
0x180061859  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18006185e  mov     rcx, r13
0x180061861  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180061867  call    cs:__imp_GetCurrentThreadId
0x18006186d  or      [r12], r14d
0x180061871  lea     r8, _TraceLoggingMetadata
0x180061878  mov     [r13+0Ch], eax
0x18006187c  xor     edx, edx
0x18006187e  mov     eax, 8
0x180061883  add     rax, r15
0x180061886  mov     [rbp+57h+var_98], rax
0x18006188a  or      [rax], r14d
0x18006188d  lea     r14, BipTraceLoggingNullSid
0x180061894  mov     eax, cs:dword_1800C3098
0x18006189a  cmp     eax, 5
0x18006189d  jbe     loc_1800619A2
0x1800618a3  mov     rcx, cs:qword_1800C30B0
0x1800618aa  mov     rax, cs:qword_1800C30A8
0x1800618b1  test    al, 2
0x1800618b3  jz      loc_1800619A2
0x1800618b9  mov     rax, rcx
0x1800618bc  and     eax, 2
0x1800618bf  cmp     rax, rcx
0x1800618c2  jnz     loc_1800619A2
0x1800618c8  test    rdi, rdi
0x1800618cb  jz      short loc_1800618E7
0x1800618cd  mov     rcx, rdi
0x1800618d0  mov     rax, rsi
0x1800618d3  cmp     [rdi+rax*2+2], dx
0x1800618d8  lea     rax, [rax+1]
0x1800618dc  jnz     short loc_1800618D3
0x1800618de  lea     eax, ds:2[rax*2]
0x1800618e5  jmp     short loc_1800618F3
0x1800618e7  lea     rcx, qword_1800A1670
0x1800618ee  mov     eax, 2
0x1800618f3  mov     [rbp+57h+var_68], eax
0x1800618f6  mov     rax, r14
0x1800618f9  mov     [rbp+57h+var_70], rcx
0x1800618fd  mov     rcx, [rbp+57h+Sid2]
0x180061901  mov     [rbp+57h+var_64], edx
0x180061904  test    rcx, rcx
0x180061907  mov     [rbp+57h+var_54], edx
0x18006190a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18006190e  cmovnz  rax, rcx
0x180061912  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180061919  mov     [rbp+57h+var_60], rax
0x18006191d  xor     r9d, r9d; RelatedActivityId
0x180061920  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x180061928  movzx   eax, byte ptr [rax+1]
0x18006192c  lea     eax, ds:8[rax*4]
0x180061933  mov     [rbp+57h+var_58], eax
0x180061936  movzx   eax, cs:word_1800B13B3
0x18006193d  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180061940  mov     rax, cs:off_1800C30A0
0x180061947  mov     [rbp+57h+var_90.Ptr], rax
0x18006194b  movzx   eax, word ptr [rax]
0x18006194e  mov     [rbp+57h+var_90.Size], eax
0x180061951  lea     rax, byte_1800B13BD
0x180061958  mov     [rbp+57h+var_80], rax
0x18006195c  lea     rax, _TraceLoggingMetadataEnd
0x180061963  sub     eax, r8d
0x180061966  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18006196d  mov     [rbp+57h+var_78], 48h ; 'H'
0x180061974  xor     r8d, r8d; ActivityId
0x180061977  mov     [rbp+57h+var_74], 1
0x18006197e  mov     [rbp+57h+var_C0], eax
0x180061981  mov     eax, [rbp+57h+var_C0]
0x180061984  mov     rcx, cs:RegHandle; RegHandle
0x18006198b  lea     rax, [rbp+57h+var_90]
0x18006198f  mov     [rsp+0F0h+UserData], rax; UserData
0x180061994  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x18006199c  call    cs:__imp_EventWriteTransfer
0x1800619a2  xor     r8d, r8d
0x1800619a5  mov     rdx, rdi
0x1800619a8  mov     rcx, r13
0x1800619ab  call    BipEnergyBudgetGetBudgetForPackage
0x1800619b0  xor     r15d, r15d
0x1800619b3  test    rax, rax
0x1800619b6  jz      loc_180061A38
0x1800619bc  lea     r12, [rax+160h]
0x1800619c3  mov     r14, [r12]
0x1800619c7  xor     r15d, r15d
0x1800619ca  cmp     r14, r12
0x1800619cd  jz      short loc_180061A2D
0x1800619cf  mov     r15, r14
0x1800619d2  mov     r9, rsi
0x1800619d5  mov     r14, [r14]
0x1800619d8  lea     r8, [r15+10h]
0x1800619dc  nop     dword ptr [rax+00h]
0x1800619e0  inc     r9
0x1800619e3  cmp     word ptr [r8+r9*2], 0
0x1800619e9  jnz     short loc_1800619E0
0x1800619eb  mov     rdx, rbx
0x1800619ee  mov     byte ptr [rsp+0F0h+UserDataCount], 1
0x1800619f3  mov     rcx, rdi
0x1800619f6  call    cs:__imp_RtlCompareUnicodeStrings
0x1800619fc  test    eax, eax
0x1800619fe  jnz     short loc_1800619C7
0x180061a00  mov     rdx, [rbp+57h+Sid2]; Sid2
0x180061a04  mov     rcx, [r15+198h]; Sid1
0x180061a0b  call    cs:__imp_RtlEqualSid
0x180061a11  test    al, al
0x180061a13  jz      short loc_1800619C7
0x180061a15  mov     rdx, r15
0x180061a18  mov     [r15+1D0h], esi
0x180061a1f  mov     rcx, r13
0x180061a22  call    BipPackageImportanceUpdateScoreForPackage
0x180061a27  mov     r15d, 1
0x180061a2d  mov     r12, [rbp+57h+var_A0]
0x180061a31  lea     r14, BipTraceLoggingNullSid
0x180061a38  mov     ecx, [r13+8]
0x180061a3c  mov     ebx, 1
0x180061a41  mov     rax, [rbp+57h+var_98]
0x180061a45  shl     ebx, cl
0x180061a47  mov     rcx, r13
0x180061a4a  not     ebx
0x180061a4c  mov     dword ptr [r13+0Ch], 0
0x180061a54  and     [rax], ebx
0x180061a56  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180061a5c  and     [r12], ebx
0x180061a60  mov     eax, cs:dword_1800C3098
0x180061a66  cmp     eax, 4
0x180061a69  jbe     loc_180061B8A
0x180061a6f  mov     rcx, cs:qword_1800C30B0
0x180061a76  mov     rax, cs:qword_1800C30A8
0x180061a7d  test    al, 3
0x180061a7f  jz      loc_180061B8A
0x180061a85  mov     rax, rcx
0x180061a88  and     eax, 3
0x180061a8b  cmp     rax, rcx
0x180061a8e  jnz     loc_180061B8A
0x180061a94  test    rdi, rdi
0x180061a97  jz      short loc_180061AB5
0x180061a99  nop     dword ptr [rax+00000000h]
0x180061aa0  cmp     word ptr [rdi+rsi*2+2], 0
0x180061aa6  lea     rsi, [rsi+1]
0x180061aaa  jnz     short loc_180061AA0
0x180061aac  lea     esi, ds:2[rsi*2]
0x180061ab3  jmp     short loc_180061AC1
0x180061ab5  lea     rdi, qword_1800A1670
0x180061abc  mov     esi, 2
0x180061ac1  mov     rax, [rbp+57h+Sid2]
0x180061ac5  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180061ac9  xor     ecx, ecx
0x180061acb  mov     [rbp+57h+var_70], rdi
0x180061acf  test    rax, rax
0x180061ad2  mov     [rbp+57h+var_64], ecx
0x180061ad5  mov     [rbp+57h+var_54], ecx
0x180061ad8  lea     rcx, _TraceLoggingMetadata
0x180061adf  cmovnz  r14, rax
0x180061ae3  mov     [rbp+57h+var_68], esi
0x180061ae6  mov     [rbp+57h+var_60], r14
0x180061aea  xor     r9d, r9d; RelatedActivityId
0x180061aed  mov     [rbp+57h+var_C0], r15d
0x180061af1  xor     r8d, r8d; ActivityId
0x180061af4  mov     [rbp+57h+var_48], 4
0x180061afc  movzx   eax, byte ptr [r14+1]
0x180061b01  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180061b08  mov     [rbp+57h+EventDescriptor.Keyword], 3
0x180061b10  lea     eax, ds:8[rax*4]
0x180061b17  mov     [rbp+57h+var_58], eax
0x180061b1a  lea     rax, [rbp+57h+var_C0]
0x180061b1e  mov     [rbp+57h+var_50], rax
0x180061b22  movzx   eax, cs:word_1800B1407
0x180061b29  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180061b2c  mov     rax, cs:off_1800C30A0
0x180061b33  mov     [rbp+57h+var_90.Ptr], rax
0x180061b37  movzx   eax, word ptr [rax]
0x180061b3a  mov     [rbp+57h+var_90.Size], eax
0x180061b3d  lea     rax, byte_1800B1411
0x180061b44  mov     [rbp+57h+var_80], rax
0x180061b48  lea     rax, _TraceLoggingMetadataEnd
0x180061b4f  sub     eax, ecx
0x180061b51  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180061b58  mov     [rbp+57h+var_78], 56h ; 'V'
0x180061b5f  mov     [rbp+57h+var_74], 1
0x180061b66  mov     dword ptr [rbp+57h+Sid2], eax
0x180061b69  mov     eax, dword ptr [rbp+57h+Sid2]
0x180061b6c  mov     rcx, cs:RegHandle; RegHandle
0x180061b73  lea     rax, [rbp+57h+var_90]
0x180061b77  mov     [rsp+0F0h+UserData], rax; UserData
0x180061b7c  mov     [rsp+0F0h+UserDataCount], 5; UserDataCount
0x180061b84  call    cs:__imp_EventWriteTransfer
0x180061b8a  mov     rcx, [rbp+57h+var_40]
0x180061b8e  xor     rcx, rsp; StackCookie
0x180061b91  call    __security_check_cookie
0x180061b96  mov     rbx, [rsp+0F0h+arg_18]
0x180061b9e  add     rsp, 0C0h
0x180061ba5  pop     r15
0x180061ba7  pop     r14
0x180061ba9  pop     r13
0x180061bab  pop     r12
0x180061bad  pop     rdi
0x180061bae  pop     rsi
0x180061baf  pop     rbp
0x180061bb0  retn
```
