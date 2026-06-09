# __std_fs_open_handle(x,x,x,x)

- ea: `0x40c96c`
- end: `0x40c9a0`
- name: `___std_fs_open_handle@16`
- size: `52`
- prototype: `DWORD __stdcall(_DWORD *, LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwFlagsAndAttributes)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x40c77d`
- `0x40c9a0`

## callees

- `0x40c96c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c991`
- `KERNEL32!GetLastError` at `0x40c991`
- `KERNEL32!CreateFileW` at `0x40c981`
- `KERNEL32!CreateFileW` at `0x40c981`

## pseudocode

```c
DWORD __stdcall __std_fs_open_handle(_DWORD *a1, LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwFlagsAndAttributes)
{
  int v4; // esi
  HANDLE FileW; // eax

  v4 = 0;
  FileW = CreateFileW(lpFileName, dwDesiredAccess, 7u, 0, 3u, dwFlagsAndAttributes, 0);
  *a1 = FileW;
  if ( FileW == (HANDLE)-1 )
    return GetLastError();
  return v4;
}

```

## disassembly

```asm
0x40c96c  push    ebp
0x40c96d  mov     ebp, esp
0x40c96f  push    esi
0x40c970  xor     esi, esi
0x40c972  push    esi; hTemplateFile
0x40c973  push    [ebp+dwFlagsAndAttributes]; dwFlagsAndAttributes
0x40c976  push    3; dwCreationDisposition
0x40c978  push    esi; lpSecurityAttributes
0x40c979  push    7; dwShareMode
0x40c97b  push    [ebp+dwDesiredAccess]; dwDesiredAccess
0x40c97e  push    [ebp+lpFileName]; lpFileName
0x40c981  call    ds:CreateFileW
0x40c987  mov     ecx, [ebp+arg_0]
0x40c98a  mov     [ecx], eax
0x40c98c  cmp     eax, 0FFFFFFFFh
0x40c98f  jnz     short loc_40C999
0x40c991  call    ds:GetLastError
0x40c997  mov     esi, eax
0x40c999  mov     eax, esi
0x40c99b  pop     esi
0x40c99c  pop     ebp
0x40c99d  retn    10h
```
