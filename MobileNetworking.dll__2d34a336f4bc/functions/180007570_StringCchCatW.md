# StringCchCatW

- ea: `0x180007570`
- end: `0x1800075d4`
- name: `StringCchCatW`
- size: `100`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005910`
- `0x180006000`
- `0x180006ee0`
- `0x1800073c0`
- `0x18000b030`

## callees

- `0x180007570`
- `0x1800075e0`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v4; // r9
  STRSAFE_LPWSTR v5; // rax
  size_t v6; // rax
  HRESULT v7; // ecx
  size_t v9; // [rsp+20h] [rbp-18h]

  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v4 = cchDest;
  v5 = pszDest;
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
    {
      v6 = 0;
      v7 = -2147024809;
      goto LABEL_7;
    }
  }
  v6 = cchDest - v4;
  v7 = 0;
LABEL_7:
  if ( v7 >= 0 )
    return StringCopyWorkerW_0(&pszDest[v6], cchDest - v6, (size_t *)pszSrc, pszSrc, v9);
  return v7;
}

```

## disassembly

```asm
0x180007570  sub     rsp, 38h
0x180007574  lea     rax, [rdx-1]
0x180007578  mov     r10, rcx
0x18000757b  cmp     rax, 7FFFFFFEh
0x180007581  ja      short loc_1800075CB
0x180007583  mov     r9, rdx
0x180007586  mov     rax, rcx
0x180007589  nop     dword ptr [rax+00000000h]
0x180007590  cmp     word ptr [rax], 0
0x180007594  jz      short loc_1800075AB
0x180007596  add     rax, 2
0x18000759a  sub     r9, 1
0x18000759e  jnz     short loc_180007590
0x1800075a0  xor     ecx, ecx
0x1800075a2  mov     eax, ecx
0x1800075a4  mov     ecx, 80070057h
0x1800075a9  jmp     short loc_1800075B3
0x1800075ab  mov     rax, rdx
0x1800075ae  sub     rax, r9
0x1800075b1  xor     ecx, ecx
0x1800075b3  test    ecx, ecx
0x1800075b5  js      short loc_1800075D0
0x1800075b7  sub     rdx, rax; cchDest
0x1800075ba  lea     rcx, [r10+rax*2]; pszDest
0x1800075be  mov     r9, r8; pszSrc
0x1800075c1  call    StringCopyWorkerW_0
0x1800075c6  add     rsp, 38h
0x1800075ca  retn
0x1800075cb  mov     ecx, 80070057h
0x1800075d0  mov     eax, ecx
0x1800075d2  jmp     short loc_1800075C6
```
