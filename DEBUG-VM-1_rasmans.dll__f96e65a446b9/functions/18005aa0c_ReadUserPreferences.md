# ReadUserPreferences

- ea: `0x18005aa0c`
- end: `0x18005af95`
- name: `ReadUserPreferences`
- size: `1417`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a480`
- `0x18005a83c`
- `0x18005a91c`

## callees

- `0x18005a2d0`
- `0x18005a39c`
- `0x18005a640`
- `0x18005aa0c`
- `0x18005cb9c`
- `0x18005d5f8`
- `0x18005d638`
- `0x18005d748`
- `0x18005d85c`
- `0x18005d8c0`
- `0x18005da00`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_wtol` at `0x18005ad38`
- `msvcrt!_wtol` at `0x18005ad38`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005adc5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005adc5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ac6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ac6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005acf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005acf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ad92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005adda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ad92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005adda`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005ae49`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005aeed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005af4f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005ae49`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005aeed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005af4f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005aef5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005aef5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005af3a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005af3a`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18005af2a`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18005af2a`

## string_xrefs

- `0x18005ab26`: `SkipConnectComplete`
- `0x18005ab39`: `RedialAttempts`
- `0x18005ab72`: `RedialOnLinkFailure`
- `0x18005ae1f`: `PersonalPhonebookPath`
- `0x18005ae73`: `AlternatePhonebookPath`

## pseudocode

