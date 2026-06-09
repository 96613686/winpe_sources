# NtfsNotifyChangeDirectory

- ea: `0x1401a6448`
- end: `0x1401a68ca`
- name: `NtfsNotifyChangeDirectory`
- size: `1154`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID FsContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a7760`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000ea70`
- `0x140010be0`
- `0x140020de0`
- `0x140184220`
- `0x1401a6448`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401a65db`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1401a65db`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a670e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a6766`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a670e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1401a6766`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1401a653b`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1401a653b`
- `ntoskrnl!SeTokenIsAdmin` at `0x1401a6783`
- `ntoskrnl!SeTokenIsAdmin` at `0x1401a6783`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401a67c3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401a67c3`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1401a6851`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1401a6851`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a67d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad7de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a67d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad7de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a674a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a66f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a674a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a64c0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a64c0`

## pseudocode

```c
__int64 __fastcall NtfsNotifyChangeDirectory(__int64 a1, IRP *a2, __int64 a3, __int64 a4, _DWORD *FsContext)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  __int64 (__fastcall *v9)(); // r14
  int v10; // edi
  __int64 v11; // rdx
  int v12; // r12d
  PVOID v13; // rdi
  UCHAR MinorFunction; // al
  PACCESS_TOKEN ClientToken; // rcx
  char v17; // [rsp+61h] [rbp-67h]
  BOOLEAN WatchTree[4]; // [rsp+64h] [rbp-64h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+80h] [rbp-48h]
  ULONG CompletionFilter; // [rsp+D8h] [rbp+10h]

  PoolWithTag = 0;
  v9 = 0;
  v17 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
  v10 = CurrentStackLocation->Flags & 1;
  *(_DWORD *)WatchTree = v10;
  *(_DWORD *)(a1 + 12) |= 1u;
  NtfsPurgeFileRecordCache(a1);
  if ( !ExAcquireResourceSharedLite((PERESOURCE)(a3 + 2160), 1u) )
  {
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1901753);
    JUMPOUT(0x1401A68CALL);
  }
  if ( !*(_WORD *)(*(_QWORD *)(a4 + 184) + 188LL) )
  {
LABEL_24:
    if ( NtfsStatusDebugFlags )
      goto LABEL_26;
    while ( 1 )
    {
      NtfsRaiseStatusInternal(a1, -1073741738, 0, 0, 854924);
LABEL_26:
      NtfsStatusTraceAndDebugInternal(a1, 3221225558LL, 854924);
    }
  }
  v12 = *(_DWORD *)(a4 + 512) & 4;
  if ( v12 || !v10 )
  {
    v13 = FsContext;
    goto LABEL_12;
  }
  v13 = FsContext;
  if ( (FsContext[1] & 0x80u) != 0 )
    goto LABEL_30;
  while ( 1 )
  {
    if ( byte_140095C7E )
    {
      if ( !_bittest16((const signed __int16 *)v13 + 52, 9u)
        && ((unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread(), v11, 0)
         || (unsigned __int8)NtfsEffectiveMode(a2) == 1) )
      {
        if ( !PoolWithTag )
        {
          PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                              (POOL_TYPE)(PoolType | 0x10),
                                                              0x20u,
                                                              0x6446744Eu);
          SeCaptureSubjectContext(PoolWithTag);
        }
        ClientToken = PoolWithTag->ClientToken;
        if ( !PoolWithTag->ClientToken )
          ClientToken = PoolWithTag->PrimaryToken;
        if ( !SeTokenIsAdmin(ClientToken) )
          v9 = NtfsNotifyTraverseCheckEx;
      }
      if ( !v9 && PoolWithTag )
      {
        SeReleaseSubjectContext(PoolWithTag);
        ExFreePoolWithTag(PoolWithTag, 0);
        PoolWithTag = 0;
      }
    }
LABEL_12:
    if ( (*((_DWORD *)v13 + 1) & 0x800000) == 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a3 + 4LL * (v12 != 0) + 2436));
      v17 = 1;
    }
    MinorFunction = CurrentStackLocation->MinorFunction;
    if ( !v12 )
      break;
    if ( MinorFunction != 3 || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
    {
      FsRtlNotifyFilterChangeDirectory(
        *(PNOTIFY_SYNC *)(a3 + 1464),
        (PLIST_ENTRY)(a3 + 1448),
        v13,
        0,
        WatchTree[0],
        0,
        CompletionFilter,
        a2,
        0,
        *(PSECURITY_SUBJECT_CONTEXT *)(a4 + 184),
        0);
      goto LABEL_17;
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 855024);
    NtfsRaiseStatusInternal(a1, -1073741637, 0, 0, 855024);
LABEL_30:
    PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                        (POOL_TYPE)(PoolType | 0x10),
                                                        0x20u,
                                                        0x6446744Eu);
    SeCaptureSubjectContext(PoolWithTag);
    v9 = NtfsNotifyTraverseCheck;
  }
  if ( MinorFunction == 3 && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 1 > 2 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225475LL, 855049);
    NtfsRaiseStatusInternal(a1, -1073741821, 0, 0, 855049);
    goto LABEL_24;
  }
  FsRtlNotifyFilterChangeDirectoryLite(
    a4 + 768,
    a4 + 752,
    v13,
    *(unsigned int *)WatchTree,
    CompletionFilter,
    a2,
    v9,
    PoolWithTag,
    TxfIsoReportChangeFilter);
LABEL_17:
  if ( v17 && (*((_DWORD *)v13 + 1) & 0x800000) == 0 )
    _InterlockedOr((volatile signed __int32 *)v13 + 1, 0x800000u);
  NtfsReleaseVcb(a1, a3);
  NtfsExtendedCompleteRequestInternal(a1, 0, 0, 0, 1);
  return 259;
}

```

