# TranslateInfStringA

- ea: `0x18000bf80`
- end: `0x18000c0b6`
- name: `TranslateInfStringA`
- size: `310`
- prototype: `HRESULT __stdcall(LPCSTR pszInfFilename, LPCSTR pszInstallSection, LPCSTR pszTranslateSection, LPCSTR pszTranslateKey, LPSTR pszBuffer, DWORD cchBuffer, PDWORD pdwRequiredSize, PVOID pvReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000bf80`
- `0x18000c0c0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000c077`
- `KERNEL32!LocalFree` at `0x18000c081`
- `KERNEL32!LocalFree` at `0x18000c08b`
- `KERNEL32!LocalFree` at `0x18000c095`
- `KERNEL32!LocalFree` at `0x18000c09e`
- `KERNEL32!LocalFree` at `0x18000c077`
- `KERNEL32!LocalFree` at `0x18000c081`
- `KERNEL32!LocalFree` at `0x18000c08b`
- `KERNEL32!LocalFree` at `0x18000c095`
- `KERNEL32!LocalFree` at `0x18000c09e`
- `KERNEL32!LocalAlloc` at `0x18000c00d`
- `KERNEL32!LocalAlloc` at `0x18000c00d`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000c068`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18000c068`

## pseudocode

```c
HRESULT __stdcall TranslateInfStringA(
        LPCSTR pszInfFilename,
        LPCSTR pszInstallSection,
        LPCSTR pszTranslateSection,
        LPCSTR pszTranslateKey,
        LPSTR pszBuffer,
        DWORD cchBuffer,
        PDWORD pdwRequiredSize,
        PVOID pvReserved)
{
  WCHAR *v8; // rdi
  WCHAR *v10; // rsi
  int v13; // r14d
  LPCWSTR pszTranslateKeya; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR pszInfFilenamea; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR pszInstallSectiona; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR pszTranslateSectiona; // [rsp+58h] [rbp-8h] BYREF

  v8 = 0;
  v10 = 0;
  pszInfFilenamea = 0;
  pszInstallSectiona = 0;
  pszTranslateSectiona = 0;
  pszTranslateKeya = 0;
  v13 = -2147467259;
  if ( (int)ThunkToUnicode(pszInfFilename, (HLOCAL *)&pszInfFilenamea) >= 0
    && (int)ThunkToUnicode(pszInstallSection, (HLOCAL *)&pszInstallSectiona) >= 0
    && (int)ThunkToUnicode(pszTranslateSection, (HLOCAL *)&pszTranslateSectiona) >= 0 )
  {
    if ( (int)ThunkToUnicode(pszTranslateKey, (HLOCAL *)&pszTranslateKeya) < 0
      || cchBuffer && (v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchBuffer)) == 0 )
    {
      v10 = (WCHAR *)pszTranslateKeya;
    }
    else
    {
      v10 = (WCHAR *)pszTranslateKeya;
      v13 = TranslateInfStringW(
              pszInfFilenamea,
              pszInstallSectiona,
              pszTranslateSectiona,
              pszTranslateKeya,
              v8,
              cchBuffer,
              pdwRequiredSize,
              pvReserved);
      if ( v13 >= 0 && pszBuffer && cchBuffer )
        SHUnicodeToAnsi(v8, pszBuffer, cchBuffer);
    }
  }
  LocalFree(v8);
  LocalFree((HLOCAL)pszInfFilenamea);
  LocalFree((HLOCAL)pszInstallSectiona);
  LocalFree((HLOCAL)pszTranslateSectiona);
  LocalFree(v10);
  return v13;
}

```

## disassembly

