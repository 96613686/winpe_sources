# StringCopyWorkerA

- ea: `0x18000cb54`
- end: `0x18000cb9d`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf68`
- `0x18000cb08`

## callees

- `0x18000cb54`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( ; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x18000cb54  mov     r8, rcx
0x18000cb57  test    rdx, rdx
0x18000cb5a  jz      short loc_18000CB7F
0x18000cb5c  mov     rax, [rsp+cchToCopy]
0x18000cb61  test    rax, rax
0x18000cb64  jz      short loc_18000CB7F
0x18000cb66  mov     cl, [r9]
0x18000cb69  test    cl, cl
0x18000cb6b  jz      short loc_18000CB7F
0x18000cb6d  mov     [r8], cl
0x18000cb70  inc     r9
0x18000cb73  inc     r8
0x18000cb76  dec     rax
0x18000cb79  sub     rdx, 1
0x18000cb7d  jnz     short loc_18000CB61
0x18000cb7f  mov     rax, rdx
0x18000cb82  lea     rcx, [r8-1]
0x18000cb86  neg     rax
0x18000cb89  sbb     eax, eax
0x18000cb8b  not     eax
0x18000cb8d  and     eax, 8007007Ah
0x18000cb92  test    rdx, rdx
0x18000cb95  cmovnz  rcx, r8
0x18000cb99  mov     byte ptr [rcx], 0
0x18000cb9c  retn
```
