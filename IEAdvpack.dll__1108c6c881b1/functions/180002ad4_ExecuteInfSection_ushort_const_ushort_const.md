# ExecuteInfSection(ushort const *,ushort const *)

- ea: `0x180002ad4`
- end: `0x180002c6b`
- name: `?ExecuteInfSection@@YAJPEBG0@Z`
- size: `407`
- prototype: `__int64 __fastcall(unsigned __int16 *, WCHAR *lpAppName)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003be0`

## callees

- `0x1800022bc`
- `0x180002ad4`
- `0x180002d50`
- `0x180003ce0`
- `0x180003e20`
- `0x180006d24`
- `0x180007454`
- `0x18000bdb0`
- `0x18000f7b0`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180002b26`
- `KERNEL32!GetTempPath2W` at `0x180002b26`

## string_xrefs

- `0x180002b45`: `ComponentName`

## pseudocode

```c
__int64 __fastcall ExecuteInfSection(unsigned __int16 *a1, WCHAR *lpAppName)
{
  unsigned int v4; // ebx
  DWORD TranslatedInt; // ebx
  HRESULT v6; // eax
  unsigned int v7; // r8d
  CABINFOW pCab; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szDir[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v11[264]; // [rsp+480h] [rbp+380h] BYREF

  v4 = -2147467259;
  if ( (unsigned int)SaveGlobalContext() )
  {
    if ( (unsigned int)GetTempPath2W(260, szDir) <= 0x104 )
    {
      TranslatedInt = 0;
      if ( (int)GetTranslatedString(a1, lpAppName, L"ComponentName", v11, 0x104u, 0) >= 0 )
        TranslatedInt = GetTranslatedInt(a1, lpAppName, L"AdvOptions", 0);
      if ( (TranslatedInt & 0x20) == 0 && (TranslatedInt & 0x140) == 0 )
      {
        v6 = RunSetupCommandW(HWND_MESSAGE|0x2LL, a1, lpAppName, szDir, 0, 0, 5u, 0);
LABEL_14:
        v4 = v6;
        goto LABEL_15;
      }
      memset_0(&pCab, 0, sizeof(pCab));
      pCab.pszInf = a1;
      StringCchCopyW(pCab.szSrcPath, 0x104u, szDir);
      pCab.dwFlags = TranslatedInt;
      if ( (TranslatedInt & 0x20) != 0 )
      {
        pCab.pszSection = lpAppName;
LABEL_13:
        v6 = ExecuteCabW(0, &pCab, 0);
        goto LABEL_14;
      }
      if ( (unsigned int)GetRollbackSection(v11, (LPBYTE)szDir, v7) )
      {
        pCab.pszSection = szDir;
        goto LABEL_13;
      }
      v4 = -2147418113;
    }
LABEL_15:
    RestoreGlobalContext();
  }
  return v4;
}

```

## disassembly

```asm
0x180002ad4  mov     [rsp-8+arg_10], rbx
0x180002ad9  mov     [rsp-8+arg_18], rsi
0x180002ade  push    rbp
0x180002adf  push    rdi
0x180002ae0  push    r14
0x180002ae2  lea     rbp, [rsp-5A0h]
0x180002aea  sub     rsp, 6A0h
0x180002af1  mov     rax, cs:__security_cookie
0x180002af8  xor     rax, rsp
0x180002afb  mov     [rbp+5B0h+var_20], rax
0x180002b02  mov     rdi, rdx
0x180002b05  mov     r14, rcx
0x180002b08  mov     ebx, 80004005h
0x180002b0d  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x180002b12  test    eax, eax
0x180002b14  jz      loc_180002C42
0x180002b1a  lea     rdx, [rbp+5B0h+szDir]
0x180002b21  mov     ecx, 104h
0x180002b26  call    cs:__imp_GetTempPath2W
0x180002b2c  cmp     eax, 104h
0x180002b31  ja      loc_180002C3D
0x180002b37  xor     ebx, ebx
0x180002b39  lea     r9, [rbp+5B0h+var_230]; unsigned __int16 *
0x180002b40  mov     [rsp+6B0h+phEXE], rbx; unsigned int *
0x180002b45  lea     r8, KeyName; "ComponentName"
0x180002b4c  mov     rdx, rdi; lpAppName
0x180002b4f  mov     dword ptr [rsp+6B0h+lpszTitle], 104h; unsigned int
0x180002b57  mov     rcx, r14; unsigned __int16 *
0x180002b5a  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180002b5f  test    eax, eax
0x180002b61  js      short loc_180002B7A
0x180002b63  xor     r9d, r9d; nDefault
0x180002b66  lea     r8, Key; "AdvOptions"
0x180002b6d  mov     rdx, rdi; Section
0x180002b70  mov     rcx, r14; unsigned __int16 *
0x180002b73  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x180002b78  mov     ebx, eax
0x180002b7a  mov     esi, ebx
0x180002b7c  and     esi, 20h
0x180002b7f  jnz     short loc_180002BC4
0x180002b81  test    ebx, 140h
0x180002b87  jnz     short loc_180002BC4
0x180002b89  mov     [rsp+6B0h+pvReserved], 0; pvReserved
0x180002b92  lea     r9, [rbp+5B0h+szDir]; szDir
0x180002b99  mov     [rsp+6B0h+dwFlags], 5; dwFlags
0x180002ba1  mov     r8, rdi; szInfSection
0x180002ba4  mov     [rsp+6B0h+phEXE], 0; phEXE
0x180002bad  mov     rdx, r14; szCmdName
0x180002bb0  or      rcx, 0FFFFFFFFFFFFFFFFh; hWnd
0x180002bb4  mov     [rsp+6B0h+lpszTitle], 0; lpszTitle
0x180002bbd  call    RunSetupCommandW
0x180002bc2  jmp     short loc_180002C3B
0x180002bc4  xor     edx, edx; Val
0x180002bc6  lea     rcx, [rsp+6B0h+pCab]; void *
0x180002bcb  mov     r8d, 228h; Size
0x180002bd1  call    memset_0
0x180002bd6  lea     r8, [rbp+5B0h+szDir]; unsigned __int16 *
0x180002bdd  mov     [rsp+6B0h+pCab.pszInf], r14
0x180002be2  mov     edx, 104h; unsigned __int64
0x180002be7  lea     rcx, [rsp+6B0h+pCab.szSrcPath]; unsigned __int16 *
0x180002bec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002bf1  mov     [rbp+5B0h+pCab.dwFlags], ebx
0x180002bf7  test    esi, esi
0x180002bf9  jz      short loc_180002C02
0x180002bfb  mov     [rsp+6B0h+pCab.pszSection], rdi
0x180002c00  jmp     short loc_180002C2C
0x180002c02  lea     rdx, [rbp+5B0h+szDir]; lpData
0x180002c09  lea     rcx, [rbp+5B0h+var_230]; unsigned __int16 *
0x180002c10  call    ?GetRollbackSection@@YAHPEBGPEAGK@Z; GetRollbackSection(ushort const *,ushort *,ulong)
0x180002c15  test    eax, eax
0x180002c17  jnz     short loc_180002C20
0x180002c19  mov     ebx, 8000FFFFh
0x180002c1e  jmp     short loc_180002C3D
0x180002c20  lea     rax, [rbp+5B0h+szDir]
0x180002c27  mov     [rsp+6B0h+pCab.pszSection], rax
0x180002c2c  xor     r8d, r8d; pReserved
0x180002c2f  lea     rdx, [rsp+6B0h+pCab]; pCab
0x180002c34  xor     ecx, ecx; hwnd
0x180002c36  call    ExecuteCabW
0x180002c3b  mov     ebx, eax
0x180002c3d  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x180002c42  mov     eax, ebx
0x180002c44  mov     rcx, [rbp+5B0h+var_20]
0x180002c4b  xor     rcx, rsp; StackCookie
0x180002c4e  call    __security_check_cookie
0x180002c53  lea     r11, [rsp+6B0h+var_10]
0x180002c5b  mov     rbx, [r11+30h]
0x180002c5f  mov     rsi, [r11+38h]
0x180002c63  mov     rsp, r11
0x180002c66  pop     r14
0x180002c68  pop     rdi
0x180002c69  pop     rbp
0x180002c6a  retn
```
