# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x180002130`
- end: `0x1800021aa`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `122`
- prototype: `signed int __fastcall(HANDLE *this, const void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180002130`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002166`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002170`

## pseudocode

```c
signed int __fastcall CFileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax
  DWORD v7; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( a4 )
    *a4 = 0;
  if ( WriteFile(this[1], a2, a3, &NumberOfBytesWritten, 0) )
  {
    v7 = NumberOfBytesWritten;
    result = 0;
    if ( NumberOfBytesWritten != a3 )
      result = -2147024867;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    v7 = NumberOfBytesWritten;
  }
  if ( a4 )
    *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_8], rbx
0x180002135  push    rdi
0x180002136  sub     rsp, 30h
0x18000213a  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180002142  mov     rbx, r9
0x180002145  mov     edi, r8d
0x180002148  test    r9, r9
0x18000214b  jz      short loc_180002154
0x18000214d  mov     dword ptr [r9], 0
0x180002154  mov     rcx, [rcx+8]; hFile
0x180002158  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000215d  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180002166  call    cs:__imp_WriteFile
0x18000216c  test    eax, eax
0x18000216e  jnz     short loc_180002188
0x180002170  call    cs:__imp_GetLastError
0x180002176  test    eax, eax
0x180002178  jle     short loc_180002182
0x18000217a  movzx   eax, ax
0x18000217d  or      eax, 80070000h
0x180002182  mov     ecx, [rsp+38h+NumberOfBytesWritten]
0x180002186  jmp     short loc_180002198
0x180002188  mov     ecx, [rsp+38h+NumberOfBytesWritten]
0x18000218c  xor     eax, eax
0x18000218e  cmp     ecx, edi
0x180002190  mov     edx, 8007001Dh
0x180002195  cmovnz  eax, edx
0x180002198  test    rbx, rbx
0x18000219b  jz      short loc_18000219F
0x18000219d  mov     [rbx], ecx
0x18000219f  mov     rbx, [rsp+38h+arg_8]
0x1800021a4  add     rsp, 30h
0x1800021a8  pop     rdi
0x1800021a9  retn
```
