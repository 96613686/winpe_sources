# StringCopyWorkerW

- ea: `0x18000aee0`
- end: `0x18000af31`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009848`
- `0x18000adec`
- `0x18000aff0`

## callees

- `0x18000aee0`

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
0x18000aee0  xor     r10d, r10d
0x18000aee3  mov     r8, rdx
0x18000aee6  mov     eax, 7FFFFFFEh
0x18000aeeb  test    rdx, rdx
0x18000aeee  jz      short loc_18000AF12
0x18000aef0  test    rax, rax
0x18000aef3  jz      short loc_18000AF12
0x18000aef5  movzx   edx, word ptr [r9]
0x18000aef9  test    dx, dx
0x18000aefc  jz      short loc_18000AF12
0x18000aefe  mov     [rcx], dx
0x18000af01  add     r9, 2
0x18000af05  add     rcx, 2
0x18000af09  dec     rax
0x18000af0c  sub     r8, 1
0x18000af10  jnz     short loc_18000AEF0
0x18000af12  mov     rax, r8
0x18000af15  lea     rdx, [rcx-2]
0x18000af19  neg     rax
0x18000af1c  sbb     eax, eax
0x18000af1e  not     eax
0x18000af20  and     eax, 8007007Ah
0x18000af25  test    r8, r8
0x18000af28  cmovnz  rdx, rcx
0x18000af2c  mov     [rdx], r10w
0x18000af30  retn
```