```c
__int64 __fastcall ReadUserPreferences(HKEY hKey, char *a2)
{
  int v5; // r12d
  unsigned int RegMultiSz; // ebx
  __int64 v7; // rcx
  __int64 List; // r14
  DWORD v9; // r15d
  DWORD i; // edx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 LocationNode; // rax
  LSTATUS v14; // eax
  WCHAR *v15; // rbx
  HKEY v16; // rcx
  const WCHAR *v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-38h] BYREF
  DWORD Type; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-2Ch] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-28h] BYREF
  WCHAR SubKey[12]; // [rsp+60h] [rbp-20h] BYREF

  if ( !a2 )
    return 87;
  cchName = -1;
  GetRegDword(hKey, L"PhonebookMode", &cchName);
  if ( cchName == -1 )
  {
    v5 = 1;
  }
  else
  {
    *((_DWORD *)a2 + 22) = cchName;
    v5 = 0;
  }
  GetRegDword(hKey, L"OperatorDial", a2);
  GetRegDword(hKey, L"PreviewPhoneNumber", a2 + 4);
  GetRegDword(hKey, L"UseLocation", a2 + 8);
  GetRegDword(hKey, L"ShowLights", a2 + 12);
  GetRegDword(hKey, L"ShowConnectStatus", a2 + 16);
  GetRegDword(hKey, L"NewEntryWizard", a2 + 36);
  GetRegDword(hKey, L"CloseOnDial", a2 + 20);
  GetRegDword(hKey, L"AllowLogonPhonebookEdits", a2 + 24);
  GetRegDword(hKey, L"AllowLogonLocationEdits", a2 + 28);
  GetRegDword(hKey, L"SkipConnectComplete", a2 + 32);
  GetRegDword(hKey, L"RedialAttempts", a2 + 40);
  GetRegDword(hKey, L"RedialSeconds", a2 + 44);
  GetRegDword(hKey, L"IdleHangUpSeconds", a2 + 48);
  GetRegDword(hKey, L"RedialOnLinkFailure", a2 + 52);
  GetRegDword(hKey, L"PopupOnTopWhenRedialing", a2 + 56);
  GetRegDword(hKey, L"ExpandAutoDialQuery", a2 + 60);
  GetRegDword(hKey, L"CallbackMode", a2 + 64);
  GetRegDword(hKey, L"UseAreaAndCountry", a2 + 128);
  GetRegDword(hKey, L"WindowX", a2 + 160);
  GetRegDword(hKey, L"WindowY", a2 + 164);
  *((_DWORD *)a2 + 9) = 1;
  GetCallbackList(hKey);
  RegMultiSz = GetRegMultiSz(hKey, L"Phonebooks");
  if ( RegMultiSz )
    goto LABEL_42;
  RegMultiSz = GetRegMultiSz(hKey, L"AreaCodes");
  if ( RegMultiSz )
    goto LABEL_42;
  Type = 0;
  cbData = 0;
  if ( !RegQueryValueExW(hKey, L"Prefixes", 0, &Type, 0, &cbData) )
  {
    RegMultiSz = GetRegMultiSz(hKey, L"Prefixes");
    if ( RegMultiSz )
      goto LABEL_42;
  }
  RegMultiSz = GetRegMultiSz(hKey, L"Suffixes");
  if ( RegMultiSz )
    goto LABEL_42;
  cchName = 0;
  phkResult = 0;
  hKeya = 0;
  List = DtlCreateList(v7);
  if ( List )
  {
    if ( !RegOpenKeyExW(hKey, L"Location", 0, 0x20019u, &phkResult) )
    {
      v9 = 0;
      for ( i = 0; ; i = v9 )
      {
        cchName = 12;
        v14 = RegEnumKeyExW(phkResult, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v14 == 259 )
          break;
        if ( !v14 && !RegOpenKeyExW(phkResult, SubKey, 0, 0x20019u, &hKeya) )
        {
          v11 = _wtol(SubKey);
          cbData = 0;
          v12 = v11;
          GetRegDword(hKeya, L"Prefix", &cbData);
          Type = 0;
          GetRegDword(hKeya, L"Suffix", &Type);
          LocationNode = CreateLocationNode(v12, cbData, Type);
          if ( LocationNode )
          {
            DtlAddNodeLast(List, LocationNode);
            RegCloseKey(hKeya);
          }
        }
        ++v9;
      }
      RegCloseKey(phkResult);
    }
    DtlDestroyList(*((HGLOBAL *)a2 + 19));
    *((_QWORD *)a2 + 19) = List;
  }
  RegMultiSz = GetRegSz(hKey, L"LastCallbackByCaller");
  if ( RegMultiSz )
    goto LABEL_42;
  hKeya = 0;
  RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookPath");
  if ( RegMultiSz )
    goto LABEL_42;
  v15 = (WCHAR *)hKeya;
  if ( !*(_WORD *)hKeya )
  {
    GlobalFree(hKeya);
    RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookFile");
    if ( !RegMultiSz )
      goto LABEL_26;
LABEL_42:
    DestroyUserPreferences(a2);
    return RegMultiSz;
  }
  v17 = &v15[lstrlenW((LPCWSTR)hKeya)];
  if ( v17 > v15 )
  {
    while ( 1 )
    {
      v18 = *v17;
      LOWORD(v18) = v18 - 47;
      if ( (unsigned __int16)v18 <= 0x2Du )
      {
        v19 = 0x200000000801LL;
        if ( _bittest64(&v19, v18) )
          break;
      }
      v17 = CharPrevW(v15, v17);
      if ( v17 <= v15 )
        goto LABEL_40;
    }
    v17 = CharNextW(v17);
  }
LABEL_40:
  *((_QWORD *)a2 + 12) = StrDup(v17);
  GlobalFree(v15);
  if ( !*((_QWORD *)a2 + 12) )
  {
    RegMultiSz = 8;
    goto LABEL_42;
  }
LABEL_26:
  RegMultiSz = GetRegSz(hKey, L"AlternatePhonebookPath");
  if ( RegMultiSz )
    goto LABEL_42;
  RegMultiSz = GetRegSz(hKey, L"DefaultEntry");
  if ( RegMultiSz )
    goto LABEL_42;
  if ( v5 )
  {
    hKeya = 0;
    RegMultiSz = GetRegSz(hKey, L"UsePersonalPhonebook");
    if ( !RegMultiSz )
    {
      v16 = hKeya;
      if ( hKeya )
      {
        if ( *(_WORD *)hKeya == 49 )
          *((_DWORD *)a2 + 22) = 1;
        GlobalFree(v16);
      }
      return RegMultiSz;
    }
    goto LABEL_42;
  }
  return RegMultiSz;
}

```

## disassembly

