# HrCreateDirectoryIfDoesntExistW(ushort const *)

- ea: `0x180009cc0`
- end: `0x180009cf6`
- name: `?HrCreateDirectoryIfDoesntExistW@@YAJPEBG@Z`
- size: `54`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b20`

## callees

- `0x180009cc0`

## import_xrefs

- `SHELL32!SHCreateDirectoryExW` at `0x180009ccc`
- `SHELL32!SHCreateDirectoryExW` at `0x180009ccc`

## pseudocode

```c
int __fastcall HrCreateDirectoryIfDoesntExistW(LPCWSTR pszPath)
{
  int result; // eax

  result = SHCreateDirectoryExW(0, pszPath, 0);
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147024816 || result == -2147024713 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180009cc0  sub     rsp, 28h
0x180009cc4  mov     rdx, rcx; pszPath
0x180009cc7  xor     r8d, r8d; psa
0x180009cca  xor     ecx, ecx; hwnd
0x180009ccc  call    cs:__imp_SHCreateDirectoryExW
0x180009cd2  test    eax, eax
0x180009cd4  jle     short loc_180009CDE
0x180009cd6  movzx   eax, ax
0x180009cd9  or      eax, 80070000h
0x180009cde  cmp     eax, 80070050h
0x180009ce3  jz      short loc_180009CEC
0x180009ce5  cmp     eax, 800700B7h
0x180009cea  jnz     short loc_180009CF1
0x180009cec  mov     eax, 1
0x180009cf1  add     rsp, 28h
0x180009cf5  retn
```
