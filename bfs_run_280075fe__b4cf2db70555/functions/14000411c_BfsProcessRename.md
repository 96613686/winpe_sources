# BfsProcessRename

- ea: `0x14000411c`
- end: `0x14000435d`
- name: `BfsProcessRename`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003140`

## callees

- `0x140001008`
- `0x140003210`
- `0x14000411c`
- `0x140005d4c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400042d0`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400042d0`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400042e1`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400042e1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000431a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000431a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400041d8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400041d8`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400041e7`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400041e7`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400041c1`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400041c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000417a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004307`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000417a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004307`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000418d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000418d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000419c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004326`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000419c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004326`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400042f6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400042f6`
- `FLTMGR!FltParseFileNameInformation` at `0x140004293`
- `FLTMGR!FltParseFileNameInformation` at `0x140004293`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140004248`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140004248`

## pseudocode

```c
__int64 __fastcall BfsProcessRename(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  bool v2; // zf
  unsigned int v6; // ebx
  BOOLEAN v7; // r12
  PACCESS_TOKEN v8; // rdi
  char v9; // r15
  struct _KPROCESS *CurrentProcess; // rax
  NTSTATUS DestinationFileNameInformation; // ecx
  int v12; // r8d
  int v13; // r9d
  int FileNameLength; // [rsp+20h] [rbp-39h]
  unsigned __int8 EffectiveOnly; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+41h] [rbp-18h] BYREF
  NTSTATUS v17; // [rsp+44h] [rbp-15h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+48h] [rbp-11h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+58h] [rbp-1h] BYREF
  NTSTATUS *v21; // [rsp+78h] [rbp+1Fh]
  __int64 v22; // [rsp+80h] [rbp+27h]

  v2 = Data->RequestorMode == 0;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  FileNameInformation = 0;
  if ( v2 )
    return 1;
  v6 = 1;
  KeEnterCriticalRegion();
  v7 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( v7 )
  {
    v8 = PsReferenceImpersonationToken(Data->Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
    if ( v8 )
    {
      v9 = 1;
      if ( ImpersonationLevel < SecurityImpersonation )
        goto LABEL_16;
    }
    else
    {
      v9 = 0;
      CurrentProcess = IoGetCurrentProcess();
      v8 = PsReferencePrimaryToken(CurrentProcess);
    }
    if ( BfsIsApplicableToken(v8, 1) )
    {
      DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                         *(PFLT_INSTANCE *)(a2 + 24),
                                         Data->Iopb->TargetFileObject,
                                         *((HANDLE *)Data->Iopb->Parameters.Create.EaBuffer + 1),
                                         (PWSTR)Data->Iopb->Parameters.Create.EaBuffer + 10,
                                         *((_DWORD *)Data->Iopb->Parameters.Create.EaBuffer + 4),
                                         0x101u,
                                         &FileNameInformation);
      if ( DestinationFileNameInformation < 0
        || (DestinationFileNameInformation = FltParseFileNameInformation(FileNameInformation),
            DestinationFileNameInformation < 0) )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v17 = DestinationFileNameInformation;
          v21 = &v17;
          v22 = 4;
          tlgWriteTransfer_EtwWriteTransfer(
            DestinationFileNameInformation,
            (int)&byte_140016D91,
            v12,
            v13,
            FileNameLength,
            &v20);
        }
      }
      else
      {
        v6 = BfsCheckPolicyAndPerformRenameAsUser(
               *(PVOID *)(a2 + 8),
               *(PVOID *)(a2 + 24),
               v8,
               Data,
               (__int64)FileNameInformation);
      }
    }
    if ( !v8 )
      goto LABEL_17;
    if ( !v9 )
    {
      PsDereferencePrimaryToken(v8);
      goto LABEL_17;
    }
LABEL_16:
    PsDereferenceImpersonationToken(v8);
  }
LABEL_17:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  return v6;
}

```

## disassembly

