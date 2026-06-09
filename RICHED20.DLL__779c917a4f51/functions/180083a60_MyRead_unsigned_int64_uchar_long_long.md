# MyRead(unsigned __int64,uchar *,long,long *)

- ea: `0x180083a60`
- end: `0x180083aa5`
- name: `?MyRead@@YAK_KPEAEJPEAJ@Z`
- size: `69`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180083a60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180083a8a`
- `KERNEL32!GetLastError` at `0x180083a8a`
- `KERNEL32!ReadFile` at `0x180083a80`
- `KERNEL32!ReadFile` at `0x180083a80`

## pseudocode

```c
signed int __fastcall MyRead(void *a1, unsigned __int8 *a2, DWORD a3, DWORD *a4)
{
  signed int result; // eax

  if ( !a1 )
    return -2147467259;
  *a4 = 0;
  if ( ReadFile(a1, a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180083a60  sub     rsp, 38h
0x180083a64  test    rcx, rcx
0x180083a67  jnz     short loc_180083A70
0x180083a69  mov     eax, 80004005h
0x180083a6e  jmp     short loc_180083AA0
0x180083a70  mov     dword ptr [r9], 0
0x180083a77  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180083a80  call    cs:__imp_ReadFile
0x180083a86  test    eax, eax
0x180083a88  jnz     short loc_180083A9E
0x180083a8a  call    cs:__imp_GetLastError
0x180083a90  test    eax, eax
0x180083a92  jle     short loc_180083AA0
0x180083a94  movzx   eax, ax
0x180083a97  or      eax, 80070000h
0x180083a9c  jmp     short loc_180083AA0
0x180083a9e  xor     eax, eax
0x180083aa0  add     rsp, 38h
0x180083aa4  retn
```
