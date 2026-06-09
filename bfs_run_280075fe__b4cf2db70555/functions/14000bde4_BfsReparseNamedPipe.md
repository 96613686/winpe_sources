# BfsReparseNamedPipe

- ea: `0x14000bde4`
- end: `0x14000be4f`
- name: `BfsReparseNamedPipe`
- size: `107`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140002a30`
- `0x14000b7bc`

## callees

- `0x14000bde4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000be0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be0c`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000be32`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000be32`

## pseudocode

```c
void __fastcall BfsReparseNamedPipe(PFLT_CALLBACK_DATA Data, UNICODE_STRING *a2)
{
  PFILE_OBJECT TargetFileObject; // rdi
  PWSTR Buffer; // rcx

  TargetFileObject = Data->Iopb->TargetFileObject;
  Buffer = TargetFileObject->FileName.Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  TargetFileObject->FileName = *a2;
  Data->IoStatus.Information = 0;
  Data->IoStatus.Status = 260;
  FltSetCallbackDataDirty(Data);
}

```

## disassembly

```asm
0x14000bde4  mov     [rsp+arg_0], rbx
0x14000bde9  mov     [rsp+arg_8], rsi
0x14000bdee  push    rdi
0x14000bdef  sub     rsp, 20h
0x14000bdf3  mov     rax, [rcx+10h]
0x14000bdf7  mov     rbx, rcx
0x14000bdfa  mov     rsi, rdx
0x14000bdfd  mov     rdi, [rax+8]
0x14000be01  mov     rcx, [rdi+60h]; P
0x14000be05  test    rcx, rcx
0x14000be08  jz      short loc_14000BE18
0x14000be0a  xor     edx, edx; Tag
0x14000be0c  call    cs:__imp_ExFreePoolWithTag
0x14000be13  nop     dword ptr [rax+rax+00h]
0x14000be18  movups  xmm0, xmmword ptr [rsi]
0x14000be1b  mov     rcx, rbx; Data
0x14000be1e  movdqu  xmmword ptr [rdi+58h], xmm0
0x14000be23  mov     qword ptr [rbx+20h], 0
0x14000be2b  mov     dword ptr [rbx+18h], 104h
0x14000be32  call    cs:__imp_FltSetCallbackDataDirty
0x14000be39  nop     dword ptr [rax+rax+00h]
0x14000be3e  mov     rbx, [rsp+28h+arg_0]
0x14000be43  mov     rsi, [rsp+28h+arg_8]
0x14000be48  add     rsp, 20h
0x14000be4c  pop     rdi
0x14000be4d  retn
```
