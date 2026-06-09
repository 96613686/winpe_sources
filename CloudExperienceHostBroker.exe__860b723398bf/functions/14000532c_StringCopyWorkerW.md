# StringCopyWorkerW

- ea: `0x14000532c`
- end: `0x14000537d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000361c`
- `0x14000524c`
- `0x140005440`

## callees

- `0x14000532c`

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
0x14000532c  xor     r10d, r10d
0x14000532f  mov     r8, rdx
0x140005332  mov     eax, 7FFFFFFEh
0x140005337  test    rdx, rdx
0x14000533a  jz      short loc_14000535E
0x14000533c  test    rax, rax
0x14000533f  jz      short loc_14000535E
0x140005341  movzx   edx, word ptr [r9]
0x140005345  test    dx, dx
0x140005348  jz      short loc_14000535E
0x14000534a  mov     [rcx], dx
0x14000534d  add     r9, 2
0x140005351  add     rcx, 2
0x140005355  dec     rax
0x140005358  sub     r8, 1
0x14000535c  jnz     short loc_14000533C
0x14000535e  mov     rax, r8
0x140005361  lea     rdx, [rcx-2]
0x140005365  neg     rax
0x140005368  sbb     eax, eax
0x14000536a  not     eax
0x14000536c  and     eax, 8007007Ah
0x140005371  test    r8, r8
0x140005374  cmovnz  rdx, rcx
0x140005378  mov     [rdx], r10w
0x14000537c  retn
```
