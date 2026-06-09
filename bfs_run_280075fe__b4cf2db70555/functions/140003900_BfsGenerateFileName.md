# BfsGenerateFileName

- ea: `0x140003900`
- end: `0x1400039b5`
- name: `BfsGenerateFileName`
- size: `181`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CALLBACK_DATA CallbackData@<r8>, __int64, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003900`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140003987`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003987`
- `FLTMGR!FltGetFileNameInformation` at `0x14000392b`
- `FLTMGR!FltGetFileNameInformation` at `0x14000392b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400039a0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400039a0`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140003967`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140003967`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003947`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003947`

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
0x140003900  push    rbx
0x140003902  sub     rsp, 20h
0x140003906  mov     eax, r9d
0x140003909  mov     [rsp+28h+FileNameInformation], 0
0x140003912  btr     eax, 18h
0x140003916  mov     r9, r8
0x140003919  mov     r10, rdx
0x14000391c  test    r8, r8
0x14000391f  jz      short loc_140003939
0x140003921  lea     r8, [rsp+28h+FileNameInformation]; FileNameInformation
0x140003926  mov     edx, eax; NameOptions
0x140003928  mov     rcx, r9; CallbackData
0x14000392b  call    cs:__imp_FltGetFileNameInformation
0x140003932  nop     dword ptr [rax+rax+00h]
0x140003937  jmp     short loc_140003953
0x140003939  mov     rdx, rcx; Instance
0x14000393c  lea     r9, [rsp+28h+FileNameInformation]; FileNameInformation
0x140003941  mov     rcx, r10; FileObject
0x140003944  mov     r8d, eax; NameOptions
0x140003947  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000394e  nop     dword ptr [rax+rax+00h]
0x140003953  mov     ebx, eax
0x140003955  test    eax, eax
0x140003957  js      short loc_1400039AC
0x140003959  mov     rdx, [rsp+28h+FileNameInformation]
0x14000395e  mov     rcx, [rsp+28h+NameCtrl]; NameCtrl
0x140003963  movzx   edx, word ptr [rdx+8]; NewSize
0x140003967  call    cs:__imp_FltCheckAndGrowNameControl
0x14000396e  nop     dword ptr [rax+rax+00h]
0x140003973  mov     ebx, eax
0x140003975  test    eax, eax
0x140003977  js      short loc_14000399B
0x140003979  mov     rdx, [rsp+28h+FileNameInformation]
0x14000397e  mov     rcx, [rsp+28h+NameCtrl]; DestinationString
0x140003983  add     rdx, 8; SourceString
0x140003987  call    cs:__imp_RtlCopyUnicodeString
0x14000398e  nop     dword ptr [rax+rax+00h]
0x140003993  mov     rax, [rsp+28h+arg_20]
0x140003998  mov     byte ptr [rax], 1
0x14000399b  mov     rcx, [rsp+28h+FileNameInformation]; FileNameInformation
0x1400039a0  call    cs:__imp_FltReleaseFileNameInformation
0x1400039a7  nop     dword ptr [rax+rax+00h]
0x1400039ac  mov     eax, ebx
0x1400039ae  add     rsp, 20h
0x1400039b2  pop     rbx
0x1400039b3  retn
```
