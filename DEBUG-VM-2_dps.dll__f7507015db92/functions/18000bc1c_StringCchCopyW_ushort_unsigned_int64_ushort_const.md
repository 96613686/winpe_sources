# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000bc1c`
- end: `0x18000bc59`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008dd8`
- `0x18000b7ec`
- `0x18000c9cc`

## callees

- `0x18000bc1c`
- `0x18000bc60`

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
0x18000bc1c  sub     rsp, 38h
0x18000bc20  mov     rax, rdx
0x18000bc23  test    rdx, rdx
0x18000bc26  jz      short loc_18000BC43
0x18000bc28  cmp     rax, 7FFFFFFFh
0x18000bc2e  jbe     short loc_18000BC37
0x18000bc30  mov     edx, 80070057h; cchDest
0x18000bc35  jmp     short loc_18000BC4D
0x18000bc37  mov     r9, r8; pszSrc
0x18000bc3a  call    StringCopyWorkerW
0x18000bc3f  mov     edx, eax
0x18000bc41  jmp     short loc_18000BC52
0x18000bc43  mov     edx, 80070057h
0x18000bc48  test    rax, rax
0x18000bc4b  jz      short loc_18000BC52
0x18000bc4d  xor     eax, eax
0x18000bc4f  mov     [rcx], ax
0x18000bc52  mov     eax, edx
0x18000bc54  add     rsp, 38h
0x18000bc58  retn
```
