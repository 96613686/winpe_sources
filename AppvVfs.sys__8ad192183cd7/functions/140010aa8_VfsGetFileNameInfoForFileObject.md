# VfsGetFileNameInfoForFileObject

- ea: `0x140010aa8`
- end: `0x140010ba5`
- name: `VfsGetFileNameInfoForFileObject`
- size: `253`
- prototype: `NTSTATUS __fastcall(__int64, struct _FILE_OBJECT *, struct _FLT_INSTANCE *, FLT_FILE_NAME_OPTIONS, PFLT_FILE_NAME_INFORMATION *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140005dc8`
- `0x1400061b4`
- `0x14000aefc`
- `0x14000b4ec`
- `0x14000be3c`
- `0x14000c6fc`
- `0x14000c8c4`

## callees

- `0x140010aa8`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x140010b0e`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140010b0e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140010adc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140010adc`
- `FLTMGR!FltParseFileNameInformation` at `0x140010b54`
- `FLTMGR!FltParseFileNameInformation` at `0x140010b54`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140010b3f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140010b3f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140010b6b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140010b6b`

## pseudocode

```c
NTSTATUS __fastcall VfsGetFileNameInfoForFileObject(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        FLT_FILE_NAME_OPTIONS a4,
        PFLT_FILE_NAME_INFORMATION *a5)
{
  __int64 v5; // rbx
  char v10; // bl
  NTSTATUS result; // eax
  NTSTATUS v12; // ebx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  FileNameInformation = 0;
  if ( (*(_DWORD *)v5 & 2) != 0
    || (v10 = *(_BYTE *)(v5 + 4), IoGetTopLevelIrp()) && v10
    || (a2->Flags & 0x4000) != 0
    || (unsigned __int8)(v10 + 6) <= 4u
    || (*(_DWORD *)a1 & 0x80000) != 0 && v10 == -1
    || KeAreAllApcsDisabled() )
  {
    if ( (((a4 & 0xFF00) - 256) & 0xFFFFFDFF) == 0 )
      return -1071906811;
  }
  result = FltGetFileNameInformationUnsafe(a2, a3, a4, &FileNameInformation);
  if ( result >= 0 )
  {
    v12 = FltParseFileNameInformation(FileNameInformation);
    if ( v12 >= 0 )
    {
      *a5 = FileNameInformation;
      return 0;
    }
    else
    {
      FltReleaseFileNameInformation(FileNameInformation);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010aa8  mov     [rsp+arg_8], rbx
0x140010aad  mov     [rsp+arg_10], rbp
0x140010ab2  push    rsi
0x140010ab3  push    rdi
0x140010ab4  push    r14
0x140010ab6  sub     rsp, 20h
0x140010aba  mov     rbx, [rcx+10h]
0x140010abe  mov     esi, r9d
0x140010ac1  mov     [rsp+38h+FileNameInformation], 0
0x140010aca  mov     r14, r8
0x140010acd  mov     rbp, rdx
0x140010ad0  mov     rdi, rcx
0x140010ad3  mov     eax, [rbx]
0x140010ad5  test    al, 2
0x140010ad7  jnz     short loc_140010B1E
0x140010ad9  mov     bl, [rbx+4]
0x140010adc  call    cs:__imp_IoGetTopLevelIrp
0x140010ae3  nop     dword ptr [rax+rax+00h]
0x140010ae8  test    rax, rax
0x140010aeb  jz      short loc_140010AF1
0x140010aed  test    bl, bl
0x140010aef  jnz     short loc_140010B1E
0x140010af1  test    dword ptr [rbp+50h], 4000h
0x140010af8  jnz     short loc_140010B1E
0x140010afa  lea     eax, [rbx+6]
0x140010afd  cmp     al, 4
0x140010aff  jbe     short loc_140010B1E
0x140010b01  test    dword ptr [rdi], 80000h
0x140010b07  jz      short loc_140010B0E
0x140010b09  cmp     bl, 0FFh
0x140010b0c  jz      short loc_140010B1E
0x140010b0e  call    cs:__imp_KeAreAllApcsDisabled
0x140010b15  nop     dword ptr [rax+rax+00h]
0x140010b1a  test    al, al
0x140010b1c  jz      short loc_140010B31
0x140010b1e  mov     eax, esi
0x140010b20  and     eax, 0FF00h
0x140010b25  sub     eax, 100h
0x140010b2a  test    eax, 0FFFFFDFFh
0x140010b2f  jz      short loc_140010B8C
0x140010b31  lea     r9, [rsp+38h+FileNameInformation]; FileNameInformation
0x140010b36  mov     r8d, esi; NameOptions
0x140010b39  mov     rdx, r14; Instance
0x140010b3c  mov     rcx, rbp; FileObject
0x140010b3f  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140010b46  nop     dword ptr [rax+rax+00h]
0x140010b4b  test    eax, eax
0x140010b4d  js      short loc_140010B91
0x140010b4f  mov     rcx, [rsp+38h+FileNameInformation]; FileNameInformation
0x140010b54  call    cs:__imp_FltParseFileNameInformation
0x140010b5b  nop     dword ptr [rax+rax+00h]
0x140010b60  mov     ebx, eax
0x140010b62  test    eax, eax
0x140010b64  jns     short loc_140010B7B
0x140010b66  mov     rcx, [rsp+38h+FileNameInformation]; FileNameInformation
0x140010b6b  call    cs:__imp_FltReleaseFileNameInformation
0x140010b72  nop     dword ptr [rax+rax+00h]
0x140010b77  mov     eax, ebx
0x140010b79  jmp     short loc_140010B91
0x140010b7b  mov     rax, [rsp+38h+FileNameInformation]
0x140010b80  mov     rcx, [rsp+38h+arg_20]
0x140010b85  mov     [rcx], rax
0x140010b88  xor     eax, eax
0x140010b8a  jmp     short loc_140010B91
0x140010b8c  mov     eax, 0C01C0005h
0x140010b91  mov     rbx, [rsp+38h+arg_8]
0x140010b96  mov     rbp, [rsp+38h+arg_10]
0x140010b9b  add     rsp, 20h
0x140010b9f  pop     r14
0x140010ba1  pop     rdi
0x140010ba2  pop     rsi
0x140010ba3  retn
```
