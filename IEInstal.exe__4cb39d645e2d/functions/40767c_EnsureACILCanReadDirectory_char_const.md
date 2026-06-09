# EnsureACILCanReadDirectory(char const *)

- ea: `0x40767c`
- end: `0x4076d4`
- name: `?EnsureACILCanReadDirectory@@YGJPBD@Z`
- size: `88`
- prototype: `unsigned int __thiscall(const CHAR *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x407a3f`

## callees

- `0x40767c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x4076b3`
- `KERNEL32!CloseHandle` at `0x4076b3`
- `KERNEL32!CreateFileA` at `0x407692`
- `KERNEL32!CreateFileA` at `0x407692`
- `KERNEL32!GetLastError` at `0x4076bb`
- `KERNEL32!GetLastError` at `0x4076bb`
- `iertutil!__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z` at `0x4076aa`
- `iertutil!__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z` at `0x4076aa`

## pseudocode

```c
unsigned int __thiscall EnsureACILCanReadDirectory(const CHAR *this)
{
  HANDLE FileA; // eax
  void *v2; // edi
  unsigned int v3; // esi
  signed int LastError; // eax

  FileA = CreateFileA(this, 0x1F0000u, 0, 0, 3u, 0x2000000u, 0);
  v2 = FileA;
  if ( FileA == (HANDLE)-1 )
  {
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  else
  {
    v3 = SetWindowsHandleAccess(FileA, 0x1240u, 0x1200A9u);
    CloseHandle(v2);
  }
  return v3;
}

```

## disassembly

```asm
0x40767c  mov     edi, edi
0x40767e  push    esi
0x40767f  push    edi
0x407680  xor     eax, eax
0x407682  push    eax; hTemplateFile
0x407683  push    2000000h; dwFlagsAndAttributes
0x407688  push    3; dwCreationDisposition
0x40768a  push    eax; lpSecurityAttributes
0x40768b  push    eax; dwShareMode
0x40768c  push    1F0000h; dwDesiredAccess
0x407691  push    ecx; lpFileName
0x407692  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x407698  mov     edi, eax
0x40769a  cmp     edi, 0FFFFFFFFh
0x40769d  jz      short loc_4076BB
0x40769f  push    1200A9h
0x4076a4  push    1240h
0x4076a9  push    edi
0x4076aa  call    ds:__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x4076b0  push    edi; hObject
0x4076b1  mov     esi, eax
0x4076b3  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4076b9  jmp     short loc_4076CF
0x4076bb  call    ds:__imp__GetLastError@0; GetLastError()
0x4076c1  movzx   esi, ax
0x4076c4  or      esi, 80070000h
0x4076ca  test    eax, eax
0x4076cc  cmovle  esi, eax
0x4076cf  pop     edi
0x4076d0  mov     eax, esi
0x4076d2  pop     esi
0x4076d3  retn
```
