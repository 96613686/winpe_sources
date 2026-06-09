# FileReader::ReadBytes<uchar>(ulong,uchar *)

- ea: `0x18000d458`
- end: `0x18000d4dd`
- name: `??$ReadBytes@E@FileReader@@QEAAJKPEAE@Z`
- size: `133`
- prototype: `int __fastcall(HANDLE *, DWORD, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000b5a4`
- `0x18000d64c`

## callees

- `0x18000d458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d493`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d489`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d489`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d4c0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d4c0`

## string_xrefs

- `0x18000d4b1`: `FileReader::ReadBytes`

## pseudocode

```c
int __fastcall FileReader::ReadBytes<unsigned char>(HANDLE *a1, DWORD a2, void *a3)
{
  signed int LastError; // eax
  int result; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( ReadFile(*a1, a3, a2, &NumberOfBytesRead, 0) )
  {
    result = 0;
    if ( NumberOfBytesRead != a2 )
      __int2c();
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    return ZTraceReportOrigination(LastError, "FileReader::ReadBytes", 55, a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000d458  mov     [rsp+arg_8], rbx
0x18000d45d  push    rdi
0x18000d45e  sub     rsp, 30h
0x18000d462  mov     rax, r8
0x18000d465  mov     [rsp+38h+NumberOfBytesRead], 0
0x18000d46d  mov     r8d, edx; nNumberOfBytesToRead
0x18000d470  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000d479  mov     ebx, edx
0x18000d47b  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d480  mov     rdi, rcx
0x18000d483  mov     rdx, rax; lpBuffer
0x18000d486  mov     rcx, [rcx]; hFile
0x18000d489  call    cs:__imp_ReadFile
0x18000d48f  test    eax, eax
0x18000d491  jnz     short loc_18000D4C8
0x18000d493  call    cs:__imp_GetLastError
0x18000d499  test    eax, eax
0x18000d49b  jz      short loc_18000D4A9
0x18000d49d  jle     short loc_18000D4AE
0x18000d49f  movzx   eax, ax
0x18000d4a2  or      eax, 80070000h
0x18000d4a7  jmp     short loc_18000D4AE
0x18000d4a9  mov     eax, 80390004h
0x18000d4ae  mov     r9, rdi
0x18000d4b1  lea     rdx, aFilereaderRead_1; "FileReader::ReadBytes"
0x18000d4b8  mov     r8d, 37h ; '7'
0x18000d4be  mov     ecx, eax
0x18000d4c0  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000d4c6  jmp     short loc_18000D4D2
0x18000d4c8  xor     eax, eax
0x18000d4ca  cmp     [rsp+38h+NumberOfBytesRead], ebx
0x18000d4ce  jz      short loc_18000D4D2
0x18000d4d0  int     2Ch; Windows NT - assertion failure
0x18000d4d2  mov     rbx, [rsp+38h+arg_8]
0x18000d4d7  add     rsp, 30h
0x18000d4db  pop     rdi
0x18000d4dc  retn
```
