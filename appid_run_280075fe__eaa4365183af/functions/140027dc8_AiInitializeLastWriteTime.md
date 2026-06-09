# AiInitializeLastWriteTime

- ea: `0x140027dc8`
- end: `0x140027eb6`
- name: `AiInitializeLastWriteTime`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140022ad0`

## callees

- `0x140027dc8`
- `0x140035d30`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x140027e60`
- `ntoskrnl!ZwOpenFile` at `0x140027e60`
- `ntoskrnl!PsCreateSystemThread` at `0x140027ea0`
- `ntoskrnl!PsCreateSystemThread` at `0x140027ea0`

## string_xrefs

- `0x140027dee`: `\SystemRoot\System32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\`

## pseudocode

```c
int AiInitializeLastWriteTime()
{
  int result; // eax
  _QWORD v1[2]; // [rsp+40h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF

  v1[0] = 9044104;
  qword_1400192E0 = 0;
  v1[1] = L"\\SystemRoot\\System32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\";
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  result = AiGetCatalogLastWriteTime();
  if ( result >= 0 )
  {
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    if ( result >= 0 )
      return PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, AipCatalogUpdateThread, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140027dc8  push    rbp
0x140027dca  lea     rbp, [rsp-57h]
0x140027dcf  sub     rsp, 90h
0x140027dd6  xorps   xmm0, xmm0
0x140027dd9  mov     [rbp+57h+var_50], 8A0088h
0x140027de1  xor     eax, eax
0x140027de3  mov     cs:qword_1400192E0, 0
0x140027dee  lea     rax, aSystemrootSyst_8; "\\SystemRoot\\System32\\CatRoot\\{F750E"...
0x140027df5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140027df9  mov     [rbp+57h+var_48], rax
0x140027dfd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140027e01  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140027e05  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140027e09  call    AiGetCatalogLastWriteTime
0x140027e0e  test    eax, eax
0x140027e10  js      loc_140027EAC
0x140027e16  lea     rax, [rbp+57h+var_50]
0x140027e1a  mov     [rsp+90h+OpenOptions], 0; OpenOptions
0x140027e22  xorps   xmm0, xmm0
0x140027e25  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140027e29  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140027e2d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140027e34  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140027e38  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140027e40  mov     edx, 80100000h; DesiredAccess
0x140027e45  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140027e4c  lea     rcx, FileHandle; FileHandle
0x140027e53  mov     [rsp+90h+ShareAccess], 7; ShareAccess
0x140027e5b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140027e60  call    cs:__imp_ZwOpenFile
0x140027e67  nop     dword ptr [rax+rax+00h]
0x140027e6c  test    eax, eax
0x140027e6e  js      short loc_140027EAC
0x140027e70  lea     rax, AipCatalogUpdateThread
0x140027e77  mov     [rsp+90h+StartContext], 0; StartContext
0x140027e80  mov     qword ptr [rsp+90h+OpenOptions], rax; StartRoutine
0x140027e85  lea     rcx, ThreadHandle; ThreadHandle
0x140027e8c  xor     r9d, r9d; ProcessHandle
0x140027e8f  mov     qword ptr [rsp+90h+ShareAccess], 0; ClientId
0x140027e98  xor     r8d, r8d; ObjectAttributes
0x140027e9b  mov     edx, 1FFFFFh; DesiredAccess
0x140027ea0  call    cs:__imp_PsCreateSystemThread
0x140027ea7  nop     dword ptr [rax+rax+00h]
0x140027eac  add     rsp, 90h
0x140027eb3  pop     rbp
0x140027eb4  retn
```
