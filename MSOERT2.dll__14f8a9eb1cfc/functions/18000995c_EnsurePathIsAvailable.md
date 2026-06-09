# EnsurePathIsAvailable

- ea: `0x18000995c`
- end: `0x180009a47`
- name: `EnsurePathIsAvailable`
- size: `235`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a220`

## callees

- `0x18000995c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009a27`
- `KERNEL32!GetLastError` at `0x180009a27`
- `KERNEL32!CloseHandle` at `0x1800099b3`
- `KERNEL32!CloseHandle` at `0x180009a02`
- `KERNEL32!CloseHandle` at `0x1800099b3`
- `KERNEL32!CloseHandle` at `0x180009a02`
- `KERNEL32!CreateFileW` at `0x18000999f`
- `KERNEL32!CreateFileW` at `0x1800099ee`
- `KERNEL32!CreateFileW` at `0x18000999f`
- `KERNEL32!CreateFileW` at `0x1800099ee`
- `KERNEL32!DeleteFileW` at `0x1800099bc`
- `KERNEL32!DeleteFileW` at `0x1800099bc`
- `KERNEL32!CreateDirectoryW` at `0x180009a1d`
- `KERNEL32!CreateDirectoryW` at `0x180009a1d`

## pseudocode

```c
signed int __fastcall EnsurePathIsAvailable(LPCWSTR lpFileName, int a2, _DWORD *a3)
{
  HANDLE FileW; // rax
  HANDLE v6; // rax
  signed int result; // eax

  *a3 = 0;
  if ( a2 )
  {
    if ( CreateDirectoryW(lpFileName, 0) )
    {
LABEL_9:
      *a3 = 1;
      return 0;
    }
  }
  else
  {
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 1u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      if ( FileW )
        CloseHandle(FileW);
      if ( DeleteFileW(lpFileName) )
      {
        v6 = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 1u, 0x80u, 0);
        if ( v6 != (HANDLE)-1LL )
        {
          if ( v6 )
            CloseHandle(v6);
          goto LABEL_9;
        }
      }
    }
  }
  result = GetLastError();
  if ( result == 183 || result == 80 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000995c  mov     rax, rsp
0x18000995f  mov     [rax+8], rsi
0x180009963  push    rdi
0x180009964  sub     rsp, 40h
0x180009968  mov     dword ptr [r8], 0
0x18000996f  mov     rdi, r8
0x180009972  mov     rsi, rcx
0x180009975  test    edx, edx
0x180009977  jnz     loc_180009A1B
0x18000997d  mov     qword ptr [rax-18h], 0
0x180009985  xor     r9d, r9d; lpSecurityAttributes
0x180009988  mov     dword ptr [rax-20h], 80h
0x18000998f  mov     edx, 0C0000000h; dwDesiredAccess
0x180009994  mov     dword ptr [rax-28h], 1
0x18000999b  lea     r8d, [r9+3]; dwShareMode
0x18000999f  call    cs:__imp_CreateFileW
0x1800099a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800099a9  jz      short loc_180009A27
0x1800099ab  test    rax, rax
0x1800099ae  jz      short loc_1800099B9
0x1800099b0  mov     rcx, rax; hObject
0x1800099b3  call    cs:__imp_CloseHandle
0x1800099b9  mov     rcx, rsi; lpFileName
0x1800099bc  call    cs:__imp_DeleteFileW
0x1800099c2  test    eax, eax
0x1800099c4  jz      short loc_180009A27
0x1800099c6  xor     r9d, r9d; lpSecurityAttributes
0x1800099c9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800099d2  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800099da  mov     edx, 0C0000000h; dwDesiredAccess
0x1800099df  mov     rcx, rsi; lpFileName
0x1800099e2  mov     [rsp+48h+dwCreationDisposition], 1; dwCreationDisposition
0x1800099ea  lea     r8d, [r9+3]; dwShareMode
0x1800099ee  call    cs:__imp_CreateFileW
0x1800099f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800099f8  jz      short loc_180009A27
0x1800099fa  test    rax, rax
0x1800099fd  jz      short loc_180009A08
0x1800099ff  mov     rcx, rax; hObject
0x180009a02  call    cs:__imp_CloseHandle
0x180009a08  mov     dword ptr [rdi], 1
0x180009a0e  xor     eax, eax
0x180009a10  mov     rsi, [rsp+48h+arg_0]
0x180009a15  add     rsp, 40h
0x180009a19  pop     rdi
0x180009a1a  retn
0x180009a1b  xor     edx, edx; lpSecurityAttributes
0x180009a1d  call    cs:__imp_CreateDirectoryW
0x180009a23  test    eax, eax
0x180009a25  jnz     short loc_180009A08
0x180009a27  call    cs:__imp_GetLastError
0x180009a2d  cmp     eax, 0B7h
0x180009a32  jz      short loc_180009A0E
0x180009a34  cmp     eax, 50h ; 'P'
0x180009a37  jz      short loc_180009A0E
0x180009a39  test    eax, eax
0x180009a3b  jle     short loc_180009A10
0x180009a3d  movzx   eax, ax
0x180009a40  or      eax, 80070000h
0x180009a45  jmp     short loc_180009A10
```
