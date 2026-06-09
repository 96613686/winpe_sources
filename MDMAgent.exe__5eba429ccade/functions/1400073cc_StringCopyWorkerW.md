# StringCopyWorkerW

- ea: `0x1400073cc`
- end: `0x14000741d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140007230`
- `0x140007324`

## callees

- `0x1400073cc`

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
0x1400073cc  xor     r10d, r10d
0x1400073cf  mov     r8, rdx
0x1400073d2  mov     eax, 7FFFFFFEh
0x1400073d7  test    rdx, rdx
0x1400073da  jz      short loc_1400073FE
0x1400073dc  test    rax, rax
0x1400073df  jz      short loc_1400073FE
0x1400073e1  movzx   edx, word ptr [r9]
0x1400073e5  test    dx, dx
0x1400073e8  jz      short loc_1400073FE
0x1400073ea  mov     [rcx], dx
0x1400073ed  add     r9, 2
0x1400073f1  add     rcx, 2
0x1400073f5  dec     rax
0x1400073f8  sub     r8, 1
0x1400073fc  jnz     short loc_1400073DC
0x1400073fe  mov     rax, r8
0x140007401  lea     rdx, [rcx-2]
0x140007405  neg     rax
0x140007408  sbb     eax, eax
0x14000740a  not     eax
0x14000740c  and     eax, 8007007Ah
0x140007411  test    r8, r8
0x140007414  cmovnz  rdx, rcx
0x140007418  mov     [rdx], r10w
0x14000741c  retn
```
