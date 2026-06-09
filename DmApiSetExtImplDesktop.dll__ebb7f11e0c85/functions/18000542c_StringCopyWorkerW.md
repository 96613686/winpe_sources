# StringCopyWorkerW

- ea: `0x18000542c`
- end: `0x18000547d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052f8`
- `0x180005384`

## callees

- `0x18000542c`

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
0x18000542c  xor     r10d, r10d
0x18000542f  mov     r8, rdx
0x180005432  mov     eax, 7FFFFFFEh
0x180005437  test    rdx, rdx
0x18000543a  jz      short loc_18000545E
0x18000543c  test    rax, rax
0x18000543f  jz      short loc_18000545E
0x180005441  movzx   edx, word ptr [r9]
0x180005445  test    dx, dx
0x180005448  jz      short loc_18000545E
0x18000544a  mov     [rcx], dx
0x18000544d  add     r9, 2
0x180005451  add     rcx, 2
0x180005455  dec     rax
0x180005458  sub     r8, 1
0x18000545c  jnz     short loc_18000543C
0x18000545e  mov     rax, r8
0x180005461  lea     rdx, [rcx-2]
0x180005465  neg     rax
0x180005468  sbb     eax, eax
0x18000546a  not     eax
0x18000546c  and     eax, 8007007Ah
0x180005471  test    r8, r8
0x180005474  cmovnz  rdx, rcx
0x180005478  mov     [rdx], r10w
0x18000547c  retn
```