```asm
0x14000411c  mov     [rsp-8+arg_10], rbx
0x140004121  mov     [rsp-8+arg_18], rsi
0x140004126  push    rbp
0x140004127  push    rdi
0x140004128  push    r12
0x14000412a  push    r14
0x14000412c  push    r15
0x14000412e  lea     rbp, [rsp-37h]
0x140004133  sub     rsp, 90h
0x14000413a  mov     rax, cs:__security_cookie
0x140004141  xor     rax, rsp
0x140004144  mov     [rbp+57h+var_28], rax
0x140004148  cmp     byte ptr [rcx+50h], 0
0x14000414c  mov     r14, rdx
0x14000414f  mov     rsi, rcx
0x140004152  mov     [rbp+57h+CopyOnOpen], 0
0x140004156  mov     [rbp+57h+EffectiveOnly], 0
0x14000415a  mov     [rbp+57h+ImpersonationLevel], 0
0x140004161  mov     [rbp+57h+FileNameInformation], 0
0x140004169  jnz     short loc_140004175
0x14000416b  mov     eax, 1
0x140004170  jmp     loc_140004334
0x140004175  mov     ebx, 1
0x14000417a  call    cs:__imp_KeEnterCriticalRegion
0x140004181  nop     dword ptr [rax+rax+00h]
0x140004186  lea     rcx, gBfsRundownProtection; RunRef
0x14000418d  call    cs:__imp_ExAcquireRundownProtection
0x140004194  nop     dword ptr [rax+rax+00h]
0x140004199  mov     r12b, al
0x14000419c  call    cs:__imp_KeLeaveCriticalRegion
0x1400041a3  nop     dword ptr [rax+rax+00h]
0x1400041a8  test    r12b, r12b
0x1400041ab  jz      loc_1400042ED
0x1400041b1  mov     rcx, [rsi+8]; Thread
0x1400041b5  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x1400041b9  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x1400041bd  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x1400041c1  call    cs:__imp_PsReferenceImpersonationToken
0x1400041c8  nop     dword ptr [rax+rax+00h]
0x1400041cd  mov     rdi, rax
0x1400041d0  test    rax, rax
0x1400041d3  jnz     short loc_1400041F8
0x1400041d5  xor     r15b, r15b
0x1400041d8  call    cs:__imp_IoGetCurrentProcess
0x1400041df  nop     dword ptr [rax+rax+00h]
0x1400041e4  mov     rcx, rax; Process
0x1400041e7  call    cs:__imp_PsReferencePrimaryToken
0x1400041ee  nop     dword ptr [rax+rax+00h]
0x1400041f3  mov     rdi, rax
0x1400041f6  jmp     short loc_140004205
0x1400041f8  cmp     [rbp+57h+ImpersonationLevel], 2
0x1400041fc  mov     r15b, bl
0x1400041ff  jl      loc_1400042DE
0x140004205  mov     dl, bl
0x140004207  mov     rcx, rdi; Object
0x14000420a  call    BfsIsApplicableToken
0x14000420f  test    al, al
0x140004211  jz      loc_1400042C3
0x140004217  mov     rdx, [rsi+10h]
0x14000421b  lea     rax, [rbp+57h+FileNameInformation]
0x14000421f  mov     rcx, [r14+18h]; Instance
0x140004223  mov     [rsp+0B0h+RetFileNameInformation], rax; RetFileNameInformation
0x140004228  mov     [rsp+0B0h+NameOptions], 101h; NameOptions
0x140004230  mov     r8, [rdx+38h]
0x140004234  mov     rdx, [rdx+8]; FileObject
0x140004238  mov     eax, [r8+10h]
0x14000423c  lea     r9, [r8+14h]; FileName
0x140004240  mov     r8, [r8+8]; RootDirectory
0x140004244  mov     [rsp+0B0h+FileNameLength], eax; int
0x140004248  call    cs:__imp_FltGetDestinationFileNameInformation
0x14000424f  nop     dword ptr [rax+rax+00h]
0x140004254  mov     ecx, eax; int
0x140004256  test    eax, eax
0x140004258  jns     short loc_14000428F
0x14000425a  mov     eax, cs:dword_140019000
0x140004260  cmp     eax, 3
0x140004263  jbe     short loc_1400042C3
0x140004265  lea     rax, [rbp+57h+var_6C]
0x140004269  mov     [rbp+57h+var_6C], ecx
0x14000426c  mov     [rbp+57h+var_38], rax
0x140004270  lea     rdx, byte_140016D91; int
0x140004277  lea     rax, [rbp+57h+var_58]
0x14000427b  mov     [rbp+57h+var_30], 4
0x140004283  mov     qword ptr [rsp+0B0h+NameOptions], rax; PEVENT_DATA_DESCRIPTOR
0x140004288  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000428d  jmp     short loc_1400042C3
0x14000428f  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004293  call    cs:__imp_FltParseFileNameInformation
0x14000429a  nop     dword ptr [rax+rax+00h]
0x14000429f  mov     ecx, eax
0x1400042a1  test    eax, eax
0x1400042a3  js      short loc_14000425A
0x1400042a5  mov     rax, [rbp+57h+FileNameInformation]
0x1400042a9  mov     r9, rsi; Data
0x1400042ac  mov     rdx, [r14+18h]; PVOID
0x1400042b0  mov     r8, rdi; Token
0x1400042b3  mov     rcx, [r14+8]; FltObject
0x1400042b7  mov     qword ptr [rsp+0B0h+FileNameLength], rax; __int64
0x1400042bc  call    BfsCheckPolicyAndPerformRenameAsUser
0x1400042c1  mov     ebx, eax
0x1400042c3  test    rdi, rdi
0x1400042c6  jz      short loc_1400042ED
0x1400042c8  test    r15b, r15b
0x1400042cb  jnz     short loc_1400042DE
0x1400042cd  mov     rcx, rdi; PrimaryToken
0x1400042d0  call    cs:__imp_PsDereferencePrimaryToken
0x1400042d7  nop     dword ptr [rax+rax+00h]
0x1400042dc  jmp     short loc_1400042ED
0x1400042de  mov     rcx, rdi; ImpersonationToken
0x1400042e1  call    cs:__imp_PsDereferenceImpersonationToken
0x1400042e8  nop     dword ptr [rax+rax+00h]
0x1400042ed  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400042f1  test    rcx, rcx
0x1400042f4  jz      short loc_140004302
0x1400042f6  call    cs:__imp_FltReleaseFileNameInformation
0x1400042fd  nop     dword ptr [rax+rax+00h]
0x140004302  test    r12b, r12b
0x140004305  jz      short loc_140004332
0x140004307  call    cs:__imp_KeEnterCriticalRegion
0x14000430e  nop     dword ptr [rax+rax+00h]
0x140004313  lea     rcx, gBfsRundownProtection; RunRef
0x14000431a  call    cs:__imp_ExReleaseRundownProtection
0x140004321  nop     dword ptr [rax+rax+00h]
0x140004326  call    cs:__imp_KeLeaveCriticalRegion
0x14000432d  nop     dword ptr [rax+rax+00h]
0x140004332  mov     eax, ebx
0x140004334  mov     rcx, [rbp+57h+var_28]
0x140004338  xor     rcx, rsp; StackCookie
0x14000433b  call    __security_check_cookie
0x140004340  lea     r11, [rsp+0B0h+var_20]
0x140004348  mov     rbx, [r11+40h]
0x14000434c  mov     rsi, [r11+48h]
0x140004350  mov     rsp, r11
0x140004353  pop     r15
0x140004355  pop     r14
0x140004357  pop     r12
0x140004359  pop     rdi
0x14000435a  pop     rbp
0x14000435b  retn
```
