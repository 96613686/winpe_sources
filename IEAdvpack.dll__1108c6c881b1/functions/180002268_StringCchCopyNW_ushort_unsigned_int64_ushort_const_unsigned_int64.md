# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180002268`
- end: `0x1800022b3`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008644`
- `0x180015c74`

## callees

- `0x180002268`
- `0x180002308`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, size_t a2, size_t *a3, size_t cchToCopy)
{
  unsigned int v4; // edx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
    {
      v4 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180002268  sub     rsp, 38h
0x18000226c  mov     rax, rdx
0x18000226f  test    rdx, rdx
0x180002272  jz      short loc_18000229D
0x180002274  cmp     rax, 7FFFFFFFh
0x18000227a  jbe     short loc_180002283
0x18000227c  mov     edx, 80070057h; cchDest
0x180002281  jmp     short loc_1800022A7
0x180002283  cmp     r9, 7FFFFFFEh
0x18000228a  ja      short loc_18000227C
0x18000228c  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180002291  mov     r9, r8; pszSrc
0x180002294  call    StringCopyWorkerW
0x180002299  mov     edx, eax
0x18000229b  jmp     short loc_1800022AC
0x18000229d  mov     edx, 80070057h
0x1800022a2  test    rax, rax
0x1800022a5  jz      short loc_1800022AC
0x1800022a7  xor     eax, eax
0x1800022a9  mov     [rcx], ax
0x1800022ac  mov     eax, edx
0x1800022ae  add     rsp, 38h
0x1800022b2  retn
```
