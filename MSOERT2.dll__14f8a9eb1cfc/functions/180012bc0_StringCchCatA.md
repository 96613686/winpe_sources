# StringCchCatA

- ea: `0x180012bc0`
- end: `0x180012c56`
- name: `StringCchCatA`
- size: `150`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001280`

## callees

- `0x180012bc0`

## string_xrefs

- `0x180012c04`: `\WindowsShell.Manifest`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v3; // r9
  STRSAFE_LPSTR v4; // rax
  HRESULT v5; // edx
  __int64 v6; // r10
  const char *v7; // rdx
  __int64 v8; // rax
  char *v9; // rcx
  __int64 v10; // r8
  char *v11; // rax

  v3 = 260;
  v4 = pszDest;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = "\\WindowsShell.Manifest";
    v8 = 2147483646;
    v9 = &pszDest[v6];
    v10 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v7 )
          break;
        *v9++ = *v7++;
        --v8;
        --v10;
      }
      while ( v10 );
    }
    v11 = v9 - 1;
    if ( v10 )
      v11 = v9;
    v5 = v10 == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180012bc0  mov     r8d, 104h
0x180012bc6  mov     r11, rcx
0x180012bc9  mov     r9d, r8d
0x180012bcc  mov     rax, rcx
0x180012bcf  cmp     byte ptr [rax], 0
0x180012bd2  jz      short loc_180012BDD
0x180012bd4  inc     rax
0x180012bd7  sub     r9, 1
0x180012bdb  jnz     short loc_180012BCF
0x180012bdd  mov     rax, r9
0x180012be0  mov     rcx, r8
0x180012be3  neg     rax
0x180012be6  mov     rax, r9
0x180012be9  sbb     edx, edx
0x180012beb  sub     rcx, r9
0x180012bee  not     edx
0x180012bf0  and     edx, 80070057h
0x180012bf6  neg     rax
0x180012bf9  sbb     r10, r10
0x180012bfc  and     r10, rcx
0x180012bff  test    r9, r9
0x180012c02  jz      short loc_180012C53
0x180012c04  lea     rdx, aWindowsshellMa; "\\WindowsShell.Manifest"
0x180012c0b  mov     eax, 7FFFFFFEh
0x180012c10  lea     rcx, [r10+r11]
0x180012c14  sub     r8, r10
0x180012c17  jz      short loc_180012C38
0x180012c19  test    rax, rax
0x180012c1c  jz      short loc_180012C38
0x180012c1e  mov     r9b, [rdx]
0x180012c21  test    r9b, r9b
0x180012c24  jz      short loc_180012C38
0x180012c26  mov     [rcx], r9b
0x180012c29  inc     rdx
0x180012c2c  inc     rcx
0x180012c2f  dec     rax
0x180012c32  sub     r8, 1
0x180012c36  jnz     short loc_180012C19
0x180012c38  test    r8, r8
0x180012c3b  lea     rax, [rcx-1]
0x180012c3f  cmovnz  rax, rcx
0x180012c43  neg     r8
0x180012c46  sbb     edx, edx
0x180012c48  not     edx
0x180012c4a  and     edx, 8007007Ah
0x180012c50  mov     byte ptr [rax], 0
0x180012c53  mov     eax, edx
0x180012c55  retn
```
