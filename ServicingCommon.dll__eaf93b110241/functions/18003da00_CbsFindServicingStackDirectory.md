# CbsFindServicingStackDirectory

- ea: `0x18003da00`
- end: `0x18003dd0d`
- name: `CbsFindServicingStackDirectory`
- size: `781`
- prototype: `__int64 __fastcall(LPWSTR lpDst, DWORD nSize)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001e4fc`
- `0x18001e51c`
- `0x1800293a0`
- `0x18003d00c`
- `0x18003d030`
- `0x18003d7d4`
- `0x18003d7f8`
- `0x18003da00`
- `0x180099cb0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003dc3f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003dc3f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003da77`
- `ADVAPI32!RegOpenKeyExW` at `0x18003da77`
- `ADVAPI32!RegEnumValueW` at `0x18003db16`
- `ADVAPI32!RegEnumValueW` at `0x18003dc12`
- `ADVAPI32!RegEnumValueW` at `0x18003db16`
- `ADVAPI32!RegEnumValueW` at `0x18003dc12`

## string_xrefs

- `0x18003da69`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Version`

## pseudocode

```c
__int64 __fastcall CbsFindServicingStackDirectory(LPWSTR lpDst, DWORD nSize, unsigned int *a3, unsigned int *a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  int v10; // r12d
  unsigned int v11; // ebx
  unsigned int v12; // edi
  int v13; // ebx
  unsigned int v14; // r11d
  DWORD v15; // eax
  const char *v16; // r9
  int LastError; // eax
  __int64 v18; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwIndex; // [rsp+48h] [rbp-B8h]
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Data[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Src[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  memset(Src, 0, 0x208u);
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Version",
         0,
         0x20019u,
         &hKey);
  if ( v8 )
  {
    v9 = 79;
LABEL_22:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\base\\cbs\\findstack\\cbsfindservicingstack.cpp",
                  (const char *)v8,
                  phkResult);
LABEL_23:
    v13 = LastError;
    goto LABEL_26;
  }
  dwIndex = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  memset(ValueName, 0, 0x208u);
  cchValueName = 260;
  Type = 0;
  memset(Data, 0, 0x208u);
  cbData = 518;
  v21 = 0;
  v8 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
  if ( v8 == 259 )
  {
LABEL_24:
    v13 = -2147023728;
    v18 = 122;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\findstack\\cbsfindservicingstack.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
LABEL_26:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v13;
  }
  do
  {
    if ( v8 )
    {
      v9 = 104;
      goto LABEL_22;
    }
    if ( !(unsigned int)FileVersionFromString_0(ValueName, (char *)&v21 + 4, &v21) && __PAIR64__(v11, v12) < v21 )
    {
      v13 = StringCchCopyW(Src, 0x104u, Data);
      if ( v13 < 0 )
      {
        v18 = 115;
        goto LABEL_25;
      }
      v12 = v21;
      v10 = 1;
      v11 = v14;
    }
    ++dwIndex;
    memset(ValueName, 0, 0x208u);
    cchValueName = 260;
    Type = 0;
    memset(Data, 0, 0x208u);
    cbData = 518;
    v21 = 0;
    v8 = RegEnumValueW(hKey, dwIndex, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
  }
  while ( v8 != 259 );
  if ( !v10 )
    goto LABEL_24;
  v15 = ExpandEnvironmentStringsW(Src, lpDst, nSize);
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\base\\cbs\\findstack\\cbsfindservicingstack.cpp",
                  v16);
    goto LABEL_23;
  }
  if ( v15 > nSize )
  {
    v13 = -2147024774;
    v18 = 130;
    goto LABEL_25;
  }
  if ( a3 )
    *a3 = v11;
  if ( a4 )
    *a4 = v12;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18003da00  push    rbp
