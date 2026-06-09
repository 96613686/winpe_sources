# StringCopyWorkerW

- ea: `0x140004024`
- end: `0x140004075`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003b70`

## callees

- `0x140004024`

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
0x140004024  xor     r10d, r10d
0x140004027  mov     r8, rdx
0x14000402a  mov     eax, 7FFFFFFEh
0x14000402f  test    rdx, rdx
0x140004032  jz      short loc_140004056
0x140004034  test    rax, rax
0x140004037  jz      short loc_140004056
0x140004039  movzx   edx, word ptr [r9]
0x14000403d  test    dx, dx
0x140004040  jz      short loc_140004056
0x140004042  mov     [rcx], dx
0x140004045  add     r9, 2
0x140004049  add     rcx, 2
0x14000404d  dec     rax
0x140004050  sub     r8, 1
0x140004054  jnz     short loc_140004034
0x140004056  mov     rax, r8
0x140004059  lea     rdx, [rcx-2]
0x14000405d  neg     rax
0x140004060  sbb     eax, eax
0x140004062  not     eax
0x140004064  and     eax, 8007007Ah
0x140004069  test    r8, r8
0x14000406c  cmovnz  rdx, rcx
0x140004070  mov     [rdx], r10w
0x140004074  retn
```
