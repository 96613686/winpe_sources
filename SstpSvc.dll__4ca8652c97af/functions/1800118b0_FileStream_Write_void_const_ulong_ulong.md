# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800118b0`
- end: `0x1800118e6`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `54`
- prototype: `signed int __fastcall(HANDLE *this, const void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800118b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800118c1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800118c1`

## pseudocode

```c
signed int __fastcall FileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( WriteFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800118b0  sub     rsp, 38h
0x1800118b4  mov     rcx, [rcx+8]; hFile
0x1800118b8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800118c1  call    cs:__imp_WriteFile
0x1800118c7  test    eax, eax
0x1800118c9  jz      short loc_1800118CF
0x1800118cb  xor     eax, eax
0x1800118cd  jmp     short loc_1800118E1
0x1800118cf  call    cs:__imp_GetLastError
0x1800118d5  test    eax, eax
0x1800118d7  jle     short loc_1800118E1
0x1800118d9  movzx   eax, ax
0x1800118dc  or      eax, 80070000h
0x1800118e1  add     rsp, 38h
0x1800118e5  retn
```
