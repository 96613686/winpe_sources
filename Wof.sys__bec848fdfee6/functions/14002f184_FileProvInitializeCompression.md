# FileProvInitializeCompression

- ea: `0x14002f184`
- end: `0x14002f24b`
- name: `FileProvInitializeCompression`
- size: `199`
- prototype: `void()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ef58`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f239`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f239`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f1c9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f206`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f1c9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002f206`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002f18d`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002f18d`

## pseudocode

```c
void FileProvInitializeCompression()
{
  FileProvNumberProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  ExInitializeNPagedLookasideList(&FileProvCompressContextLookaside, 0, 0, 0x200u, 0x130u, 0x44527066u, 0);
  ExInitializeNPagedLookasideList(
    &FileProvCompressWorkitemsLookaside,
    0,
    0,
    0x200u,
    136LL * (unsigned int)FileProvNumberProcessors,
    0x44527066u,
    0);
  ExInitializePagedLookasideList(&FileProvCompressReadLookaside, 0, 0, 0, 0x40000u, 0x44527066u, 0);
}

```

## disassembly

```asm
0x14002f184  sub     rsp, 48h
0x14002f188  mov     ecx, 0FFFFh; GroupNumber
0x14002f18d  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14002f194  nop     dword ptr [rax+rax+00h]
0x14002f199  mov     cs:FileProvNumberProcessors, eax
0x14002f19f  mov     r9d, 200h; Flags
0x14002f1a5  xor     eax, eax
0x14002f1a7  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14002f1ae  mov     [rsp+48h+Depth], ax; Depth
0x14002f1b3  xor     r8d, r8d; Free
0x14002f1b6  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f1be  xor     edx, edx; Allocate
0x14002f1c0  mov     [rsp+48h+Size], 130h; Size
0x14002f1c9  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002f1d0  nop     dword ptr [rax+rax+00h]
0x14002f1d5  mov     eax, cs:FileProvNumberProcessors
0x14002f1db  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14002f1e2  imul    rax, 88h
0x14002f1e9  xor     edx, edx; Allocate
0x14002f1eb  mov     r9d, 200h; Flags
0x14002f1f1  mov     [rsp+48h+Depth], dx; Depth
0x14002f1f6  xor     r8d, r8d; Free
0x14002f1f9  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f201  mov     [rsp+48h+Size], rax; Size
0x14002f206  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002f20d  nop     dword ptr [rax+rax+00h]
0x14002f212  xor     eax, eax
0x14002f214  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14002f21b  mov     [rsp+48h+Depth], ax; Depth
0x14002f220  xor     r9d, r9d; Flags
0x14002f223  mov     [rsp+48h+Tag], 44527066h; Tag
0x14002f22b  xor     r8d, r8d; Free
0x14002f22e  xor     edx, edx; Allocate
0x14002f230  mov     [rsp+48h+Size], 40000h; Size
0x14002f239  call    cs:__imp_ExInitializePagedLookasideList
0x14002f240  nop     dword ptr [rax+rax+00h]
0x14002f245  add     rsp, 48h
0x14002f249  retn
```
