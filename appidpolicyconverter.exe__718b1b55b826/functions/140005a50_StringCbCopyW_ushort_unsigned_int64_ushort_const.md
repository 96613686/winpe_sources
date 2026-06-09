# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005a50`
- end: `0x140005a90`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `64`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, size_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d94`
- `0x140005634`
- `0x140005be0`

## callees

- `0x140005a50`
- `0x140005a98`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 >> 1 )
  {
    if ( a2 >> 1 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2 >> 1, a3, (STRSAFE_PCNZWCH)a3, v5);
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
0x140005a50  sub     rsp, 38h
0x140005a54  mov     rax, rdx
0x140005a57  shr     rax, 1
0x140005a5a  jz      short loc_140005A7A
0x140005a5c  cmp     rax, 7FFFFFFFh
0x140005a62  jbe     short loc_140005A6B
0x140005a64  mov     edx, 80070057h
0x140005a69  jmp     short loc_140005A84
0x140005a6b  mov     r9, r8; pszSrc
0x140005a6e  mov     rdx, rax; cchDest
0x140005a71  call    StringCopyWorkerW
0x140005a76  mov     edx, eax
0x140005a78  jmp     short loc_140005A89
0x140005a7a  mov     edx, 80070057h
0x140005a7f  test    rax, rax
0x140005a82  jz      short loc_140005A89
0x140005a84  xor     eax, eax
0x140005a86  mov     [rcx], ax
0x140005a89  mov     eax, edx
0x140005a8b  add     rsp, 38h
0x140005a8f  retn
```
