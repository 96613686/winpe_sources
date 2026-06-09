# VfsPostReadWrite

- ea: `0x14000a990`
- end: `0x14000aa1a`
- name: `VfsPostReadWrite`
- size: `138`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000a990`

## import_xrefs

- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x14000aa00`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x14000aa00`

## pseudocode

```c
__int64 __fastcall VfsPostReadWrite(
        PFLT_CALLBACK_DATA Data,
        const struct _FLT_RELATED_OBJECTS *a2,
        LARGE_INTEGER *a3,
        FLT_POST_OPERATION_FLAGS a4)
{
  PFILE_OBJECT FileObject; // r11
  SECTION_OBJECT_POINTERS *QuadPart; // rax
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+48h] [rbp+10h] BYREF

  FileObject = a2->FileObject;
  if ( !FileObject || !a3 )
    return 0;
  QuadPart = (SECTION_OBJECT_POINTERS *)a3[5].QuadPart;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  if ( FileObject->SectionObjectPointer != QuadPart )
    FileObject->SectionObjectPointer = QuadPart;
  if ( (a3[10].LowPart & 2) != 0 && (Data->Iopb->IrpFlags & 2) == 0 )
    FileObject->CurrentByteOffset = a3[13];
  if ( Data->Iopb->MajorFunction == 4 && Data->IoStatus.Status >= 0 )
    FltDoCompletionProcessingWhenSafe(Data, a2, a3, a4, VfsUpdateFileSizesWorker, &RetPostOperationStatus);
  return (unsigned int)RetPostOperationStatus;
}

```

## disassembly

```asm
0x14000a990  sub     rsp, 38h
0x14000a994  mov     r11, [rdx+20h]
0x14000a998  mov     r10, rcx
0x14000a99b  test    r11, r11
0x14000a99e  jz      short loc_14000AA12
0x14000a9a0  test    r8, r8
0x14000a9a3  jz      short loc_14000AA12
0x14000a9a5  mov     rax, [r8+28h]
0x14000a9a9  mov     [rsp+38h+arg_8], 0
0x14000a9b1  cmp     [r11+28h], rax
0x14000a9b5  jz      short loc_14000A9BB
0x14000a9b7  mov     [r11+28h], rax
0x14000a9bb  mov     eax, [r8+50h]
0x14000a9bf  test    al, 2
0x14000a9c1  jz      short loc_14000A9D6
0x14000a9c3  mov     rax, [rcx+10h]
0x14000a9c7  mov     ecx, [rax]
0x14000a9c9  test    cl, 2
0x14000a9cc  jnz     short loc_14000A9D6
0x14000a9ce  mov     rax, [r8+68h]
0x14000a9d2  mov     [r11+68h], rax
0x14000a9d6  mov     rax, [r10+10h]
0x14000a9da  cmp     byte ptr [rax+4], 4
0x14000a9de  jnz     short loc_14000AA0C
0x14000a9e0  cmp     dword ptr [r10+18h], 0
0x14000a9e5  jl      short loc_14000AA0C
0x14000a9e7  lea     rax, [rsp+38h+arg_8]
0x14000a9ec  mov     rcx, r10; Data
0x14000a9ef  mov     [rsp+38h+RetPostOperationStatus], rax; RetPostOperationStatus
0x14000a9f4  lea     rax, VfsUpdateFileSizesWorker
0x14000a9fb  mov     [rsp+38h+SafePostCallback], rax; SafePostCallback
0x14000aa00  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x14000aa07  nop     dword ptr [rax+rax+00h]
0x14000aa0c  mov     eax, [rsp+38h+arg_8]
0x14000aa10  jmp     short loc_14000AA14
0x14000aa12  xor     eax, eax
0x14000aa14  add     rsp, 38h
0x14000aa18  retn
```