## disassembly

```asm
0x1401a6448  mov     rax, rsp
0x1401a644b  mov     [rax+18h], r8
0x1401a644f  mov     [rax+8], rcx
0x1401a6453  push    rbx
0x1401a6454  push    rsi
0x1401a6455  push    rdi
0x1401a6456  push    r12
0x1401a6458  push    r13
0x1401a645a  push    r14
0x1401a645c  push    r15
0x1401a645e  sub     rsp, 90h
0x1401a6465  mov     r13, r9
0x1401a6468  mov     r15, r8
0x1401a646b  mov     [rax-58h], rdx
0x1401a646f  mov     rbx, rcx
0x1401a6472  xor     ecx, ecx
0x1401a6474  mov     esi, ecx
0x1401a6476  mov     [rax-60h], rcx
0x1401a647a  mov     r14d, ecx
0x1401a647d  mov     [rax-66h], cl
0x1401a6480  mov     [rax-68h], cl
0x1401a6483  mov     [rax-67h], cl
0x1401a6486  mov     rax, [rdx+0B8h]
0x1401a648d  mov     [rsp+0C8h+var_48], rax
0x1401a6495  mov     ecx, [rax+10h]
0x1401a6498  mov     [rsp+0C8h+arg_8], ecx
0x1401a649f  mov     al, [rax+2]
0x1401a64a2  and     al, 1
0x1401a64a4  movzx   edi, al
0x1401a64a7  mov     dword ptr [rsp+0C8h+var_64], edi
0x1401a64ab  or      dword ptr [rbx+0Ch], 1
0x1401a64af  mov     rcx, rbx
0x1401a64b2  call    NtfsPurgeFileRecordCache
0x1401a64b7  lea     rcx, [r15+870h]; Resource
0x1401a64be  mov     dl, 1; Wait
0x1401a64c0  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a64c7  nop     dword ptr [rax+rax+00h]
0x1401a64cc  xor     r8d, r8d
0x1401a64cf  test    al, al
0x1401a64d1  jz      loc_1401A68AA
0x1401a64d7  mov     rax, [r13+0B8h]
0x1401a64de  cmp     [rax+0BCh], r8w
0x1401a64e6  jz      loc_1401A666A
0x1401a64ec  mov     r12d, [r13+200h]
0x1401a64f3  and     r12d, 4
0x1401a64f7  setnz   [rsp+0C8h+var_66]
0x1401a64fc  test    r12d, r12d
0x1401a64ff  jnz     short loc_1401A6569
0x1401a6501  test    edi, edi
0x1401a6503  jz      short loc_1401A6569
0x1401a6505  mov     rdi, [rsp+0C8h+FsContext]
0x1401a650d  mov     eax, [rdi+4]
0x1401a6510  test    al, al
0x1401a6512  js      loc_1401A66DE
0x1401a6518  mov     [rsp+0C8h+var_68], r8b
0x1401a651d  cmp     cs:byte_140095C7E, 0
0x1401a6524  jz      short loc_1401A6571
0x1401a6526  bt      word ptr [rdi+68h], 9
0x1401a652c  jb      loc_1401A67A4
0x1401a6532  mov     rcx, gs:188h
0x1401a653b  call    cs:__imp_PsIsThreadImpersonating
0x1401a6542  nop     dword ptr [rax+rax+00h]
0x1401a6547  test    al, al
0x1401a6549  jnz     loc_1401A6733
0x1401a654f  mov     rcx, [rsp+0C8h+var_58]
0x1401a6554  call    NtfsEffectiveMode
0x1401a6559  cmp     al, 1
0x1401a655b  jz      loc_1401A6733
0x1401a6561  xor     r8d, r8d
0x1401a6564  jmp     loc_1401A67A4
0x1401a6569  mov     rdi, [rsp+0C8h+FsContext]
0x1401a6571  test    dword ptr [rdi+4], 800000h
0x1401a6578  jz      loc_1401A660B
0x1401a657e  mov     rcx, [rsp+0C8h+var_48]
0x1401a6586  mov     al, [rcx+1]
0x1401a6589  test    r12d, r12d
0x1401a658c  jnz     loc_1401A67F5
0x1401a6592  cmp     al, 3
0x1401a6594  jz      loc_1401A6623
0x1401a659a  lea     rdx, [r13+2F0h]
0x1401a65a1  lea     rcx, [r13+300h]
0x1401a65a8  lea     rax, TxfIsoReportChangeFilter
0x1401a65af  mov     [rsp+0C8h+TraverseCallback], rax
0x1401a65b4  mov     [rsp+0C8h+NotifyIrp], rsi
0x1401a65b9  mov     qword ptr [rsp+0C8h+CompletionFilter], r14
0x1401a65be  mov     rax, [rsp+0C8h+var_58]
0x1401a65c3  mov     qword ptr [rsp+0C8h+IgnoreBuffer], rax
0x1401a65c8  mov     eax, [rsp+0C8h+arg_8]
0x1401a65cf  mov     dword ptr [rsp+0C8h+WatchTree], eax
0x1401a65d3  mov     r9d, dword ptr [rsp+0C8h+var_64]
0x1401a65d8  mov     r8, rdi
0x1401a65db  call    cs:__imp_FsRtlNotifyFilterChangeDirectoryLite
0x1401a65e2  nop     dword ptr [rax+rax+00h]
0x1401a65e7  cmp     [rsp+0C8h+var_67], 0
0x1401a65ec  jz      loc_1401A6862
0x1401a65f2  mov     eax, [rdi+4]
0x1401a65f5  mov     ecx, 800000h
0x1401a65fa  test    ecx, eax
0x1401a65fc  jnz     loc_1401A6862
0x1401a6602  lock or [rdi+4], ecx
0x1401a6606  jmp     loc_1401A6862
0x1401a660b  movzx   eax, [rsp+0C8h+var_66]
0x1401a6610  lock inc dword ptr [r15+rax*4+984h]
0x1401a6619  mov     [rsp+0C8h+var_67], 1
0x1401a661e  jmp     loc_1401A657E
0x1401a6623  mov     eax, [rcx+18h]
0x1401a6626  dec     eax
0x1401a6628  cmp     eax, 2
0x1401a662b  jbe     loc_1401A659A
0x1401a6631  mov     al, cs:NtfsStatusDebugFlags
0x1401a6637  test    al, al
0x1401a6639  jz      short loc_1401A664E
0x1401a663b  mov     edx, 0C0000003h
0x1401a6640  mov     r8d, 0D0C09h
0x1401a6646  mov     rcx, rbx
0x1401a6649  call    NtfsStatusTraceAndDebugInternal
0x1401a664e  mov     qword ptr [rsp+0C8h+WatchTree], 0D0C09h
0x1401a6657  xor     r9d, r9d
0x1401a665a  xor     r8d, r8d
0x1401a665d  mov     edx, 0C0000003h
0x1401a6662  mov     rcx, rbx
0x1401a6665  call    NtfsRaiseStatusInternal
0x1401a666a  mov     al, cs:NtfsStatusDebugFlags
0x1401a6670  test    al, al
0x1401a6672  jnz     short loc_1401A6690
0x1401a6674  mov     qword ptr [rsp+0C8h+WatchTree], 0D0B8Ch
0x1401a667d  xor     r9d, r9d
0x1401a6680  xor     r8d, r8d
0x1401a6683  mov     edx, 0C0000056h
0x1401a6688  mov     rcx, rbx
0x1401a668b  call    NtfsRaiseStatusInternal
0x1401a6690  mov     edx, 0C0000056h
0x1401a6695  mov     r8d, 0D0B8Ch
0x1401a669b  mov     rcx, rbx
0x1401a669e  call    NtfsStatusTraceAndDebugInternal
0x1401a66a3  jmp     short loc_1401A6674
0x1401a66a5  mov     al, cs:NtfsStatusDebugFlags
0x1401a66ab  test    al, al
0x1401a66ad  jz      short loc_1401A66C2
0x1401a66af  mov     edx, 0C00000BBh
0x1401a66b4  mov     r8d, 0D0BF0h
0x1401a66ba  mov     rcx, rbx
0x1401a66bd  call    NtfsStatusTraceAndDebugInternal
0x1401a66c2  mov     qword ptr [rsp+0C8h+WatchTree], 0D0BF0h
0x1401a66cb  xor     r9d, r9d
0x1401a66ce  xor     r8d, r8d
0x1401a66d1  mov     edx, 0C00000BBh
0x1401a66d6  mov     rcx, rbx
0x1401a66d9  call    NtfsRaiseStatusInternal
0x1401a66de  mov     ecx, cs:PoolType
0x1401a66e4  or      ecx, 10h; PoolType
0x1401a66e7  mov     edx, 20h ; ' '; NumberOfBytes
0x1401a66ec  mov     r8d, 6446744Eh; Tag
0x1401a66f2  call    cs:__imp_ExAllocatePoolWithTag
0x1401a66f9  nop     dword ptr [rax+rax+00h]
0x1401a66fe  mov     rsi, rax
0x1401a6701  mov     [rsp+0C8h+var_60], rax
0x1401a6706  mov     [rsp+0C8h+var_68], 1
0x1401a670b  mov     rcx, rax; SubjectContext
0x1401a670e  call    cs:__imp_SeCaptureSubjectContext
0x1401a6715  nop     dword ptr [rax+rax+00h]
0x1401a671a  xor     r8d, r8d
0x1401a671d  mov     [rsp+0C8h+var_68], r8b
0x1401a6722  lea     r14, NtfsNotifyTraverseCheck
0x1401a6729  mov     [rsp+0C8h+var_50], r14
0x1401a672e  jmp     loc_1401A6518
0x1401a6733  test    rsi, rsi
0x1401a6736  jnz     short loc_1401A6777
0x1401a6738  mov     ecx, cs:PoolType
0x1401a673e  or      ecx, 10h; PoolType
0x1401a6741  lea     edx, [rsi+20h]; NumberOfBytes
0x1401a6744  mov     r8d, 6446744Eh; Tag
0x1401a674a  call    cs:__imp_ExAllocatePoolWithTag
0x1401a6751  nop     dword ptr [rax+rax+00h]
0x1401a6756  mov     rsi, rax
0x1401a6759  mov     [rsp+0C8h+var_60], rax
0x1401a675e  mov     [rsp+0C8h+var_68], 1
0x1401a6763  mov     rcx, rax; SubjectContext
0x1401a6766  call    cs:__imp_SeCaptureSubjectContext
0x1401a676d  nop     dword ptr [rax+rax+00h]
0x1401a6772  mov     [rsp+0C8h+var_68], 0
0x1401a6777  mov     rcx, [rsi]
0x1401a677a  test    rcx, rcx
0x1401a677d  jnz     short loc_1401A6783
0x1401a677f  mov     rcx, [rsi+10h]; Token
0x1401a6783  call    cs:__imp_SeTokenIsAdmin
0x1401a678a  nop     dword ptr [rax+rax+00h]
0x1401a678f  lea     rcx, NtfsNotifyTraverseCheckEx
0x1401a6796  xor     r8d, r8d
0x1401a6799  test    al, al
0x1401a679b  cmovz   r14, rcx
0x1401a679f  mov     [rsp+0C8h+var_50], r14
0x1401a67a4  mov     [rsp+0C8h+var_68], r8b
0x1401a67a9  test    r14, r14
0x1401a67ac  jnz     loc_1401A6571
0x1401a67b2  mov     [rsp+0C8h+var_68], r8b
0x1401a67b7  test    rsi, rsi
0x1401a67ba  jz      loc_1401A6571
0x1401a67c0  mov     rcx, rsi; SubjectContext
0x1401a67c3  call    cs:__imp_SeReleaseSubjectContext
0x1401a67ca  nop     dword ptr [rax+rax+00h]
0x1401a67cf  xor     edx, edx; Tag
0x1401a67d1  mov     rcx, rsi; P
0x1401a67d4  call    cs:__imp_ExFreePoolWithTag
0x1401a67db  nop     dword ptr [rax+rax+00h]
0x1401a67e0  xor     r8d, r8d
0x1401a67e3  mov     esi, r8d
0x1401a67e6  mov     [rsp+0C8h+var_60], r8
0x1401a67eb  mov     [rsp+0C8h+var_68], r8b
0x1401a67f0  jmp     loc_1401A6571
0x1401a67f5  cmp     al, 3
0x1401a67f7  jnz     short loc_1401A6803
0x1401a67f9  cmp     dword ptr [rcx+18h], 1
0x1401a67fd  jnz     loc_1401A66A5
0x1401a6803  lea     rdx, [r15+5A8h]; NotifyList
0x1401a680a  mov     [rsp+0C8h+FilterCallback], r8; FilterCallback
0x1401a680f  mov     rax, [r13+0B8h]
0x1401a6816  mov     [rsp+0C8h+SubjectContext], rax; SubjectContext
0x1401a681b  mov     [rsp+0C8h+TraverseCallback], r8; TraverseCallback
0x1401a6820  mov     rax, [rsp+0C8h+var_58]
0x1401a6825  mov     [rsp+0C8h+NotifyIrp], rax; NotifyIrp
0x1401a682a  mov     eax, [rsp+0C8h+arg_8]
0x1401a6831  mov     [rsp+0C8h+CompletionFilter], eax; CompletionFilter
0x1401a6835  mov     [rsp+0C8h+IgnoreBuffer], r8b; IgnoreBuffer
0x1401a683a  mov     r9d, dword ptr [rsp+0C8h+var_64]
0x1401a683f  mov     [rsp+0C8h+WatchTree], r9b; WatchTree
0x1401a6844  xor     r9d, r9d; FullDirectoryName
0x1401a6847  mov     r8, rdi; FsContext
0x1401a684a  mov     rcx, [r15+5B8h]; NotifySync
0x1401a6851  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1401a6858  nop     dword ptr [rax+rax+00h]
0x1401a685d  jmp     loc_1401A65E7
0x1401a6862  mov     al, cs:NtfsStatusDebugFlags
0x1401a6868  mov     rdx, r15
0x1401a686b  mov     rcx, rbx
0x1401a686e  call    NtfsReleaseVcb
0x1401a6873  mov     al, cs:NtfsStatusDebugFlags
0x1401a6879  mov     dword ptr [rsp+0C8h+WatchTree], 1
0x1401a6881  xor     r9d, r9d
0x1401a6884  xor     r8d, r8d
0x1401a6887  xor     edx, edx
0x1401a6889  mov     rcx, rbx
0x1401a688c  call    NtfsExtendedCompleteRequestInternal
0x1401a6891  mov     eax, 103h
0x1401a6896  add     rsp, 90h
0x1401a689d  pop     r15
0x1401a689f  pop     r14
0x1401a68a1  pop     r13
0x1401a68a3  pop     r12
0x1401a68a5  pop     rdi
0x1401a68a6  pop     rsi
0x1401a68a7  pop     rbx
0x1401a68a8  retn
0x1401a68aa  mov     al, cs:NtfsStatusDebugFlags
0x1401a68b0  mov     qword ptr [rsp+0C8h+WatchTree], 1D04B9h
0x1401a68b9  xor     r9d, r9d
0x1401a68bc  mov     edx, 0C00000D8h
0x1401a68c1  mov     rcx, rbx
0x1401a68c4  call    NtfsRaiseStatusInternal
0x1401a68c9  nop
0x1402ad76c  push    rbx
0x1402ad76e  push    rbp
0x1402ad76f  push    rdi
0x1402ad770  sub     rsp, 60h
0x1402ad774  mov     rbp, rdx
0x1402ad777  movzx   edi, cl
0x1402ad77a  test    cl, cl
0x1402ad77c  jz      short loc_1402AD784
0x1402ad77e  mov     al, cs:NtfsStatusDebugFlags
0x1402ad784  mov     rbx, [rbp+0E0h]
0x1402ad78b  mov     rdx, rbx
0x1402ad78e  mov     rcx, [rbp+0D0h]
0x1402ad795  call    NtfsReleaseVcb
0x1402ad79a  mov     eax, edi
0x1402ad79c  test    dil, dil
0x1402ad79f  jz      short loc_1402AD7EB
0x1402ad7a1  cmp     byte ptr [rbp+61h], 0
0x1402ad7a5  jz      short loc_1402AD7D2
0x1402ad7a7  mov     rcx, [rbp+0F0h]
0x1402ad7ae  add     rcx, 4
0x1402ad7b2  mov     edx, 800000h
0x1402ad7b7  call    ClearFlagInterlocked
0x1402ad7bc  cmp     byte ptr [rbp+62h], 0
0x1402ad7c0  jz      short loc_1402AD7CB
0x1402ad7c2  lock dec dword ptr [rbx+988h]
0x1402ad7c9  jmp     short loc_1402AD7D2
0x1402ad7cb  lock dec dword ptr [rbx+984h]
0x1402ad7d2  cmp     byte ptr [rbp+60h], 0
0x1402ad7d6  jz      short loc_1402AD7EB
0x1402ad7d8  xor     edx, edx; Tag
0x1402ad7da  mov     rcx, [rbp+68h]; P
0x1402ad7de  call    cs:__imp_ExFreePoolWithTag
0x1402ad7e5  nop     dword ptr [rax+rax+00h]
0x1402ad7ea  nop
0x1402ad7eb  add     rsp, 60h
0x1402ad7ef  pop     rdi
0x1402ad7f0  pop     rbp
0x1402ad7f1  pop     rbx
0x1402ad7f2  retn
```
