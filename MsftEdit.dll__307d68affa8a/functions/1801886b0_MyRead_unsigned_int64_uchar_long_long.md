# MyRead(unsigned __int64,uchar *,long,long *)

- ea: `0x1801886b0`
- end: `0x1801886f5`
- name: `?MyRead@@YAK_KPEAEJPEAJ@Z`
- size: `69`
- prototype: `unsigned int __fastcall(unsigned __int64, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1801886b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801886da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801886da`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801886d0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801886d0`

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
0x1801886b0  sub     rsp, 38h
0x1801886b4  test    rcx, rcx
0x1801886b7  jnz     short loc_1801886C0
0x1801886b9  mov     eax, 80004005h
0x1801886be  jmp     short loc_1801886F0
0x1801886c0  mov     dword ptr [r9], 0
0x1801886c7  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1801886d0  call    cs:__imp_ReadFile
0x1801886d6  test    eax, eax
0x1801886d8  jnz     short loc_1801886EE
0x1801886da  call    cs:__imp_GetLastError
0x1801886e0  test    eax, eax
0x1801886e2  jle     short loc_1801886F0
0x1801886e4  movzx   eax, ax
0x1801886e7  or      eax, 80070000h
0x1801886ec  jmp     short loc_1801886F0
0x1801886ee  xor     eax, eax
0x1801886f0  add     rsp, 38h
0x1801886f4  retn
```
