# GetPersistentRegPathFromRegPath

- ea: `0x18000b030`
- end: `0x18000b0e4`
- name: `GetPersistentRegPathFromRegPath`
- size: `180`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, _DWORD *, wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007570`
- `0x180007640`
- `0x18000b030`
- `0x18000b0ec`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathFromRegPath(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, _DWORD *a3, wchar_t *a4)
{
  const wchar_t *v7; // r10
  int v8; // esi
  __int64 result; // rax
  size_t v10; // rbp
  size_t pcchLength; // [rsp+68h] [rbp+10h] BYREF

  pcchLength = 0;
  v7 = pszSrc;
  v8 = 0;
  if ( a2 && *a2 )
  {
    if ( StringCchLengthW(a2, (size_t)a2, &pcchLength) < 0 )
      return 87;
    v8 = pcchLength;
  }
  v10 = (unsigned int)*a3;
  result = GetPersistentRegRootPath(v7);
  if ( a2 && *a2 )
    *a3 += v8 + 1;
  if ( !(_DWORD)result )
  {
    if ( (unsigned int)v10 >= *a3 )
    {
      if ( a2 )
      {
        if ( *a2 )
        {
          StringCchCatW(a4, v10, L"\\");
          StringCchCatW(a4, v10, a2);
        }
      }
      return 0;
    }
    else
    {
      return 234;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b030  push    rbx
0x18000b032  push    rbp
0x18000b033  push    rsi
0x18000b034  push    rdi
0x18000b035  push    r14
0x18000b037  push    r15
0x18000b039  sub     rsp, 28h
0x18000b03d  xor     r15d, r15d
0x18000b040  mov     r14, r9
0x18000b043  mov     [rsp+58h+pcchLength], r15
0x18000b048  mov     rbx, r8
0x18000b04b  mov     rdi, rdx
0x18000b04e  mov     r10, rcx
0x18000b051  mov     esi, r15d
0x18000b054  test    rdx, rdx
0x18000b057  jz      short loc_18000B07B
0x18000b059  cmp     [rdx], r15w
0x18000b05d  jz      short loc_18000B07B
0x18000b05f  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x18000b064  mov     rcx, rdx; psz
0x18000b067  call    StringCchLengthW
0x18000b06c  test    eax, eax
0x18000b06e  jns     short loc_18000B076
0x18000b070  lea     eax, [r15+57h]
0x18000b074  jmp     short loc_18000B0D7
0x18000b076  mov     rsi, [rsp+58h+pcchLength]
0x18000b07b  mov     ebp, [rbx]
0x18000b07d  mov     r9, r14
0x18000b080  mov     r8, rbx
0x18000b083  mov     rcx, r10; pszSrc
0x18000b086  call    GetPersistentRegRootPath
0x18000b08b  test    rdi, rdi
0x18000b08e  jz      short loc_18000B09B
0x18000b090  cmp     [rdi], r15w
0x18000b094  jz      short loc_18000B09B
0x18000b096  lea     ecx, [rsi+1]
0x18000b099  add     [rbx], ecx
0x18000b09b  test    eax, eax
0x18000b09d  jnz     short loc_18000B0D7
0x18000b09f  cmp     ebp, [rbx]
0x18000b0a1  jnb     short loc_18000B0AA
0x18000b0a3  mov     eax, 0EAh
0x18000b0a8  jmp     short loc_18000B0D7
0x18000b0aa  test    rdi, rdi
0x18000b0ad  jz      short loc_18000B0D5
0x18000b0af  cmp     [rdi], r15w
0x18000b0b3  jz      short loc_18000B0D5
0x18000b0b5  lea     r8, asc_180013DE4; "\\"
0x18000b0bc  mov     rdx, rbp; cchDest
0x18000b0bf  mov     rcx, r14; pszDest
0x18000b0c2  call    StringCchCatW
0x18000b0c7  mov     r8, rdi; pszSrc
0x18000b0ca  mov     rdx, rbp; cchDest
0x18000b0cd  mov     rcx, r14; pszDest
0x18000b0d0  call    StringCchCatW
0x18000b0d5  xor     eax, eax
0x18000b0d7  add     rsp, 28h
0x18000b0db  pop     r15
0x18000b0dd  pop     r14
0x18000b0df  pop     rdi
0x18000b0e0  pop     rsi
0x18000b0e1  pop     rbp
0x18000b0e2  pop     rbx
0x18000b0e3  retn
```
