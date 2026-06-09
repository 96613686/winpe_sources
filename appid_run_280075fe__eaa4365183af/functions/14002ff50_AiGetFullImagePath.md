# AiGetFullImagePath

- ea: `0x14002ff50`
- end: `0x1400302a3`
- name: `AiGetFullImagePath`
- size: `851`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, PFILE_OBJECT FileObject@<rdx>, PUNICODE_STRING DestinationString, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14002fe20`
- `0x1400333b0`
- `0x1400365f0`

## callees

- `0x140006c40`
- `0x14002ff50`
- `0x140032a50`
- `0x140032a90`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400300b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140030106`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400300b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140030106`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030281`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030281`
- `ntoskrnl!ExAllocatePool2` at `0x14003008d`
- `ntoskrnl!ExAllocatePool2` at `0x1400300e2`
- `ntoskrnl!ExAllocatePool2` at `0x14003008d`
- `ntoskrnl!ExAllocatePool2` at `0x1400300e2`
- `ntoskrnl!ZwQueryInformationFile` at `0x14003019c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400301f6`
- `ntoskrnl!ZwQueryInformationFile` at `0x14003019c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400301f6`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14002ffc4`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14002ffc4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030292`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030292`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003001a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003001a`

## pseudocode

```c
__int64 __fastcall AiGetFullImagePath(
        HANDLE FileHandle,
        PFILE_OBJECT FileObject,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        PUNICODE_STRING DestinationString,
        _DWORD *a6,
        _DWORD *a7)
{
  PUNICODE_STRING v7; // r14
  NTSTATUS FileNameInformationUnsafe; // ebx
  char v13; // al
  __int64 v14; // r9
  unsigned int MaximumLength; // ecx
  __int64 Pool2; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  PWSTR Buffer; // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // rdi
  ULONG v24; // ebx
  _DWORD *v25; // rax
  USHORT v26; // ax
  WCHAR *v27; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-38h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp+18h] BYREF
  __int64 FsInformation; // [rsp+88h] [rbp+20h] BYREF

  v7 = DestinationString;
  FileNameInformation = 0;
  FsInformation = 0;
  a4->Buffer = 0;
  IoStatusBlock = 0;
  if ( v7 )
    v7->Buffer = 0;
  if ( a3 )
  {
    *(_OWORD *)a3 = 0;
    *(_QWORD *)(a3 + 16) = 0;
  }
  FileNameInformationUnsafe = ZwQueryVolumeInformationFile(
                                FileHandle,
                                &IoStatusBlock,
                                &FsInformation,
                                8u,
                                FileFsDeviceInformation);
  if ( FileNameInformationUnsafe >= 0 )
  {
    if ( a6 )
      *a6 = FsInformation;
    v13 = BYTE4(FsInformation);
    if ( a7 )
      *a7 = HIDWORD(FsInformation);
    if ( (v13 & 0x10) != 0 )
    {
      v22 = (_DWORD *)AiAlloc(528);
      v23 = v22;
      if ( !v22 )
      {
        FileNameInformationUnsafe = -1073741801;
        goto LABEL_12;
      }
      FileNameInformationUnsafe = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v22, 0x210u, FileNameInformation);
      if ( FileNameInformationUnsafe == -2147483643 )
      {
        v24 = *v23 + 8;
        ExFreePoolWithTag(v23, 0);
        v25 = (_DWORD *)AiAlloc(v24);
        v23 = v25;
        if ( !v25 )
        {
          FileNameInformationUnsafe = -1073741801;
          goto LABEL_12;
        }
        FileNameInformationUnsafe = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v25, v24, FileNameInformation);
      }
      if ( FileNameInformationUnsafe < 0 )
        goto LABEL_16;
      if ( *v23 <= 0xFFFDu )
      {
        v26 = *v23 + 2;
        a4->Length = v26;
        a4->MaximumLength = v26;
        v27 = (WCHAR *)AiAlloc(v26);
        a4->Buffer = v27;
        if ( v27 )
        {
          *v27 = 92;
          memmove(a4->Buffer + 1, v23 + 1, (unsigned int)*v23);
          if ( v7 )
          {
            *(_DWORD *)&v7->Length = 0;
            v7->Buffer = 0;
          }
        }
        else
        {
          FileNameInformationUnsafe = -1073741801;
        }
      }
      else
      {
        FileNameInformationUnsafe = -1073741823;
      }
      if ( v23 )
