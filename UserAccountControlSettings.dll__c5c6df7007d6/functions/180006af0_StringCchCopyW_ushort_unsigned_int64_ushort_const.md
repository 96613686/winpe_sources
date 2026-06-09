# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006af0`
- end: `0x180006b1f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180004fb0`
- `0x180006ce0`
- `0x18000995c`
- `0x180009b0c`
- `0x18000a83c`

## callees

- `0x180006af0`
- `0x180006bc4`
- `0x180006c70`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006af0  sub     rsp, 38h
0x180006af4  call    StringValidateDestW
0x180006af9  mov     r9d, eax
0x180006afc  test    eax, eax
0x180006afe  js      short loc_180006B0D
0x180006b00  mov     r9, r8; pszSrc
0x180006b03  call    StringCopyWorkerW
0x180006b08  mov     r9d, eax
0x180006b0b  jmp     short loc_180006B17
0x180006b0d  test    rdx, rdx
0x180006b10  jz      short loc_180006B17
0x180006b12  xor     eax, eax
0x180006b14  mov     [rcx], ax
0x180006b17  mov     eax, r9d
0x180006b1a  add     rsp, 38h
0x180006b1e  retn
```
