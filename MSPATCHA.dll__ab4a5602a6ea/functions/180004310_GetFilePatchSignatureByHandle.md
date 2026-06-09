# GetFilePatchSignatureByHandle

- ea: `0x180004310`
- end: `0x1800043cb`
- name: `GetFilePatchSignatureByHandle`
- size: `187`
- prototype: `BOOL __stdcall(HANDLE FileHandle, ULONG OptionFlags, PVOID OptionData, ULONG IgnoreRangeCount, PPATCH_IGNORE_RANGE IgnoreRangeArray, ULONG RetainRangeCount, PPATCH_RETAIN_RANGE RetainRangeArray, ULONG SignatureBufferSize, LPSTR SignatureBuffer)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800040d0`
- `0x1800043e0`

## callees

- `0x180004180`
- `0x180004310`
- `0x180006ee8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043ba`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800043a1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800043a1`

## pseudocode

```c
BOOL __stdcall GetFilePatchSignatureByHandle(
        HANDLE FileHandle,
        ULONG OptionFlags,
        PVOID OptionData,
        ULONG IgnoreRangeCount,
        PPATCH_IGNORE_RANGE IgnoreRangeArray,
        ULONG RetainRangeCount,
        PPATCH_RETAIN_RANGE RetainRangeArray,
        ULONG SignatureBufferSize,
        LPSTR SignatureBuffer)
{
  int FilePatchSignatureByBuffer; // ebx

  FilePatchSignatureByBuffer = MyMapViewOfFileByHandle(FileHandle);
  if ( !FilePatchSignatureByBuffer
    || (FilePatchSignatureByBuffer = GetFilePatchSignatureByBuffer(
                                       0,
                                       0,
                                       OptionFlags,
                                       OptionData,
                                       IgnoreRangeCount,
                                       IgnoreRangeArray,
                                       RetainRangeCount,
                                       RetainRangeArray,
                                       SignatureBufferSize,
                                       SignatureBuffer),
        UnmapViewOfFile(0),
        !FilePatchSignatureByBuffer) )
  {
    if ( !GetLastError() )
      SetLastError(0x4B8u);
  }
  return FilePatchSignatureByBuffer;
}

```

## disassembly

```asm
0x180004310  mov     rax, rsp
0x180004313  push    rbx
0x180004314  push    rbp
0x180004315  push    rsi
0x180004316  push    rdi
0x180004317  sub     rsp, 68h
0x18000431b  mov     rsi, r8
0x18000431e  mov     qword ptr [rax-30h], 0
0x180004326  mov     ebp, edx
0x180004328  mov     dword ptr [rax-38h], 0
0x18000432f  lea     r8, [rax-30h]
0x180004333  mov     edi, r9d
0x180004336  lea     rdx, [rax-38h]
0x18000433a  call    MyMapViewOfFileByHandle
0x18000433f  mov     ebx, eax
0x180004341  test    eax, eax
0x180004343  jz      short loc_1800043AB
0x180004345  mov     rax, [rsp+88h+SignatureBuffer]
0x18000434d  mov     r9, rsi; OptionData
0x180004350  mov     edx, [rsp+88h+FileSize]; FileSize
0x180004354  mov     r8d, ebp; OptionFlags
0x180004357  mov     rcx, [rsp+88h+FileBufferWritable]; FileBufferWritable
0x18000435c  mov     [rsp+88h+var_40], rax; SignatureBuffer
0x180004361  mov     eax, [rsp+88h+SignatureBufferSize]
0x180004368  mov     [rsp+88h+var_48], eax; SignatureBufferSize
0x18000436c  mov     rax, [rsp+88h+RetainRangeArray]
0x180004374  mov     [rsp+88h+var_50], rax; RetainRangeArray
0x180004379  mov     eax, [rsp+88h+RetainRangeCount]
0x180004380  mov     [rsp+88h+var_58], eax; RetainRangeCount
0x180004384  mov     rax, [rsp+88h+IgnoreRangeArray]
0x18000438c  mov     [rsp+88h+var_60], rax; IgnoreRangeArray
0x180004391  mov     [rsp+88h+IgnoreRangeCount], edi; IgnoreRangeCount
0x180004395  call    GetFilePatchSignatureByBuffer
0x18000439a  mov     rcx, [rsp+88h+FileBufferWritable]; lpBaseAddress
0x18000439f  mov     ebx, eax
0x1800043a1  call    cs:__imp_UnmapViewOfFile
0x1800043a7  test    ebx, ebx
0x1800043a9  jnz     short loc_1800043C0
0x1800043ab  call    cs:__imp_GetLastError
0x1800043b1  test    eax, eax
0x1800043b3  jnz     short loc_1800043C0
0x1800043b5  mov     ecx, 4B8h; dwErrCode
0x1800043ba  call    cs:__imp_SetLastError
0x1800043c0  mov     eax, ebx
0x1800043c2  add     rsp, 68h
0x1800043c6  pop     rdi
0x1800043c7  pop     rsi
0x1800043c8  pop     rbp
0x1800043c9  pop     rbx
0x1800043ca  retn
```