LABEL_16:
        ExFreePoolWithTag(v23, 0);
    }
    else
    {
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, 0, 0x101u, &FileNameInformation);
      if ( FileNameInformationUnsafe < 0 )
        goto LABEL_12;
      MaximumLength = FileNameInformation->Name.MaximumLength;
      a4->MaximumLength = MaximumLength;
      Pool2 = ExAllocatePool2(258, MaximumLength, 1145663553, v14);
      a4->Buffer = (PWSTR)Pool2;
      if ( !Pool2 )
      {
        FileNameInformationUnsafe = -1073741801;
        goto LABEL_12;
      }
      RtlCopyUnicodeString(a4, &FileNameInformation->Name);
      if ( !v7 )
        goto LABEL_21;
      v19 = FileNameInformation->Volume.MaximumLength;
      v7->MaximumLength = v19;
      v20 = ExAllocatePool2(258, v19, 1145663553, v18);
      v7->Buffer = (PWSTR)v20;
      if ( v20 )
      {
        RtlCopyUnicodeString(v7, &FileNameInformation->Volume);
LABEL_21:
        if ( a3 )
          AipGetImageId(FileHandle, &FileNameInformation->Volume);
        goto LABEL_12;
      }
      Buffer = a4->Buffer;
      FileNameInformationUnsafe = -1073741801;
      if ( Buffer )
        ExFreePoolWithTag(Buffer, 0);
      a4->Buffer = 0;
    }
  }
