# AslEnvGetSysNativeDirPathForGuestBuf

- ea: `0x140032adc`
- end: `0x140032c0b`
- name: `AslEnvGetSysNativeDirPathForGuestBuf`
- size: `303`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR, __int16, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14002d480`

## callees

- `0x1400012f0`
- `0x1400079f0`
- `0x140007e40`
- `0x140032adc`
- `0x140032c14`
- `0x14003e364`
- `0x1400403cc`
- `0x140040a5c`

## string_xrefs

- `0x140032baf`: `RtlStringCchCopyW failed [%x]`
- `0x140032b57`: `AslPathToSystemPathBuf failed [%x]`
- `0x140032b8a`: `AslPathCombine failed [%x]`
- `0x140032bbc`: `AslEnvGetSysNativeDirPathForGuestBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSysNativeDirPathForGuestBuf(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        NTSTRSAFE_PCWSTR a3,
        __int16 a4,
        _WORD *a5)
{
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  NTSTATUS v14; // [rsp+20h] [rbp-C8h]
  wchar_t pszSrc[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset(pszSrc, 0, sizeof(pszSrc));
  *pszDest = 0;
  if ( a5 && *a5 != a4 )
  {
    v9 = AslPathToSystemPathBuf(pszSrc, 64, L"\\SysNative");
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = "AslPathToSystemPathBuf failed [%x]";
      v12 = 1847;
LABEL_11:
      v14 = v9;
      AslLogCallPrintf(1, "AslEnvGetSysNativeDirPathForGuestBuf", v12, v11, v14);
      return v10;
    }
    if ( a3 && *a3 )
    {
      v9 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "AslPathCombine failed [%x]";
        v12 = 1857;
        goto LABEL_11;
      }
    }
    else
    {
      v9 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "RtlStringCchCopyW failed [%x]";
        v12 = 1865;
        goto LABEL_11;
      }
    }
    return v10;
  }
  return AslEnvGetSystem32DirPathBuf(pszDest, cchDest, a3, (__int64)a5);
}

```

## disassembly

```asm
0x140032adc  push    rbx
0x140032ade  push    rbp
0x140032adf  push    rsi
0x140032ae0  push    rdi
0x140032ae1  push    r14
0x140032ae3  sub     rsp, 0C0h
0x140032aea  mov     rax, cs:__security_cookie
0x140032af1  xor     rax, rsp
0x140032af4  mov     [rsp+0E8h+var_38], rax
0x140032afc  mov     rdi, r8
0x140032aff  mov     rbp, rdx
0x140032b02  mov     rsi, rcx
0x140032b05  xor     edx, edx; Val
0x140032b07  mov     r8d, 80h; Size
0x140032b0d  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x140032b12  movzx   ebx, r9w
0x140032b16  call    memset
0x140032b1b  mov     rax, [rsp+0E8h+arg_20]
0x140032b23  xor     r14d, r14d
0x140032b26  mov     [rsi], r14w
0x140032b2a  test    rax, rax
0x140032b2d  jz      loc_140032BD5
0x140032b33  cmp     [rax], bx
0x140032b36  jz      loc_140032BD5
0x140032b3c  lea     r8, aSysnative; "\\SysNative"
0x140032b43  lea     edx, [r14+40h]
0x140032b47  lea     rcx, [rsp+0E8h+pszSrc]
0x140032b4c  call    AslPathToSystemPathBuf
0x140032b51  mov     ebx, eax
0x140032b53  test    eax, eax
0x140032b55  jns     short loc_140032B66
0x140032b57  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140032b5e  mov     r8d, 737h
0x140032b64  jmp     short loc_140032BBC
0x140032b66  test    rdi, rdi
0x140032b69  jz      short loc_140032B99
0x140032b6b  cmp     [rdi], r14w
0x140032b6f  jz      short loc_140032B99
0x140032b71  mov     r9, rbp; cchDest
0x140032b74  lea     rcx, [rsp+0E8h+pszSrc]; pszSrc
0x140032b79  mov     r8, rsi; pszDest
0x140032b7c  mov     rdx, rdi; NTSTRSAFE_PCWSTR
0x140032b7f  call    AslPathCombine
0x140032b84  mov     ebx, eax
0x140032b86  test    eax, eax
0x140032b88  jns     short loc_140032BD1
0x140032b8a  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140032b91  mov     r8d, 741h
0x140032b97  jmp     short loc_140032BBC
0x140032b99  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x140032b9e  mov     rdx, rbp; cchDest
0x140032ba1  mov     rcx, rsi; pszDest
0x140032ba4  call    RtlStringCchCopyW
0x140032ba9  mov     ebx, eax
0x140032bab  test    eax, eax
0x140032bad  jns     short loc_140032BD1
0x140032baf  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140032bb6  mov     r8d, 749h
0x140032bbc  lea     rdx, aAslenvgetsysna; "AslEnvGetSysNativeDirPathForGuestBuf"
0x140032bc3  mov     [rsp+0E8h+var_C8], eax
0x140032bc7  mov     ecx, 1
0x140032bcc  call    AslLogCallPrintf
0x140032bd1  mov     eax, ebx
0x140032bd3  jmp     short loc_140032BEC
0x140032bd5  movzx   r9d, bx
0x140032bd9  mov     qword ptr [rsp+0E8h+var_C8], rax; __int64
0x140032bde  mov     r8, rdi; NTSTRSAFE_PCWSTR
0x140032be1  mov     rdx, rbp; cchDest
0x140032be4  mov     rcx, rsi; pszDest
0x140032be7  call    AslEnvGetSystem32DirPathBuf
0x140032bec  mov     rcx, [rsp+0E8h+var_38]
0x140032bf4  xor     rcx, rsp; StackCookie
0x140032bf7  call    __security_check_cookie
0x140032bfc  add     rsp, 0C0h
0x140032c03  pop     r14
0x140032c05  pop     rdi
0x140032c06  pop     rsi
0x140032c07  pop     rbp
0x140032c08  pop     rbx
0x140032c09  retn
```
