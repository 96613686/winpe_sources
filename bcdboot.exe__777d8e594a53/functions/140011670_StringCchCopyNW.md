# StringCchCopyNW

- ea: `0x140011670`
- end: `0x1400116ed`
- name: `StringCchCopyNW`
- size: `125`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002c14`
- `0x140011b18`
- `0x140012810`

## callees

- `0x140011670`

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
0x140011670  mov     [rsp+arg_0], rbx
0x140011675  xor     ebx, ebx
0x140011677  mov     r10, rdx
0x14001167a  mov     r11, rcx
0x14001167d  test    rdx, rdx
0x140011680  jz      short loc_1400116D8
0x140011682  cmp     rdx, 7FFFFFFFh
0x140011689  jbe     short loc_140011692
0x14001168b  mov     edx, 80070057h
0x140011690  jmp     short loc_1400116E2
0x140011692  cmp     r9, 7FFFFFFEh
0x140011699  ja      short loc_14001168B
0x14001169b  test    r9, r9
0x14001169e  jz      short loc_1400116BE
0x1400116a0  movzx   eax, word ptr [r8]
0x1400116a4  test    ax, ax
0x1400116a7  jz      short loc_1400116BE
0x1400116a9  mov     [r11], ax
0x1400116ad  add     r8, 2
0x1400116b1  add     r11, 2
0x1400116b5  dec     r9
0x1400116b8  sub     r10, 1
0x1400116bc  jnz     short loc_14001169B
0x1400116be  test    r10, r10
0x1400116c1  lea     rcx, [r11-2]
0x1400116c5  cmovnz  rcx, r11
0x1400116c9  neg     r10
0x1400116cc  sbb     edx, edx
0x1400116ce  not     edx
0x1400116d0  and     edx, 8007007Ah
0x1400116d6  jmp     short loc_1400116E2
0x1400116d8  mov     edx, 80070057h
0x1400116dd  test    r10, r10
0x1400116e0  jz      short loc_1400116E5
0x1400116e2  mov     [rcx], bx
0x1400116e5  mov     rbx, [rsp+arg_0]
0x1400116ea  mov     eax, edx
0x1400116ec  retn
```
