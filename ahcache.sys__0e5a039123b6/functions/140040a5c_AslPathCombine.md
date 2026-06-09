# AslPathCombine

- ea: `0x140040a5c`
- end: `0x140040c00`
- name: `AslPathCombine`
- size: `420`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, NTSTRSAFE_PCWSTR, NTSTRSAFE_PWSTR pszDest, size_t cchDest)`
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400052f0`
- `0x140005470`
- `0x14002d480`
- `0x14002d5c0`
- `0x14002d6a0`
- `0x140032adc`
- `0x140032c14`
- `0x140040970`
- `0x140042e28`

## callees

- `0x1400012f0`
- `0x1400013d0`
- `0x14003e364`
- `0x140040a5c`

## string_xrefs

- `0x140040ba6`: `AslPathCombine`

## pseudocode

```c
__int64 __fastcall AslPathCombine(
        NTSTRSAFE_PCWSTR pszSrc,
        NTSTRSAFE_PCWSTR a2,
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest)
{
  NTSTRSAFE_PCWSTR v6; // r10
  NTSTRSAFE_PCWSTR v8; // rax
  __int64 v9; // r8
  NTSTATUS v10; // ebx
  __int64 v11; // rbp
  __int64 v12; // rcx
  NTSTRSAFE_PCWSTR v13; // rax
  __int64 v14; // rdx
  bool v15; // zf
  const wchar_t *v16; // rbp
  unsigned int v17; // edx
  int v18; // r10d

  v6 = a2;
  if ( cchDest )
  {
    if ( pszSrc )
    {
      v8 = pszSrc;
      v9 = 0x7FFFFFFF;
      do
      {
        if ( !*v8 )
          break;
        ++v8;
        --v9;
      }
      while ( v9 );
      v10 = v9 == 0 ? 0xC000000D : 0;
      v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
      if ( v9 )
      {
        if ( a2 )
        {
          v12 = 0x7FFFFFFF;
          v13 = a2;
          do
          {
            if ( !*v13 )
              break;
            ++v13;
            --v12;
          }
          while ( v12 );
          v10 = v12 == 0 ? 0xC000000D : 0;
          v14 = (0x7FFFFFFF - v12) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
          if ( v12 )
          {
            if ( v11 )
            {
              if ( v14 )
              {
                v15 = pszSrc[v11 - 1] == 92;
                v16 = v6 + 1;
                v17 = v15 + 1;
                if ( *v6 != 92 )
                  v17 = v15;
                if ( v17 <= 1 )
                  v16 = v6;
                v10 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
                if ( v10 < 0 )
                  goto LABEL_22;
                if ( !v18 )
                {
                  v10 = RtlStringCchCatW(pszDest, cchDest, L"\\");
                  if ( v10 < 0 )
                    goto LABEL_22;
                }
                v10 = RtlStringCchCatW(pszDest, cchDest, v16);
                if ( v10 < 0 )
                  goto LABEL_22;
                return 0;
              }
              v6 = pszSrc;
            }
            else if ( !v14 )
            {
              *pszDest = 0;
              return 0;
            }
            v10 = RtlStringCchCopyW(pszDest, cchDest, v6);
            if ( v10 >= 0 )
              return (unsigned int)v10;
          }
        }
        else
        {
          v10 = -1073741811;
        }
      }
    }
    else
    {
      v10 = -1073741811;
    }
LABEL_22:
    AslLogCallPrintf(1, "AslPathCombine", 1420, "An RtlString API failed [%x]", v10);
    return (unsigned int)v10;
  }
  return 3221225507LL;
}

```

## disassembly

