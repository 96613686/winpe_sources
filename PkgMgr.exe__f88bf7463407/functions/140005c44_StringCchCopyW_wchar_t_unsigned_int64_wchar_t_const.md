# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x140005c44`
- end: `0x140005c73`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `47`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140004190`
- `0x140005f40`
- `0x1400098b8`
- `0x140011884`
- `0x1400244a0`

## callees

- `0x140005c44`
- `0x140005d70`
- `0x140005e1c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, size_t a2, const wchar_t *a3)
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
0x140005c44  sub     rsp, 38h
0x140005c48  call    StringValidateDestW
0x140005c4d  mov     r9d, eax
0x140005c50  test    eax, eax
0x140005c52  js      short loc_140005C61
0x140005c54  mov     r9, r8; pszSrc
0x140005c57  call    StringCopyWorkerW
0x140005c5c  mov     r9d, eax
0x140005c5f  jmp     short loc_140005C6B
0x140005c61  test    rdx, rdx
0x140005c64  jz      short loc_140005C6B
0x140005c66  xor     eax, eax
0x140005c68  mov     [rcx], ax
0x140005c6b  mov     eax, r9d
0x140005c6e  add     rsp, 38h
0x140005c72  retn
```
