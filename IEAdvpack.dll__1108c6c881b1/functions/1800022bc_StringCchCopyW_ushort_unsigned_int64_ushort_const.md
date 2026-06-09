# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800022bc`
- end: `0x180002302`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `62`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e40`
- `0x180002450`
- `0x18000279c`
- `0x180002ad4`
- `0x180002d50`
- `0x1800042f8`
- `0x180004754`
- `0x180004880`
- `0x18000521c`
- `0x1800053f0`
- `0x180005a8c`
- `0x18000616c`
- `0x18000631c`
- `0x1800063c4`
- `0x1800067dc`
- `0x1800071c0`
- `0x180007454`
- `0x1800076a8`
- `0x1800079c0`
- `0x180008524`
- `0x1800088c4`
- `0x180008a6c`
- `0x180008cf0`
- `0x180009c14`
- `0x18000a61c`
- `0x18000a918`
- `0x18000ae68`
- `0x18000b240`
- `0x18000b710`
- `0x18000b8f0`
- `0x18000c3b8`
- `0x18000c760`
- `0x18000c99c`
- `0x18000cc80`
- `0x18000ced8`
- `0x18000d184`
- `0x18000d490`
- `0x18000e060`
- `0x18000ec98`
- `0x18000ef90`
- `0x18000f7b0`
- `0x180010050`
- `0x1800104c0`
- `0x1800108a0`
- `0x180010d50`
- `0x1800115b0`
- `0x180011940`
- `0x1800126c0`
- `0x1800127bc`
- `0x180013280`

## callees

- `0x1800022bc`
- `0x180002308`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, 0x7FFFFFFEu);
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
0x1800022bc  sub     rsp, 38h
0x1800022c0  mov     rax, rdx
0x1800022c3  test    rdx, rdx
0x1800022c6  jz      short loc_1800022EC
0x1800022c8  cmp     rax, 7FFFFFFFh
0x1800022ce  jbe     short loc_1800022D7
0x1800022d0  mov     edx, 80070057h; cchDest
0x1800022d5  jmp     short loc_1800022F6
0x1800022d7  mov     r9, r8; pszSrc
0x1800022da  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800022e3  call    StringCopyWorkerW
0x1800022e8  mov     edx, eax
0x1800022ea  jmp     short loc_1800022FB
0x1800022ec  mov     edx, 80070057h
0x1800022f1  test    rax, rax
0x1800022f4  jz      short loc_1800022FB
0x1800022f6  xor     eax, eax
0x1800022f8  mov     [rcx], ax
0x1800022fb  mov     eax, edx
0x1800022fd  add     rsp, 38h
0x180002301  retn
```
