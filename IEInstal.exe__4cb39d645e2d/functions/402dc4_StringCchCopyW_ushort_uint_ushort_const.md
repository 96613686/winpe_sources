# StringCchCopyW(ushort *,uint,ushort const *)

- ea: `0x402dc4`
- end: `0x402df3`
- name: `?StringCchCopyW@@YGJPAGIPBG@Z`
- size: `47`
- prototype: `int __stdcall(size_t cchDest, unsigned int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x404214`
- `0x4044ae`
- `0x406c66`
- `0x40aec9`
- `0x40b08b`

## callees

- `0x402690`
- `0x402dc4`

## pseudocode

```c

```

## disassembly

```asm
0x402dc4  mov     edi, edi
0x402dc6  push    ebp; pszSrc
0x402dc7  mov     ebp, esp
0x402dc9  test    edx, edx
0x402dcb  jz      short loc_402DE1
0x402dcd  cmp     edx, 7FFFFFFFh
0x402dd3  ja      short loc_402DE1
0x402dd5  push    ecx; pcchNewDestLength
0x402dd6  push    [ebp+cchDest]; cchDest
0x402dd9  push    ecx; pszDest
0x402dda  call    StringCopyWorkerW
0x402ddf  jmp     short loc_402DEF
0x402de1  mov     eax, 80070057h
0x402de6  test    edx, edx
0x402de8  jz      short loc_402DEF
0x402dea  xor     edx, edx
0x402dec  mov     [ecx], dx
0x402def  pop     ebp
0x402df0  retn    4
```
