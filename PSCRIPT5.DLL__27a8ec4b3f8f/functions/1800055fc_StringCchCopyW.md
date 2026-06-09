# StringCchCopyW

- ea: `0x1800055fc`
- end: `0x180005667`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f70`
- `0x1800206c4`
- `0x1800350fc`
- `0x18003638c`
- `0x1800372bc`
- `0x180037748`
- `0x180055658`
- `0x180055ed4`
- `0x18005a5f0`

## callees

- `0x1800055fc`

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
0x1800055fc  xor     r10d, r10d
0x1800055ff  mov     r9, rcx
0x180005602  test    rdx, rdx
0x180005605  jz      short loc_180005658
0x180005607  cmp     rdx, 7FFFFFFFh
0x18000560e  jbe     short loc_180005617
0x180005610  mov     eax, 80070057h
0x180005615  jmp     short loc_180005662
0x180005617  mov     eax, 7FFFFFFEh
0x18000561c  test    rax, rax
0x18000561f  jz      short loc_18000563F
0x180005621  movzx   ecx, word ptr [r8]
0x180005625  test    cx, cx
0x180005628  jz      short loc_18000563F
0x18000562a  mov     [r9], cx
0x18000562e  add     r8, 2
0x180005632  add     r9, 2
0x180005636  dec     rax
0x180005639  sub     rdx, 1
0x18000563d  jnz     short loc_18000561C
0x18000563f  test    rdx, rdx
0x180005642  lea     rcx, [r9-2]
0x180005646  cmovnz  rcx, r9
0x18000564a  neg     rdx
0x18000564d  sbb     eax, eax
0x18000564f  not     eax
0x180005651  and     eax, 8007007Ah
0x180005656  jmp     short loc_180005662
0x180005658  mov     eax, 80070057h
0x18000565d  test    rdx, rdx
0x180005660  jz      short locret_180005666
0x180005662  mov     [rcx], r10w
0x180005666  retn
```
