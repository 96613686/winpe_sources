# TFileStream::Write(void const *,ulong,ulong *)

- ea: `0x18000bc80`
- end: `0x18000bcb6`
- name: `?Write@TFileStream@@UEAAJPEBXKPEAK@Z`
- size: `54`
- prototype: `__int64 __fastcall(TFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000bc80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bc9f`
- `KERNEL32!GetLastError` at `0x18000bc9f`
- `KERNEL32!WriteFile` at `0x18000bc91`
- `KERNEL32!WriteFile` at `0x18000bc91`

## pseudocode

```c
signed int __fastcall TFileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
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
0x18000bc80  sub     rsp, 38h
0x18000bc84  mov     rcx, [rcx+8]; hFile
0x18000bc88  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000bc91  call    cs:__imp_WriteFile
0x18000bc97  test    eax, eax
0x18000bc99  jz      short loc_18000BC9F
0x18000bc9b  xor     eax, eax
0x18000bc9d  jmp     short loc_18000BCB1
0x18000bc9f  call    cs:__imp_GetLastError
0x18000bca5  test    eax, eax
0x18000bca7  jle     short loc_18000BCB1
0x18000bca9  movzx   eax, ax
0x18000bcac  or      eax, 80070000h
0x18000bcb1  add     rsp, 38h
0x18000bcb5  retn
```
