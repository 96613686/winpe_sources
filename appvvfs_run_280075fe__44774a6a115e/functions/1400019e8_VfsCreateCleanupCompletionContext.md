# VfsCreateCleanupCompletionContext

- ea: `0x1400019e8`
- end: `0x140001b25`
- name: `VfsCreateCleanupCompletionContext`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400011c0`

## callees

- `0x1400019e8`
- `0x140001b2c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001aa2`
- `ntoskrnl!ExAllocatePool2` at `0x140001aa2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140001ad2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140001ad2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001a66`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001a66`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001aec`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001450f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140001aec`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001450f`
- `FLTMGR!FltGetFileNameInformation` at `0x140001a20`
- `FLTMGR!FltGetFileNameInformation` at `0x140001a20`

## string_xrefs

- `0x140001a49`: `VfsCreateCleanupCompletionContext() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateCleanupCompletionContext(struct _FLT_CALLBACK_DATA *a1, _QWORD *a2)
{
  char *v4; // rdi
  NTSTATUS v5; // ebx
  PFLT_FILE_NAME_INFORMATION v6; // r15
  unsigned __int16 Length; // bx
  __int64 Pool2; // rax
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp+18h] BYREF

  FileNameInformation = 0;
  v4 = 0;
  v5 = FltGetFileNameInformation(a1, 0x101u, &FileNameInformation);
  if ( v5 >= 0 )
  {
    v4 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
    if ( v4
      && (*(_OWORD *)v4 = 0,
          *((_QWORD *)v4 + 2) = 0,
          v6 = FileNameInformation,
          Length = FileNameInformation->Name.Length,
          Pool2 = ExAllocatePool2(256, Length, 1951614550),
          (*((_QWORD *)v4 + 2) = Pool2) != 0) )
    {
      *((_WORD *)v4 + 4) = 0;
      *((_WORD *)v4 + 5) = Length;
      v5 = 0;
      RtlCopyUnicodeString((PUNICODE_STRING)(v4 + 8), &v6->Name);
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    LogWrite(
      1,
      0,
      L"VfsCreateCleanupCompletionContext() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X",
      a1,
      a1->Iopb->MajorFunction,
      v5,
      v5,
      0);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v5 >= 0 )
  {
    *a2 = v4;
  }
  else if ( v4 )
  {
    VfsDeleteCleanupCompletionContext(v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400019e8  mov     rax, rsp
0x1400019eb  mov     [rax+8], rbx
0x1400019ef  mov     [rax+20h], rsi
0x1400019f3  mov     [rax+10h], rdx
0x1400019f7  push    rdi
0x1400019f8  push    r14
0x1400019fa  push    r15
0x1400019fc  sub     rsp, 40h
0x140001a00  mov     r14, rdx
0x140001a03  mov     rsi, rcx
0x140001a06  mov     qword ptr [rax+18h], 0
0x140001a0e  xor     edi, edi
0x140001a10  mov     [rax-20h], rdi
0x140001a14  mov     [rax-28h], edi
0x140001a17  lea     r8, [rax+18h]; FileNameInformation
0x140001a1b  mov     edx, 101h; NameOptions
0x140001a20  call    cs:__imp_FltGetFileNameInformation
0x140001a27  nop     dword ptr [rax+rax+00h]
0x140001a2c  mov     ebx, eax
0x140001a2e  mov     [rsp+58h+var_28], eax
0x140001a32  test    eax, eax
0x140001a34  jns     short loc_140001A5F
0x140001a36  mov     rax, [rsi+10h]
0x140001a3a  movzx   ecx, byte ptr [rax+4]
0x140001a3e  mov     [rsp+58h+var_30], ebx
0x140001a42  mov     [rsp+58h+var_38], ecx
0x140001a46  mov     r9, rsi
0x140001a49  lea     r8, aVfscreateclean; "VfsCreateCleanupCompletionContext() - F"...
0x140001a50  xor     edx, edx
0x140001a52  lea     ecx, [rdi+1]
0x140001a55  call    LogWrite
0x140001a5a  jmp     loc_140001AE2
0x140001a5f  lea     rcx, Lookaside; Lookaside
0x140001a66  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140001a6d  nop     dword ptr [rax+rax+00h]
0x140001a72  mov     rdi, rax
0x140001a75  mov     [rsp+58h+var_20], rax
0x140001a7a  test    rax, rax
0x140001a7d  jz      short loc_140001AB7
0x140001a7f  xorps   xmm0, xmm0
0x140001a82  xor     eax, eax
0x140001a84  movups  xmmword ptr [rdi], xmm0
0x140001a87  mov     [rdi+10h], rax
0x140001a8b  mov     r15, [rsp+58h+FileNameInformation]
0x140001a90  movzx   ebx, word ptr [r15+8]
0x140001a95  mov     edx, ebx
0x140001a97  mov     ecx, 100h
0x140001a9c  mov     r8d, 74534656h
0x140001aa2  call    cs:__imp_ExAllocatePool2
0x140001aa9  nop     dword ptr [rax+rax+00h]
0x140001aae  mov     [rdi+10h], rax
0x140001ab2  test    rax, rax
0x140001ab5  jnz     short loc_140001ABE
0x140001ab7  mov     ebx, 0C000009Ah
0x140001abc  jmp     short loc_140001ADE
0x140001abe  xor     eax, eax
0x140001ac0  mov     [rdi+8], ax
0x140001ac4  mov     [rdi+0Ah], bx
0x140001ac8  xor     ebx, ebx
0x140001aca  lea     rdx, [r15+8]; SourceString
0x140001ace  lea     rcx, [rdi+8]; DestinationString
0x140001ad2  call    cs:__imp_RtlCopyUnicodeString
0x140001ad9  nop     dword ptr [rax+rax+00h]
0x140001ade  mov     [rsp+58h+var_28], ebx
0x140001ae2  mov     rcx, [rsp+58h+FileNameInformation]; FileNameInformation
0x140001ae7  test    rcx, rcx
0x140001aea  jz      short loc_140001AF8
0x140001aec  call    cs:__imp_FltReleaseFileNameInformation
0x140001af3  nop     dword ptr [rax+rax+00h]
0x140001af8  test    ebx, ebx
0x140001afa  jns     short loc_140001B0B
0x140001afc  test    rdi, rdi
0x140001aff  jz      short loc_140001B0E
0x140001b01  mov     rcx, rdi; Entry
0x140001b04  call    VfsDeleteCleanupCompletionContext
0x140001b09  jmp     short loc_140001B0E
0x140001b0b  mov     [r14], rdi
0x140001b0e  mov     eax, ebx
0x140001b10  mov     rbx, [rsp+58h+arg_0]
0x140001b15  mov     rsi, [rsp+58h+arg_18]
0x140001b1a  add     rsp, 40h
0x140001b1e  pop     r15
0x140001b20  pop     r14
0x140001b22  pop     rdi
0x140001b23  retn
0x1400144fd  push    rbp
0x1400144ff  sub     rsp, 30h
0x140014503  mov     rbp, rdx
0x140014506  mov     rcx, [rbp+70h]; FileNameInformation
0x14001450a  test    rcx, rcx
0x14001450d  jz      short loc_14001451C
0x14001450f  call    cs:__imp_FltReleaseFileNameInformation
0x140014516  nop     dword ptr [rax+rax+00h]
0x14001451b  nop
0x14001451c  cmp     dword ptr [rbp+30h], 0
0x140014520  jge     short loc_140014532
0x140014522  mov     rcx, [rbp+38h]; Entry
0x140014526  test    rcx, rcx
0x140014529  jz      short loc_14001453D
0x14001452b  call    VfsDeleteCleanupCompletionContext
0x140014530  jmp     short loc_14001453D
0x140014532  mov     rcx, [rbp+68h]
0x140014536  mov     rax, [rbp+38h]
0x14001453a  mov     [rcx], rax
0x14001453d  add     rsp, 30h
0x140014541  pop     rbp
0x140014542  retn
```