0x18003da02  push    rbx
0x18003da03  push    rsi
0x18003da04  push    rdi
0x18003da05  push    r12
0x18003da07  push    r13
0x18003da09  push    r14
0x18003da0b  push    r15
0x18003da0d  lea     rbp, [rsp-5A8h]
0x18003da15  sub     rsp, 6A8h
0x18003da1c  mov     rax, cs:__security_cookie
0x18003da23  xor     rax, rsp
0x18003da26  mov     [rbp+5E0h+var_50], rax
0x18003da2d  mov     r14, r8
0x18003da30  mov     r15d, edx
0x18003da33  mov     r13, rcx
0x18003da36  xor     edx, edx; Val
0x18003da38  mov     r8d, 208h; Size
0x18003da3e  lea     rcx, [rbp+5E0h+Src]; void *
0x18003da45  mov     rsi, r9
0x18003da48  call    memset
0x18003da4d  lea     rax, [rsp+6E0h+hKey]
0x18003da52  mov     [rsp+6E0h+hKey], 0
0x18003da5b  mov     r9d, 20019h; samDesired
0x18003da61  mov     [rsp+6E0h+phkResult], rax; phkResult
0x18003da66  xor     r8d, r8d; ulOptions
0x18003da69  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003da70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003da77  call    cs:__imp_RegOpenKeyExW
0x18003da7e  nop     dword ptr [rax+rax+00h]
0x18003da83  test    eax, eax
0x18003da85  jz      short loc_18003DA91
0x18003da87  mov     edx, 4Fh ; 'O'
0x18003da8c  jmp     loc_18003DCA3
0x18003da91  xor     edx, edx; Val
0x18003da93  lea     rcx, [rbp+5E0h+ValueName]; void *
0x18003da9a  mov     r8d, 208h; Size
0x18003daa0  mov     [rsp+6E0h+dwIndex], edx
0x18003daa4  xor     r12d, r12d
0x18003daa7  xor     ebx, ebx
0x18003daa9  xor     edi, edi
0x18003daab  call    memset
0x18003dab0  xor     edx, edx; Val
0x18003dab2  mov     [rsp+6E0h+cchValueName], 104h
0x18003daba  mov     r8d, 208h; Size
0x18003dac0  mov     [rsp+6E0h+Type], ebx
0x18003dac4  lea     rcx, [rsp+6E0h+Data]; void *
0x18003dac9  call    memset
0x18003dace  xor     ecx, ecx
0x18003dad0  mov     [rsp+6E0h+cbData], 206h
0x18003dad8  lea     rax, [rsp+6E0h+cbData]
0x18003dadd  mov     dword ptr [rsp+6E0h+var_6A0+4], ecx
0x18003dae1  mov     [rsp+6E0h+lpcbData], rax; lpcbData
0x18003dae6  lea     r9, [rsp+6E0h+cchValueName]; lpcchValueName
0x18003daeb  lea     rax, [rsp+6E0h+Data]
0x18003daf0  mov     dword ptr [rsp+6E0h+var_6A0], ecx
0x18003daf4  mov     [rsp+6E0h+lpData], rax; lpData
0x18003daf9  lea     r8, [rbp+5E0h+ValueName]; lpValueName
0x18003db00  lea     rax, [rsp+6E0h+Type]
0x18003db05  xor     edx, edx; dwIndex
0x18003db07  mov     [rsp+6E0h+lpType], rax; lpType
0x18003db0c  mov     [rsp+6E0h+phkResult], rcx; int
0x18003db11  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003db16  call    cs:__imp_RegEnumValueW
0x18003db1d  nop     dword ptr [rax+rax+00h]
0x18003db22  cmp     eax, 103h
0x18003db27  jz      loc_18003DCBD
0x18003db2d  test    eax, eax
0x18003db2f  jnz     loc_18003DC9E
0x18003db35  lea     r8, [rsp+6E0h+var_6A0]
0x18003db3a  lea     rdx, [rsp+6E0h+var_6A0+4]
0x18003db3f  lea     rcx, [rbp+5E0h+ValueName]
0x18003db46  call    FileVersionFromString_0
0x18003db4b  test    eax, eax
0x18003db4d  jnz     short loc_18003DB8E
0x18003db4f  mov     r11d, dword ptr [rsp+6E0h+var_6A0+4]
0x18003db54  cmp     ebx, r11d
0x18003db57  jb      short loc_18003DB61
0x18003db59  jnz     short loc_18003DB8E
0x18003db5b  cmp     edi, dword ptr [rsp+6E0h+var_6A0]
0x18003db5f  jnb     short loc_18003DB8E
0x18003db61  lea     r8, [rsp+6E0h+Data]; wchar_t *
0x18003db66  mov     edx, 104h; unsigned __int64
0x18003db6b  lea     rcx, [rbp+5E0h+Src]; wchar_t *
0x18003db72  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003db77  mov     ebx, eax
0x18003db79  test    eax, eax
0x18003db7b  js      loc_18003DC69
0x18003db81  mov     edi, dword ptr [rsp+6E0h+var_6A0]
0x18003db85  mov     r12d, 1
0x18003db8b  mov     ebx, r11d
0x18003db8e  inc     [rsp+6E0h+dwIndex]
0x18003db92  lea     rcx, [rbp+5E0h+ValueName]; void *
0x18003db99  xor     edx, edx; Val
0x18003db9b  mov     r8d, 208h; Size
0x18003dba1  call    memset
0x18003dba6  xor     edx, edx; Val
0x18003dba8  mov     [rsp+6E0h+cchValueName], 104h
0x18003dbb0  mov     r8d, 208h; Size
0x18003dbb6  mov     [rsp+6E0h+Type], 0
0x18003dbbe  lea     rcx, [rsp+6E0h+Data]; void *
0x18003dbc3  call    memset
0x18003dbc8  mov     edx, [rsp+6E0h+dwIndex]; dwIndex
0x18003dbcc  lea     rax, [rsp+6E0h+cbData]
0x18003dbd1  mov     [rsp+6E0h+lpcbData], rax; lpcbData
0x18003dbd6  lea     r9, [rsp+6E0h+cchValueName]; lpcchValueName
0x18003dbdb  xor     ecx, ecx
0x18003dbdd  mov     [rsp+6E0h+cbData], 206h
0x18003dbe5  lea     rax, [rsp+6E0h+Data]
0x18003dbea  mov     dword ptr [rsp+6E0h+var_6A0+4], ecx
0x18003dbee  mov     [rsp+6E0h+lpData], rax; lpData
0x18003dbf3  lea     r8, [rbp+5E0h+ValueName]; lpValueName
0x18003dbfa  lea     rax, [rsp+6E0h+Type]
0x18003dbff  mov     dword ptr [rsp+6E0h+var_6A0], ecx
0x18003dc03  mov     [rsp+6E0h+lpType], rax; lpType
0x18003dc08  mov     [rsp+6E0h+phkResult], rcx; lpReserved
0x18003dc0d  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18003dc12  call    cs:__imp_RegEnumValueW
0x18003dc19  nop     dword ptr [rax+rax+00h]
0x18003dc1e  cmp     eax, 103h
0x18003dc23  jnz     loc_18003DB2D
0x18003dc29  test    r12d, r12d
0x18003dc2c  jz      loc_18003DCBD
0x18003dc32  mov     r8d, r15d; nSize
0x18003dc35  lea     rcx, [rbp+5E0h+Src]; lpSrc
0x18003dc3c  mov     rdx, r13; lpDst
0x18003dc3f  call    cs:__imp_ExpandEnvironmentStringsW
0x18003dc46  nop     dword ptr [rax+rax+00h]
0x18003dc4b  test    eax, eax
0x18003dc4d  jnz     short loc_18003DC70
0x18003dc4f  mov     rcx, [rbp+5E8h]; this
0x18003dc56  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\findstack\\cbsfinds"...
0x18003dc5d  mov     edx, 81h; void *
0x18003dc62  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003dc67  jmp     short loc_18003DCB9
0x18003dc69  mov     edx, 73h ; 's'
0x18003dc6e  jmp     short loc_18003DCC7
0x18003dc70  cmp     eax, r15d
0x18003dc73  jbe     short loc_18003DC81
0x18003dc75  mov     ebx, 8007007Ah
0x18003dc7a  mov     edx, 82h
0x18003dc7f  jmp     short loc_18003DCC7
0x18003dc81  test    r14, r14
0x18003dc84  jz      short loc_18003DC89
0x18003dc86  mov     [r14], ebx
0x18003dc89  test    rsi, rsi
0x18003dc8c  jz      short loc_18003DC90
0x18003dc8e  mov     [rsi], edi
0x18003dc90  lea     rcx, [rsp+6E0h+hKey]
0x18003dc95  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dc9a  xor     eax, eax
0x18003dc9c  jmp     short loc_18003DCE9
0x18003dc9e  mov     edx, 68h ; 'h'; void *
0x18003dca3  mov     rcx, [rbp+5E8h]; this
0x18003dcaa  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\findstack\\cbsfinds"...
0x18003dcb1  mov     r9d, eax; char *
0x18003dcb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003dcb9  mov     ebx, eax
0x18003dcbb  jmp     short loc_18003DCDD
0x18003dcbd  mov     ebx, 80070490h
0x18003dcc2  mov     edx, 7Ah ; 'z'; void *
0x18003dcc7  mov     rcx, [rbp+5E8h]; this
0x18003dcce  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\findstack\\cbsfinds"...
0x18003dcd5  mov     r9d, ebx; char *
0x18003dcd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dcdd  lea     rcx, [rsp+6E0h+hKey]
0x18003dce2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dce7  mov     eax, ebx
0x18003dce9  mov     rcx, [rbp+5E0h+var_50]
0x18003dcf0  xor     rcx, rsp; StackCookie
0x18003dcf3  call    __security_check_cookie
0x18003dcf8  add     rsp, 6A8h
0x18003dcff  pop     r15
0x18003dd01  pop     r14
0x18003dd03  pop     r13
0x18003dd05  pop     r12
0x18003dd07  pop     rdi
0x18003dd08  pop     rsi
0x18003dd09  pop     rbx
0x18003dd0a  pop     rbp
0x18003dd0b  retn
```
