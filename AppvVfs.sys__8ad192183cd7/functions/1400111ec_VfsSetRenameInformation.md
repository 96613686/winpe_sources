# VfsSetRenameInformation

- ea: `0x1400111ec`
- end: `0x1400112ec`
- name: `VfsSetRenameInformation`
- size: `256`
- prototype: `int __fastcall(struct _FLT_INSTANCE *, struct _FILE_OBJECT *, LARGE_INTEGER, _BYTE *, ULONG Length)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000c1b4`

## callees

- `0x1400111ec`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x1400112be`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400112be`
- `FLTMGR!FltFreeCallbackData` at `0x1400112d2`
- `FLTMGR!FltFreeCallbackData` at `0x1400112d2`
- `FLTMGR!FltAllocateCallbackData` at `0x14001123f`
- `FLTMGR!FltAllocateCallbackData` at `0x14001123f`
- `FLTMGR!FltSetInformationFile` at `0x140011229`
- `FLTMGR!FltSetInformationFile` at `0x140011229`

## pseudocode

```c
int __fastcall VfsSetRenameInformation(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        LARGE_INTEGER a3,
        _BYTE *a4,
        ULONG Length)
{
  bool v5; // zf
  int result; // eax
  NTSTATUS Status; // ebx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+30h] [rbp-18h] BYREF

  v5 = *((_WORD *)a4 + 10) == 92;
  RetNewCallbackData = 0;
  if ( !v5 && !*((_QWORD *)a4 + 1) || !a3.QuadPart )
    return FltSetInformationFile(a1, a2, a4, Length, FileRenameInformation);
  result = FltAllocateCallbackData(a1, a2, &RetNewCallbackData);
  if ( result >= 0 )
  {
    RetNewCallbackData->Iopb->MajorFunction = 6;
    RetNewCallbackData->Iopb->Parameters.Read.Length = Length;
    RetNewCallbackData->Iopb->Parameters.Create.Options = 10;
    RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = a3;
    RetNewCallbackData->Iopb->Parameters.CreatePipe.Parameters = 0;
    RetNewCallbackData->Iopb->Parameters.SetFileInformation.ReplaceIfExists = *a4;
    RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = a4;
    FltPerformSynchronousIo(RetNewCallbackData);
    Status = RetNewCallbackData->IoStatus.Status;
    FltFreeCallbackData(RetNewCallbackData);
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x1400111ec  mov     [rsp+arg_0], rbx
0x1400111f1  push    rdi
0x1400111f2  sub     rsp, 40h
0x1400111f6  cmp     word ptr [r9+14h], 5Ch ; '\'
0x1400111fc  mov     rbx, r9
0x1400111ff  mov     rdi, r8
0x140011202  mov     [rsp+48h+RetNewCallbackData], 0
0x14001120b  jz      short loc_140011214
0x14001120d  cmp     qword ptr [r9+8], 0
0x140011212  jz      short loc_140011219
0x140011214  test    rdi, rdi
0x140011217  jnz     short loc_14001123A
0x140011219  mov     r9d, [rsp+48h+Length]; Length
0x14001121e  mov     r8, rbx; FileInformation
0x140011221  mov     [rsp+48h+FileInformationClass], 0Ah; FileInformationClass
0x140011229  call    cs:__imp_FltSetInformationFile
0x140011230  nop     dword ptr [rax+rax+00h]
0x140011235  jmp     loc_1400112E0
0x14001123a  lea     r8, [rsp+48h+RetNewCallbackData]; RetNewCallbackData
0x14001123f  call    cs:__imp_FltAllocateCallbackData
0x140011246  nop     dword ptr [rax+rax+00h]
0x14001124b  test    eax, eax
0x14001124d  js      loc_1400112E0
0x140011253  mov     rax, [rsp+48h+RetNewCallbackData]
0x140011258  mov     rcx, [rax+10h]
0x14001125c  mov     byte ptr [rcx+4], 6
0x140011260  mov     rax, [rsp+48h+RetNewCallbackData]
0x140011265  mov     rcx, [rax+10h]
0x140011269  mov     eax, [rsp+48h+Length]
0x14001126d  mov     [rcx+18h], eax
0x140011270  mov     rax, [rsp+48h+RetNewCallbackData]
0x140011275  mov     rcx, [rax+10h]
0x140011279  mov     dword ptr [rcx+20h], 0Ah
0x140011280  mov     rax, [rsp+48h+RetNewCallbackData]
0x140011285  mov     rcx, [rax+10h]
0x140011289  mov     [rcx+28h], rdi
0x14001128d  mov     rax, [rsp+48h+RetNewCallbackData]
0x140011292  mov     rcx, [rax+10h]
0x140011296  mov     qword ptr [rcx+30h], 0
0x14001129e  mov     rax, [rsp+48h+RetNewCallbackData]
0x1400112a3  mov     rcx, [rax+10h]
0x1400112a7  mov     al, [rbx]
0x1400112a9  mov     [rcx+30h], al
0x1400112ac  mov     rax, [rsp+48h+RetNewCallbackData]
0x1400112b1  mov     rcx, [rax+10h]
0x1400112b5  mov     [rcx+38h], rbx
0x1400112b9  mov     rcx, [rsp+48h+RetNewCallbackData]; CallbackData
0x1400112be  call    cs:__imp_FltPerformSynchronousIo
0x1400112c5  nop     dword ptr [rax+rax+00h]
0x1400112ca  mov     rcx, [rsp+48h+RetNewCallbackData]; CallbackData
0x1400112cf  mov     ebx, [rcx+18h]
0x1400112d2  call    cs:__imp_FltFreeCallbackData
0x1400112d9  nop     dword ptr [rax+rax+00h]
0x1400112de  mov     eax, ebx
0x1400112e0  mov     rbx, [rsp+48h+arg_0]
0x1400112e5  add     rsp, 40h
0x1400112e9  pop     rdi
0x1400112ea  retn
```
