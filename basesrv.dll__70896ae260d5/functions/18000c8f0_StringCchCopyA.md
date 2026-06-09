# StringCchCopyA

- ea: `0x18000c8f0`
- end: `0x18000c932`
- name: `StringCchCopyA`
- size: `66`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800099ac`
- `0x180009a58`

## callees

- `0x18000c8f0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v3; // rdx
  signed __int64 v4; // r8
  char v5; // al
  STRSAFE_LPSTR v6; // rax

  v3 = 128;
  v4 = pszSrc - pszDest;
  do
  {
    if ( v3 == -2147483518 )
      break;
    v5 = pszDest[v4];
    if ( !v5 )
      break;
    *pszDest++ = v5;
    --v3;
  }
  while ( v3 );
  v6 = pszDest - 1;
  if ( v3 )
    v6 = pszDest;
  *v6 = 0;
  return v3 == 0 ? 0x8007007A : 0;
}

```

## disassembly

```asm
0x18000c8f0  mov     edx, 80h
0x18000c8f5  sub     r8, rcx
0x18000c8f8  lea     rax, [rdx+7FFFFF7Eh]
0x18000c8ff  test    rax, rax
0x18000c902  jz      short loc_18000C917
0x18000c904  mov     al, [r8+rcx]
0x18000c908  test    al, al
0x18000c90a  jz      short loc_18000C917
0x18000c90c  mov     [rcx], al
0x18000c90e  inc     rcx
0x18000c911  sub     rdx, 1
0x18000c915  jnz     short loc_18000C8F8
0x18000c917  test    rdx, rdx
0x18000c91a  lea     rax, [rcx-1]
0x18000c91e  cmovnz  rax, rcx
0x18000c922  neg     rdx
0x18000c925  mov     byte ptr [rax], 0
0x18000c928  sbb     eax, eax
0x18000c92a  not     eax
0x18000c92c  and     eax, 8007007Ah
0x18000c931  retn
```
