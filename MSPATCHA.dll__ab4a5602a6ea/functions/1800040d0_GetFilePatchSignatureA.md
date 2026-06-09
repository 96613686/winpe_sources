# GetFilePatchSignatureA

- ea: `0x1800040d0`
- end: `0x180004179`
- name: `GetFilePatchSignatureA`
- size: `169`
- prototype: `BOOL __stdcall(LPCSTR FileName, ULONG OptionFlags, PVOID OptionData, ULONG IgnoreRangeCount, PPATCH_IGNORE_RANGE IgnoreRangeArray, ULONG RetainRangeCount, PPATCH_RETAIN_RANGE RetainRangeArray, ULONG SignatureBufferSize, LPSTR SignatureBuffer)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x1800040d0`
- `0x180004310`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180004104`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180004104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004166`

## pseudocode

```c
BOOL __stdcall GetFilePatchSignatureA(
        LPCSTR FileName,
        ULONG OptionFlags,
        PVOID OptionData,
        ULONG IgnoreRangeCount,
        PPATCH_IGNORE_RANGE IgnoreRangeArray,
        ULONG RetainRangeCount,
        PPATCH_RETAIN_RANGE RetainRangeArray,
        ULONG SignatureBufferSize,
        LPSTR SignatureBuffer)
{
  BOOL FilePatchSignatureByHandle; // ebx
  HANDLE FileA; // rax
  void *v14; // rdi

  FilePatchSignatureByHandle = 0;
  FileA = CreateFileA(FileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  v14 = FileA;
  if ( FileA != (HANDLE)-1LL )
  {
    FilePatchSignatureByHandle = GetFilePatchSignatureByHandle(
                                   FileA,
                                   OptionFlags,
                                   OptionData,
                                   IgnoreRangeCount,
                                   IgnoreRangeArray,
                                   RetainRangeCount,
                                   RetainRangeArray,
                                   SignatureBufferSize,
                                   SignatureBuffer);
    CloseHandle(v14);
  }
  return FilePatchSignatureByHandle;
}

```

## disassembly

```asm
0x1800040d0  push    rbx
0x1800040d2  push    rbp
0x1800040d3  push    rsi
0x1800040d4  push    rdi
0x1800040d5  push    r14
0x1800040d7  sub     rsp, 50h
0x1800040db  xor     ebx, ebx
0x1800040dd  mov     rbp, r8
0x1800040e0  mov     esi, r9d
0x1800040e3  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x1800040e8  mov     r14d, edx
0x1800040eb  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800040f3  xor     r9d, r9d; lpSecurityAttributes
0x1800040f6  mov     edx, 80000000h; dwDesiredAccess
0x1800040fb  lea     r8d, [rbx+3]; dwShareMode
0x1800040ff  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x180004104  call    cs:__imp_CreateFileA
0x18000410a  mov     rdi, rax
0x18000410d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004111  jz      short loc_18000416C
0x180004113  mov     rax, [rsp+78h+SignatureBuffer]
0x18000411b  mov     r9d, esi; IgnoreRangeCount
0x18000411e  mov     [rsp+78h+var_38], rax; SignatureBuffer
0x180004123  mov     r8, rbp; OptionData
0x180004126  mov     eax, [rsp+78h+SignatureBufferSize]
0x18000412d  mov     edx, r14d; OptionFlags
0x180004130  mov     [rsp+78h+var_40], eax; SignatureBufferSize
0x180004134  mov     rcx, rdi; FileHandle
0x180004137  mov     rax, [rsp+78h+RetainRangeArray]
0x18000413f  mov     [rsp+78h+hTemplateFile], rax; RetainRangeArray
0x180004144  mov     eax, [rsp+78h+RetainRangeCount]
0x18000414b  mov     [rsp+78h+dwFlagsAndAttributes], eax; RetainRangeCount
0x18000414f  mov     rax, [rsp+78h+IgnoreRangeArray]
0x180004157  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; IgnoreRangeArray
0x18000415c  call    GetFilePatchSignatureByHandle
0x180004161  mov     rcx, rdi; hObject
0x180004164  mov     ebx, eax
0x180004166  call    cs:__imp_CloseHandle
0x18000416c  mov     eax, ebx
0x18000416e  add     rsp, 50h
0x180004172  pop     r14
0x180004174  pop     rdi
0x180004175  pop     rsi
0x180004176  pop     rbp
0x180004177  pop     rbx
0x180004178  retn
```
