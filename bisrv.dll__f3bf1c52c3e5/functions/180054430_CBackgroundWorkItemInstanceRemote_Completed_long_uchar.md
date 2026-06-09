# CBackgroundWorkItemInstanceRemote::Completed(long,uchar)

- ea: `0x180054430`
- end: `0x180054803`
- name: `?Completed@CBackgroundWorkItemInstanceRemote@@UEAAJJE@Z`
- size: `979`
- prototype: `__int64 __fastcall(CBackgroundWorkItemInstanceRemote *__hidden this, int, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000db40`
- `0x18003fd6c`
- `0x180054430`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlWaitOnAddress` at `0x180054621`
- `ntdll!RtlWaitOnAddress` at `0x180054621`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054567`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005462e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054567`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005462e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005460a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054656`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005460a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054656`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005455a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800547d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005455a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800547d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005456d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054634`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005456d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054634`

## pseudocode

```c
__int64 __fastcall CBackgroundWorkItemInstanceRemote::Completed(
        CBackgroundWorkItemInstanceRemote *this,
        int a2,
        unsigned __int8 a3)
{
  bool v3; // si
  int v4; // r13d
  DWORD CurrentThreadId; // eax
  int *v8; // rdi
  int v9; // ecx
  __int64 v10; // r15
  __int64 v11; // rcx
  char v13; // [rsp+30h] [rbp-99h] BYREF
  char v14; // [rsp+31h] [rbp-98h] BYREF
  bool v15; // [rsp+32h] [rbp-97h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-95h] BYREF
  _DWORD v17[2]; // [rsp+38h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-79h] BYREF
  int *v20; // [rsp+60h] [rbp-69h]
  int v21; // [rsp+68h] [rbp-61h]
  int v22; // [rsp+6Ch] [rbp-5Dh]
  const unsigned __int16 *v23; // [rsp+70h] [rbp-59h]
  __int64 v24; // [rsp+78h] [rbp-51h]
  char *v25; // [rsp+80h] [rbp-49h]
  __int64 v26; // [rsp+88h] [rbp-41h]
  char *v27; // [rsp+90h] [rbp-39h]
  __int64 v28; // [rsp+98h] [rbp-31h]
  char *v29; // [rsp+A0h] [rbp-29h]
  __int64 v30; // [rsp+A8h] [rbp-21h]
  bool *v31; // [rsp+B0h] [rbp-19h]
  __int64 v32; // [rsp+B8h] [rbp-11h]
  unsigned int *v33; // [rsp+C0h] [rbp-9h]
  __int64 v34; // [rsp+C8h] [rbp-1h]
  char *v35; // [rsp+D0h] [rbp+7h]
  __int64 v36; // [rsp+D8h] [rbp+Fh]

  v3 = 0;
  v4 = a3;
  v17[0] = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v23 = &qword_1800A1850;
    v27 = (char *)this + 76;
    v28 = 16;
    v25 = (char *)this + 92;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v26 = 16;
    v24 = 1;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v20 = (int *)byte_1800AE703;
    UserData.Reserved = 2;
    v21 = 69;
    v22 = 1;
    v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 20);
  CurrentThreadId = GetCurrentThreadId();
  v8 = (int *)((char *)this + 176);
  *((_DWORD *)this + 52) = a2;
  *((_DWORD *)this + 38) = CurrentThreadId;
  v9 = *((_DWORD *)this + 44) ^ (*((_DWORD *)this + 44) ^ (v4 << 6)) & 0x40;
  *((_DWORD *)this + 44) = v9;
  if ( (v9 & 1) != 0 )
  {
    v10 = 0;
    v13 = 1;
  }
  else
  {
    v10 = *((_QWORD *)this + 23);
    *v8 = v9 | 0x21;
    v13 = 0;
    *((_QWORD *)this + 23) = 0;
    CBackgroundWorkItemInstanceRemote::DisarmProcessWaitCallback(this);
    v11 = *((_QWORD *)this + 21);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v9 = *v8;
    v3 = (*v8 & 0x10) != 0;
  }
  if ( (v9 & 2) != 0 )
  {
    do
    {
      if ( (v9 & 4) != 0 )
        break;
      v17[0] = v9;
      *((_DWORD *)this + 38) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
      RtlWaitOnAddress((char *)this + 176, v17, 4, 0);
      AcquireSRWLockExclusive((PSRWLOCK)this + 20);
      *((_DWORD *)this + 38) = GetCurrentThreadId();
      v9 = *v8;
    }
    while ( (*v8 & 2) != 0 );
  }
  *((_DWORD *)this + 38) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v3 )
    BipTaskCompletionCallback((unsigned __int8 *)this + 92, (char *)this + 76, v4, a2);
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v14 = v4;
    v35 = &v14;
    v16 = a2;
    v33 = &v16;
    v15 = v3;
    v31 = &v15;
    v29 = &v13;
    v27 = (char *)this + 76;
    v25 = (char *)this + 92;
    v23 = &qword_1800A1850;
    *(_DWORD *)&EventDescriptor.Level = 517;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v36 = 1;
    v34 = 4;
    v32 = 1;
    v30 = 1;
    v28 = 16;
    v26 = 16;
    v24 = 1;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v20 = &dword_1800AE754;
    UserData.Reserved = 2;
    v21 = 132;
    v22 = 1;
    v17[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
  }
  return 0;
}

