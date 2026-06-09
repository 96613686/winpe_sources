# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800059a8`
- end: `0x1800059e6`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030d8`
- `0x180003378`
- `0x180005b78`
- `0x18001bc30`

## callees

- `0x1800059a8`
- `0x180005a50`

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
0x1800059a8  sub     rsp, 38h
0x1800059ac  mov     rax, rdx
0x1800059af  test    rdx, rdx
0x1800059b2  jz      short loc_1800059CF
0x1800059b4  cmp     rax, 7FFFFFFFh
0x1800059ba  jbe     short loc_1800059C3
0x1800059bc  mov     edx, 80070057h; cchDest
0x1800059c1  jmp     short loc_1800059D9
0x1800059c3  mov     r9, r8; pszSrc
0x1800059c6  call    StringCopyWorkerW
0x1800059cb  mov     edx, eax
0x1800059cd  jmp     short loc_1800059DE
0x1800059cf  mov     edx, 80070057h
0x1800059d4  test    rax, rax
0x1800059d7  jz      short loc_1800059DE
0x1800059d9  xor     eax, eax
0x1800059db  mov     [rcx], ax
0x1800059de  mov     eax, edx
0x1800059e0  add     rsp, 38h
0x1800059e4  retn
```
