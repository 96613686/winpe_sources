# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ff80`
- end: `0x18000ffbe`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180008904`
- `0x18000a718`
- `0x18000a864`
- `0x18000fa24`
- `0x18000fb24`
- `0x180010b5c`
- `0x180017e2c`
- `0x18001895c`
- `0x180019a90`
- `0x18001a7a0`
- `0x18001b744`

## callees

- `0x18000ff80`
- `0x18000ffc4`

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
0x18000ff80  sub     rsp, 38h
0x18000ff84  mov     rax, rdx
0x18000ff87  test    rdx, rdx
0x18000ff8a  jz      short loc_18000FFA7
0x18000ff8c  cmp     rax, 7FFFFFFFh
0x18000ff92  jbe     short loc_18000FF9B
0x18000ff94  mov     edx, 80070057h; cchDest
0x18000ff99  jmp     short loc_18000FFB1
0x18000ff9b  mov     r9, r8; pszSrc
0x18000ff9e  call    StringCopyWorkerW
0x18000ffa3  mov     edx, eax
0x18000ffa5  jmp     short loc_18000FFB6
0x18000ffa7  mov     edx, 80070057h
0x18000ffac  test    rax, rax
0x18000ffaf  jz      short loc_18000FFB6
0x18000ffb1  xor     eax, eax
0x18000ffb3  mov     [rcx], ax
0x18000ffb6  mov     eax, edx
0x18000ffb8  add     rsp, 38h
0x18000ffbc  retn
```
