# StringCchCopyW

- ea: `0x18001ca98`
- end: `0x18001cb03`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001446c`
- `0x180014f60`
- `0x180015324`
- `0x180015850`
- `0x1800160c8`
- `0x180017954`
- `0x18001c158`

## callees

- `0x18001ca98`

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
0x18001ca98  xor     r10d, r10d
0x18001ca9b  mov     r9, rcx
0x18001ca9e  test    rdx, rdx
0x18001caa1  jz      short loc_18001CAF4
0x18001caa3  cmp     rdx, 7FFFFFFFh
0x18001caaa  jbe     short loc_18001CAB3
0x18001caac  mov     eax, 80070057h
0x18001cab1  jmp     short loc_18001CAFE
0x18001cab3  mov     eax, 7FFFFFFEh
0x18001cab8  test    rax, rax
0x18001cabb  jz      short loc_18001CADB
0x18001cabd  movzx   ecx, word ptr [r8]
0x18001cac1  test    cx, cx
0x18001cac4  jz      short loc_18001CADB
0x18001cac6  mov     [r9], cx
0x18001caca  add     r8, 2
0x18001cace  add     r9, 2
0x18001cad2  dec     rax
0x18001cad5  sub     rdx, 1
0x18001cad9  jnz     short loc_18001CAB8
0x18001cadb  test    rdx, rdx
0x18001cade  lea     rcx, [r9-2]
0x18001cae2  cmovnz  rcx, r9
0x18001cae6  neg     rdx
0x18001cae9  sbb     eax, eax
0x18001caeb  not     eax
0x18001caed  and     eax, 8007007Ah
0x18001caf2  jmp     short loc_18001CAFE
0x18001caf4  mov     eax, 80070057h
0x18001caf9  test    rdx, rdx
0x18001cafc  jz      short locret_18001CB02
0x18001cafe  mov     [rcx], r10w
0x18001cb02  retn
```
