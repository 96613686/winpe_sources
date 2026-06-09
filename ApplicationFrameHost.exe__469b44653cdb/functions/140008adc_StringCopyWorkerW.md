# StringCopyWorkerW

- ea: `0x140008adc`
- end: `0x140008b2d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005630`
- `0x1400089fc`
- `0x140008e8c`

## callees

- `0x140008adc`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x140008adc  xor     r10d, r10d
0x140008adf  mov     r8, rdx
0x140008ae2  mov     eax, 7FFFFFFEh
0x140008ae7  test    rdx, rdx
0x140008aea  jz      short loc_140008B0E
0x140008aec  test    rax, rax
0x140008aef  jz      short loc_140008B0E
0x140008af1  movzx   edx, word ptr [r9]
0x140008af5  test    dx, dx
0x140008af8  jz      short loc_140008B0E
0x140008afa  mov     [rcx], dx
0x140008afd  add     r9, 2
0x140008b01  add     rcx, 2
0x140008b05  dec     rax
0x140008b08  sub     r8, 1
0x140008b0c  jnz     short loc_140008AEC
0x140008b0e  mov     rax, r8
0x140008b11  lea     rdx, [rcx-2]
0x140008b15  neg     rax
0x140008b18  sbb     eax, eax
0x140008b1a  not     eax
0x140008b1c  and     eax, 8007007Ah
0x140008b21  test    r8, r8
0x140008b24  cmovnz  rdx, rcx
0x140008b28  mov     [rdx], r10w
0x140008b2c  retn
```
