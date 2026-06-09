# ARI::ProcessToken::AutoSysAppId::OpenProcessIfPackaged(void *)

- ea: `0x180033578`
- end: `0x1800337f1`
- name: `?OpenProcessIfPackaged@AutoSysAppId@ProcessToken@ARI@@QEAAJPEAX@Z`
- size: `633`
- prototype: `__int64 __fastcall(ARI::ProcessToken::AutoSysAppId *__hidden this, HANDLE ProcessHandle)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180033200`
- `0x180034060`
- `0x1800b7190`
- `0x1800fb020`

## callees

- `0x1800134a0`
- `0x180033578`
- `0x180033d08`
- `0x180033d34`
- `0x180048f30`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800336b3`
- `ntdll!RtlInitUnicodeString` at `0x1800336cb`
- `ntdll!RtlInitUnicodeString` at `0x1800336b3`
- `ntdll!RtlInitUnicodeString` at `0x1800336cb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800337ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7aa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800337ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7aa`
- `ntdll!NtQueryInformationToken` at `0x180033608`
- `ntdll!NtQueryInformationToken` at `0x180033686`
- `ntdll!NtQueryInformationToken` at `0x180033608`
- `ntdll!NtQueryInformationToken` at `0x180033686`
- `ntdll!RtlCompareUnicodeString` at `0x1800336f9`
- `ntdll!RtlCompareUnicodeString` at `0x180033712`
- `ntdll!RtlCompareUnicodeString` at `0x1800336f9`
- `ntdll!RtlCompareUnicodeString` at `0x180033712`
- `ntdll!NtOpenProcessToken` at `0x1800335c3`
- `ntdll!NtOpenProcessToken` at `0x1800335c3`
- `ntdll!RtlAllocateHeap` at `0x180033654`
- `ntdll!RtlAllocateHeap` at `0x180033654`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::AutoSysAppId::OpenProcessIfPackaged(
        ARI::ProcessToken::AutoSysAppId *this,
        HANDLE ProcessHandle)
{
  void *v4; // rcx
  NTSTATUS v5; // eax
  ULONG LastErrorValue; // ebx
  __int64 v7; // rbx
  NTSTATUS v8; // eax
  char v9; // r14
  PVOID Heap; // rax
  PVOID v11; // rdi
  int v12; // eax
  char v13; // r13
  __int64 v14; // rbx
  char v15; // r12
  __int64 v16; // rax
  const UNICODE_STRING *v17; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+90h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp+48h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+50h]

  v4 = *(void **)this;
  if ( v4 )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v4);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  TokenHandle = 0;
  if ( ProcessHandle == (HANDLE)-1LL )
  {
    v7 = -4;
    TokenHandle = (HANDLE)-4LL;
  }
  else
  {
    v5 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
    if ( v5 < 0 )
    {
      BaseSetLastNTError((unsigned int)v5);
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( LastErrorValue )
        return LastErrorValue;
    }
    v7 = (__int64)TokenHandle;
  }
  TokenInformationLength = 0;
  v8 = NtQueryInformationToken((HANDLE)v7, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v8 != -1073741789 )
  {
    if ( v8 )
      LastErrorValue = RtlNtStatusToDosErrorNoTeb(v8);
    else
      LastErrorValue = 1359;
    goto LABEL_10;
  }
  v23 = 0;
  if ( !is_mul_ok(TokenInformationLength, 0x10u)
    || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v11 = Heap) == 0) )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    LastErrorValue = 8;
LABEL_10:
    v9 = 0;
    goto LABEL_23;
  }
  memset_0(Heap, 0, TokenInformationLength);
  v12 = NtQueryInformationToken(
          (HANDLE)v7,
          TokenSecurityAttributes,
          v11,
          TokenInformationLength,
          &TokenInformationLength);
  if ( v12 < 0 )
  {
    LastErrorValue = RtlNtStatusToDosErrorNoTeb(v12);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
    goto LABEL_10;
  }
  if ( *((_DWORD *)v11 + 1) )
  {
    v13 = 1;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
    String1 = 0;
    RtlInitUnicodeString(&String1, L"WIN://PKG");
    v14 = 0;
    v15 = 1;
    v9 = 0;
    while ( (unsigned int)v14 < *((_DWORD *)v11 + 1) )
    {
      v16 = *((_QWORD *)v11 + 1);
      v17 = (const UNICODE_STRING *)(v16 + 40 * v14);
      if ( v13 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v16 + 40 * v14), 1u) )
      {
        *((_QWORD *)this + 1) = v17;
        if ( !v15 )
          goto LABEL_32;
        v13 = 0;
      }
      else if ( v15 && !RtlCompareUnicodeString(&String1, v17, 1u) )
      {
        v9 = 1;
        if ( !v13 )
        {
LABEL_32:
          *(_QWORD *)this = v11;
          AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
          LastErrorValue = 0;
          goto LABEL_23;
        }
        v15 = 0;
      }
      v14 = (unsigned int)(v14 + 1);
    }
  }
  else
  {
    v9 = 0;
  }
  AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
  LastErrorValue = 1168;
LABEL_23:
  if ( TokenHandle != (HANDLE)-4LL )
    CloseHandle(TokenHandle);
  if ( LastErrorValue || v9 )
    return LastErrorValue;
  ARI::ProcessToken::AutoSysAppId::Close(this);
  return 15700;
}

```

