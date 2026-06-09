# StringCchCopyW

- ea: `0x180013fa8`
- end: `0x180014013`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014104`

## callees

- `0x180013fa8`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180013fa8  xor     r10d, r10d
0x180013fab  mov     r9, rcx
0x180013fae  test    rdx, rdx
0x180013fb1  jz      short loc_180014004
0x180013fb3  cmp     rdx, 7FFFFFFFh
0x180013fba  jbe     short loc_180013FC3
0x180013fbc  mov     eax, 80070057h
0x180013fc1  jmp     short loc_18001400E
0x180013fc3  mov     eax, 7FFFFFFEh
0x180013fc8  test    rax, rax
0x180013fcb  jz      short loc_180013FEB
0x180013fcd  movzx   ecx, word ptr [r8]
0x180013fd1  test    cx, cx
0x180013fd4  jz      short loc_180013FEB
0x180013fd6  mov     [r9], cx
0x180013fda  add     r8, 2
0x180013fde  add     r9, 2
0x180013fe2  dec     rax
0x180013fe5  sub     rdx, 1
0x180013fe9  jnz     short loc_180013FC8
0x180013feb  test    rdx, rdx
0x180013fee  lea     rcx, [r9-2]
0x180013ff2  cmovnz  rcx, r9
0x180013ff6  neg     rdx
0x180013ff9  sbb     eax, eax
0x180013ffb  not     eax
0x180013ffd  and     eax, 8007007Ah
0x180014002  jmp     short loc_18001400E
0x180014004  mov     eax, 80070057h
0x180014009  test    rdx, rdx
0x18001400c  jz      short locret_180014012
0x18001400e  mov     [rcx], r10w
0x180014012  retn
```
