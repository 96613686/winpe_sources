# WdcStartupMonitor::LoadFolderList(void)

- ea: `0x1800d4d24`
- end: `0x1800d515b`
- name: `?LoadFolderList@WdcStartupMonitor@@QEAAJXZ`
- size: `1079`
- prototype: `__int64 __fastcall(WdcStartupMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x1800d715c`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x18000f07c`
- `0x18009d56c`
- `0x1800d433c`
- `0x1800d4b84`
- `0x1800d4bf8`
- `0x1800d4d24`
- `0x1800d5988`
- `0x1800d62b0`
- `0x1800d631c`
- `0x1800d6d44`
- `0x1800d6e00`
- `0x1800d6ea4`
- `0x1800d728c`
- `0x1800d76e8`
- `0x1800dba40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4efd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d507b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d50cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d50d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4efd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d507b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d50cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d50d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4f99`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d4e55`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800d4e55`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d5088`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800d5088`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d4e37`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800d4e37`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800d4dcd`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1800d4dcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WdcStartupMonitor::LoadFolderList(WdcStartupMonitor *this)
{
  WdcStartupMonitor *v1; // rbx
  char *v2; // rsi
  int v3; // r12d
  __int64 v4; // r15
  unsigned int v5; // r14d
  signed int LastError; // eax
  int v7; // eax
  unsigned int v8; // edi
  char *FirstFileW; // r13
  char *v10; // rcx
  signed int v11; // eax
  HSTRING v12; // rdi
  HSTRING v13; // rbx
  WdcStartupMonitor *v14; // rcx
  WdcStartupMonitor *v15; // rcx
  WdcStartupMonitor *v16; // rcx
  HSTRING v17; // rcx
  HSTRING v18; // rcx
  void *StringRawBuffer; // rax
  WdcStartupMonitor *v20; // r15
  int v21; // eax
  __int64 v22; // rdx
  struct _WDC_STARTUP_INFO *v23; // r15
  WdcStartupMonitor *v24; // rcx
  bool v25; // r8
  StartupDB::GamingStartupApproval *GamingStartupApprovalObject; // rax
  bool *cFileName; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+64h] [rbp-9Ch] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v32; // [rsp+70h] [rbp-90h]
  char *v33; // [rsp+78h] [rbp-88h] BYREF
  struct _WDC_STARTUP_INFO *v34; // [rsp+80h] [rbp-80h] BYREF
  WdcStartupMonitor *v35; // [rsp+88h] [rbp-78h]
  struct _FILETIME v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  struct StartupDB::StartupApproval *StartupApprovalObject; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v39; // [rsp+A8h] [rbp-58h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszPath[1024]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v42[1024]; // [rsp+B00h] [rbp+A00h] BYREF
  WCHAR FileName[1024]; // [rsp+1300h] [rbp+1200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B58h] [rbp+1A58h]

  v1 = this;
  v35 = this;
  v2 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  v30 = 0;
  v29 = 0;
  v3 = 0;
  while ( 1 )
  {
    pszPath[0] = 0;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v4 = 16LL * v3;
    v37 = v4;
    v39 = *(_QWORD *)&asc_18011DE30[v4 + 8];
    StartupApprovalObject = WdcStartupMonitor::_GetStartupApprovalObject(v1, v39);
    if ( SHGetSpecialFolderPathW(0, pszPath, *(_DWORD *)&asc_18011DE30[v4], 0) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( !LastError )
      {
        v5 = -2147467259;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x327,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
          (const char *)v5,
          (int)cFileName);
LABEL_42:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v33);
        return v5;
      }
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        goto LABEL_41;
    }
    v7 = StringCchPrintfW(FileName, 0x400u, L"%s\\*.*", pszPath);
    v8 = v7;
    if ( v7 < 0 )
      break;
    FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
    v10 = v2;
    v2 = FirstFileW;
    v33 = FirstFileW;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(v10);
    if ( FirstFileW != (char *)-1LL )
    {
      while ( 1 )
      {
        v42[0] = 0;
        v12 = 0;
        v32 = 0;
        v13 = 0;
        string = 0;
        if ( (FindFileData.dwFileAttributes & 0x12) != 0
          || STRINGS_ARE_EQUAL_NONLINGUISTIC(FindFileData.cFileName, L"desktop.ini") )
        {
          goto LABEL_32;
        }
        if ( WdcStartupMonitor::_GetApprovalItemStatus(
               v14,
               StartupApprovalObject,
               FindFileData.cFileName,
               (enum _tagTM_ITEMSTATUS *)&v30,
               &v29,
               &v36) < 0 )
          goto LABEL_24;
        if ( !(unsigned int)WdcStartupMonitor::IsLinkFile(v15, FindFileData.cFileName) )
          break;
        WindowsDeleteString(0);
        string = 0;
        if ( (int)WdcStartupMonitor::GetTargetFromLnkFile(v16, FindFileData.cFileName, pszPath, &string) >= 0 )
        {
          v13 = string;
          if ( string )
            goto LABEL_26;
LABEL_24:
          v17 = 0;
          goto LABEL_22;
        }
        v17 = string;
LABEL_22:
        WindowsDeleteString(v17);
        v18 = 0;
LABEL_33:
        WindowsDeleteString(v18);
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          v1 = v35;
          goto LABEL_35;
        }
      }
      cFileName = (bool *)FindFileData.cFileName;
      if ( StringCchPrintfW(v42, 0x400u, L"%s\\%s", pszPath) >= 0 )
      {
LABEL_26:
        WindowsDeleteString(0);
        v32 = 0;
        if ( v13 )
          StringRawBuffer = (void *)WindowsGetStringRawBuffer(v13, 0);
        else
          StringRawBuffer = v42;
        cFileName = (bool *)&v36;
        v20 = v35;
        v21 = WdcStartupMonitor::SetData(v35, StringRawBuffer, FindFileData.cFileName, pszPath);
        v8 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37A,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
            (const char *)(unsigned int)v21,
            (int)&v36);
          WindowsDeleteString(v13);
          WindowsDeleteString(v32);
          goto LABEL_39;
        }
        WdcStartupMonitor::MapStartupProcesses(v20, v22, &v34);
        v23 = v34;
        *((_BYTE *)v34 + 577) = 0;
        *((_QWORD *)v23 + 4) = v39;
        v12 = v32;
        WdcStartupMonitor::_SetIcon(v24, v32, v25, v23);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54629273>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54629273>::GetImpl'::`2'::impl) )
        {
          GamingStartupApprovalObject = WdcStartupMonitor::_GetGamingStartupApprovalObject(v35, *((_QWORD *)v23 + 4));
          *((_BYTE *)v23 + 580) = StartupDB::GamingStartupApproval::IsItemEnabled(
                                    GamingStartupApprovalObject,
                                    FindFileData.cFileName);
        }
