# StringCopyWorkerW_0

- ea: `0x180003654`
- end: `0x1800036ca`
- name: `StringCopyWorkerW_0`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003180`
- `0x180003218`
- `0x1800033a8`

## callees

- `0x180003654`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  for ( i = 0; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
    ++i;
  }
  v9 = i - 1;
  if ( cchDest )
    v9 = i;
  v10 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v10 = pszDest;
  *v10 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v9;
  return result;
}

```

## disassembly

```asm
0x180003654  mov     [rsp+arg_0], rbx
0x180003659  mov     r10, rdx
0x18000365c  xor     ebx, ebx
0x18000365e  mov     r11, r8
0x180003661  mov     edx, ebx
0x180003663  test    r10, r10
0x180003666  jz      short loc_180003694
0x180003668  mov     rax, [rsp+arg_20]
0x18000366d  test    rax, rax
0x180003670  jz      short loc_180003694
0x180003672  movzx   r8d, word ptr [r9]
0x180003676  test    r8w, r8w
0x18000367a  jz      short loc_180003694
0x18000367c  mov     [rcx], r8w
0x180003680  add     r9, 2
0x180003684  add     rcx, 2
0x180003688  dec     rax
0x18000368b  inc     rdx
0x18000368e  sub     r10, 1
0x180003692  jnz     short loc_18000366D
0x180003694  test    r10, r10
0x180003697  lea     r8, [rdx-1]
0x18000369b  mov     rax, r10
0x18000369e  cmovnz  r8, rdx
0x1800036a2  neg     rax
0x1800036a5  lea     rdx, [rcx-2]
0x1800036a9  sbb     eax, eax
0x1800036ab  not     eax
0x1800036ad  and     eax, 8007007Ah
0x1800036b2  test    r10, r10
0x1800036b5  cmovnz  rdx, rcx
0x1800036b9  mov     [rdx], bx
0x1800036bc  test    r11, r11
0x1800036bf  jz      short loc_1800036C4
0x1800036c1  mov     [r11], r8
0x1800036c4  mov     rbx, [rsp+arg_0]
0x1800036c9  retn
```