```

## disassembly

```asm
0x180054430  mov     [rsp-8+arg_18], rbx
0x180054435  push    rbp
0x180054436  push    rsi
0x180054437  push    rdi
0x180054438  push    r12
0x18005443a  push    r13
0x18005443c  push    r14
0x18005443e  push    r15
0x180054440  lea     rbp, [rsp-27h]
0x180054445  sub     rsp, 0F0h
0x18005444c  mov     rax, cs:__security_cookie
0x180054453  xor     rax, rsp
0x180054456  mov     [rbp+57h+var_40], rax
0x18005445a  mov     eax, cs:dword_1800C3098
0x180054460  xor     esi, esi
0x180054462  movzx   r13d, r8b
0x180054466  mov     r12d, edx
0x180054469  mov     [rsp+120h+var_E8], esi
0x18005446d  mov     rbx, rcx
0x180054470  lea     rdx, qword_1800A1850
0x180054477  lea     r8, _TraceLoggingMetadata
0x18005447e  cmp     eax, 5
0x180054481  jbe     loc_180054560
0x180054487  mov     rcx, cs:qword_1800C30B0
0x18005448e  mov     rax, cs:qword_1800C30A8
0x180054495  test    al, 2
0x180054497  jz      loc_180054560
0x18005449d  mov     rax, rcx
0x1800544a0  and     eax, 2
0x1800544a3  cmp     rax, rcx
0x1800544a6  jnz     loc_180054560
0x1800544ac  mov     [rbp+57h+var_B0], rdx
0x1800544b0  lea     rax, [rbx+4Ch]
0x1800544b4  mov     [rbp+57h+var_90], rax
0x1800544b8  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800544bd  lea     rax, [rbx+5Ch]
0x1800544c1  mov     [rbp+57h+var_88], 10h
0x1800544c9  mov     [rbp+57h+var_A0], rax
0x1800544cd  xor     r9d, r9d; RelatedActivityId
0x1800544d0  movzx   eax, cs:word_1800AE6F9
0x1800544d7  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x1800544db  mov     rax, cs:off_1800C30A0
0x1800544e2  mov     [rbp+57h+var_D0.Ptr], rax
0x1800544e6  mov     [rbp+57h+var_98], 10h
0x1800544ee  mov     [rbp+57h+var_A8], 1
0x1800544f6  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1800544fe  mov     [rsp+120h+EventDescriptor.Keyword], 2
0x180054507  movzx   eax, word ptr [rax]
0x18005450a  mov     [rbp+57h+var_D0.Size], eax
0x18005450d  lea     rax, byte_1800AE703
0x180054514  mov     [rbp+57h+var_C0], rax
0x180054518  lea     rax, _TraceLoggingMetadataEnd
0x18005451f  sub     eax, r8d
0x180054522  mov     dword ptr [rbp+57h+var_D0.0Ch], 2
0x180054529  mov     [rbp+57h+var_B8], 45h ; 'E'
0x180054530  xor     r8d, r8d; ActivityId
0x180054533  mov     [rbp+57h+var_B4], 1
0x18005453a  mov     [rsp+120h+var_EC], eax
0x18005453e  mov     eax, [rsp+120h+var_EC]
0x180054542  mov     rcx, cs:RegHandle; RegHandle
0x180054549  lea     rax, [rbp+57h+var_D0]
0x18005454d  mov     [rsp+120h+UserData], rax; UserData
0x180054552  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x18005455a  call    cs:__imp_EventWriteTransfer
0x180054560  lea     rcx, [rbx+0A0h]; SRWLock
0x180054567  call    cs:__imp_AcquireSRWLockExclusive
0x18005456d  call    cs:__imp_GetCurrentThreadId
0x180054573  lea     rdi, [rbx+0B0h]
0x18005457a  mov     [rbx+0D0h], r12d
0x180054581  mov     ecx, r13d
0x180054584  mov     [rbx+98h], eax
0x18005458a  shl     ecx, 6
0x18005458d  xor     ecx, [rdi]
0x18005458f  and     ecx, 40h
0x180054592  xor     ecx, [rdi]
0x180054594  mov     [rdi], ecx
0x180054596  test    cl, 1
0x180054599  jnz     short loc_1800545E0
0x18005459b  mov     r15, [rbx+0B8h]
0x1800545a2  or      ecx, 21h
0x1800545a5  mov     [rdi], ecx
0x1800545a7  mov     rcx, rbx; this
0x1800545aa  mov     [rsp+120h+var_F0], sil
0x1800545af  mov     [rbx+0B8h], rsi
0x1800545b6  call    ?DisarmProcessWaitCallback@CBackgroundWorkItemInstanceRemote@@AEAAXXZ; CBackgroundWorkItemInstanceRemote::DisarmProcessWaitCallback(void)
0x1800545bb  mov     rcx, [rbx+0A8h]
0x1800545c2  test    rcx, rcx
0x1800545c5  jz      short loc_1800545D3
0x1800545c7  mov     rax, [rcx]
0x1800545ca  mov     rax, [rax+10h]
0x1800545ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545d3  mov     ecx, [rdi]
0x1800545d5  mov     esi, ecx
0x1800545d7  shr     esi, 4
0x1800545da  and     sil, 1
0x1800545de  jmp     short loc_1800545E8
0x1800545e0  xor     r15d, r15d
0x1800545e3  mov     [rsp+120h+var_F0], 1
0x1800545e8  test    cl, 2
0x1800545eb  jz      short loc_180054647
0x1800545ed  nop     dword ptr [rax]
0x1800545f0  test    cl, 4
0x1800545f3  jnz     short loc_180054647
0x1800545f5  mov     [rsp+120h+var_E8], ecx
0x1800545f9  lea     rcx, [rbx+0A0h]; SRWLock
0x180054600  mov     dword ptr [rbx+98h], 0
0x18005460a  call    cs:__imp_ReleaseSRWLockExclusive
0x180054610  xor     r9d, r9d
0x180054613  lea     rdx, [rsp+120h+var_E8]
0x180054618  mov     r8d, 4
0x18005461e  mov     rcx, rdi
0x180054621  call    cs:__imp_RtlWaitOnAddress
0x180054627  lea     rcx, [rbx+0A0h]; SRWLock
0x18005462e  call    cs:__imp_AcquireSRWLockExclusive
0x180054634  call    cs:__imp_GetCurrentThreadId
0x18005463a  mov     [rbx+98h], eax
0x180054640  mov     ecx, [rdi]
0x180054642  test    cl, 2
0x180054645  jnz     short loc_1800545F0
0x180054647  xor     edi, edi
0x180054649  lea     rcx, [rbx+0A0h]; SRWLock
0x180054650  mov     [rbx+98h], edi
0x180054656  call    cs:__imp_ReleaseSRWLockExclusive
0x18005465c  test    r15, r15
0x18005465f  jz      short loc_180054670
0x180054661  mov     rax, [r15]
0x180054664  mov     rcx, r15
0x180054667  mov     rax, [rax+10h]
0x18005466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054670  test    sil, sil
0x180054673  jz      short loc_180054689
0x180054675  lea     rdx, [rbx+4Ch]; Source2
0x180054679  mov     r9d, r12d
0x18005467c  lea     rcx, [rbx+5Ch]; Source1
0x180054680  movzx   r8d, r13b
0x180054684  call    BipTaskCompletionCallback
0x180054689  mov     eax, cs:dword_1800C3098
0x18005468f  cmp     eax, 5
0x180054692  jbe     loc_1800547DA
0x180054698  mov     rcx, cs:qword_1800C30B0
0x18005469f  mov     rax, cs:qword_1800C30A8
0x1800546a6  test    al, 2
0x1800546a8  jz      loc_1800547DA
0x1800546ae  mov     rax, rcx
0x1800546b1  and     eax, 2
0x1800546b4  cmp     rax, rcx
0x1800546b7  jnz     loc_1800547DA
0x1800546bd  movzx   eax, [rsp+120h+var_F0]
0x1800546c2  lea     rcx, _TraceLoggingMetadata
0x1800546c9  mov     [rsp+120h+var_F0], al
0x1800546cd  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800546d2  mov     [rsp+120h+var_EF], r13b
0x1800546d7  lea     rax, [rsp+120h+var_EF]
0x1800546dc  mov     [rbp+57h+var_50], rax
0x1800546e0  xor     r9d, r9d; RelatedActivityId
0x1800546e3  mov     [rsp+120h+var_EC], r12d
0x1800546e8  lea     rax, [rsp+120h+var_EC]
0x1800546ed  mov     [rbp+57h+var_60], rax
0x1800546f1  xor     r8d, r8d; ActivityId
0x1800546f4  mov     [rsp+120h+var_EE], sil
0x1800546f9  lea     rax, [rsp+120h+var_EE]
0x1800546fe  mov     [rbp+57h+var_70], rax
0x180054702  lea     rax, [rsp+120h+var_F0]
0x180054707  mov     [rbp+57h+var_80], rax
0x18005470b  lea     rax, [rbx+4Ch]
0x18005470f  mov     [rbp+57h+var_90], rax
0x180054713  lea     rax, [rbx+5Ch]
0x180054717  mov     [rbp+57h+var_A0], rax
0x18005471b  lea     rax, qword_1800A1850
0x180054722  mov     [rbp+57h+var_B0], rax
0x180054726  movzx   eax, cs:word_1800AE74A
0x18005472d  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180054731  mov     rax, cs:off_1800C30A0
0x180054738  mov     [rbp+57h+var_D0.Ptr], rax
0x18005473c  mov     [rbp+57h+var_48], 1
0x180054744  mov     [rbp+57h+var_58], 4
0x18005474c  mov     [rbp+57h+var_68], 1
0x180054754  mov     [rbp+57h+var_78], 1
0x18005475c  mov     [rbp+57h+var_88], 10h
0x180054764  mov     [rbp+57h+var_98], 10h
0x18005476c  mov     [rbp+57h+var_A8], 1
0x180054774  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18005477c  mov     [rsp+120h+EventDescriptor.Keyword], 2
0x180054785  movzx   eax, word ptr [rax]
0x180054788  mov     [rbp+57h+var_D0.Size], eax
0x18005478b  lea     rax, dword_1800AE754
0x180054792  mov     [rbp+57h+var_C0], rax
0x180054796  lea     rax, _TraceLoggingMetadataEnd
0x18005479d  sub     eax, ecx
0x18005479f  mov     dword ptr [rbp+57h+var_D0.0Ch], 2
0x1800547a6  mov     [rbp+57h+var_B8], 84h
0x1800547ad  mov     [rbp+57h+var_B4], 1
0x1800547b4  mov     [rsp+120h+var_E4], eax
0x1800547b8  mov     eax, [rsp+120h+var_E4]
0x1800547bc  mov     rcx, cs:RegHandle; RegHandle
0x1800547c3  lea     rax, [rbp+57h+var_D0]
0x1800547c7  mov     [rsp+120h+UserData], rax; UserData
0x1800547cc  mov     [rsp+120h+UserDataCount], 9; UserDataCount
0x1800547d4  call    cs:__imp_EventWriteTransfer
0x1800547da  xor     eax, eax
0x1800547dc  mov     rcx, [rbp+57h+var_40]
0x1800547e0  xor     rcx, rsp; StackCookie
0x1800547e3  call    __security_check_cookie
0x1800547e8  mov     rbx, [rsp+120h+arg_18]
0x1800547f0  add     rsp, 0F0h
0x1800547f7  pop     r15
0x1800547f9  pop     r14
0x1800547fb  pop     r13
0x1800547fd  pop     r12
0x1800547ff  pop     rdi
0x180054800  pop     rsi
0x180054801  pop     rbp
0x180054802  retn
```
