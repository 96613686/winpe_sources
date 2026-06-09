# StringCopyWorkerW

- ea: `0x180002308`
- end: `0x180002359`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e40`
- `0x180002268`
- `0x1800022bc`
- `0x180008138`

## callees

- `0x180002308`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180002308  xor     r10d, r10d
0x18000230b  mov     r8, rdx
0x18000230e  test    rdx, rdx
0x180002311  jz      short loc_18000233A
0x180002313  mov     rax, [rsp+cchToCopy]
0x180002318  test    rax, rax
0x18000231b  jz      short loc_18000233A
0x18000231d  movzx   edx, word ptr [r9]
0x180002321  test    dx, dx
0x180002324  jz      short loc_18000233A
0x180002326  mov     [rcx], dx
0x180002329  add     r9, 2
0x18000232d  add     rcx, 2
0x180002331  dec     rax
0x180002334  sub     r8, 1
0x180002338  jnz     short loc_180002318
0x18000233a  mov     rax, r8
0x18000233d  lea     rdx, [rcx-2]
0x180002341  neg     rax
0x180002344  sbb     eax, eax
0x180002346  not     eax
0x180002348  and     eax, 8007007Ah
0x18000234d  test    r8, r8
0x180002350  cmovnz  rdx, rcx
0x180002354  mov     [rdx], r10w
0x180002358  retn
```
