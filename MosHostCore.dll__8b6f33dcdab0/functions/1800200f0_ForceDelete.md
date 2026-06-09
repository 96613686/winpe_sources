# ForceDelete

- ea: `0x1800200f0`
- end: `0x180020165`
- name: `ForceDelete`
- size: `117`
- prototype: `signed int __fastcall(unsigned int, const WCHAR *, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001ff1c`
- `0x1800200f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002012f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002012f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020125`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020125`

## pseudocode

```c
signed int __fastcall ForceDelete(unsigned int a1, const WCHAR *a2, _DWORD *a3)
{
  signed int result; // eax
  bool v7; // sf

  if ( !a2 || !a3 )
    return -2147024809;
  if ( a1 > 1 || (*a3 & 1) == 0 || SetFileAttributesW(a2, *a3 & 0xFFFFFFFE) )
    return Delete(a1, a2, (__int64)a3);
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    return Delete(a1, a2, (__int64)a3);
  return result;
}

```

## disassembly

```asm
0x1800200f0  push    rbx
0x1800200f2  push    rbp
0x1800200f3  push    rsi
0x1800200f4  push    rdi
0x1800200f5  sub     rsp, 28h
0x1800200f9  mov     rbp, r9
0x1800200fc  mov     rbx, r8
0x1800200ff  mov     rsi, rdx
0x180020102  mov     edi, ecx
0x180020104  test    rdx, rdx
0x180020107  jz      short loc_180020157
0x180020109  test    rbx, rbx
0x18002010c  jz      short loc_180020157
0x18002010e  test    ecx, ecx
0x180020110  jz      short loc_180020117
0x180020112  cmp     ecx, 1
0x180020115  jnz     short loc_180020145
0x180020117  mov     edx, [r8]
0x18002011a  test    dl, 1
0x18002011d  jz      short loc_180020145
0x18002011f  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180020122  mov     rcx, rsi; lpFileName
0x180020125  call    cs:__imp_SetFileAttributesW
0x18002012b  test    eax, eax
0x18002012d  jnz     short loc_180020145
0x18002012f  call    cs:__imp_GetLastError
0x180020135  test    eax, eax
0x180020137  jle     short loc_180020143
0x180020139  movzx   eax, ax
0x18002013c  or      eax, 80070000h
0x180020141  test    eax, eax
0x180020143  js      short loc_18002015C
0x180020145  mov     r9, rbp
0x180020148  mov     r8, rbx
0x18002014b  mov     rdx, rsi
0x18002014e  mov     ecx, edi
0x180020150  call    Delete
0x180020155  jmp     short loc_18002015C
0x180020157  mov     eax, 80070057h
0x18002015c  add     rsp, 28h
0x180020160  pop     rdi
0x180020161  pop     rsi
0x180020162  pop     rbp
0x180020163  pop     rbx
0x180020164  retn
```
