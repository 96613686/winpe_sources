# StringCopyWorkerW

- ea: `0x140006770`
- end: `0x1400067c1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037b0`
- `0x140006690`
- `0x140006b7c`

## callees

- `0x140006770`

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
0x140006770  xor     r10d, r10d
0x140006773  mov     r8, rdx
0x140006776  mov     eax, 7FFFFFFEh
0x14000677b  test    rdx, rdx
0x14000677e  jz      short loc_1400067A2
0x140006780  test    rax, rax
0x140006783  jz      short loc_1400067A2
0x140006785  movzx   edx, word ptr [r9]
0x140006789  test    dx, dx
0x14000678c  jz      short loc_1400067A2
0x14000678e  mov     [rcx], dx
0x140006791  add     r9, 2
0x140006795  add     rcx, 2
0x140006799  dec     rax
0x14000679c  sub     r8, 1
0x1400067a0  jnz     short loc_140006780
0x1400067a2  mov     rax, r8
0x1400067a5  lea     rdx, [rcx-2]
0x1400067a9  neg     rax
0x1400067ac  sbb     eax, eax
0x1400067ae  not     eax
0x1400067b0  and     eax, 8007007Ah
0x1400067b5  test    r8, r8
0x1400067b8  cmovnz  rdx, rcx
0x1400067bc  mov     [rdx], r10w
0x1400067c0  retn
```
