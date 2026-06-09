# BfsGenerateFileName

- ea: `0x140003a30`
- end: `0x140003ae5`
- name: `BfsGenerateFileName`
- size: `181`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData, int, _BYTE *, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003a30`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140003ab7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003ab7`
- `FLTMGR!FltGetFileNameInformation` at `0x140003a5b`
- `FLTMGR!FltGetFileNameInformation` at `0x140003a5b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003ad0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003ad0`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140003a97`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140003a97`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003a77`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003a77`

## pseudocode

```c
__int64 __fastcall BfsGenerateFileName(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        _BYTE *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  FLT_FILE_NAME_OPTIONS v6; // eax
  NTSTATUS FileNameInformationUnsafe; // eax
  NTSTATUS v8; // ebx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp+18h] BYREF

  FileNameInformation = 0;
  v6 = a4 & 0xFEFFFFFF;
  if ( CallbackData )
    FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v6, &FileNameInformation);
  else
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, v6, &FileNameInformation);
  v8 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe >= 0 )
  {
    v8 = FltCheckAndGrowNameControl(NameCtrl, FileNameInformation->Name.Length);
    if ( v8 >= 0 )
    {
      RtlCopyUnicodeString(&NameCtrl->Name, &FileNameInformation->Name);
      *a5 = 1;
    }
    FltReleaseFileNameInformation(FileNameInformation);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140003a30  push    rbx
0x140003a32  sub     rsp, 20h
0x140003a36  mov     eax, r9d
0x140003a39  mov     [rsp+28h+FileNameInformation], 0
0x140003a42  btr     eax, 18h
0x140003a46  mov     r9, r8
0x140003a49  mov     r10, rdx
0x140003a4c  test    r8, r8
0x140003a4f  jz      short loc_140003A69
0x140003a51  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x140003a56  mov     edx, eax; NameOptions
0x140003a58  mov     rcx, r9; CallbackData
0x140003a5b  call    cs:__imp_FltGetFileNameInformation
0x140003a62  nop     dword ptr [rax+rax+00h]
0x140003a67  jmp     short loc_140003A83
0x140003a69  mov     rdx, rcx; Instance
0x140003a6c  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x140003a71  mov     rcx, r10; FileObject
0x140003a74  mov     r8d, eax; NameOptions
0x140003a77  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140003a7e  nop     dword ptr [rax+rax+00h]
0x140003a83  mov     ebx, eax
0x140003a85  test    eax, eax
0x140003a87  js      short loc_140003ADC
0x140003a89  mov     rdx, [rsp+28h+FileNameInformation]
0x140003a8e  mov     rcx, [rsp+28h+NameCtrl]; NameCtrl
0x140003a93  movzx   edx, word ptr [rdx+8]; NewSize
0x140003a97  call    cs:__imp_FltCheckAndGrowNameControl
0x140003a9e  nop     dword ptr [rax+rax+00h]
0x140003aa3  mov     ebx, eax
0x140003aa5  test    eax, eax
0x140003aa7  js      short loc_140003ACB
0x140003aa9  mov     rdx, [rsp+28h+FileNameInformation]
0x140003aae  mov     rcx, [rsp+28h+NameCtrl]; DestinationString
0x140003ab3  add     rdx, 8; SourceString
0x140003ab7  call    cs:__imp_RtlCopyUnicodeString
0x140003abe  nop     dword ptr [rax+rax+00h]
0x140003ac3  mov     rax, [rsp+28h+arg_20]
0x140003ac8  mov     byte ptr [rax], 1
0x140003acb  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x140003ad0  call    cs:__imp_FltReleaseFileNameInformation
0x140003ad7  nop     dword ptr [rax+rax+00h]
0x140003adc  mov     eax, ebx
0x140003ade  add     rsp, 20h
0x140003ae2  pop     rbx
0x140003ae3  retn
```
