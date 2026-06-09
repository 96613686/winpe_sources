# UserUnInstStubWrapperW

- ea: `0x180011940`
- end: `0x180011c8a`
- name: `UserUnInstStubWrapperW`
- size: `842`
- prototype: `HRESULT __stdcall(HWND hwnd, HINSTANCE hInstance, LPCWSTR pszParms, INT nShow)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800118d0`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x180008644`
- `0x180008a6c`
- `0x18000c574`
- `0x18000c8c8`
- `0x180011940`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011bcb`
- `KERNEL32!GetLastError` at `0x180011be0`
- `KERNEL32!GetLastError` at `0x180011bcb`
- `KERNEL32!GetLastError` at `0x180011be0`
- `KERNEL32!FormatMessageW` at `0x180011c0c`
- `KERNEL32!FormatMessageW` at `0x180011c0c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011b8b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011b8b`
- `ADVAPI32!RegQueryValueExW` at `0x180011b5b`
- `ADVAPI32!RegQueryValueExW` at `0x180011b5b`
- `ADVAPI32!RegCloseKey` at `0x180011aca`
- `ADVAPI32!RegCloseKey` at `0x180011ad5`
- `ADVAPI32!RegCloseKey` at `0x180011c43`
- `ADVAPI32!RegCloseKey` at `0x180011c4e`
- `ADVAPI32!RegCloseKey` at `0x180011aca`
- `ADVAPI32!RegCloseKey` at `0x180011ad5`
- `ADVAPI32!RegCloseKey` at `0x180011c43`
- `ADVAPI32!RegCloseKey` at `0x180011c4e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800119d0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800119f9`
- `ADVAPI32!RegOpenKeyExW` at `0x180011a89`
- `ADVAPI32!RegOpenKeyExW` at `0x180011b1c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800119d0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800119f9`
- `ADVAPI32!RegOpenKeyExW` at `0x180011a89`
- `ADVAPI32!RegOpenKeyExW` at `0x180011b1c`

## string_xrefs

- `0x180011b50`: `RealStubPath`
- `0x1800119c2`: `software\microsoft\Active Setup\Installed Components`
- `0x180011a0d`: `software\microsoft\Active Setup\Installed Components`

## pseudocode

```c
HRESULT __stdcall UserUnInstStubWrapperW(HWND hwnd, HINSTANCE hInstance, LPCWSTR pszParms, INT nShow)
{
  unsigned int v5; // ebx
  LPCWSTR v6; // rsi
  signed int LastError; // eax
  DWORD v8; // eax
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY v13; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v16; // [rsp+60h] [rbp-A0h] BYREF
  size_t pszPathOut[66]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[520]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[512]; // [rsp+690h] [rbp+590h] BYREF

  hKey = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  cbData = 0;
  Type = 0;
  if ( !pszParms || !*pszParms )
    return -2147024809;
  v5 = 0;
  AdvWriteToLog(L"UserUnInstStubWrapper:\r\n", hInstance, pszParms, nShow);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"software\\microsoft\\Active Setup\\Installed Components",
          0,
          0x2001Fu,
          &hKey) )
  {
    if ( !RegOpenKeyExW(hKey, pszParms, 0, 0x20019u, &v14) )
    {
      StringCchCopyW(
        (unsigned __int16 *)pszPathOut,
        0x104u,
        (size_t *)L"software\\microsoft\\Active Setup\\Installed Components");
      v6 = pszParms;
      if ( !(unsigned int)PathIsUnc2(
                            (unsigned __int16 *)pszParms,
                            0,
                            (unsigned __int8 (__fastcall *)(_QWORD))IsBackslash)
        && !IsExtendedLengthDosDevicePath(pszParms)
        && *pszParms == 92 )
      {
        do
          ++v6;
        while ( *v6 == 92 );
      }
      PathCchCombineEx((PWSTR)pszPathOut, 0x104u, (PCWSTR)pszPathOut, v6, phkResult);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, (LPCWSTR)pszPathOut, 0, 0x2001Fu, &v13) )
      {
        CopyRegValue(v14, v13, L"Version", L"Version");
        CopyRegValue(v14, v13, L"Locale", L"Locale");
        RegCloseKey(v13);
      }
      RegCloseKey(v14);
    }
    StringCchCopyW((unsigned __int16 *)pszPathOut, 0x104u, (size_t *)pszParms);
    StringCchCatW((unsigned __int16 *)pszPathOut, 260, L".Restore");
    if ( !RegOpenKeyExW(hKey, (LPCWSTR)pszPathOut, 0, 0x20019u, &v16) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(v16, L"RealStubPath", 0, &Type, (LPBYTE)pszPathOut, &cbData) && LOWORD(pszPathOut[0]) )
      {
        if ( Type == 2 )
          ExpandEnvironmentStringsW((LPCWSTR)pszPathOut, Dst, 0x208u);
        else
          StringCchCopyW(Dst, 0x208u, pszPathOut);
        if ( (unsigned int)LaunchAndWait(Dst, 0, 0, 0xFFFFFFFF, 1) == -2147467259 )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          v8 = GetLastError();
          FormatMessageW(0x1000u, 0, v8, 0, Buffer, 0x200u, 0);
          MsgBox2Param(hWnd, 0x476u, Dst, Buffer, 0x10u, 0);
        }
      }
      RegCloseKey(v16);
    }
    RegCloseKey(hKey);
  }
  AdvWriteToLog(L"UserUnInstStubWrapper: End hr=0x%1!x!\r\n", v5);
  return v5;
}

```

