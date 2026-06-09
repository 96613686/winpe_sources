# SmpQueryFile

- ea: `0x140001350`
- end: `0x140001390`
- name: `SmpQueryFile`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14000137e`
- `FLTMGR!FltQueryInformationFile` at `0x14000137e`

## pseudocode

```c
NTSTATUS __fastcall SmpQueryFile(__int64 a1, void *a2)
{
  ULONG LengthReturned; // [rsp+40h] [rbp+8h] BYREF

  LengthReturned = 0;
  return FltQueryInformationFile(
           *(PFLT_INSTANCE *)a1,
           *(PFILE_OBJECT *)(a1 + 8),
           a2,
           0x18u,
           FileStandardInformation,
           &LengthReturned);
}

```

## disassembly

```asm
0x140001350  sub     rsp, 38h
0x140001354  lea     rax, [rsp+38h+arg_0]
0x140001359  mov     [rsp+38h+arg_0], 0
0x140001361  mov     r8, rdx; FileInformation
0x140001364  mov     [rsp+38h+LengthReturned], rax; LengthReturned
0x140001369  mov     rdx, [rcx+8]; FileObject
0x14000136d  mov     r9d, 18h; Length
0x140001373  mov     rcx, [rcx]; Instance
0x140001376  mov     [rsp+38h+FileInformationClass], 5; FileInformationClass
0x14000137e  call    cs:__imp_FltQueryInformationFile
0x140001385  nop     dword ptr [rax+rax+00h]
0x14000138a  add     rsp, 38h
0x14000138e  retn
```
