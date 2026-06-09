# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x14004d810`
- end: `0x14004d86f`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `95`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x14004d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d848`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14004d83e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14004d83e`

## pseudocode

```c
signed int __fastcall CFileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  DWORD v4; // eax
  signed int result; // eax
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  NumberOfBytesRead = 0;
  if ( !a2 )
    return -2147467261;
  if ( a3 )
  {
    if ( !ReadFile(this[3], a2, a3, &NumberOfBytesRead, 0) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v4 = NumberOfBytesRead;
  }
  if ( a4 )
    *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x14004d810  push    rbx
0x14004d812  sub     rsp, 30h
0x14004d816  xor     eax, eax
0x14004d818  mov     rbx, r9
0x14004d81b  mov     [rsp+38h+NumberOfBytesRead], eax
0x14004d81f  test    rdx, rdx
0x14004d822  jnz     short loc_14004D82B
0x14004d824  mov     eax, 80004003h
0x14004d829  jmp     short loc_14004D869
0x14004d82b  test    r8d, r8d
0x14004d82e  jz      short loc_14004D860
0x14004d830  mov     rcx, [rcx+18h]; hFile
0x14004d834  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14004d839  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x14004d83e  call    cs:__imp_ReadFile
0x14004d844  test    eax, eax
0x14004d846  jnz     short loc_14004D85C
0x14004d848  call    cs:__imp_GetLastError
0x14004d84e  test    eax, eax
0x14004d850  jle     short loc_14004D869
0x14004d852  movzx   eax, ax
0x14004d855  or      eax, 80070000h
0x14004d85a  jmp     short loc_14004D869
0x14004d85c  mov     eax, [rsp+38h+NumberOfBytesRead]
0x14004d860  test    rbx, rbx
0x14004d863  jz      short loc_14004D867
0x14004d865  mov     [rbx], eax
0x14004d867  xor     eax, eax
0x14004d869  add     rsp, 30h
0x14004d86d  pop     rbx
0x14004d86e  retn
```
