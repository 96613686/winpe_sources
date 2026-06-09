# CFBFileFormatCheck::GetSectorData(ulong,ulong *,ulong)

- ea: `0x180008228`
- end: `0x1800082b0`
- name: `?GetSectorData@CFBFileFormatCheck@@AEAAKKPEAKK@Z`
- size: `136`
- prototype: `unsigned int(CFBFileFormatCheck *__hidden this, unsigned int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006a30`
- `0x18000801c`

## callees

- `0x180008228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180008252`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180008252`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008285`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008285`

## pseudocode

```c
__int64 __fastcall CFBFileFormatCheck::GetSectorData(CFBFileFormatCheck *this, int a2, unsigned int *a3, DWORD a4)
{
  unsigned int v7; // ecx
  void *v8; // rcx
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  if ( SetFilePointerEx(
         *(HANDLE *)this,
         (LARGE_INTEGER)(*((unsigned int *)this + 14) * (unsigned __int64)(unsigned int)(a2 + 1)),
         0,
         0)
    && (v8 = *(void **)this, NumberOfBytesRead = 0, ReadFile(v8, a3, a4, &NumberOfBytesRead, 0)) )
  {
    v7 = 0;
    if ( NumberOfBytesRead != *((_DWORD *)this + 14) )
      return 13;
  }
  else
  {
    return GetLastError();
  }
  return v7;
}

```

## disassembly

```asm
0x180008228  mov     [rsp+arg_0], rbx
0x18000822d  mov     [rsp+arg_10], rsi
0x180008232  push    rdi
0x180008233  sub     rsp, 30h
0x180008237  mov     eax, [rcx+38h]
0x18000823a  inc     edx
0x18000823c  mov     edi, r9d
0x18000823f  mov     rsi, r8
0x180008242  mov     rbx, rcx
0x180008245  xor     r9d, r9d; dwMoveMethod
0x180008248  mov     rcx, [rcx]; hFile
0x18000824b  xor     r8d, r8d; lpNewFilePointer
0x18000824e  imul    rdx, rax; liDistanceToMove
0x180008252  call    cs:__imp_SetFilePointerEx
0x180008258  test    eax, eax
0x18000825a  jnz     short loc_180008266
0x18000825c  call    cs:__imp_GetLastError
0x180008262  mov     ecx, eax
0x180008264  jmp     short loc_18000829E
0x180008266  mov     rcx, [rbx]; hFile
0x180008269  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000826e  mov     r8d, edi; nNumberOfBytesToRead
0x180008271  mov     [rsp+38h+NumberOfBytesRead], 0
0x180008279  mov     rdx, rsi; lpBuffer
0x18000827c  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180008285  call    cs:__imp_ReadFile
0x18000828b  test    eax, eax
0x18000828d  jz      short loc_18000825C
0x18000828f  mov     eax, [rbx+38h]
0x180008292  xor     ecx, ecx
0x180008294  cmp     [rsp+38h+NumberOfBytesRead], eax
0x180008298  lea     edx, [rcx+0Dh]
0x18000829b  cmovnz  ecx, edx
0x18000829e  mov     rbx, [rsp+38h+arg_0]
0x1800082a3  mov     eax, ecx
0x1800082a5  mov     rsi, [rsp+38h+arg_10]
0x1800082aa  add     rsp, 30h
0x1800082ae  pop     rdi
0x1800082af  retn
```
