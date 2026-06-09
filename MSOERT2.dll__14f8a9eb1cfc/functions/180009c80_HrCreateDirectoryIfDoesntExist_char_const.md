# HrCreateDirectoryIfDoesntExist(char const *)

- ea: `0x180009c80`
- end: `0x180009cb6`
- name: `?HrCreateDirectoryIfDoesntExist@@YAJPEBD@Z`
- size: `54`
- prototype: `__int64 __fastcall(LPCSTR pszPath)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009c80`

## import_xrefs

- `SHELL32!SHCreateDirectoryExA` at `0x180009c8c`
- `SHELL32!SHCreateDirectoryExA` at `0x180009c8c`

## pseudocode

```c
int __fastcall HrCreateDirectoryIfDoesntExist(LPCSTR pszPath)
{
  int result; // eax

  result = SHCreateDirectoryExA(0, pszPath, 0);
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147024816 || result == -2147024713 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180009c80  sub     rsp, 28h
0x180009c84  mov     rdx, rcx; pszPath
0x180009c87  xor     r8d, r8d; psa
0x180009c8a  xor     ecx, ecx; hwnd
0x180009c8c  call    cs:__imp_SHCreateDirectoryExA
0x180009c92  test    eax, eax
0x180009c94  jle     short loc_180009C9E
0x180009c96  movzx   eax, ax
0x180009c99  or      eax, 80070000h
0x180009c9e  cmp     eax, 80070050h
0x180009ca3  jz      short loc_180009CAC
0x180009ca5  cmp     eax, 800700B7h
0x180009caa  jnz     short loc_180009CB1
0x180009cac  mov     eax, 1
0x180009cb1  add     rsp, 28h
0x180009cb5  retn
```
