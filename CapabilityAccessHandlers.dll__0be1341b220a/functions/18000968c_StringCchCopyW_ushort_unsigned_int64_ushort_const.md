# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000968c`
- end: `0x1800096c9`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fbc`
- `0x1800075ac`
- `0x1800098bc`

## callees

- `0x18000968c`
- `0x180009734`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000968c  sub     rsp, 38h
0x180009690  mov     rax, rdx
0x180009693  test    rdx, rdx
0x180009696  jz      short loc_1800096B3
0x180009698  cmp     rax, 7FFFFFFFh
0x18000969e  jbe     short loc_1800096A7
0x1800096a0  mov     edx, 80070057h; cchDest
0x1800096a5  jmp     short loc_1800096BD
0x1800096a7  mov     r9, r8; pszSrc
0x1800096aa  call    StringCopyWorkerW
0x1800096af  mov     edx, eax
0x1800096b1  jmp     short loc_1800096C2
0x1800096b3  mov     edx, 80070057h
0x1800096b8  test    rax, rax
0x1800096bb  jz      short loc_1800096C2
0x1800096bd  xor     eax, eax
0x1800096bf  mov     [rcx], ax
0x1800096c2  mov     eax, edx
0x1800096c4  add     rsp, 38h
0x1800096c8  retn
```
