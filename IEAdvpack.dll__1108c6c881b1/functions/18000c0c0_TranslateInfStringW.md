# TranslateInfStringW

- ea: `0x18000c0c0`
- end: `0x18000c224`
- name: `TranslateInfStringW`
- size: `356`
- prototype: `HRESULT __stdcall(LPCWSTR pszInfFilename, LPCWSTR pszInstallSection, LPCWSTR pszTranslateSection, LPCWSTR pszTranslateKey, LPWSTR pszBuffer, DWORD cchBuffer, PDWORD pdwRequiredSize, PVOID pvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bf80`

## callees

- `0x180003ce0`
- `0x180003e20`
- `0x180004700`
- `0x180004754`
- `0x180007454`
- `0x18000a61c`
- `0x18000c0c0`
- `0x18000c574`
- `0x18001b980`

## pseudocode

```c
HRESULT __stdcall TranslateInfStringW(
        LPCWSTR pszInfFilename,
        LPCWSTR pszInstallSection,
        LPCWSTR pszTranslateSection,
        LPCWSTR pszTranslateKey,
        LPWSTR pszBuffer,
        DWORD cchBuffer,
        PDWORD pdwRequiredSize,
        PVOID pvReserved)
{
  HRESULT TranslatedString; // ebx
  unsigned __int16 v14[256]; // [rsp+40h] [rbp-248h] BYREF

  AdvWriteToLog(L"TranslateInfString:");
  if ( (unsigned int)SaveGlobalContext() )
  {
    word_1800257D2 = 1;
    if ( pszInfFilename && pszTranslateSection && pszTranslateKey && pdwRequiredSize )
    {
      AdvWriteToLog(L"Inf=%1 Sec=%2 Key=%3\r\n", pszInfFilename, pszTranslateSection, pszTranslateKey);
      TranslatedString = CommonInstallInit(
                           pszInfFilename,
                           pszInstallSection,
                           v14,
                           0x100u,
                           0,
                           0,
                           ((unsigned __int64)pvReserved >> 2) & 0x100);
      if ( TranslatedString >= 0 )
      {
        TranslatedString = SetLDIDs(pszInfFilename, v14, 0, 0);
        if ( TranslatedString >= 0 )
          TranslatedString = GetTranslatedString(
                               pszInfFilename,
                               pszTranslateSection,
                               pszTranslateKey,
                               pszBuffer,
                               cchBuffer,
                               pdwRequiredSize);
      }
    }
    else
    {
      TranslatedString = -2147024809;
    }
    CommonInstallCleanup();
    RestoreGlobalContext();
  }
  else
  {
    TranslatedString = -2147024882;
    CommonInstallCleanup();
  }
  AdvWriteToLog(L"TranslateInfString: End hr=0x%1!x!\r\n", (unsigned int)TranslatedString);
  return TranslatedString;
}

```

## disassembly

```asm
0x18000c0c0  push    rbx
0x18000c0c2  push    rbp
0x18000c0c3  push    rsi
0x18000c0c4  push    rdi
0x18000c0c5  push    r14
0x18000c0c7  push    r15
0x18000c0c9  sub     rsp, 258h
0x18000c0d0  mov     rax, cs:__security_cookie
0x18000c0d7  xor     rax, rsp
0x18000c0da  mov     [rsp+288h+var_48], rax
0x18000c0e2  mov     r15, [rsp+288h+pszBuffer]
0x18000c0ea  mov     rdi, rcx
0x18000c0ed  mov     r14, [rsp+288h+pdwRequiredSize]
0x18000c0f5  lea     rcx, aTranslateinfst_6; "TranslateInfString:"
0x18000c0fc  mov     rbp, r9
0x18000c0ff  mov     rsi, r8
0x18000c102  mov     rbx, rdx
0x18000c105  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000c10a  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x18000c10f  test    eax, eax
0x18000c111  jnz     short loc_18000C122
0x18000c113  mov     ebx, 8007000Eh
0x18000c118  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x18000c11d  jmp     loc_18000C1F4
0x18000c122  mov     eax, 1
0x18000c127  mov     cs:word_1800257D2, ax
0x18000c12e  test    rdi, rdi
0x18000c131  jz      loc_18000C1E5
0x18000c137  test    rsi, rsi
0x18000c13a  jz      loc_18000C1E5
0x18000c140  test    rbp, rbp
0x18000c143  jz      loc_18000C1E5
0x18000c149  test    r14, r14
0x18000c14c  jz      loc_18000C1E5
0x18000c152  mov     r9, rbp
0x18000c155  lea     rcx, aInf1Sec2Key3; "Inf=%1 Sec=%2 Key=%3\r\n"
0x18000c15c  mov     r8, rsi
0x18000c15f  mov     rdx, rdi
0x18000c162  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000c167  mov     rax, [rsp+288h+pvReserved]
0x18000c16f  lea     r8, [rsp+288h+var_248]; unsigned __int16 *
0x18000c174  shr     rax, 2
0x18000c178  mov     r9d, 100h; unsigned int
0x18000c17e  and     eax, r9d
0x18000c181  mov     rdx, rbx; unsigned __int16 *
0x18000c184  mov     [rsp+288h+var_258], eax; unsigned int
0x18000c188  mov     rcx, rdi; unsigned __int16 *
0x18000c18b  mov     dword ptr [rsp+288h+var_260], 0; int
0x18000c193  mov     [rsp+288h+var_268], 0; unsigned __int16 *
0x18000c19c  call    ?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z; CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)
0x18000c1a1  mov     ebx, eax
0x18000c1a3  test    eax, eax
0x18000c1a5  js      short loc_18000C1EA
0x18000c1a7  xor     r9d, r9d; unsigned __int16 *
0x18000c1aa  lea     rdx, [rsp+288h+var_248]; unsigned __int16 *
0x18000c1af  xor     r8d, r8d; unsigned int
0x18000c1b2  mov     rcx, rdi; unsigned __int16 *
0x18000c1b5  call    ?SetLDIDs@@YAJPEBG0K0@Z; SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)
0x18000c1ba  mov     ebx, eax
0x18000c1bc  test    eax, eax
0x18000c1be  js      short loc_18000C1EA
0x18000c1c0  mov     eax, [rsp+288h+cchBuffer]
0x18000c1c7  mov     r9, r15; unsigned __int16 *
0x18000c1ca  mov     [rsp+288h+var_260], r14; unsigned int *
0x18000c1cf  mov     r8, rbp; lpKeyName
0x18000c1d2  mov     rdx, rsi; lpAppName
0x18000c1d5  mov     dword ptr [rsp+288h+var_268], eax; unsigned int
0x18000c1d9  mov     rcx, rdi; unsigned __int16 *
0x18000c1dc  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000c1e1  mov     ebx, eax
0x18000c1e3  jmp     short loc_18000C1EA
0x18000c1e5  mov     ebx, 80070057h
0x18000c1ea  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x18000c1ef  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000c1f4  mov     edx, ebx
0x18000c1f6  lea     rcx, aTranslateinfst_5; "TranslateInfString: End hr=0x%1!x!\r\n"
0x18000c1fd  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000c202  mov     eax, ebx
0x18000c204  mov     rcx, [rsp+288h+var_48]
0x18000c20c  xor     rcx, rsp; StackCookie
0x18000c20f  call    __security_check_cookie
0x18000c214  add     rsp, 258h
0x18000c21b  pop     r15
0x18000c21d  pop     r14
0x18000c21f  pop     rdi
0x18000c220  pop     rsi
0x18000c221  pop     rbp
0x18000c222  pop     rbx
0x18000c223  retn
```
