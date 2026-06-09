# UserInstStubWrapperW

- ea: `0x1800115b0`
- end: `0x1800118c5`
- name: `UserInstStubWrapperW`
- size: `789`
- prototype: `HRESULT __stdcall(HWND hwnd, HINSTANCE hInstance, LPCWSTR pszParms, INT nShow)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011540`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x180008644`
- `0x180008a6c`
- `0x18000c574`
- `0x18000c8c8`
- `0x1800115b0`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011707`
- `KERNEL32!GetLastError` at `0x18001171c`
- `KERNEL32!GetLastError` at `0x180011707`
- `KERNEL32!GetLastError` at `0x18001171c`
- `KERNEL32!FormatMessageW` at `0x180011748`
- `KERNEL32!FormatMessageW` at `0x180011748`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800116c4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800116c4`
- `ADVAPI32!RegCreateKeyExW` at `0x180011836`
- `ADVAPI32!RegCreateKeyExW` at `0x180011836`
- `ADVAPI32!RegQueryValueExW` at `0x180011697`
- `ADVAPI32!RegQueryValueExW` at `0x180011697`
- `ADVAPI32!RegCloseKey` at `0x18001177e`
- `ADVAPI32!RegCloseKey` at `0x180011789`
- `ADVAPI32!RegCloseKey` at `0x180011877`
- `ADVAPI32!RegCloseKey` at `0x180011882`
- `ADVAPI32!RegCloseKey` at `0x18001188d`
- `ADVAPI32!RegCloseKey` at `0x18001177e`
- `ADVAPI32!RegCloseKey` at `0x180011789`
- `ADVAPI32!RegCloseKey` at `0x180011877`
- `ADVAPI32!RegCloseKey` at `0x180011882`
- `ADVAPI32!RegCloseKey` at `0x18001188d`
- `ADVAPI32!RegOpenKeyExW` at `0x180011633`
- `ADVAPI32!RegOpenKeyExW` at `0x180011659`
- `ADVAPI32!RegOpenKeyExW` at `0x180011633`
- `ADVAPI32!RegOpenKeyExW` at `0x180011659`

## string_xrefs

- `0x18001168c`: `RealStubPath`
- `0x180011625`: `software\microsoft\Active Setup\Installed Components`
- `0x18001179b`: `software\microsoft\Active Setup\Installed Components`

## pseudocode

```c
HRESULT __stdcall UserInstStubWrapperW(HWND hwnd, HINSTANCE hInstance, LPCWSTR pszParms, INT nShow)
{
  WCHAR *v4; // rbx
  signed int LastError; // eax
  HRESULT v6; // ebx
  DWORD v7; // eax
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v11; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v13; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  size_t Data[66]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Dst[520]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Buffer[512]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v4 = (WCHAR *)pszParms;
  hKey = 0;
  v13 = 0;
  v11 = 0;
  cbData = 0;
  Type = 0;
  if ( !pszParms || !*pszParms )
    return -2147024809;
  AdvWriteToLog(L"UserInstStubWrapper:\r\n", hInstance, pszParms, nShow);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"software\\microsoft\\Active Setup\\Installed Components", 0, 0x20019u, &hKey) )
  {
LABEL_23:
    AdvWriteToLog(L"UserInstStubWrapper: End hr=0x%1!x!\r\n", 0);
    return 0;
  }
  if ( RegOpenKeyExW(hKey, v4, 0, 0x20019u, &v11) )
  {
LABEL_22:
    RegCloseKey(hKey);
    goto LABEL_23;
  }
  cbData = 520;
  if ( RegQueryValueExW(v11, L"RealStubPath", 0, &Type, (LPBYTE)Data, &cbData) || !LOWORD(Data[0]) )
    goto LABEL_14;
  if ( Type == 2 )
    ExpandEnvironmentStringsW((LPCWSTR)Data, Dst, 0x208u);
  else
    StringCchCopyW(Dst, 0x208u, Data);
  if ( (unsigned int)LaunchAndWait(Dst, 0, 0, 0xFFFFFFFF, 1) != -2147467259 )
  {
LABEL_14:
    StringCchCopyW(
      (unsigned __int16 *)Data,
      0x104u,
      (size_t *)L"software\\microsoft\\Active Setup\\Installed Components");
    if ( !(unsigned int)PathIsUnc2(v4, 0, (unsigned __int8 (__fastcall *)(_QWORD))IsBackslash)
      && !IsExtendedLengthDosDevicePath(v4) )
    {
      while ( *v4 == 92 )
        ++v4;
    }
    PathCchCombineEx((PWSTR)Data, 0x104u, (PCWSTR)Data, v4, phkResult);
    StringCchCatW((unsigned __int16 *)Data, 260, L".Restore");
    if ( !RegCreateKeyExW(HKEY_CURRENT_USER, (LPCWSTR)Data, 0, 0, 0, 0x2001Fu, 0, &v13, &cbData) )
    {
      CopyRegValue(v11, v13, L"Version", L"Version");
      CopyRegValue(v11, v13, L"Locale", L"Locale");
      RegCloseKey(v13);
    }
    RegCloseKey(v11);
    goto LABEL_22;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v7 = GetLastError();
  FormatMessageW(0x1000u, 0, v7, 0, Buffer, 0x200u, 0);
  MsgBox2Param(hWnd, 0x476u, Dst, Buffer, 0x10u, 0);
  RegCloseKey(v11);
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800115b0  push    rbp
0x1800115b2  push    rbx
0x1800115b3  push    rsi
0x1800115b4  push    rdi
0x1800115b5  lea     rbp, [rsp-9B8h]
0x1800115bd  sub     rsp, 0AB8h
0x1800115c4  mov     rax, cs:__security_cookie
0x1800115cb  xor     rax, rsp
0x1800115ce  mov     [rbp+9D0h+var_30], rax
0x1800115d5  xor     edi, edi
0x1800115d7  mov     rbx, r8
0x1800115da  mov     [rsp+0AD0h+hKey], rdi
0x1800115df  mov     [rsp+0AD0h+var_A68], rdi
0x1800115e4  mov     [rsp+0AD0h+var_A78], rdi
0x1800115e9  mov     [rsp+0AD0h+cbData], edi
0x1800115ed  mov     [rsp+0AD0h+Type], edi
0x1800115f1  test    r8, r8
0x1800115f4  jz      loc_1800118A5
0x1800115fa  cmp     [r8], di
0x1800115fe  jz      loc_1800118A5
0x180011604  lea     rcx, aUserinststubwr_3; "UserInstStubWrapper:\r\n"
0x18001160b  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180011610  lea     rax, [rsp+0AD0h+hKey]
0x180011615  mov     esi, 20019h
0x18001161a  mov     r9d, esi; samDesired
0x18001161d  mov     [rsp+0AD0h+phkResult], rax; phkResult
0x180011622  xor     r8d, r8d; ulOptions
0x180011625  lea     rdx, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x18001162c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011633  call    cs:__imp_RegOpenKeyExW
0x180011639  test    eax, eax
0x18001163b  jnz     loc_180011893
0x180011641  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x180011646  lea     rax, [rsp+0AD0h+var_A78]
0x18001164b  mov     r9d, esi; samDesired
0x18001164e  mov     [rsp+0AD0h+phkResult], rax; phkResult
0x180011653  xor     r8d, r8d; ulOptions
0x180011656  mov     rdx, rbx; lpSubKey
0x180011659  call    cs:__imp_RegOpenKeyExW
0x18001165f  test    eax, eax
0x180011661  jnz     loc_180011888
0x180011667  mov     rcx, [rsp+0AD0h+var_A78]; hKey
0x18001166c  lea     rax, [rsp+0AD0h+cbData]
0x180011671  mov     [rsp+0AD0h+lpcbData], rax; lpcbData
0x180011676  lea     r9, [rsp+0AD0h+Type]; lpType
0x18001167b  lea     rax, [rbp+9D0h+Data]
0x18001167f  mov     esi, 208h
0x180011684  xor     r8d, r8d; lpReserved
0x180011687  mov     [rsp+0AD0h+phkResult], rax; lpData
0x18001168c  lea     rdx, aRealstubpath; "RealStubPath"
0x180011693  mov     [rsp+0AD0h+cbData], esi
0x180011697  call    cs:__imp_RegQueryValueExW
0x18001169d  test    eax, eax
0x18001169f  jnz     loc_180011796
0x1800116a5  cmp     word ptr [rbp+9D0h+Data], di
0x1800116a9  jz      loc_180011796
0x1800116af  cmp     [rsp+0AD0h+Type], 2
0x1800116b4  jnz     short loc_1800116CC
0x1800116b6  mov     r8d, esi; nSize
0x1800116b9  lea     rdx, [rbp+9D0h+Dst]; lpDst
0x1800116c0  lea     rcx, [rbp+9D0h+Data]; lpSrc
0x1800116c4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800116ca  jmp     short loc_1800116DF
0x1800116cc  lea     r8, [rbp+9D0h+Data]; unsigned __int16 *
0x1800116d0  mov     rdx, rsi; unsigned __int64
0x1800116d3  lea     rcx, [rbp+9D0h+Dst]; unsigned __int16 *
0x1800116da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800116df  or      r9d, 0FFFFFFFFh; unsigned int
0x1800116e3  mov     dword ptr [rsp+0AD0h+phkResult], 1; unsigned int
0x1800116eb  xor     r8d, r8d; void **
0x1800116ee  lea     rcx, [rbp+9D0h+Dst]; unsigned __int16 *
0x1800116f5  xor     edx, edx; lpCurrentDirectory
0x1800116f7  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x1800116fc  cmp     eax, 80004005h
0x180011701  jnz     loc_180011796
0x180011707  call    cs:__imp_GetLastError
0x18001170d  mov     ebx, eax
0x18001170f  test    eax, eax
0x180011711  jle     short loc_18001171C
0x180011713  movzx   ebx, ax
0x180011716  or      ebx, 80070000h
0x18001171c  call    cs:__imp_GetLastError
0x180011722  mov     [rsp+0AD0h+Arguments], rdi; Arguments
0x180011727  xor     r9d, r9d; dwLanguageId
0x18001172a  mov     r8d, eax; dwMessageId
0x18001172d  mov     dword ptr [rsp+0AD0h+lpcbData], 200h; nSize
0x180011735  lea     rax, [rbp+9D0h+Buffer]
0x18001173c  xor     edx, edx; lpSource
0x18001173e  mov     ecx, 1000h; dwFlags
0x180011743  mov     [rsp+0AD0h+phkResult], rax; lpBuffer
0x180011748  call    cs:__imp_FormatMessageW
0x18001174e  mov     rcx, cs:hWnd; hWnd
0x180011755  lea     r9, [rbp+9D0h+Buffer]; unsigned __int16 *
0x18001175c  lea     r8, [rbp+9D0h+Dst]; unsigned __int16 *
0x180011763  mov     dword ptr [rsp+0AD0h+lpcbData], edi; unsigned int
0x180011767  mov     edx, 476h; uID
0x18001176c  mov     dword ptr [rsp+0AD0h+phkResult], 10h; unsigned int
0x180011774  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180011779  mov     rcx, [rsp+0AD0h+var_A78]; hKey
0x18001177e  call    cs:__imp_RegCloseKey
0x180011784  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x180011789  call    cs:__imp_RegCloseKey
0x18001178f  mov     eax, ebx
0x180011791  jmp     loc_1800118AA
0x180011796  mov     esi, 104h
0x18001179b  lea     r8, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x1800117a2  mov     edx, esi; unsigned __int64
0x1800117a4  lea     rcx, [rbp+9D0h+Data]; unsigned __int16 *
0x1800117a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800117ad  lea     r8, IsBackslash
0x1800117b4  xor     edx, edx
0x1800117b6  mov     rcx, rbx; unsigned __int16 *
0x1800117b9  call    PathIsUnc2
0x1800117be  test    eax, eax
0x1800117c0  jnz     short loc_1800117DA
0x1800117c2  mov     rcx, rbx; unsigned __int16 *
0x1800117c5  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x1800117ca  test    al, al
0x1800117cc  jnz     short loc_1800117DA
0x1800117ce  jmp     short loc_1800117D4
0x1800117d0  add     rbx, 2
0x1800117d4  cmp     word ptr [rbx], 5Ch ; '\'
0x1800117d8  jz      short loc_1800117D0
0x1800117da  mov     r9, rbx; pszMore
0x1800117dd  lea     r8, [rbp+9D0h+Data]; pszPathIn
0x1800117e1  mov     rdx, rsi; cchPathOut
0x1800117e4  lea     rcx, [rbp+9D0h+Data]; pszPathOut
0x1800117e8  call    PathCchCombineEx
0x1800117ed  lea     r8, aRestore; ".Restore"
0x1800117f4  mov     rdx, rsi; unsigned __int64
0x1800117f7  lea     rcx, [rbp+9D0h+Data]; unsigned __int16 *
0x1800117fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011800  lea     rax, [rsp+0AD0h+cbData]
0x180011805  xor     r9d, r9d; lpClass
0x180011808  mov     [rsp+0AD0h+lpdwDisposition], rax; lpdwDisposition
0x18001180d  lea     rdx, [rbp+9D0h+Data]; lpSubKey
0x180011811  lea     rax, [rsp+0AD0h+var_A68]
0x180011816  xor     r8d, r8d; Reserved
0x180011819  mov     [rsp+0AD0h+var_A98], rax; phkResult
0x18001181e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011825  mov     [rsp+0AD0h+Arguments], rdi; lpSecurityAttributes
0x18001182a  mov     dword ptr [rsp+0AD0h+lpcbData], 2001Fh; samDesired
0x180011832  mov     dword ptr [rsp+0AD0h+phkResult], edi; dwOptions
0x180011836  call    cs:__imp_RegCreateKeyExW
0x18001183c  test    eax, eax
0x18001183e  jnz     short loc_18001187D
0x180011840  mov     rdx, [rsp+0AD0h+var_A68]; HKEY
0x180011845  lea     r8, aVersion; "Version"
0x18001184c  mov     rcx, [rsp+0AD0h+var_A78]; HKEY
0x180011851  mov     r9, r8; unsigned __int16 *
0x180011854  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011859  mov     rdx, [rsp+0AD0h+var_A68]; HKEY
0x18001185e  lea     r8, aLocale; "Locale"
0x180011865  mov     rcx, [rsp+0AD0h+var_A78]; HKEY
0x18001186a  mov     r9, r8; unsigned __int16 *
0x18001186d  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011872  mov     rcx, [rsp+0AD0h+var_A68]; hKey
0x180011877  call    cs:__imp_RegCloseKey
0x18001187d  mov     rcx, [rsp+0AD0h+var_A78]; hKey
0x180011882  call    cs:__imp_RegCloseKey
0x180011888  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x18001188d  call    cs:__imp_RegCloseKey
0x180011893  xor     edx, edx
0x180011895  lea     rcx, aUserinststubwr_2; "UserInstStubWrapper: End hr=0x%1!x!\r\n"
0x18001189c  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800118a1  xor     eax, eax
0x1800118a3  jmp     short loc_1800118AA
0x1800118a5  mov     eax, 80070057h
0x1800118aa  mov     rcx, [rbp+9D0h+var_30]
0x1800118b1  xor     rcx, rsp; StackCookie
0x1800118b4  call    __security_check_cookie
0x1800118b9  add     rsp, 0AB8h
0x1800118c0  pop     rdi
0x1800118c1  pop     rsi
0x1800118c2  pop     rbx
0x1800118c3  pop     rbp
0x1800118c4  retn
```
