# StringCbCopyA

- ea: `0x180023280`
- end: `0x180023296`
- name: `StringCbCopyA`
- size: `22`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f80`

## callees

- `0x1800141e0`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  size_t v4; // [rsp+20h] [rbp-18h]

  return StringCopyWorkerA(pszDest, 0x81u, (size_t *)pszSrc, pszSrc, v4);
}

```

## disassembly

```asm
0x180023280  sub     rsp, 38h
0x180023284  mov     r9, r8; pszSrc
0x180023287  mov     edx, 81h; cchDest
0x18002328c  call    StringCopyWorkerA
0x180023291  add     rsp, 38h
0x180023295  retn
```