LABEL_12:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x14002ff50  mov     rax, rsp
0x14002ff53  mov     [rax+8], rbx
0x14002ff57  mov     [rax+10h], rbp
0x14002ff5b  push    rsi
0x14002ff5c  push    rdi
0x14002ff5d  push    r12
0x14002ff5f  push    r14
0x14002ff61  push    r15
0x14002ff63  sub     rsp, 40h
0x14002ff67  mov     r14, [rsp+68h+DestinationString]
0x14002ff6f  xor     r12d, r12d
0x14002ff72  mov     [rax+18h], r12
0x14002ff76  xorps   xmm0, xmm0
0x14002ff79  mov     [rax+20h], r12
0x14002ff7d  mov     r15, r9
0x14002ff80  mov     [r9+8], r12
0x14002ff84  mov     rdi, r8
0x14002ff87  mov     rsi, rdx
0x14002ff8a  mov     rbp, rcx
0x14002ff8d  movups  xmmword ptr [rax-38h], xmm0
0x14002ff91  test    r14, r14
0x14002ff94  jz      short loc_14002FF9A
0x14002ff96  mov     [r14+8], r12
0x14002ff9a  test    rdi, rdi
0x14002ff9d  jz      short loc_14002FFA9
0x14002ff9f  xor     eax, eax
0x14002ffa1  movups  xmmword ptr [r8], xmm0
0x14002ffa5  mov     [r8+10h], rax
0x14002ffa9  mov     r9d, 8; Length
0x14002ffaf  mov     [rsp+68h+FsInformationClass], 4; FsInformationClass
0x14002ffb7  lea     r8, [rsp+68h+FsInformation]; FsInformation
0x14002ffbf  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x14002ffc4  call    cs:__imp_ZwQueryVolumeInformationFile
0x14002ffcb  nop     dword ptr [rax+rax+00h]
0x14002ffd0  mov     ebx, eax
0x14002ffd2  test    eax, eax
0x14002ffd4  js      short loc_14003002C
0x14002ffd6  mov     rcx, [rsp+68h+arg_28]
0x14002ffde  test    rcx, rcx
0x14002ffe1  jnz     loc_140030152
0x14002ffe7  mov     rcx, [rsp+68h+arg_30]
0x14002ffef  mov     eax, [rsp+68h+arg_1C]
0x14002fff6  test    rcx, rcx
0x14002fff9  jnz     loc_140030160
0x14002ffff  test    al, 10h
0x140030001  jnz     loc_140030167
0x140030007  lea     r9, [rsp+68h+FileNameInformation]; FileNameInformation
0x14003000f  xor     edx, edx; Instance
0x140030011  mov     r8d, 101h; NameOptions
0x140030017  mov     rcx, rsi; FileObject
0x14003001a  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140030021  nop     dword ptr [rax+rax+00h]
0x140030026  mov     ebx, eax
0x140030028  test    eax, eax
0x14003002a  jns     short loc_14003006F
0x14003002c  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x140030034  test    rcx, rcx
0x140030037  jnz     loc_140030292
0x14003003d  mov     rbp, [rsp+68h+arg_8]
0x140030042  mov     eax, ebx
0x140030044  mov     rbx, [rsp+68h+arg_0]
0x140030049  add     rsp, 40h
0x14003004d  pop     r15
0x14003004f  pop     r14
0x140030051  pop     r12
0x140030053  pop     rdi
0x140030054  pop     rsi
0x140030055  retn
0x140030057  test    rdi, rdi
0x14003005a  jz      short loc_14003002C
0x14003005c  xor     edx, edx; Tag
0x14003005e  mov     rcx, rdi; P
0x140030061  call    cs:__imp_ExFreePoolWithTag
0x140030068  nop     dword ptr [rax+rax+00h]
0x14003006d  jmp     short loc_14003002C
0x14003006f  mov     rax, [rsp+68h+FileNameInformation]
0x140030077  mov     r8d, 44497041h
0x14003007d  movzx   ecx, word ptr [rax+0Ah]
0x140030081  mov     [r15+2], cx
0x140030086  mov     edx, ecx
0x140030088  mov     ecx, 102h
0x14003008d  call    cs:__imp_ExAllocatePool2
0x140030094  nop     dword ptr [rax+rax+00h]
0x140030099  mov     [r15+8], rax
0x14003009d  test    rax, rax
0x1400300a0  jz      loc_140030275
0x1400300a6  mov     rdx, [rsp+68h+FileNameInformation]
0x1400300ae  mov     rcx, r15; DestinationString
0x1400300b1  add     rdx, 8; SourceString
0x1400300b5  call    cs:__imp_RtlCopyUnicodeString
0x1400300bc  nop     dword ptr [rax+rax+00h]
0x1400300c1  test    r14, r14
0x1400300c4  jz      short loc_140030112
0x1400300c6  mov     rax, [rsp+68h+FileNameInformation]
0x1400300ce  mov     ecx, 102h
0x1400300d3  mov     r8d, 44497041h
0x1400300d9  movzx   edx, word ptr [rax+1Ah]
0x1400300dd  mov     [r14+2], dx
0x1400300e2  call    cs:__imp_ExAllocatePool2
0x1400300e9  nop     dword ptr [rax+rax+00h]
0x1400300ee  mov     [r14+8], rax
0x1400300f2  test    rax, rax
0x1400300f5  jz      short loc_140030137
0x1400300f7  mov     rdx, [rsp+68h+FileNameInformation]
0x1400300ff  mov     rcx, r14; DestinationString
0x140030102  add     rdx, 18h; SourceString
0x140030106  call    cs:__imp_RtlCopyUnicodeString
0x14003010d  nop     dword ptr [rax+rax+00h]
0x140030112  test    rdi, rdi
0x140030115  jz      loc_14003002C
0x14003011b  mov     rdx, [rsp+68h+FileNameInformation]
0x140030123  mov     r8, rdi
0x140030126  add     rdx, 18h; String1
0x14003012a  mov     rcx, rbp; FileHandle
0x14003012d  call    AipGetImageId
0x140030132  jmp     loc_14003002C
0x140030137  mov     rcx, [r15+8]; P
0x14003013b  mov     ebx, 0C0000017h
0x140030140  test    rcx, rcx
0x140030143  jnz     loc_14003027F
0x140030149  mov     [r15+8], r12
0x14003014d  jmp     loc_14003002C
0x140030152  mov     eax, [rsp+68h+FsInformation]
0x140030159  mov     [rcx], eax
0x14003015b  jmp     loc_14002FFE7
0x140030160  mov     [rcx], eax
0x140030162  jmp     loc_14002FFFF
0x140030167  mov     ecx, 210h
0x14003016c  call    AiAlloc
0x140030171  mov     rdi, rax
0x140030174  test    rax, rax
0x140030177  jnz     short loc_140030183
0x140030179  mov     ebx, 0C0000017h
0x14003017e  jmp     loc_14003002C
0x140030183  mov     r9d, 210h; Length
0x140030189  mov     [rsp+68h+FsInformationClass], 9; FileInformationClass
0x140030191  mov     r8, rdi; FileInformation
0x140030194  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x140030199  mov     rcx, rbp; FileHandle
0x14003019c  call    cs:__imp_ZwQueryInformationFile
0x1400301a3  nop     dword ptr [rax+rax+00h]
0x1400301a8  mov     ebx, eax
0x1400301aa  cmp     eax, 80000005h
0x1400301af  jnz     short loc_140030204
0x1400301b1  mov     ebx, [rdi]
0x1400301b3  xor     edx, edx; Tag
0x1400301b5  mov     rcx, rdi; P
0x1400301b8  add     ebx, 8
0x1400301bb  call    cs:__imp_ExFreePoolWithTag
0x1400301c2  nop     dword ptr [rax+rax+00h]
0x1400301c7  mov     ecx, ebx
0x1400301c9  call    AiAlloc
0x1400301ce  mov     rdi, rax
0x1400301d1  test    rax, rax
0x1400301d4  jnz     short loc_1400301E0
0x1400301d6  mov     ebx, 0C0000017h
0x1400301db  jmp     loc_14003002C
0x1400301e0  mov     r9d, ebx; Length
0x1400301e3  mov     [rsp+68h+FsInformationClass], 9; FileInformationClass
0x1400301eb  mov     r8, rax; FileInformation
0x1400301ee  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x1400301f3  mov     rcx, rbp; FileHandle
0x1400301f6  call    cs:__imp_ZwQueryInformationFile
0x1400301fd  nop     dword ptr [rax+rax+00h]
0x140030202  mov     ebx, eax
0x140030204  test    ebx, ebx
0x140030206  js      loc_14003005C
0x14003020c  mov     eax, [rdi]
0x14003020e  cmp     eax, 0FFFDh
0x140030213  jbe     short loc_14003021F
0x140030215  mov     ebx, 0C0000001h
0x14003021a  jmp     loc_140030057
0x14003021f  add     ax, 2
0x140030223  movzx   ecx, ax
0x140030226  mov     [r15], cx
0x14003022a  mov     [r15+2], cx
0x14003022f  call    AiAlloc
0x140030234  mov     [r15+8], rax
0x140030238  test    rax, rax
0x14003023b  jnz     short loc_140030247
0x14003023d  mov     ebx, 0C0000017h
0x140030242  jmp     loc_140030057
0x140030247  mov     word ptr [rax], 5Ch ; '\'
0x14003024c  lea     rdx, [rdi+4]; Src
0x140030250  mov     rcx, [r15+8]
0x140030254  mov     r8d, [rdi]; Size
0x140030257  add     rcx, 2; void *
0x14003025b  call    memmove
0x140030260  test    r14, r14
0x140030263  jz      loc_140030057
0x140030269  mov     [r14], r12d
0x14003026c  mov     [r14+8], r12
0x140030270  jmp     loc_140030057
0x140030275  mov     ebx, 0C0000017h
0x14003027a  jmp     loc_14003002C
0x14003027f  xor     edx, edx; Tag
0x140030281  call    cs:__imp_ExFreePoolWithTag
0x140030288  nop     dword ptr [rax+rax+00h]
0x14003028d  jmp     loc_140030149
0x140030292  call    cs:__imp_FltReleaseFileNameInformation
0x140030299  nop     dword ptr [rax+rax+00h]
0x14003029e  jmp     loc_14003003D
```
