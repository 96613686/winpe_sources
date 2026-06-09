# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x140005754`
- end: `0x140005791`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `61`
- prototype: `__int64 __fastcall(wchar_t *, size_t, wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ecc`
- `0x140005988`
- `0x140017ec8`
- `0x140018090`

## callees

- `0x140005754`
- `0x140005858`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, size_t a2, wchar_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, (size_t *)a3, a3, v5);
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
0x140005754  sub     rsp, 38h
0x140005758  mov     rax, rdx
0x14000575b  test    rdx, rdx
0x14000575e  jz      short loc_14000577B
0x140005760  cmp     rax, 7FFFFFFFh
0x140005766  jbe     short loc_14000576F
0x140005768  mov     edx, 80070057h; cchDest
0x14000576d  jmp     short loc_140005785
0x14000576f  mov     r9, r8; pszSrc
0x140005772  call    StringCopyWorkerW
0x140005777  mov     edx, eax
0x140005779  jmp     short loc_14000578A
0x14000577b  mov     edx, 80070057h
0x140005780  test    rax, rax
0x140005783  jz      short loc_14000578A
0x140005785  xor     eax, eax
0x140005787  mov     [rcx], ax
0x14000578a  mov     eax, edx
0x14000578c  add     rsp, 38h
0x140005790  retn
```