```asm
0x18000bf80  push    rbp; TranslateInfString
0x18000bf82  push    rbx
0x18000bf83  push    rsi
0x18000bf84  push    rdi
0x18000bf85  push    r12
0x18000bf87  push    r14
0x18000bf89  push    r15
0x18000bf8b  mov     rbp, rsp
0x18000bf8e  sub     rsp, 60h
0x18000bf92  xor     edi, edi
0x18000bf94  mov     r15, rdx
0x18000bf97  xor     esi, esi
0x18000bf99  mov     [rbp+pszInfFilename], rdi
0x18000bf9d  lea     rdx, [rbp+pszInfFilename]
0x18000bfa1  mov     [rbp+pszInstallSection], rdi
0x18000bfa5  mov     [rbp+pszTranslateSection], rdi
0x18000bfa9  mov     rbx, r9
0x18000bfac  mov     [rbp+pszTranslateKey], rsi
0x18000bfb0  mov     r12, r8
0x18000bfb3  mov     r14d, 80004005h
0x18000bfb9  call    ThunkToUnicode
0x18000bfbe  test    eax, eax
0x18000bfc0  js      loc_18000C074
0x18000bfc6  lea     rdx, [rbp+pszInstallSection]
0x18000bfca  mov     rcx, r15; lpMultiByteStr
0x18000bfcd  call    ThunkToUnicode
0x18000bfd2  test    eax, eax
0x18000bfd4  js      loc_18000C074
0x18000bfda  lea     rdx, [rbp+pszTranslateSection]
0x18000bfde  mov     rcx, r12; lpMultiByteStr
0x18000bfe1  call    ThunkToUnicode
0x18000bfe6  test    eax, eax
0x18000bfe8  js      loc_18000C074
0x18000bfee  lea     rdx, [rbp+pszTranslateKey]
0x18000bff2  mov     rcx, rbx; lpMultiByteStr
0x18000bff5  call    ThunkToUnicode
0x18000bffa  test    eax, eax
0x18000bffc  js      short loc_18000C070
0x18000bffe  mov     ebx, [rbp+cchBuffer]
0x18000c001  test    ebx, ebx
0x18000c003  jz      short loc_18000C01B
0x18000c005  mov     edx, ebx
0x18000c007  lea     ecx, [rdi+40h]; uFlags
0x18000c00a  add     rdx, rdx; uBytes
0x18000c00d  call    cs:__imp_LocalAlloc
0x18000c013  mov     rdi, rax
0x18000c016  test    rax, rax
0x18000c019  jz      short loc_18000C070
0x18000c01b  mov     rax, [rbp+pvReserved]
0x18000c01f  mov     rsi, [rbp+pszTranslateKey]
0x18000c023  mov     r8, [rbp+pszTranslateSection]; pszTranslateSection
0x18000c027  mov     r9, rsi; pszTranslateKey
0x18000c02a  mov     rdx, [rbp+pszInstallSection]; pszInstallSection
0x18000c02e  mov     rcx, [rbp+pszInfFilename]; pszInfFilename
0x18000c032  mov     [rsp+60h+var_28], rax; pvReserved
0x18000c037  mov     rax, [rbp+pdwRequiredSize]
0x18000c03b  mov     [rsp+60h+var_30], rax; pdwRequiredSize
0x18000c040  mov     [rsp+60h+var_38], ebx; cchBuffer
0x18000c044  mov     [rsp+60h+var_40], rdi; pszBuffer
0x18000c049  call    TranslateInfStringW
0x18000c04e  mov     r14d, eax
0x18000c051  test    eax, eax
0x18000c053  js      short loc_18000C074
0x18000c055  mov     rdx, [rbp+pszBuffer]; pszDst
0x18000c059  test    rdx, rdx
0x18000c05c  jz      short loc_18000C074
0x18000c05e  test    ebx, ebx
0x18000c060  jz      short loc_18000C074
0x18000c062  mov     r8d, ebx; cchBuf
0x18000c065  mov     rcx, rdi; pwszSrc
0x18000c068  call    cs:__imp_SHUnicodeToAnsi
0x18000c06e  jmp     short loc_18000C074
0x18000c070  mov     rsi, [rbp+pszTranslateKey]
0x18000c074  mov     rcx, rdi; hMem
0x18000c077  call    cs:__imp_LocalFree
0x18000c07d  mov     rcx, [rbp+pszInfFilename]; hMem
0x18000c081  call    cs:__imp_LocalFree
0x18000c087  mov     rcx, [rbp+pszInstallSection]; hMem
0x18000c08b  call    cs:__imp_LocalFree
0x18000c091  mov     rcx, [rbp+pszTranslateSection]; hMem
0x18000c095  call    cs:__imp_LocalFree
0x18000c09b  mov     rcx, rsi; hMem
0x18000c09e  call    cs:__imp_LocalFree
0x18000c0a4  mov     eax, r14d
0x18000c0a7  add     rsp, 60h
0x18000c0ab  pop     r15
0x18000c0ad  pop     r14
0x18000c0af  pop     r12
0x18000c0b1  pop     rdi
0x18000c0b2  pop     rsi
0x18000c0b3  pop     rbx
0x18000c0b4  pop     rbp
0x18000c0b5  retn
```
