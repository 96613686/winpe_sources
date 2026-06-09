# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180016eb0`
- end: `0x180016eed`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd68`
- `0x180010760`
- `0x180013420`
- `0x180017544`
- `0x18001e270`
- `0x180020394`
- `0x180023954`
- `0x180027428`

## callees

- `0x180016eb0`
- `0x180016fd8`

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
0x180016eb0  sub     rsp, 38h
0x180016eb4  mov     rax, rdx
0x180016eb7  test    rdx, rdx
0x180016eba  jz      short loc_180016ED7
0x180016ebc  cmp     rax, 7FFFFFFFh
0x180016ec2  jbe     short loc_180016ECB
0x180016ec4  mov     edx, 80070057h; cchDest
0x180016ec9  jmp     short loc_180016EE1
0x180016ecb  mov     r9, r8; pszSrc
0x180016ece  call    StringCopyWorkerW
0x180016ed3  mov     edx, eax
0x180016ed5  jmp     short loc_180016EE6
0x180016ed7  mov     edx, 80070057h
0x180016edc  test    rax, rax
0x180016edf  jz      short loc_180016EE6
0x180016ee1  xor     eax, eax
0x180016ee3  mov     [rcx], ax
0x180016ee6  mov     eax, edx
0x180016ee8  add     rsp, 38h
0x180016eec  retn
```
