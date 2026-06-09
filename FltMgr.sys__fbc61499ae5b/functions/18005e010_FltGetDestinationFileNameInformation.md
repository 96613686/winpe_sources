# FltGetDestinationFileNameInformation

- ea: `0x18005e010`
- end: `0x18005e2dd`
- name: `FltGetDestinationFileNameInformation`
- size: `717`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, HANDLE RootDirectory, PWSTR FileName, ULONG FileNameLength, FLT_FILE_NAME_OPTIONS NameOptions, PFLT_FILE_NAME_INFORMATION *RetFileNameInformation)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x180084bf0`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18001ee00`
- `0x18001ef84`
- `0x180024800`
- `0x180024c40`
- `0x1800584e0`
- `0x180058640`
- `0x180059220`
- `0x18005c5a0`
- `0x18005e010`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18005e0f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005e0f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005e2a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005e2c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005e2a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005e2c2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005e1e1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005e276`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005e1e1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18005e276`
- `ntoskrnl!IoGetTopLevelIrp` at `0x18005e071`
- `ntoskrnl!IoGetTopLevelIrp` at `0x18005e071`

## pseudocode

```c
NTSTATUS __stdcall FltGetDestinationFileNameInformation(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        HANDLE RootDirectory,
        PWSTR FileName,
        ULONG FileNameLength,
        FLT_FILE_NAME_OPTIONS NameOptions,
        PFLT_FILE_NAME_INFORMATION *RetFileNameInformation)
{
  unsigned int InitializeNameGenerationContext; // edi
  PVOID v12; // rdi
  char v13; // bp
  __int64 v14; // rax
  __int64 v15; // rcx
  int NormalizedDestinationFileName; // eax
  NTSTATUS FileNameInformation; // esi
  __int64 v18; // rcx
  __int64 v19; // rcx
  PVOID Entry[2]; // [rsp+60h] [rbp-178h] BYREF
  _OWORD v22[18]; // [rsp+70h] [rbp-168h] BYREF

  memset(v22, 0, sizeof(v22));
  Entry[0] = 0;
  if ( !FileObject->FsContext || IoGetTopLevelIrp() || (unsigned __int8)NameOptions == 3 )
    return -1071906811;
  InitializeNameGenerationContext = FltpAllocateInitializeNameGenerationContext(
                                      Entry,
                                      Instance,
                                      FileObject,
                                      0,
                                      NameOptions,
                                      0,
                                      RootDirectory,
                                      FileName,
                                      FileNameLength);
  if ( (int)FltpDbgStatus(InitializeNameGenerationContext, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 7558, 0) < 0 )
    return InitializeNameGenerationContext;
  KeEnterCriticalRegion();
  v12 = Entry[0];
  v13 = 1;
  if ( (NameOptions & 0x1000000) != 0 )
    FltpGetNameGenerateNodesForInstance(*((_QWORD *)Entry[0] + 2), (_QWORD *)Entry[0] + 6, (_QWORD *)Entry[0] + 7);
  if ( !*((_QWORD *)v12 + 6) )
  {
    FltpGetNextNameGenerateNodesForInstance(*((_QWORD *)v12 + 2), (_QWORD *)v12 + 6, (_QWORD *)v12 + 7);
    if ( !*((_QWORD *)v12 + 6) )
    {
      KeLeaveCriticalRegion();
      v13 = 0;
    }
  }
  v14 = *((_QWORD *)v12 + 6);
  if ( v14 )
    v15 = *(_QWORD *)(v14 + 16);
  else
    v15 = 0;
  *((_QWORD *)v12 + 17) = v15;
  *((_QWORD *)v12 + 18) = _InterlockedExchangeAdd64(&qword_180040350, 0);
  *RetFileNameInformation = 0;
  LODWORD(v22[1]) = 0;
  *(_QWORD *)((char *)&v22[1] + 4) = 254;
  *(_QWORD *)&v22[0] = 16646144;
  *((_QWORD *)&v22[0] + 1) = (char *)&v22[1] + 12;
  *((_QWORD *)v12 + 14) = v22;
  if ( (unsigned __int8)NameOptions == 1 )
  {
    NormalizedDestinationFileName = FltpGetNormalizedDestinationFileName(v12);
    goto LABEL_15;
  }
  if ( (unsigned __int8)NameOptions == 2 )
  {
    NormalizedDestinationFileName = FltpGetOpenedDestinationFileName((__int64)v12);
LABEL_15:
    FileNameInformation = NormalizedDestinationFileName;
    if ( NormalizedDestinationFileName >= 0 )
    {
      FileNameInformation = FltpAllocateFileNameInformation(v12);
      if ( FileNameInformation >= 0 )
        *RetFileNameInformation = (PFLT_FILE_NAME_INFORMATION)*((_QWORD *)v12 + 15);
    }
    goto LABEL_16;
  }
  FileNameInformation = -1073741811;
LABEL_16:
  FltpCleanupNameControl(v22);
  v18 = *((_QWORD *)v12 + 6);
  if ( v18 )
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v18 + 16) + 56LL), 1u);
  v19 = *((_QWORD *)v12 + 7);
  if ( v19 )
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v19 + 16) + 56LL), 1u);
  if ( v13 )
    KeLeaveCriticalRegion();
  FltpFreeNameGenerationContext(v12);
  return FileNameInformation;
}

```

