# StringCchCopyA

- ea: `0x18000ccd0`
- end: `0x18000cd19`
- name: `StringCchCopyA`
- size: `73`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c98`
- `0x180009d44`

## callees

- `0x18000ccd0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  STRSAFE_LPSTR v6; // rcx
  HRESULT result; // eax

  v4 = 2147483646;
  v5 = 128;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x18000ccd0  mov     r9, rcx
0x18000ccd3  mov     eax, 7FFFFFFEh
0x18000ccd8  mov     edx, 80h
0x18000ccdd  test    rax, rax
0x18000cce0  jz      short loc_18000CCFB
0x18000cce2  mov     cl, [r8]
0x18000cce5  test    cl, cl
0x18000cce7  jz      short loc_18000CCFB
0x18000cce9  mov     [r9], cl
0x18000ccec  inc     r8
0x18000ccef  inc     r9
0x18000ccf2  dec     rax
0x18000ccf5  sub     rdx, 1
0x18000ccf9  jnz     short loc_18000CCDD
0x18000ccfb  mov     rax, rdx
0x18000ccfe  lea     rcx, [r9-1]
0x18000cd02  neg     rax
0x18000cd05  sbb     eax, eax
0x18000cd07  not     eax
0x18000cd09  and     eax, 8007007Ah
0x18000cd0e  test    rdx, rdx
0x18000cd11  cmovnz  rcx, r9
0x18000cd15  mov     byte ptr [rcx], 0
0x18000cd18  retn
```
