# StringCopyWorkerW

- ea: `0x14000768c`
- end: `0x1400076dd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400074ec`
- `0x1400075e4`

## callees

- `0x14000768c`

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
0x14000768c  xor     r10d, r10d
0x14000768f  mov     r8, rdx
0x140007692  mov     eax, 7FFFFFFEh
0x140007697  test    rdx, rdx
0x14000769a  jz      short loc_1400076BE
0x14000769c  test    rax, rax
0x14000769f  jz      short loc_1400076BE
0x1400076a1  movzx   edx, word ptr [r9]
0x1400076a5  test    dx, dx
0x1400076a8  jz      short loc_1400076BE
0x1400076aa  mov     [rcx], dx
0x1400076ad  add     r9, 2
0x1400076b1  add     rcx, 2
0x1400076b5  dec     rax
0x1400076b8  sub     r8, 1
0x1400076bc  jnz     short loc_14000769C
0x1400076be  mov     rax, r8
0x1400076c1  lea     rdx, [rcx-2]
0x1400076c5  neg     rax
0x1400076c8  sbb     eax, eax
0x1400076ca  not     eax
0x1400076cc  and     eax, 8007007Ah
0x1400076d1  test    r8, r8
0x1400076d4  cmovnz  rdx, rcx
0x1400076d8  mov     [rdx], r10w
0x1400076dc  retn
```
