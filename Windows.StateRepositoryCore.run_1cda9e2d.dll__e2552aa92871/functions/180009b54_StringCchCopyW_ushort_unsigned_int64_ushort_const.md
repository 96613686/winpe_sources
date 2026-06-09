# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009b54`
- end: `0x180009b91`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046e0`
- `0x18000a07c`
- `0x18000dc7c`
- `0x18000e9a0`

## callees

- `0x180009b54`
- `0x180009c44`

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
0x180009b54  sub     rsp, 38h
0x180009b58  mov     rax, rdx
0x180009b5b  test    rdx, rdx
0x180009b5e  jz      short loc_180009B7B
0x180009b60  cmp     rax, 7FFFFFFFh
0x180009b66  jbe     short loc_180009B6F
0x180009b68  mov     edx, 80070057h; cchDest
0x180009b6d  jmp     short loc_180009B85
0x180009b6f  mov     r9, r8; pszSrc
0x180009b72  call    StringCopyWorkerW
0x180009b77  mov     edx, eax
0x180009b79  jmp     short loc_180009B8A
0x180009b7b  mov     edx, 80070057h
0x180009b80  test    rax, rax
0x180009b83  jz      short loc_180009B8A
0x180009b85  xor     eax, eax
0x180009b87  mov     [rcx], ax
0x180009b8a  mov     eax, edx
0x180009b8c  add     rsp, 38h
0x180009b90  retn
```