```asm
0x18005aa0c  mov     [rsp-38h+arg_10], rbx
0x18005aa11  push    rbp
0x18005aa12  push    rsi
0x18005aa13  push    rdi
0x18005aa14  push    r12
0x18005aa16  push    r13
0x18005aa18  push    r14
0x18005aa1a  push    r15
0x18005aa1c  mov     rbp, rsp
0x18005aa1f  sub     rsp, 80h
0x18005aa26  mov     rax, cs:__security_cookie
0x18005aa2d  xor     rax, rsp
0x18005aa30  mov     [rbp+var_8], rax
0x18005aa34  xor     r13d, r13d
0x18005aa37  mov     rdi, rdx
0x18005aa3a  mov     rsi, rcx
0x18005aa3d  test    rdx, rdx
0x18005aa40  jnz     short loc_18005AA4A
0x18005aa42  lea     eax, [rdx+57h]
0x18005aa45  jmp     loc_18005AF6E
0x18005aa4a  or      ebx, 0FFFFFFFFh
0x18005aa4d  lea     r8, [rbp+cchName]
0x18005aa51  lea     rdx, aPhonebookmode; "PhonebookMode"
0x18005aa58  mov     [rbp+cchName], ebx
0x18005aa5b  call    GetRegDword
0x18005aa60  mov     eax, [rbp+cchName]
0x18005aa63  cmp     eax, ebx
0x18005aa65  jz      short loc_18005AA6F
0x18005aa67  mov     [rdi+58h], eax
0x18005aa6a  mov     r12d, r13d
0x18005aa6d  jmp     short loc_18005AA75
0x18005aa6f  mov     r12d, 1
0x18005aa75  mov     r8, rdi
0x18005aa78  lea     rdx, aOperatordial; "OperatorDial"
0x18005aa7f  mov     rcx, rsi
0x18005aa82  call    GetRegDword
0x18005aa87  lea     r8, [rdi+4]
0x18005aa8b  mov     rcx, rsi
0x18005aa8e  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x18005aa95  call    GetRegDword
0x18005aa9a  lea     r8, [rdi+8]
0x18005aa9e  mov     rcx, rsi
0x18005aaa1  lea     rdx, aUselocation; "UseLocation"
0x18005aaa8  call    GetRegDword
0x18005aaad  lea     r8, [rdi+0Ch]
0x18005aab1  mov     rcx, rsi
0x18005aab4  lea     rdx, aShowlights; "ShowLights"
0x18005aabb  call    GetRegDword
0x18005aac0  lea     r8, [rdi+10h]
0x18005aac4  mov     rcx, rsi
0x18005aac7  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x18005aace  call    GetRegDword
0x18005aad3  lea     r8, [rdi+24h]
0x18005aad7  mov     rcx, rsi
0x18005aada  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x18005aae1  call    GetRegDword
0x18005aae6  lea     r8, [rdi+14h]
0x18005aaea  mov     rcx, rsi
0x18005aaed  lea     rdx, aCloseondial; "CloseOnDial"
0x18005aaf4  call    GetRegDword
0x18005aaf9  lea     r8, [rdi+18h]
0x18005aafd  mov     rcx, rsi
0x18005ab00  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x18005ab07  call    GetRegDword
0x18005ab0c  lea     r8, [rdi+1Ch]
0x18005ab10  mov     rcx, rsi
0x18005ab13  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x18005ab1a  call    GetRegDword
0x18005ab1f  lea     r8, [rdi+20h]
0x18005ab23  mov     rcx, rsi
0x18005ab26  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x18005ab2d  call    GetRegDword
0x18005ab32  lea     r8, [rdi+28h]
0x18005ab36  mov     rcx, rsi
0x18005ab39  lea     rdx, aRedialattempts_0; "RedialAttempts"
0x18005ab40  call    GetRegDword
0x18005ab45  lea     r8, [rdi+2Ch]
0x18005ab49  mov     rcx, rsi
0x18005ab4c  lea     rdx, aRedialseconds; "RedialSeconds"
0x18005ab53  call    GetRegDword
0x18005ab58  lea     r8, [rdi+30h]
0x18005ab5c  mov     rcx, rsi
0x18005ab5f  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x18005ab66  call    GetRegDword
0x18005ab6b  lea     r8, [rdi+34h]
0x18005ab6f  mov     rcx, rsi
0x18005ab72  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x18005ab79  call    GetRegDword
0x18005ab7e  lea     r8, [rdi+38h]
0x18005ab82  mov     rcx, rsi
0x18005ab85  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x18005ab8c  call    GetRegDword
0x18005ab91  lea     r8, [rdi+3Ch]
0x18005ab95  mov     rcx, rsi
0x18005ab98  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x18005ab9f  call    GetRegDword
0x18005aba4  lea     r8, [rdi+40h]
0x18005aba8  mov     rcx, rsi
0x18005abab  lea     rdx, aCallbackmode_0; "CallbackMode"
0x18005abb2  call    GetRegDword
0x18005abb7  lea     r8, [rdi+80h]
0x18005abbe  mov     rcx, rsi
0x18005abc1  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x18005abc8  call    GetRegDword
0x18005abcd  lea     r8, [rdi+0A0h]
0x18005abd4  mov     rcx, rsi
0x18005abd7  lea     rdx, aWindowx; "WindowX"
0x18005abde  call    GetRegDword
0x18005abe3  lea     r8, [rdi+0A4h]
0x18005abea  mov     rcx, rsi
0x18005abed  lea     rdx, aWindowy; "WindowY"
0x18005abf4  call    GetRegDword
0x18005abf9  mov     dword ptr [rdi+24h], 1
0x18005ac00  lea     rdx, [rdi+48h]
0x18005ac04  mov     rcx, rsi; hKey
0x18005ac07  call    GetCallbackList
0x18005ac0c  lea     r8, [rdi+70h]
0x18005ac10  mov     rcx, rsi; hKey
0x18005ac13  lea     rdx, aPhonebooks; "Phonebooks"
0x18005ac1a  call    GetRegMultiSz
0x18005ac1f  mov     ebx, eax
0x18005ac21  test    eax, eax
0x18005ac23  jnz     loc_18005AF64
0x18005ac29  lea     r8, [rdi+78h]
0x18005ac2d  mov     rcx, rsi; hKey
0x18005ac30  lea     rdx, aAreacodes; "AreaCodes"
0x18005ac37  call    GetRegMultiSz
0x18005ac3c  mov     ebx, eax
0x18005ac3e  test    eax, eax
0x18005ac40  jnz     loc_18005AF64
0x18005ac46  lea     rax, [rbp+cbData]
0x18005ac4a  mov     [rbp+Type], r13d
0x18005ac4e  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18005ac53  lea     r9, [rbp+Type]; lpType
0x18005ac57  xor     r8d, r8d; lpReserved
0x18005ac5a  mov     [rsp+80h+lpData], r13; lpData
0x18005ac5f  lea     rdx, aPrefixes; "Prefixes"
0x18005ac66  mov     [rbp+cbData], r13d
0x18005ac6a  mov     rcx, rsi; hKey
0x18005ac6d  call    cs:__imp_RegQueryValueExW
0x18005ac73  test    eax, eax
0x18005ac75  jnz     short loc_18005AC97
0x18005ac77  lea     r8, [rdi+88h]
0x18005ac7e  mov     rcx, rsi; hKey
0x18005ac81  lea     rdx, aPrefixes; "Prefixes"
0x18005ac88  call    GetRegMultiSz
0x18005ac8d  mov     ebx, eax
0x18005ac8f  test    eax, eax
0x18005ac91  jnz     loc_18005AF64
0x18005ac97  lea     r8, [rdi+90h]
0x18005ac9e  mov     rcx, rsi; hKey
0x18005aca1  lea     rdx, aSuffixes; "Suffixes"
0x18005aca8  call    GetRegMultiSz
0x18005acad  mov     ebx, eax
0x18005acaf  test    eax, eax
0x18005acb1  jnz     loc_18005AF64
0x18005acb7  mov     [rbp+cchName], r13d
0x18005acbb  mov     [rbp+phkResult], r13
0x18005acbf  mov     [rbp+hKey], r13
0x18005acc3  call    DtlCreateList
0x18005acc8  mov     r14, rax
0x18005accb  test    rax, rax
0x18005acce  jz      loc_18005ADFA
0x18005acd4  lea     rax, [rbp+phkResult]
0x18005acd8  mov     r9d, 20019h; samDesired
0x18005acde  xor     r8d, r8d; ulOptions
0x18005ace1  mov     [rsp+80h+lpData], rax; phkResult
0x18005ace6  lea     rdx, aLocation; "Location"
0x18005aced  mov     rcx, rsi; hKey
0x18005acf0  call    cs:__imp_RegOpenKeyExW
0x18005acf6  test    eax, eax
0x18005acf8  jnz     loc_18005ADE0
0x18005acfe  mov     r15d, r13d
0x18005ad01  xor     edx, edx
0x18005ad03  jmp     loc_18005AD9E
0x18005ad08  test    eax, eax
0x18005ad0a  jnz     loc_18005AD98
0x18005ad10  mov     rcx, [rbp+phkResult]; hKey
0x18005ad14  lea     rax, [rbp+hKey]
0x18005ad18  mov     r9d, 20019h; samDesired
0x18005ad1e  mov     [rsp+80h+lpData], rax; phkResult
0x18005ad23  xor     r8d, r8d; ulOptions
0x18005ad26  lea     rdx, [rbp+SubKey]; lpSubKey
0x18005ad2a  call    cs:__imp_RegOpenKeyExW
0x18005ad30  test    eax, eax
0x18005ad32  jnz     short loc_18005AD98
0x18005ad34  lea     rcx, [rbp+SubKey]; String
0x18005ad38  call    cs:__imp__wtol
0x18005ad3e  mov     rcx, [rbp+hKey]
0x18005ad42  lea     r8, [rbp+cbData]
0x18005ad46  lea     rdx, aPrefix; "Prefix"
0x18005ad4d  mov     [rbp+cbData], r13d
0x18005ad51  mov     ebx, eax
0x18005ad53  call    GetRegDword
0x18005ad58  mov     rcx, [rbp+hKey]
0x18005ad5c  lea     r8, [rbp+Type]
0x18005ad60  lea     rdx, aSuffix; "Suffix"
0x18005ad67  mov     [rbp+Type], r13d
0x18005ad6b  call    GetRegDword
0x18005ad70  mov     r8d, [rbp+Type]
0x18005ad74  mov     ecx, ebx
0x18005ad76  mov     edx, [rbp+cbData]
0x18005ad79  call    CreateLocationNode
0x18005ad7e  test    rax, rax
0x18005ad81  jz      short loc_18005AD98
0x18005ad83  mov     rdx, rax
0x18005ad86  mov     rcx, r14
0x18005ad89  call    DtlAddNodeLast
0x18005ad8e  mov     rcx, [rbp+hKey]; hKey
0x18005ad92  call    cs:__imp_RegCloseKey
0x18005ad98  inc     r15d
0x18005ad9b  mov     edx, r15d; dwIndex
0x18005ad9e  mov     rcx, [rbp+phkResult]; hKey
0x18005ada2  lea     r9, [rbp+cchName]; lpcchName
0x18005ada6  mov     [rsp+80h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18005adab  lea     r8, [rbp+SubKey]; lpName
0x18005adaf  mov     [rsp+80h+lpcchClass], r13; lpcchClass
0x18005adb4  mov     [rsp+80h+lpcbData], r13; lpClass
0x18005adb9  mov     [rsp+80h+lpData], r13; lpReserved
0x18005adbe  mov     [rbp+cchName], 0Ch
0x18005adc5  call    cs:__imp_RegEnumKeyExW
0x18005adcb  cmp     eax, 103h
0x18005add0  jnz     loc_18005AD08
0x18005add6  mov     rcx, [rbp+phkResult]; hKey
0x18005adda  call    cs:__imp_RegCloseKey
0x18005ade0  mov     rcx, [rdi+98h]; hMem
0x18005ade7  lea     rdx, DestroyEntryTypeNode
0x18005adee  call    DtlDestroyList
0x18005adf3  mov     [rdi+98h], r14
0x18005adfa  lea     r8, [rdi+50h]
0x18005adfe  mov     rcx, rsi; hKey
0x18005ae01  lea     rdx, aLastcallbackby; "LastCallbackByCaller"
0x18005ae08  call    GetRegSz
0x18005ae0d  mov     ebx, eax
0x18005ae0f  test    eax, eax
0x18005ae11  jnz     loc_18005AF64
0x18005ae17  lea     r8, [rbp+hKey]
0x18005ae1b  mov     [rbp+hKey], r13
0x18005ae1f  lea     rdx, aPersonalphoneb; "PersonalPhonebookPath"
0x18005ae26  mov     rcx, rsi; hKey
0x18005ae29  call    GetRegSz
0x18005ae2e  mov     ebx, eax
0x18005ae30  test    eax, eax
0x18005ae32  jnz     loc_18005AF64
0x18005ae38  mov     rbx, [rbp+hKey]
0x18005ae3c  mov     rcx, rbx; lpString
0x18005ae3f  cmp     [rbx], r13w
0x18005ae43  jnz     loc_18005AEF5
0x18005ae49  call    cs:__imp_GlobalFree
0x18005ae4f  lea     r8, [rdi+60h]
0x18005ae53  mov     rcx, rsi; hKey
0x18005ae56  lea     rdx, aPersonalphoneb_0; "PersonalPhonebookFile"
0x18005ae5d  call    GetRegSz
0x18005ae62  mov     ebx, eax
0x18005ae64  test    eax, eax
0x18005ae66  jnz     loc_18005AF64
0x18005ae6c  lea     r8, [rdi+68h]
0x18005ae70  mov     rcx, rsi; hKey
0x18005ae73  lea     rdx, aAlternatephone; "AlternatePhonebookPath"
0x18005ae7a  call    GetRegSz
0x18005ae7f  mov     ebx, eax
0x18005ae81  test    eax, eax
0x18005ae83  jnz     loc_18005AF64
0x18005ae89  lea     r8, [rdi+0A8h]
0x18005ae90  mov     rcx, rsi; hKey
0x18005ae93  lea     rdx, aDefaultentry; "DefaultEntry"
0x18005ae9a  call    GetRegSz
0x18005ae9f  mov     ebx, eax
0x18005aea1  test    eax, eax
0x18005aea3  jnz     loc_18005AF64
0x18005aea9  test    r12d, r12d
0x18005aeac  jz      loc_18005AF6C
0x18005aeb2  lea     r8, [rbp+hKey]
0x18005aeb6  mov     [rbp+hKey], r13
0x18005aeba  lea     rdx, aUsepersonalpho; "UsePersonalPhonebook"
0x18005aec1  mov     rcx, rsi; hKey
0x18005aec4  call    GetRegSz
0x18005aec9  mov     ebx, eax
0x18005aecb  test    eax, eax
0x18005aecd  jnz     loc_18005AF64
0x18005aed3  mov     rcx, [rbp+hKey]; hMem
0x18005aed7  test    rcx, rcx
0x18005aeda  jz      loc_18005AF6C
0x18005aee0  cmp     word ptr [rcx], 31h ; '1'
0x18005aee4  jnz     short loc_18005AEED
0x18005aee6  mov     dword ptr [rdi+58h], 1
0x18005aeed  call    cs:__imp_GlobalFree
0x18005aef3  jmp     short loc_18005AF6C
0x18005aef5  call    cs:__imp_lstrlenW
0x18005aefb  movsxd  rcx, eax
0x18005aefe  lea     rcx, [rbx+rcx*2]; lpsz
0x18005af02  cmp     rcx, rbx
0x18005af05  jbe     short loc_18005AF43
0x18005af07  movzx   eax, word ptr [rcx]
0x18005af0a  sub     ax, 2Fh ; '/'
0x18005af0e  cmp     ax, 2Dh ; '-'
0x18005af12  ja      short loc_18005AF24
0x18005af14  mov     rdx, 200000000801h
0x18005af1e  bt      rdx, rax
0x18005af22  jb      short loc_18005AF3A
  ... truncated ...
```