```asm
0x140040a5c  push    rbx
0x140040a5e  push    rbp
0x140040a5f  push    rsi
0x140040a60  push    rdi
0x140040a61  push    r14
0x140040a63  sub     rsp, 30h
0x140040a67  xor     r14d, r14d
0x140040a6a  mov     rsi, r9
0x140040a6d  mov     rdi, r8
0x140040a70  mov     r10, rdx
0x140040a73  mov     r11, rcx
0x140040a76  test    r9, r9
0x140040a79  jz      loc_140040BC5
0x140040a7f  test    rcx, rcx
0x140040a82  jz      loc_140040BF9
0x140040a88  mov     r9d, 7FFFFFFFh
0x140040a8e  mov     rax, rcx
0x140040a91  mov     r8d, r9d
0x140040a94  cmp     [rax], r14w
0x140040a98  jz      short loc_140040AA4
0x140040a9a  add     rax, 2
0x140040a9e  sub     r8, 1
0x140040aa2  jnz     short loc_140040A94
0x140040aa4  mov     rax, r8
0x140040aa7  mov     edx, 0C000000Dh
0x140040aac  neg     rax
0x140040aaf  mov     rcx, r9
0x140040ab2  mov     rax, r8
0x140040ab5  sbb     ebx, ebx
0x140040ab7  sub     rcx, r8
0x140040aba  not     ebx
0x140040abc  and     ebx, edx
0x140040abe  neg     rax
0x140040ac1  sbb     rbp, rbp
0x140040ac4  and     rbp, rcx
0x140040ac7  test    r8, r8
0x140040aca  jz      loc_140040B95
0x140040ad0  test    r10, r10
0x140040ad3  jz      loc_140040BF5
0x140040ad9  mov     rcx, r9
0x140040adc  mov     rax, r10
0x140040adf  cmp     [rax], r14w
0x140040ae3  jz      short loc_140040AEF
0x140040ae5  add     rax, 2
0x140040ae9  sub     rcx, 1
0x140040aed  jnz     short loc_140040ADF
0x140040aef  mov     rax, rcx
0x140040af2  neg     rax
0x140040af5  mov     rax, rcx
0x140040af8  sbb     ebx, ebx
0x140040afa  sub     r9, rcx
0x140040afd  not     ebx
0x140040aff  and     ebx, edx
0x140040b01  neg     rax
0x140040b04  sbb     rdx, rdx
0x140040b07  and     rdx, r9
0x140040b0a  test    rcx, rcx
0x140040b0d  jz      loc_140040B95
0x140040b13  test    rbp, rbp
0x140040b16  jz      loc_140040BE2
0x140040b1c  test    rdx, rdx
0x140040b1f  jz      loc_140040BF0
0x140040b25  cmp     word ptr [r11+rbp*2-2], 5Ch ; '\'
0x140040b2c  mov     ecx, r14d
0x140040b2f  lea     rbp, [r10+2]
0x140040b33  mov     r8, r11; pszSrc
0x140040b36  setz    cl
0x140040b39  cmp     word ptr [r10], 5Ch ; '\'
0x140040b3e  lea     edx, [rcx+1]
0x140040b41  cmovnz  edx, ecx
0x140040b44  mov     rcx, rdi; pszDest
0x140040b47  cmp     edx, 1
0x140040b4a  cmovbe  rbp, r10
0x140040b4e  lea     r10d, [rdx-1]
0x140040b52  cmovbe  r10d, edx
0x140040b56  mov     rdx, rsi; cchDest
0x140040b59  call    RtlStringCchCopyW
0x140040b5e  mov     ebx, eax
0x140040b60  test    eax, eax
0x140040b62  js      short loc_140040B95
0x140040b64  test    r10d, r10d
0x140040b67  jnz     short loc_140040B81
0x140040b69  lea     r8, asc_14000AF88; "\\"
0x140040b70  mov     rdx, rsi; cchDest
0x140040b73  mov     rcx, rdi; pszDest
0x140040b76  call    RtlStringCchCatW
0x140040b7b  mov     ebx, eax
0x140040b7d  test    eax, eax
0x140040b7f  js      short loc_140040B95
0x140040b81  mov     r8, rbp; pszSrc
0x140040b84  mov     rdx, rsi; cchDest
0x140040b87  mov     rcx, rdi; pszDest
0x140040b8a  call    RtlStringCchCatW
0x140040b8f  mov     ebx, eax
0x140040b91  test    eax, eax
0x140040b93  jns     short loc_140040BEB
0x140040b95  lea     r9, aAnRtlstringApi; "An RtlString API failed [%x]"
0x140040b9c  mov     [rsp+58h+var_38], ebx
0x140040ba0  mov     r8d, 58Ch
0x140040ba6  lea     rdx, aAslpathcombine; "AslPathCombine"
0x140040bad  mov     ecx, 1
0x140040bb2  call    AslLogCallPrintf
0x140040bb7  mov     eax, ebx
0x140040bb9  add     rsp, 30h
0x140040bbd  pop     r14
0x140040bbf  pop     rdi
0x140040bc0  pop     rsi
0x140040bc1  pop     rbp
0x140040bc2  pop     rbx
0x140040bc3  retn
0x140040bc5  mov     eax, 0C0000023h
0x140040bca  jmp     short loc_140040BB9
0x140040bcc  mov     r8, r10; pszSrc
0x140040bcf  mov     rdx, rsi; cchDest
0x140040bd2  mov     rcx, rdi; pszDest
0x140040bd5  call    RtlStringCchCopyW
0x140040bda  mov     ebx, eax
0x140040bdc  test    eax, eax
0x140040bde  jns     short loc_140040BB7
0x140040be0  jmp     short loc_140040B95
0x140040be2  test    rdx, rdx
0x140040be5  jnz     short loc_140040BCC
0x140040be7  mov     [rdi], r14w
0x140040beb  mov     ebx, r14d
0x140040bee  jmp     short loc_140040BB7
0x140040bf0  mov     r10, r11
0x140040bf3  jmp     short loc_140040BCC
0x140040bf5  mov     ebx, edx
0x140040bf7  jmp     short loc_140040B95
0x140040bf9  mov     ebx, 0C000000Dh
0x140040bfe  jmp     short loc_140040B95
```
