# StringCopyWorkerA

- ea: `0x18006d550`
- end: `0x18006d598`
- name: `StringCopyWorkerA`
- size: `72`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006d08c`

## callees

- `0x18006d550`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  HRESULT result; // eax
  STRSAFE_LPSTR v8; // rcx

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  result = -2147024774;
  if ( cchDest )
    result = 0;
  v8 = pszDest - 1;
  if ( cchDest )
    v8 = pszDest;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x18006d550  mov     r8, rcx
0x18006d553  mov     eax, 7FFFFFFEh
0x18006d558  test    rdx, rdx
0x18006d55b  jz      short loc_18006D57F
0x18006d55d  nop     dword ptr [rax]
0x18006d560  test    rax, rax
0x18006d563  jz      short loc_18006D57F
0x18006d565  movzx   ecx, byte ptr [r9]
0x18006d569  test    cl, cl
0x18006d56b  jz      short loc_18006D57F
0x18006d56d  mov     [r8], cl
0x18006d570  inc     r9
0x18006d573  inc     r8
0x18006d576  dec     rax
0x18006d579  sub     rdx, 1
0x18006d57d  jnz     short loc_18006D560
0x18006d57f  xor     ecx, ecx
0x18006d581  mov     eax, 8007007Ah
0x18006d586  test    rdx, rdx
0x18006d589  cmovnz  eax, ecx
0x18006d58c  lea     rcx, [r8-1]
0x18006d590  cmovnz  rcx, r8
0x18006d594  mov     byte ptr [rcx], 0
0x18006d597  retn
```