## disassembly

```asm
0x180011940  push    rbp
0x180011942  push    rbx
0x180011943  push    rsi
0x180011944  push    rdi
0x180011945  push    r14
0x180011947  push    r15
0x180011949  lea     rbp, [rsp-9A8h]
0x180011951  sub     rsp, 0AA8h
0x180011958  mov     rax, cs:__security_cookie
0x18001195f  xor     rax, rsp
0x180011962  mov     [rbp+9D0h+var_40], rax
0x180011969  xor     r14d, r14d
0x18001196c  mov     rdi, r8
0x18001196f  mov     [rsp+0AD0h+hKey], r14
0x180011974  mov     [rsp+0AD0h+var_A70], r14
0x180011979  mov     [rsp+0AD0h+var_A80], r14
0x18001197e  mov     [rsp+0AD0h+var_A88], r14
0x180011983  mov     [rsp+0AD0h+cbData], r14d
0x180011988  mov     [rsp+0AD0h+Type], r14d
0x18001198d  test    r8, r8
0x180011990  jz      loc_180011C66
0x180011996  cmp     [r8], r14w
0x18001199a  jz      loc_180011C66
0x1800119a0  lea     rcx, aUseruninststub_3; "UserUnInstStubWrapper:\r\n"
0x1800119a7  mov     ebx, r14d
0x1800119aa  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800119af  lea     rax, [rsp+0AD0h+hKey]
0x1800119b4  mov     r9d, 2001Fh; samDesired
0x1800119ba  xor     r8d, r8d; ulOptions
0x1800119bd  mov     [rsp+0AD0h+phkResult], rax; phkResult
0x1800119c2  lea     rdx, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x1800119c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800119d0  call    cs:__imp_RegOpenKeyExW
0x1800119d6  test    eax, eax
0x1800119d8  jnz     loc_180011C54
0x1800119de  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x1800119e3  lea     rax, [rsp+0AD0h+var_A80]
0x1800119e8  mov     r9d, 20019h; samDesired
0x1800119ee  mov     [rsp+0AD0h+phkResult], rax; dwFlags
0x1800119f3  xor     r8d, r8d; ulOptions
0x1800119f6  mov     rdx, rdi; lpSubKey
0x1800119f9  call    cs:__imp_RegOpenKeyExW
0x1800119ff  mov     r15d, 104h
0x180011a05  test    eax, eax
0x180011a07  jnz     loc_180011ADB
0x180011a0d  lea     r8, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x180011a14  mov     edx, r15d; unsigned __int64
0x180011a17  lea     rcx, [rsp+0AD0h+pszPathOut]; unsigned __int16 *
0x180011a1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011a21  lea     r8, IsBackslash
0x180011a28  xor     edx, edx
0x180011a2a  mov     rcx, rdi; unsigned __int16 *
0x180011a2d  mov     rsi, rdi
0x180011a30  call    PathIsUnc2
0x180011a35  test    eax, eax
0x180011a37  jnz     short loc_180011A55
0x180011a39  mov     rcx, rdi; unsigned __int16 *
0x180011a3c  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180011a41  test    al, al
0x180011a43  jnz     short loc_180011A55
0x180011a45  cmp     word ptr [rdi], 5Ch ; '\'
0x180011a49  jnz     short loc_180011A55
0x180011a4b  add     rsi, 2
0x180011a4f  cmp     word ptr [rsi], 5Ch ; '\'
0x180011a53  jz      short loc_180011A4B
0x180011a55  mov     r9, rsi; pszMore
0x180011a58  lea     r8, [rsp+0AD0h+pszPathOut]; pszPathIn
0x180011a5d  mov     rdx, r15; cchPathOut
0x180011a60  lea     rcx, [rsp+0AD0h+pszPathOut]; pszPathOut
0x180011a65  call    PathCchCombineEx
0x180011a6a  lea     rax, [rsp+0AD0h+var_A88]
0x180011a6f  mov     r9d, 2001Fh; samDesired
0x180011a75  xor     r8d, r8d; ulOptions
0x180011a78  mov     [rsp+0AD0h+phkResult], rax; phkResult
0x180011a7d  lea     rdx, [rsp+0AD0h+pszPathOut]; lpSubKey
0x180011a82  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011a89  call    cs:__imp_RegOpenKeyExW
0x180011a8f  test    eax, eax
0x180011a91  jnz     short loc_180011AD0
0x180011a93  mov     rdx, [rsp+0AD0h+var_A88]; HKEY
0x180011a98  lea     r8, aVersion; "Version"
0x180011a9f  mov     rcx, [rsp+0AD0h+var_A80]; HKEY
0x180011aa4  mov     r9, r8; unsigned __int16 *
0x180011aa7  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011aac  mov     rdx, [rsp+0AD0h+var_A88]; HKEY
0x180011ab1  lea     r8, aLocale; "Locale"
0x180011ab8  mov     rcx, [rsp+0AD0h+var_A80]; HKEY
0x180011abd  mov     r9, r8; unsigned __int16 *
0x180011ac0  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011ac5  mov     rcx, [rsp+0AD0h+var_A88]; hKey
0x180011aca  call    cs:__imp_RegCloseKey
0x180011ad0  mov     rcx, [rsp+0AD0h+var_A80]; hKey
0x180011ad5  call    cs:__imp_RegCloseKey
0x180011adb  mov     r8, rdi; unsigned __int16 *
0x180011ade  lea     rcx, [rsp+0AD0h+pszPathOut]; unsigned __int16 *
0x180011ae3  mov     rdx, r15; unsigned __int64
0x180011ae6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011aeb  lea     r8, aRestore; ".Restore"
0x180011af2  mov     rdx, r15; unsigned __int64
0x180011af5  lea     rcx, [rsp+0AD0h+pszPathOut]; unsigned __int16 *
0x180011afa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011aff  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x180011b04  lea     rax, [rsp+0AD0h+var_A70]
0x180011b09  mov     r9d, 20019h; samDesired
0x180011b0f  mov     [rsp+0AD0h+phkResult], rax; phkResult
0x180011b14  xor     r8d, r8d; ulOptions
0x180011b17  lea     rdx, [rsp+0AD0h+pszPathOut]; lpSubKey
0x180011b1c  call    cs:__imp_RegOpenKeyExW
0x180011b22  test    eax, eax
0x180011b24  jnz     loc_180011C49
0x180011b2a  mov     rcx, [rsp+0AD0h+var_A70]; hKey
0x180011b2f  lea     rax, [rsp+0AD0h+cbData]
0x180011b34  mov     [rsp+0AD0h+lpcbData], rax; lpcbData
0x180011b39  lea     r9, [rsp+0AD0h+Type]; lpType
0x180011b3e  lea     rax, [rsp+0AD0h+pszPathOut]
0x180011b43  mov     edi, 208h
0x180011b48  xor     r8d, r8d; lpReserved
0x180011b4b  mov     [rsp+0AD0h+phkResult], rax; lpData
0x180011b50  lea     rdx, aRealstubpath; "RealStubPath"
0x180011b57  mov     [rsp+0AD0h+cbData], edi
0x180011b5b  call    cs:__imp_RegQueryValueExW
0x180011b61  test    eax, eax
0x180011b63  jnz     loc_180011C3E
0x180011b69  cmp     word ptr [rsp+0AD0h+pszPathOut], r14w
0x180011b6f  jz      loc_180011C3E
0x180011b75  cmp     [rsp+0AD0h+Type], 2
0x180011b7a  jnz     short loc_180011B93
0x180011b7c  mov     r8d, edi; nSize
0x180011b7f  lea     rdx, [rbp+9D0h+Dst]; lpDst
0x180011b86  lea     rcx, [rsp+0AD0h+pszPathOut]; lpSrc
0x180011b8b  call    cs:__imp_ExpandEnvironmentStringsW
0x180011b91  jmp     short loc_180011BA7
0x180011b93  lea     r8, [rsp+0AD0h+pszPathOut]; unsigned __int16 *
0x180011b98  mov     rdx, rdi; unsigned __int64
0x180011b9b  lea     rcx, [rbp+9D0h+Dst]; unsigned __int16 *
0x180011ba2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011ba7  or      r9d, 0FFFFFFFFh; unsigned int
0x180011bab  mov     dword ptr [rsp+0AD0h+phkResult], 1; unsigned int
0x180011bb3  xor     r8d, r8d; void **
0x180011bb6  lea     rcx, [rbp+9D0h+Dst]; unsigned __int16 *
0x180011bbd  xor     edx, edx; lpCurrentDirectory
0x180011bbf  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x180011bc4  cmp     eax, 80004005h
0x180011bc9  jnz     short loc_180011C3E
0x180011bcb  call    cs:__imp_GetLastError
0x180011bd1  mov     ebx, eax
0x180011bd3  test    eax, eax
0x180011bd5  jle     short loc_180011BE0
0x180011bd7  movzx   ebx, ax
0x180011bda  or      ebx, 80070000h
0x180011be0  call    cs:__imp_GetLastError
0x180011be6  mov     [rsp+0AD0h+Arguments], r14; Arguments
0x180011beb  xor     r9d, r9d; dwLanguageId
0x180011bee  mov     r8d, eax; dwMessageId
0x180011bf1  mov     dword ptr [rsp+0AD0h+lpcbData], 200h; nSize
0x180011bf9  lea     rax, [rbp+9D0h+Buffer]
0x180011c00  xor     edx, edx; lpSource
0x180011c02  mov     ecx, 1000h; dwFlags
0x180011c07  mov     [rsp+0AD0h+phkResult], rax; lpBuffer
0x180011c0c  call    cs:__imp_FormatMessageW
0x180011c12  mov     rcx, cs:hWnd; hWnd
0x180011c19  lea     r9, [rbp+9D0h+Buffer]; unsigned __int16 *
0x180011c20  lea     r8, [rbp+9D0h+Dst]; unsigned __int16 *
0x180011c27  mov     dword ptr [rsp+0AD0h+lpcbData], r14d; unsigned int
0x180011c2c  mov     edx, 476h; uID
0x180011c31  mov     dword ptr [rsp+0AD0h+phkResult], 10h; unsigned int
0x180011c39  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180011c3e  mov     rcx, [rsp+0AD0h+var_A70]; hKey
0x180011c43  call    cs:__imp_RegCloseKey
0x180011c49  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x180011c4e  call    cs:__imp_RegCloseKey
0x180011c54  mov     edx, ebx
0x180011c56  lea     rcx, aUseruninststub_2; "UserUnInstStubWrapper: End hr=0x%1!x!\r"...
0x180011c5d  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180011c62  mov     eax, ebx
0x180011c64  jmp     short loc_180011C6B
0x180011c66  mov     eax, 80070057h
0x180011c6b  mov     rcx, [rbp+9D0h+var_40]
0x180011c72  xor     rcx, rsp; StackCookie
0x180011c75  call    __security_check_cookie
0x180011c7a  add     rsp, 0AA8h
0x180011c81  pop     r15
0x180011c83  pop     r14
0x180011c85  pop     rdi
0x180011c86  pop     rsi
0x180011c87  pop     rbx
0x180011c88  pop     rbp
0x180011c89  retn
```
