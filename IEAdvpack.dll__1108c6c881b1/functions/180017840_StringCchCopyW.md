# StringCchCopyW

- ea: `0x180017840`
- end: `0x1800178ab`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180017434`
- `0x180017bcc`
- `0x180017f14`

## callees

- `0x180017840`

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
0x180017840  xor     r10d, r10d
0x180017843  mov     r9, rcx
0x180017846  test    rdx, rdx
0x180017849  jz      short loc_18001789C
0x18001784b  cmp     rdx, 7FFFFFFFh
0x180017852  jbe     short loc_18001785B
0x180017854  mov     eax, 80070057h
0x180017859  jmp     short loc_1800178A6
0x18001785b  mov     eax, 7FFFFFFEh
0x180017860  test    rax, rax
0x180017863  jz      short loc_180017883
0x180017865  movzx   ecx, word ptr [r8]
0x180017869  test    cx, cx
0x18001786c  jz      short loc_180017883
0x18001786e  mov     [r9], cx
0x180017872  add     r8, 2
0x180017876  add     r9, 2
0x18001787a  dec     rax
0x18001787d  sub     rdx, 1
0x180017881  jnz     short loc_180017860
0x180017883  test    rdx, rdx
0x180017886  lea     rcx, [r9-2]
0x18001788a  cmovnz  rcx, r9
0x18001788e  neg     rdx
0x180017891  sbb     eax, eax
0x180017893  not     eax
0x180017895  and     eax, 8007007Ah
0x18001789a  jmp     short loc_1800178A6
0x18001789c  mov     eax, 80070057h
0x1800178a1  test    rdx, rdx
0x1800178a4  jz      short locret_1800178AA
0x1800178a6  mov     [rcx], r10w
0x1800178aa  retn
```