## disassembly

```asm
0x18005e010  mov     [rsp+arg_10], rbx
0x18005e015  push    rbp
0x18005e016  push    rsi
0x18005e017  push    rdi
0x18005e018  push    r12
0x18005e01a  push    r13
0x18005e01c  push    r14
0x18005e01e  push    r15
0x18005e020  sub     rsp, 1A0h
0x18005e027  mov     rax, cs:__security_cookie
0x18005e02e  xor     rax, rsp
0x18005e031  mov     [rsp+1D8h+var_48], rax
0x18005e039  mov     r12, [rsp+1D8h+RetFileNameInformation]
0x18005e041  mov     r14, r8
0x18005e044  mov     rdi, rdx
0x18005e047  mov     r15, rcx
0x18005e04a  xor     edx, edx; Val
0x18005e04c  lea     rcx, [rsp+1D8h+var_168]; void *
0x18005e051  mov     r8d, 120h; Size
0x18005e057  mov     rbp, r9
0x18005e05a  call    memset
0x18005e05f  xor     r13d, r13d
0x18005e062  mov     [rsp+1D8h+Entry], r13
0x18005e067  cmp     [rdi+18h], r13
0x18005e06b  jz      loc_18005E2D3
0x18005e071  call    cs:__imp_IoGetTopLevelIrp
0x18005e078  nop     dword ptr [rax+rax+00h]
0x18005e07d  test    rax, rax
0x18005e080  jnz     loc_18005E2D3
0x18005e086  mov     ebx, [rsp+1D8h+NameOptions]
0x18005e08d  movzx   esi, bl
0x18005e090  cmp     esi, 3
0x18005e093  jz      loc_18005E2D3
0x18005e099  mov     eax, [rsp+1D8h+FileNameLength]
0x18005e0a0  lea     rcx, [rsp+1D8h+Entry]
0x18005e0a5  mov     [rsp+1D8h+var_188], 11h
0x18005e0ad  xor     r9d, r9d
0x18005e0b0  mov     [rsp+1D8h+var_198], eax
0x18005e0b4  mov     r8, rdi
0x18005e0b7  mov     [rsp+1D8h+var_1A0], rbp
0x18005e0bc  mov     rdx, r15
0x18005e0bf  mov     [rsp+1D8h+var_1A8], r14
0x18005e0c4  mov     [rsp+1D8h+var_1B0], r13
0x18005e0c9  mov     [rsp+1D8h+var_1B8], ebx
0x18005e0cd  call    FltpAllocateInitializeNameGenerationContext
0x18005e0d2  mov     r8d, 1D86h
0x18005e0d8  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005e0df  xor     r9d, r9d
0x18005e0e2  mov     ecx, eax
0x18005e0e4  mov     edi, eax
0x18005e0e6  call    FltpDbgStatus
0x18005e0eb  test    eax, eax
0x18005e0ed  js      loc_18005E287
0x18005e0f3  call    cs:__imp_KeEnterCriticalRegion
0x18005e0fa  nop     dword ptr [rax+rax+00h]
0x18005e0ff  mov     rdi, [rsp+1D8h+Entry]
0x18005e104  mov     bpl, 1
0x18005e107  bt      ebx, 18h
0x18005e10b  jb      loc_18005E28E
0x18005e111  cmp     [rdi+30h], r13
0x18005e115  jnz     short loc_18005E132
0x18005e117  mov     rcx, [rdi+10h]
0x18005e11b  lea     r8, [rdi+38h]
0x18005e11f  lea     rdx, [rdi+30h]
0x18005e123  call    FltpGetNextNameGenerateNodesForInstance
0x18005e128  cmp     [rdi+30h], r13
0x18005e12c  jz      loc_18005E2A4
0x18005e132  mov     rax, [rdi+30h]
0x18005e136  test    rax, rax
0x18005e139  jz      loc_18005E235
0x18005e13f  mov     rcx, [rax+10h]
0x18005e143  mov     [rdi+88h], rcx
0x18005e14a  mov     rax, r13
0x18005e14d  lock xadd cs:qword_180040350, rax
0x18005e156  mov     [rdi+90h], rax
0x18005e15d  mov     eax, 0FEh
0x18005e162  mov     [r12], r13
0x18005e166  xorps   xmm0, xmm0
0x18005e169  mov     [rsp+1D8h+var_158], r13d
0x18005e171  mov     [rsp+1D8h+var_154], 0FEh
0x18005e17d  movups  [rsp+1D8h+var_168], xmm0
0x18005e182  mov     word ptr [rsp+1D8h+var_168+2], ax
0x18005e187  lea     rax, [rsp+1D8h+var_14C]
0x18005e18f  mov     qword ptr [rsp+1D8h+var_168+8], rax
0x18005e194  lea     rax, [rsp+1D8h+var_168]
0x18005e199  mov     [rdi+70h], rax
0x18005e19d  sub     esi, 1
0x18005e1a0  jz      loc_18005E23D
0x18005e1a6  cmp     esi, 1
0x18005e1a9  jnz     loc_18005E2B8
0x18005e1af  mov     rcx, rdi
0x18005e1b2  call    FltpGetOpenedDestinationFileName
0x18005e1b7  mov     esi, eax
0x18005e1b9  test    eax, eax
0x18005e1bb  jns     loc_18005E24A
0x18005e1c1  lea     rcx, [rsp+1D8h+var_168]
0x18005e1c6  call    FltpCleanupNameControl
0x18005e1cb  mov     rcx, [rdi+30h]
0x18005e1cf  test    rcx, rcx
0x18005e1d2  jz      short loc_18005E1ED
0x18005e1d4  mov     rcx, [rcx+10h]
0x18005e1d8  mov     edx, 1; Count
0x18005e1dd  mov     rcx, [rcx+38h]; RunRef
0x18005e1e1  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18005e1e8  nop     dword ptr [rax+rax+00h]
0x18005e1ed  mov     rcx, [rdi+38h]
0x18005e1f1  test    rcx, rcx
0x18005e1f4  jnz     short loc_18005E269
0x18005e1f6  test    bpl, bpl
0x18005e1f9  jnz     loc_18005E2C2
0x18005e1ff  mov     rcx, rdi; Entry
0x18005e202  call    FltpFreeNameGenerationContext
0x18005e207  mov     eax, esi
0x18005e209  mov     rcx, [rsp+1D8h+var_48]
0x18005e211  xor     rcx, rsp; StackCookie
0x18005e214  call    __security_check_cookie
0x18005e219  mov     rbx, [rsp+1D8h+arg_10]
0x18005e221  add     rsp, 1A0h
0x18005e228  pop     r15
0x18005e22a  pop     r14
0x18005e22c  pop     r13
0x18005e22e  pop     r12
0x18005e230  pop     rdi
0x18005e231  pop     rsi
0x18005e232  pop     rbp
0x18005e233  retn
0x18005e235  mov     rcx, r13
0x18005e238  jmp     loc_18005E143
0x18005e23d  mov     rcx, rdi
0x18005e240  call    FltpGetNormalizedDestinationFileName
0x18005e245  jmp     loc_18005E1B7
0x18005e24a  mov     rcx, rdi
0x18005e24d  call    FltpAllocateFileNameInformation
0x18005e252  mov     esi, eax
0x18005e254  test    eax, eax
0x18005e256  js      loc_18005E1C1
0x18005e25c  mov     rax, [rdi+78h]
0x18005e260  mov     [r12], rax
0x18005e264  jmp     loc_18005E1C1
0x18005e269  mov     rcx, [rcx+10h]
0x18005e26d  mov     edx, 1; Count
0x18005e272  mov     rcx, [rcx+38h]; RunRef
0x18005e276  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18005e27d  nop     dword ptr [rax+rax+00h]
0x18005e282  jmp     loc_18005E1F6
0x18005e287  mov     eax, edi
0x18005e289  jmp     loc_18005E209
0x18005e28e  mov     rcx, [rdi+10h]
0x18005e292  lea     r8, [rdi+38h]
0x18005e296  lea     rdx, [rdi+30h]
0x18005e29a  call    FltpGetNameGenerateNodesForInstance
0x18005e29f  jmp     loc_18005E111
0x18005e2a4  call    cs:__imp_KeLeaveCriticalRegion
0x18005e2ab  nop     dword ptr [rax+rax+00h]
0x18005e2b0  xor     bpl, bpl
0x18005e2b3  jmp     loc_18005E132
0x18005e2b8  mov     esi, 0C000000Dh
0x18005e2bd  jmp     loc_18005E1C1
0x18005e2c2  call    cs:__imp_KeLeaveCriticalRegion
0x18005e2c9  nop     dword ptr [rax+rax+00h]
0x18005e2ce  jmp     loc_18005E1FF
0x18005e2d3  mov     eax, 0C01C0005h
0x18005e2d8  jmp     loc_18005E209
```
