# AslEnvGetSystem32DirPathBuf

- ea: `0x140032c14`
- end: `0x140032d5e`
- name: `AslEnvGetSystem32DirPathBuf`
- size: `330`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR, __int16, __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14002d790`
- `0x140032adc`

## callees

- `0x1400012f0`
- `0x1400079f0`
- `0x140007e40`
- `0x140032c14`
- `0x14003e364`
- `0x1400403cc`
- `0x140040a5c`

## string_xrefs

- `0x140032d24`: `RtlStringCchCopyW failed [%x]`
- `0x140032cb7`: `AslPathToSystemPathBuf failed [%x]`
- `0x140032cff`: `AslPathCombine failed [%x]`
- `0x140032cc4`: `AslEnvGetSystem32DirPathBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSystem32DirPathBuf(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        NTSTRSAFE_PCWSTR a3,
        __int16 a4,
        __int16 *a5)
{
  __int16 v9; // cx
  unsigned __int64 i; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  __int64 v14; // r8
  wchar_t pszSrc[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset(pszSrc, 0, sizeof(pszSrc));
  *pszDest = 0;
  if ( a5 )
    v9 = *a5;
  else
    v9 = a4;
  for ( i = 0; ; ++i )
  {
    if ( i >= 8 )
      return (unsigned int)-1073741637;
    if ( word_14001E090[8 * i] == a4 && word_14001E090[8 * i + 1] == v9 )
      break;
  }
  v11 = AslPathToSystemPathBuf(pszSrc, 64, *(_QWORD *)&word_14001E090[8 * i + 4]);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = "AslPathToSystemPathBuf failed [%x]";
    v14 = 1575;
LABEL_11:
    AslLogCallPrintf(1, "AslEnvGetSystem32DirPathBuf", v14, v13, v11);
    return v12;
  }
  if ( a3 && *a3 )
  {
    v11 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = "AslPathCombine failed [%x]";
      v14 = 1585;
      goto LABEL_11;
    }
  }
  else
  {
    v11 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = "RtlStringCchCopyW failed [%x]";
      v14 = 1593;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140032c14  push    rbx
0x140032c16  push    rbp
0x140032c17  push    rsi
0x140032c18  push    rdi
0x140032c19  push    r14
0x140032c1b  sub     rsp, 0C0h
0x140032c22  mov     rax, cs:__security_cookie
0x140032c29  xor     rax, rsp
0x140032c2c  mov     [rsp+0E8h+var_38], rax
0x140032c34  mov     rdi, r8
0x140032c37  mov     rbp, rdx
0x140032c3a  mov     rsi, rcx
0x140032c3d  xor     edx, edx; Val
0x140032c3f  mov     r8d, 80h; Size
0x140032c45  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x140032c4a  movzx   ebx, r9w
0x140032c4e  call    memset
0x140032c53  mov     rcx, [rsp+0E8h+arg_20]
0x140032c5b  xor     r14d, r14d
0x140032c5e  mov     [rsi], r14w
0x140032c62  test    rcx, rcx
0x140032c65  jz      short loc_140032C6C
0x140032c67  movzx   ecx, word ptr [rcx]
0x140032c6a  jmp     short loc_140032C6F
0x140032c6c  movzx   ecx, bx
0x140032c6f  mov     rax, r14
0x140032c72  lea     rdx, word_14001E090
0x140032c79  cmp     rax, 8
0x140032c7d  jnb     loc_140032D38
0x140032c83  mov     r8, rax
0x140032c86  add     r8, r8
0x140032c89  cmp     [rdx+r8*8], bx
0x140032c8e  jnz     short loc_140032C98
0x140032c90  cmp     [rdx+r8*8+2], cx
0x140032c96  jz      short loc_140032C9D
0x140032c98  inc     rax
0x140032c9b  jmp     short loc_140032C79
0x140032c9d  mov     r8, [rdx+r8*8+8]
0x140032ca2  lea     rcx, [rsp+0E8h+pszSrc]
0x140032ca7  mov     edx, 40h ; '@'
0x140032cac  call    AslPathToSystemPathBuf
0x140032cb1  mov     ebx, eax
0x140032cb3  test    eax, eax
0x140032cb5  jns     short loc_140032CDB
0x140032cb7  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140032cbe  mov     r8d, 627h
0x140032cc4  lea     rdx, aAslenvgetsyste; "AslEnvGetSystem32DirPathBuf"
0x140032ccb  mov     [rsp+0E8h+var_C8], eax
0x140032ccf  mov     ecx, 1
0x140032cd4  call    AslLogCallPrintf
0x140032cd9  jmp     short loc_140032D3D
0x140032cdb  test    rdi, rdi
0x140032cde  jz      short loc_140032D0E
0x140032ce0  cmp     [rdi], r14w
0x140032ce4  jz      short loc_140032D0E
0x140032ce6  mov     r9, rbp; cchDest
0x140032ce9  lea     rcx, [rsp+0E8h+pszSrc]; pszSrc
0x140032cee  mov     r8, rsi; pszDest
0x140032cf1  mov     rdx, rdi; NTSTRSAFE_PCWSTR
0x140032cf4  call    AslPathCombine
0x140032cf9  mov     ebx, eax
0x140032cfb  test    eax, eax
0x140032cfd  jns     short loc_140032D33
0x140032cff  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140032d06  mov     r8d, 631h
0x140032d0c  jmp     short loc_140032CC4
0x140032d0e  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x140032d13  mov     rdx, rbp; cchDest
0x140032d16  mov     rcx, rsi; pszDest
0x140032d19  call    RtlStringCchCopyW
0x140032d1e  mov     ebx, eax
0x140032d20  test    eax, eax
0x140032d22  jns     short loc_140032D33
0x140032d24  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140032d2b  mov     r8d, 639h
0x140032d31  jmp     short loc_140032CC4
0x140032d33  mov     ebx, r14d
0x140032d36  jmp     short loc_140032D3D
0x140032d38  mov     ebx, 0C00000BBh
0x140032d3d  mov     eax, ebx
0x140032d3f  mov     rcx, [rsp+0E8h+var_38]
0x140032d47  xor     rcx, rsp; StackCookie
0x140032d4a  call    __security_check_cookie
0x140032d4f  add     rsp, 0C0h
0x140032d56  pop     r14
0x140032d58  pop     rdi
0x140032d59  pop     rsi
0x140032d5a  pop     rbp
0x140032d5b  pop     rbx
0x140032d5c  retn
```