LABEL_32:
        WindowsDeleteString(v13);
        v18 = v12;
        goto LABEL_33;
      }
      goto LABEL_24;
    }
    v11 = GetLastError();
    v5 = 0;
    if ( v11 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      else
        v5 = v11;
    }
LABEL_35:
    if ( (unsigned int)++v3 >= 2 )
      goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x330,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
    (const char *)(unsigned int)v7,
    (int)cFileName);
LABEL_39:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v33);
  return v8;
}

```

## disassembly

```asm
0x1800d4d24  push    rbp
0x1800d4d26  push    rbx
0x1800d4d27  push    rsi
0x1800d4d28  push    rdi
0x1800d4d29  push    r12
0x1800d4d2b  push    r13
0x1800d4d2d  push    r14
0x1800d4d2f  push    r15
0x1800d4d31  lea     rbp, [rsp-1A18h]
0x1800d4d39  mov     eax, 1B18h
0x1800d4d3e  call    _alloca_probe
0x1800d4d43  sub     rsp, rax
0x1800d4d46  mov     rax, cs:__security_cookie
0x1800d4d4d  xor     rax, rsp
0x1800d4d50  mov     [rbp+1A50h+var_50], rax
0x1800d4d57  mov     rbx, rcx
0x1800d4d5a  mov     [rbp+1A50h+var_1AC8], rcx
0x1800d4d5e  xor     esi, esi
0x1800d4d60  mov     [rsp+1B50h+var_1AD8], rsi
0x1800d4d65  mov     [rbp+1A50h+var_1AD0], rsi
0x1800d4d69  mov     qword ptr [rbp+1A50h+var_1AC0.dwLowDateTime], rsi
0x1800d4d6d  mov     [rsp+1B50h+var_1AEC], esi
0x1800d4d71  mov     [rsp+1B50h+var_1AF0], sil
0x1800d4d76  xor     r12d, r12d
0x1800d4d79  lea     rdi, asc_18011DE30; "\a"
0x1800d4d80  xor     eax, eax
0x1800d4d82  mov     [rbp+1A50h+pszPath], ax
0x1800d4d89  xor     edx, edx; Val
0x1800d4d8b  mov     r8d, 250h; Size
0x1800d4d91  lea     rcx, [rbp+1A50h+FindFileData]; void *
0x1800d4d95  call    memset_0
0x1800d4d9a  movsxd  r15, r12d
0x1800d4d9d  shl     r15, 4
0x1800d4da1  mov     [rbp+1A50h+var_1AB8], r15
0x1800d4da5  mov     rax, [r15+rdi+8]
0x1800d4daa  mov     [rbp+1A50h+var_1AA8], rax
0x1800d4dae  mov     rdx, rax; unsigned __int64
0x1800d4db1  mov     rcx, rbx; this
0x1800d4db4  call    ?_GetStartupApprovalObject@WdcStartupMonitor@@AEAAPEAVStartupApproval@StartupDB@@_K@Z; WdcStartupMonitor::_GetStartupApprovalObject(unsigned __int64)
0x1800d4db9  mov     [rbp+1A50h+var_1AB0], rax
0x1800d4dbd  xor     r9d, r9d; fCreate
0x1800d4dc0  mov     r8d, [r15+rdi]; csidl
0x1800d4dc4  lea     rdx, [rbp+1A50h+pszPath]; pszPath
0x1800d4dcb  xor     ecx, ecx; hwnd
0x1800d4dcd  call    cs:__imp_SHGetSpecialFolderPathW
0x1800d4dd3  test    eax, eax
0x1800d4dd5  jz      short loc_1800D4DDC
0x1800d4dd7  xor     r14d, r14d
0x1800d4dda  jmp     short loc_1800D4E03
0x1800d4ddc  call    cs:__imp_GetLastError
0x1800d4de2  mov     r14d, eax
0x1800d4de5  test    eax, eax
0x1800d4de7  jz      loc_1800D5109
0x1800d4ded  jle     short loc_1800D4DFA
0x1800d4def  movzx   r14d, ax
0x1800d4df3  or      r14d, 80070000h
0x1800d4dfa  test    r14d, r14d
0x1800d4dfd  js      loc_1800D510F
0x1800d4e03  lea     r9, [rbp+1A50h+pszPath]
0x1800d4e0a  lea     r8, aS; "%s\\*.*"
0x1800d4e11  mov     edx, 400h; unsigned __int64
0x1800d4e16  lea     rcx, [rbp+1A50h+FileName]; unsigned __int16 *
0x1800d4e1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d4e22  mov     edi, eax
0x1800d4e24  test    eax, eax
0x1800d4e26  js      loc_1800D50DF
0x1800d4e2c  lea     rdx, [rbp+1A50h+FindFileData]; lpFindFileData
0x1800d4e30  lea     rcx, [rbp+1A50h+FileName]; lpFileName
0x1800d4e37  call    cs:__imp_FindFirstFileW
0x1800d4e3d  mov     r13, rax
0x1800d4e40  mov     rcx, rsi; hFindFile
0x1800d4e43  mov     rsi, rax
0x1800d4e46  mov     [rsp+1B50h+var_1AD8], rax
0x1800d4e4b  lea     rdx, [rcx-1]
0x1800d4e4f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800d4e53  ja      short loc_1800D4E5B
0x1800d4e55  call    cs:__imp_FindClose
0x1800d4e5b  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800d4e5f  jnz     short loc_1800D4E8C
0x1800d4e61  call    cs:__imp_GetLastError
0x1800d4e67  xor     r14d, r14d
0x1800d4e6a  test    eax, eax
0x1800d4e6c  jz      loc_1800D509A
0x1800d4e72  jg      short loc_1800D4E7C
0x1800d4e74  mov     r14d, eax
0x1800d4e77  jmp     loc_1800D509A
0x1800d4e7c  movzx   r14d, ax
0x1800d4e80  or      r14d, 80070000h
0x1800d4e87  jmp     loc_1800D509A
0x1800d4e8c  xor     eax, eax
0x1800d4e8e  mov     [rbp+1A50h+var_1050], ax
0x1800d4e95  xor     edi, edi
0x1800d4e97  mov     [rsp+1B50h+var_1AE0], rdi
0x1800d4e9c  xor     ebx, ebx
0x1800d4e9e  mov     [rsp+1B50h+string], rbx
0x1800d4ea3  test    byte ptr [rbp+1A50h+FindFileData.dwFileAttributes], 12h
0x1800d4ea7  jnz     loc_1800D506E
0x1800d4ead  lea     rdx, aDesktopIni; "desktop.ini"
0x1800d4eb4  lea     rcx, [rbp+1A50h+FindFileData.cFileName]; unsigned __int16 *
0x1800d4eb8  call    ?STRINGS_ARE_EQUAL_NONLINGUISTIC@@YA_NPEBG0@Z; STRINGS_ARE_EQUAL_NONLINGUISTIC(ushort const *,ushort const *)
0x1800d4ebd  cmp     al, 1
0x1800d4ebf  jz      loc_1800D506E
0x1800d4ec5  lea     rax, [rbp+1A50h+var_1AC0]
0x1800d4ec9  mov     [rsp+1B50h+var_1B28], rax; struct _FILETIME *
0x1800d4ece  lea     rax, [rsp+1B50h+var_1AF0]
0x1800d4ed3  mov     [rsp+1B50h+var_1B30], rax; bool *
0x1800d4ed8  lea     r9, [rsp+1B50h+var_1AEC]; enum _tagTM_ITEMSTATUS *
0x1800d4edd  lea     r8, [rbp+1A50h+FindFileData.cFileName]; unsigned __int16 *
0x1800d4ee1  mov     rdx, [rbp+1A50h+var_1AB0]; struct StartupDB::StartupApproval *
0x1800d4ee5  call    ?_GetApprovalItemStatus@WdcStartupMonitor@@AEAAJPEAVStartupApproval@StartupDB@@PEBGPEAW4_tagTM_ITEMSTATUS@@PEA_NPEAU_FILETIME@@@Z; WdcStartupMonitor::_GetApprovalItemStatus(StartupDB::StartupApproval *,ushort const *,_tagTM_ITEMSTATUS *,bool *,_FILETIME *)
0x1800d4eea  test    eax, eax
0x1800d4eec  js      short loc_1800D4F3E
0x1800d4eee  lea     rdx, [rbp+1A50h+FindFileData.cFileName]; unsigned __int16 *
0x1800d4ef2  call    ?IsLinkFile@WdcStartupMonitor@@QEAAHPEAG@Z; WdcStartupMonitor::IsLinkFile(ushort *)
0x1800d4ef7  test    eax, eax
0x1800d4ef9  jz      short loc_1800D4F42
0x1800d4efb  xor     ecx, ecx; string
0x1800d4efd  call    cs:__imp_WindowsDeleteString
0x1800d4f03  mov     [rsp+1B50h+string], rbx
0x1800d4f08  lea     r9, [rsp+1B50h+string]; HSTRING *
0x1800d4f0d  lea     r8, [rbp+1A50h+pszPath]; unsigned __int16 *
0x1800d4f14  lea     rdx, [rbp+1A50h+FindFileData.cFileName]; unsigned __int16 *
0x1800d4f18  call    ?GetTargetFromLnkFile@WdcStartupMonitor@@QEAAJPEAG0PEAPEAUHSTRING__@@@Z; WdcStartupMonitor::GetTargetFromLnkFile(ushort *,ushort *,HSTRING__ * *)
0x1800d4f1d  test    eax, eax
0x1800d4f1f  jns     short loc_1800D4F34
0x1800d4f21  mov     rcx, [rsp+1B50h+string]; string
0x1800d4f26  call    cs:__imp_WindowsDeleteString
0x1800d4f2c  nop
0x1800d4f2d  xor     ecx, ecx
0x1800d4f2f  jmp     loc_1800D507B
0x1800d4f34  mov     rbx, [rsp+1B50h+string]
0x1800d4f39  test    rbx, rbx
0x1800d4f3c  jnz     short loc_1800D4F6E
0x1800d4f3e  xor     ecx, ecx
0x1800d4f40  jmp     short loc_1800D4F26
0x1800d4f42  lea     rax, [rbp+1A50h+FindFileData.cFileName]
0x1800d4f46  mov     [rsp+1B50h+var_1B30], rax
0x1800d4f4b  lea     r9, [rbp+1A50h+pszPath]
0x1800d4f52  lea     r8, aSS_0; "%s\\%s"
0x1800d4f59  mov     edx, 400h; unsigned __int64
0x1800d4f5e  lea     rcx, [rbp+1A50h+var_1050]; unsigned __int16 *
0x1800d4f65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d4f6a  test    eax, eax
0x1800d4f6c  js      short loc_1800D4F3E
0x1800d4f6e  xor     ecx, ecx; string
0x1800d4f70  call    cs:__imp_WindowsDeleteString
0x1800d4f76  mov     [rsp+1B50h+var_1AE0], 0
0x1800d4f7f  lea     rax, asc_18011DE30; "\a"
0x1800d4f86  mov     edi, [r15+rax]
0x1800d4f8a  mov     r15b, [rsp+1B50h+var_1AF0]
0x1800d4f8f  test    rbx, rbx
0x1800d4f92  jz      short loc_1800D4FA1
0x1800d4f94  xor     edx, edx; length
0x1800d4f96  mov     rcx, rbx; string
0x1800d4f99  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4f9f  jmp     short loc_1800D4FA8
0x1800d4fa1  lea     rax, [rbp+1A50h+var_1050]
0x1800d4fa8  lea     rcx, [rbp+1A50h+var_1AD0]
0x1800d4fac  mov     [rsp+1B50h+var_1AF8], rcx
0x1800d4fb1  lea     rcx, [rsp+1B50h+var_1AE0]
0x1800d4fb6  mov     [rsp+1B50h+var_1B00], rcx
0x1800d4fbb  mov     [rsp+1B50h+var_1B08], 1
0x1800d4fc3  mov     [rsp+1B50h+var_1B10], 0
0x1800d4fcc  mov     [rsp+1B50h+var_1B18], edi
0x1800d4fd0  mov     [rsp+1B50h+var_1B20], r15b
0x1800d4fd5  mov     ecx, [rsp+1B50h+var_1AEC]
0x1800d4fd9  mov     dword ptr [rsp+1B50h+var_1B28], ecx
0x1800d4fdd  lea     rcx, [rbp+1A50h+var_1AC0]
0x1800d4fe1  mov     [rsp+1B50h+var_1B30], rcx; int
0x1800d4fe6  lea     r9, [rbp+1A50h+pszPath]
0x1800d4fed  lea     r8, [rbp+1A50h+FindFileData.cFileName]
0x1800d4ff1  mov     rdx, rax
0x1800d4ff4  mov     r15, [rbp+1A50h+var_1AC8]
0x1800d4ff8  mov     rcx, r15
0x1800d4ffb  call    ?SetData@WdcStartupMonitor@@QEAAJPEBG00PEBU_FILETIME@@W4_tagTM_ITEMSTATUS@@_NHPEAUHKEY__@@W4_STARTUP_LOCATION@@PEAPEAUHSTRING__@@PEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetData(ushort const *,ushort const *,ushort const *,_FILETIME const *,_tagTM_ITEMSTATUS,bool,int,HKEY__ *,_STARTUP_LOCATION,HSTRING__ * *,_WDC_STARTUP_INFO * *)
0x1800d5000  mov     edi, eax
0x1800d5002  test    eax, eax
0x1800d5004  js      loc_1800D50AC
0x1800d500a  lea     r8, [rbp+1A50h+var_1AD0]
0x1800d500e  mov     rcx, r15
0x1800d5011  call    ?MapStartupProcesses@WdcStartupMonitor@@QEAAJW4_STARTUP_LOCATION@@PEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::MapStartupProcesses(_STARTUP_LOCATION,_WDC_STARTUP_INFO * *)
0x1800d5016  mov     r15, [rbp+1A50h+var_1AD0]
0x1800d501a  mov     byte ptr [r15+241h], 0
0x1800d5022  mov     rax, [rbp+1A50h+var_1AA8]
0x1800d5026  mov     [r15+20h], rax
0x1800d502a  mov     r9, r15; struct _WDC_STARTUP_INFO *
0x1800d502d  mov     rdi, [rsp+1B50h+var_1AE0]
0x1800d5032  mov     rdx, rdi; HSTRING
0x1800d5035  call    ?_SetIcon@WdcStartupMonitor@@AEAAJPEAUHSTRING__@@_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::_SetIcon(HSTRING__ *,bool,_WDC_STARTUP_INFO *)
0x1800d503a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54629273@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54629273@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54629273> `wil::Feature<__WilFeatureTraits_Feature_54629273>::GetImpl(void)'::`2'::impl
0x1800d5041  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54629273@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54629273>::__private_IsEnabled(void)
0x1800d5046  test    al, al
0x1800d5048  jz      short loc_1800D506A
0x1800d504a  mov     rdx, [r15+20h]; unsigned __int64
0x1800d504e  mov     rcx, [rbp+1A50h+var_1AC8]; this
0x1800d5052  call    ?_GetGamingStartupApprovalObject@WdcStartupMonitor@@AEAAPEAVGamingStartupApproval@StartupDB@@_K@Z; WdcStartupMonitor::_GetGamingStartupApprovalObject(unsigned __int64)
0x1800d5057  lea     rdx, [rbp+1A50h+FindFileData.cFileName]; unsigned __int16 *
0x1800d505b  mov     rcx, rax; this
0x1800d505e  call    ?IsItemEnabled@GamingStartupApproval@StartupDB@@QEAA_NPEBG@Z; StartupDB::GamingStartupApproval::IsItemEnabled(ushort const *)
0x1800d5063  mov     [r15+244h], al
0x1800d506a  mov     r15, [rbp+1A50h+var_1AB8]
0x1800d506e  mov     rcx, rbx; string
0x1800d5071  call    cs:__imp_WindowsDeleteString
0x1800d5077  nop
0x1800d5078  mov     rcx, rdi; string
0x1800d507b  call    cs:__imp_WindowsDeleteString
0x1800d5081  lea     rdx, [rbp+1A50h+FindFileData]; lpFindFileData
0x1800d5085  mov     rcx, r13; hFindFile
0x1800d5088  call    cs:__imp_FindNextFileW
0x1800d508e  test    eax, eax
0x1800d5090  jnz     loc_1800D4E8C
0x1800d5096  mov     rbx, [rbp+1A50h+var_1AC8]
0x1800d509a  inc     r12d
0x1800d509d  cmp     r12d, 2
0x1800d50a1  jnb     loc_1800D512B
0x1800d50a7  jmp     loc_1800D4D79
0x1800d50ac  mov     rcx, [rbp+1A58h]; this
0x1800d50b3  mov     r9d, eax; char *
0x1800d50b6  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d50bd  mov     edx, 37Ah; void *
0x1800d50c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d50c7  nop
0x1800d50c8  mov     rcx, rbx; string
0x1800d50cb  call    cs:__imp_WindowsDeleteString
0x1800d50d1  nop
0x1800d50d2  mov     rcx, [rsp+1B50h+var_1AE0]; string
0x1800d50d7  call    cs:__imp_WindowsDeleteString
0x1800d50dd  jmp     short loc_1800D50FB
0x1800d50df  mov     rcx, [rbp+1A58h]; this
0x1800d50e6  mov     r9d, eax; char *
0x1800d50e9  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d50f0  mov     edx, 330h; void *
0x1800d50f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d50fa  nop
0x1800d50fb  lea     rcx, [rsp+1B50h+var_1AD8]
0x1800d5100  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d5105  mov     eax, edi
0x1800d5107  jmp     short loc_1800D5138
0x1800d5109  mov     r14d, 80004005h
0x1800d510f  mov     rcx, [rbp+1A58h]; this
0x1800d5116  mov     r9d, r14d; char *
0x1800d5119  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d5120  mov     edx, 327h; void *
0x1800d5125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d512a  nop
0x1800d512b  lea     rcx, [rsp+1B50h+var_1AD8]
0x1800d5130  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800d5135  mov     eax, r14d
0x1800d5138  mov     rcx, [rbp+1A50h+var_50]
0x1800d513f  xor     rcx, rsp; StackCookie
0x1800d5142  call    __security_check_cookie
0x1800d5147  add     rsp, 1B18h
0x1800d514e  pop     r15
0x1800d5150  pop     r14
0x1800d5152  pop     r13
0x1800d5154  pop     r12
0x1800d5156  pop     rdi
0x1800d5157  pop     rsi
0x1800d5158  pop     rbx
0x1800d5159  pop     rbp
0x1800d515a  retn
```
