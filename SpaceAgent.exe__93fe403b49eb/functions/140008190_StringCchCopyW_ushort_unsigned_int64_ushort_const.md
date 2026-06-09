# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140008190`
- end: `0x1400081cd`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140004f00`
- `0x140008ba4`
- `0x14000e3f8`
- `0x140014e74`
- `0x140014f14`
- `0x140015604`
- `0x140016eac`
- `0x140016f48`
- `0x140017380`
- `0x140018750`
- `0x140018fbc`
- `0x1400196d8`
- `0x14001c3b0`
- `0x14001d140`
- `0x14001d1e4`
- `0x14001db30`
- `0x14001e464`

## callees

- `0x140008190`
- `0x140008238`

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
0x140008190  sub     rsp, 38h
0x140008194  mov     rax, rdx
0x140008197  test    rdx, rdx
0x14000819a  jz      short loc_1400081B7
0x14000819c  cmp     rax, 7FFFFFFFh
0x1400081a2  jbe     short loc_1400081AB
0x1400081a4  mov     edx, 80070057h; cchDest
0x1400081a9  jmp     short loc_1400081C1
0x1400081ab  mov     r9, r8; pszSrc
0x1400081ae  call    StringCopyWorkerW
0x1400081b3  mov     edx, eax
0x1400081b5  jmp     short loc_1400081C6
0x1400081b7  mov     edx, 80070057h
0x1400081bc  test    rax, rax
0x1400081bf  jz      short loc_1400081C6
0x1400081c1  xor     eax, eax
0x1400081c3  mov     [rcx], ax
0x1400081c6  mov     eax, edx
0x1400081c8  add     rsp, 38h
0x1400081cc  retn
```
