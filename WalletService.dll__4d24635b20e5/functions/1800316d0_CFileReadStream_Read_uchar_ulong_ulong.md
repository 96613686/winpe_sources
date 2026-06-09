# CFileReadStream::Read(uchar *,ulong,ulong *)

- ea: `0x1800316d0`
- end: `0x18003170f`
- name: `?Read@CFileReadStream@@UEAAJPEAEKPEAK@Z`
- size: `63`
- prototype: `__int64 __fastcall(CFileReadStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800316d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800316e1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800316e1`

## pseudocode

```c
signed int __fastcall CFileReadStream::Read(HANDLE *this, unsigned __int8 *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( !result )
    return -2143748092;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800316d0  sub     rsp, 38h
0x1800316d4  mov     rcx, [rcx+8]; hFile
0x1800316d8  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800316e1  call    cs:__imp_ReadFile
0x1800316e7  test    eax, eax
0x1800316e9  jnz     short loc_180031708
0x1800316eb  call    cs:__imp_GetLastError
0x1800316f1  test    eax, eax
0x1800316f3  jz      short loc_180031701
0x1800316f5  jle     short loc_18003170A
0x1800316f7  movzx   eax, ax
0x1800316fa  or      eax, 80070000h
0x1800316ff  jmp     short loc_18003170A
0x180031701  mov     eax, 80390004h
0x180031706  jmp     short loc_18003170A
0x180031708  xor     eax, eax
0x18003170a  add     rsp, 38h
0x18003170e  retn
```
