# TFileStream::Read(void *,ulong,ulong *)

- ea: `0x180008350`
- end: `0x180008386`
- name: `?Read@TFileStream@@UEAAJPEAXKPEAK@Z`
- size: `54`
- prototype: `signed int __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180008350`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000836f`
- `KERNEL32!GetLastError` at `0x18000836f`
- `KERNEL32!ReadFile` at `0x180008361`
- `KERNEL32!ReadFile` at `0x180008361`

## pseudocode

```c
signed int __fastcall TFileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008350  sub     rsp, 38h
0x180008354  mov     rcx, [rcx+8]; hFile
0x180008358  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180008361  call    cs:__imp_ReadFile
0x180008367  test    eax, eax
0x180008369  jz      short loc_18000836F
0x18000836b  xor     eax, eax
0x18000836d  jmp     short loc_180008381
0x18000836f  call    cs:__imp_GetLastError
0x180008375  test    eax, eax
0x180008377  jle     short loc_180008381
0x180008379  movzx   eax, ax
0x18000837c  or      eax, 80070000h
0x180008381  add     rsp, 38h
0x180008385  retn
```
