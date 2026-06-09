# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18001c940`
- end: `0x18001c95f`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `31`
- prototype: `HRESULT __fastcall(unsigned __int16 *, __int64, size_t *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cb04`
- `0x18001f5e4`
- `0x1800208fc`
- `0x1800212f0`
- `0x1800216c0`
- `0x180021b10`
- `0x180022ab4`

## callees

- `0x18001c9bc`

## pseudocode

```c
HRESULT __fastcall StringCbCopyW(unsigned __int16 *a1, __int64 a2, size_t *a3)
{
  return StringCopyWorkerW_0(a1, 0x104u, a3, (STRSAFE_PCNZWCH)a3, 0x7FFFFFFEu);
}

```

## disassembly

```asm
0x18001c940  sub     rsp, 38h
0x18001c944  mov     r9, r8; pszSrc
0x18001c947  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18001c950  mov     edx, 104h; cchDest
0x18001c955  call    StringCopyWorkerW_0
0x18001c95a  add     rsp, 38h
0x18001c95e  retn
```
