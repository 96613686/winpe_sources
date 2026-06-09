# FwspSeek

- ea: `0x140010fb0`
- end: `0x140011015`
- name: `FwspSeek`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ff4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140010fe6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140010fe6`

## pseudocode

```c
signed int __fastcall FwspSeek(__int64 a1, LARGE_INTEGER a2, DWORD a3, union _LARGE_INTEGER *a4)
{
  signed int result; // eax

  if ( a3 && a3 - 1 >= 2 )
  {
    if ( a4 )
      a4->QuadPart = 0;
    return -2147024809;
  }
  else if ( SetFilePointerEx(*(HANDLE *)(a1 + 8), a2, a4, a3) )
  {
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x140010fb0  sub     rsp, 28h
0x140010fb4  mov     r10, r9
0x140010fb7  mov     eax, r8d
0x140010fba  test    r8d, r8d
0x140010fbd  jz      short loc_140010FDC
0x140010fbf  sub     eax, 1
0x140010fc2  jz      short loc_140010FDC
0x140010fc4  cmp     eax, 1
0x140010fc7  jz      short loc_140010FDC
0x140010fc9  test    r9, r9
0x140010fcc  jz      short loc_140010FD5
0x140010fce  mov     qword ptr [r9], 0
0x140010fd5  mov     eax, 80070057h
0x140010fda  jmp     short loc_140011010
0x140010fdc  mov     rcx, [rcx+8]; hFile
0x140010fe0  mov     r9d, r8d; dwMoveMethod
0x140010fe3  mov     r8, r10; lpNewFilePointer
0x140010fe6  call    cs:__imp_SetFilePointerEx
0x140010fec  test    eax, eax
0x140010fee  jz      short loc_140010FF4
0x140010ff0  xor     eax, eax
0x140010ff2  jmp     short loc_140011010
0x140010ff4  call    cs:__imp_GetLastError
0x140010ffa  test    eax, eax
0x140010ffc  jle     short loc_140011006
0x140010ffe  movzx   eax, ax
0x140011001  or      eax, 80070000h
0x140011006  test    eax, eax
0x140011008  mov     ecx, 80004005h
0x14001100d  cmovns  eax, ecx
0x140011010  add     rsp, 28h
0x140011014  retn
```
