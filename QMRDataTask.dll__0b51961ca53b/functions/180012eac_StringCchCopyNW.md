# StringCchCopyNW

- ea: `0x180012eac`
- end: `0x180012f29`
- name: `StringCchCopyNW`
- size: `125`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800128a0`
- `0x18001331c`

## callees

- `0x180012eac`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)
{
  size_t v4; // r10
  STRSAFE_LPWSTR v5; // r11
  HRESULT v6; // edx

  v4 = cchDest;
  v5 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
  {
    v6 = -2147024809;
  }
  else
  {
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *v5++ = *pszSrc++;
      --cchToCopy;
      --v4;
    }
    while ( v4 );
    pszDest = v5 - 1;
    if ( v4 )
      pszDest = v5;
    v6 = v4 == 0 ? 0x8007007A : 0;
  }
  *pszDest = 0;
  return v6;
}

```

## disassembly

```asm
0x180012eac  mov     [rsp+arg_0], rbx
0x180012eb1  xor     ebx, ebx
0x180012eb3  mov     r10, rdx
0x180012eb6  mov     r11, rcx
0x180012eb9  test    rdx, rdx
0x180012ebc  jz      short loc_180012F14
0x180012ebe  cmp     rdx, 7FFFFFFFh
0x180012ec5  jbe     short loc_180012ECE
0x180012ec7  mov     edx, 80070057h
0x180012ecc  jmp     short loc_180012F1E
0x180012ece  cmp     r9, 7FFFFFFEh
0x180012ed5  ja      short loc_180012EC7
0x180012ed7  test    r9, r9
0x180012eda  jz      short loc_180012EFA
0x180012edc  movzx   eax, word ptr [r8]
0x180012ee0  test    ax, ax
0x180012ee3  jz      short loc_180012EFA
0x180012ee5  mov     [r11], ax
0x180012ee9  add     r8, 2
0x180012eed  add     r11, 2
0x180012ef1  dec     r9
0x180012ef4  sub     r10, 1
0x180012ef8  jnz     short loc_180012ED7
0x180012efa  test    r10, r10
0x180012efd  lea     rcx, [r11-2]
0x180012f01  cmovnz  rcx, r11
0x180012f05  neg     r10
0x180012f08  sbb     edx, edx
0x180012f0a  not     edx
0x180012f0c  and     edx, 8007007Ah
0x180012f12  jmp     short loc_180012F1E
0x180012f14  mov     edx, 80070057h
0x180012f19  test    r10, r10
0x180012f1c  jz      short loc_180012F21
0x180012f1e  mov     [rcx], bx
0x180012f21  mov     rbx, [rsp+arg_0]
0x180012f26  mov     eax, edx
0x180012f28  retn
```