## disassembly

```asm
0x180033578  mov     [rsp-38h+arg_18], rbx
0x18003357d  push    rbp
0x18003357e  push    rsi
0x18003357f  push    rdi
0x180033580  push    r12
0x180033582  push    r13
0x180033584  push    r14
0x180033586  push    r15
0x180033588  mov     rbp, rsp
0x18003358b  sub     rsp, 50h
0x18003358f  mov     rsi, rcx
0x180033592  mov     rbx, rdx
0x180033595  mov     rcx, [rcx]; P
0x180033598  test    rcx, rcx
0x18003359b  jnz     loc_1800337A7
0x1800335a1  mov     [rbp+TokenHandle], 0
0x1800335a9  mov     r14d, 8
0x1800335af  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800335b3  jz      loc_180033797
0x1800335b9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800335bd  mov     edx, r14d; DesiredAccess
0x1800335c0  mov     rcx, rbx; ProcessHandle
0x1800335c3  call    cs:__imp_NtOpenProcessToken
0x1800335c9  test    eax, eax
0x1800335cb  jns     short loc_1800335E4
0x1800335cd  mov     ecx, eax
0x1800335cf  call    BaseSetLastNTError
0x1800335d4  mov     ebx, gs:68h
0x1800335dc  test    ebx, ebx
0x1800335de  jnz     loc_18003373E
0x1800335e4  mov     rbx, [rbp+TokenHandle]
0x1800335e8  xor     r9d, r9d; TokenInformationLength
0x1800335eb  mov     [rbp+TokenInformationLength], 0
0x1800335f2  lea     rax, [rbp+TokenInformationLength]
0x1800335f6  xor     r8d, r8d; TokenInformation
0x1800335f9  mov     rcx, rbx; TokenHandle
0x1800335fc  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180033601  lea     r15d, [r9+27h]
0x180033605  mov     edx, r15d; TokenInformationClass
0x180033608  call    cs:__imp_NtQueryInformationToken
0x18003360e  cmp     eax, 0C0000023h
0x180033613  jnz     loc_1800337DF
0x180033619  mov     ecx, [rbp+TokenInformationLength]
0x18003361c  lea     eax, [r15-17h]
0x180033620  mul     rcx
0x180033623  mov     [rbp+arg_10], 0
0x18003362b  test    rdx, rdx
0x18003362e  jz      short loc_180033642
0x180033630  xor     ecx, ecx; P
0x180033632  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033637  mov     ebx, r14d
0x18003363a  xor     r14b, r14b
0x18003363d  jmp     loc_180033730
0x180033642  mov     rcx, gs:60h
0x18003364b  mov     r8, rax; Size
0x18003364e  xor     edx, edx; Flags
0x180033650  mov     rcx, [rcx+30h]; HeapHandle
0x180033654  call    cs:__imp_RtlAllocateHeap
0x18003365a  mov     rdi, rax
0x18003365d  test    rax, rax
0x180033660  jz      short loc_180033630
0x180033662  mov     r8d, [rbp+TokenInformationLength]; Size
0x180033666  xor     edx, edx; Val
0x180033668  mov     rcx, rax; void *
0x18003366b  call    memset_0
0x180033670  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180033674  lea     rax, [rbp+TokenInformationLength]
0x180033678  mov     r8, rdi; TokenInformation
0x18003367b  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180033680  mov     edx, r15d; TokenInformationClass
0x180033683  mov     rcx, rbx; TokenHandle
0x180033686  call    cs:__imp_NtQueryInformationToken
0x18003368c  test    eax, eax
0x18003368e  js      loc_1800337C8
0x180033694  cmp     dword ptr [rdi+4], 0
0x180033698  jbe     loc_180033720
0x18003369e  xorps   xmm0, xmm0
0x1800336a1  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800336a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800336ac  mov     r13b, 1
0x1800336af  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800336b3  call    cs:__imp_RtlInitUnicodeString
0x1800336b9  xorps   xmm0, xmm0
0x1800336bc  lea     rdx, aWinPkg; "WIN://PKG"
0x1800336c3  lea     rcx, [rbp+String1]; DestinationString
0x1800336c7  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1800336cb  call    cs:__imp_RtlInitUnicodeString
0x1800336d1  xor     ebx, ebx
0x1800336d3  mov     r12b, r13b
0x1800336d6  xor     r14b, r14b
0x1800336d9  cmp     ebx, [rdi+4]
0x1800336dc  jnb     short loc_180033723
0x1800336de  mov     rax, [rdi+8]
0x1800336e2  lea     rcx, [rbx+rbx*4]
0x1800336e6  lea     r15, [rax+rcx*8]
0x1800336ea  test    r13b, r13b
0x1800336ed  jz      short loc_180033703
0x1800336ef  mov     r8b, 1; CaseInsensitive
0x1800336f2  lea     rcx, [rbp+DestinationString]; String1
0x1800336f6  mov     rdx, r15; String2
0x1800336f9  call    cs:__imp_RtlCompareUnicodeString
0x1800336ff  test    eax, eax
0x180033701  jz      short loc_180033773
0x180033703  test    r12b, r12b
0x180033706  jz      short loc_18003371C
0x180033708  mov     r8b, 1; CaseInsensitive
0x18003370b  lea     rcx, [rbp+String1]; String1
0x18003370f  mov     rdx, r15; String2
0x180033712  call    cs:__imp_RtlCompareUnicodeString
0x180033718  test    eax, eax
0x18003371a  jz      short loc_180033781
0x18003371c  inc     ebx
0x18003371e  jmp     short loc_1800336D9
0x180033720  xor     r14b, r14b
0x180033723  mov     rcx, rdi; P
0x180033726  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18003372b  mov     ebx, 490h
0x180033730  mov     rcx, [rbp+TokenHandle]; hObject
0x180033734  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180033738  jnz     short loc_180033758
0x18003373a  test    ebx, ebx
0x18003373c  jz      short loc_18003375F
0x18003373e  mov     eax, ebx
0x180033740  mov     rbx, [rsp+50h+arg_18]
0x180033748  add     rsp, 50h
0x18003374c  pop     r15
0x18003374e  pop     r14
0x180033750  pop     r13
0x180033752  pop     r12
0x180033754  pop     rdi
0x180033755  pop     rsi
0x180033756  pop     rbp
0x180033757  retn
0x180033758  call    CloseHandle
0x18003375d  jmp     short loc_18003373A
0x18003375f  test    r14b, r14b
0x180033762  jnz     short loc_18003373E
0x180033764  mov     rcx, rsi; this
0x180033767  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18003376c  mov     eax, 3D54h
0x180033771  jmp     short loc_180033740
0x180033773  mov     [rsi+8], r15
0x180033777  test    r12b, r12b
0x18003377a  jz      short loc_180033789
0x18003377c  xor     r13b, r13b
0x18003377f  jmp     short loc_18003371C
0x180033781  mov     r14b, 1
0x180033784  test    r13b, r13b
0x180033787  jnz     short loc_1800337C0
0x180033789  xor     ecx, ecx; P
0x18003378b  mov     [rsi], rdi
0x18003378e  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033793  xor     ebx, ebx
0x180033795  jmp     short loc_180033730
0x180033797  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x18003379e  mov     [rbp+TokenHandle], rbx
0x1800337a2  jmp     loc_1800335E8
0x1800337a7  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800337ac  mov     qword ptr [rsi], 0
0x1800337b3  mov     qword ptr [rsi+8], 0
0x1800337bb  jmp     loc_1800335A1
0x1800337c0  xor     r12b, r12b
0x1800337c3  jmp     loc_18003371C
0x1800337c8  mov     ecx, eax; Status
0x1800337ca  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800337d0  mov     rcx, rdi; P
0x1800337d3  mov     ebx, eax
0x1800337d5  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800337da  jmp     loc_18003363A
0x1800337df  test    eax, eax
0x1800337e1  jnz     loc_18018D7A8
0x1800337e7  mov     ebx, 54Fh
0x1800337ec  jmp     loc_18003363A
0x18018d7a8  mov     ecx, eax; Status
0x18018d7aa  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018d7b0  mov     ebx, eax
0x18018d7b2  jmp     loc_18003363A
```
