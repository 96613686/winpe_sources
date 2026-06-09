# RetailDemoUserAgent::CleanupRecycleBin(void)

- ea: `0x1800396f0`
- end: `0x180039825`
- name: `?CleanupRecycleBin@RetailDemoUserAgent@@UEAAJXZ`
- size: `309`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x18000aa7c`
- `0x180022484`
- `0x180036580`
- `0x1800396f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003977b`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003977b`
- `SHELL32!SHQueryRecycleBinW` at `0x18003971b`
- `SHELL32!SHQueryRecycleBinW` at `0x18003971b`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180039800`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180039800`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x1800397bd`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x1800397bd`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x180039757`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x180039757`

## string_xrefs

- `0x180039731`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180039793`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800397ce`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003976d`: `Software\Microsoft\Windows\CurrentVersion\Explorer\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}`

## pseudocode

```c
__int64 __fastcall RetailDemoUserAgent::CleanupRecycleBin(RetailDemoUserAgent *this)
{
  HRESULT v1; // ebx
  __int64 v2; // rdx
  unsigned int v4; // eax
  HRESULT v5; // eax
  LPITEMIDLIST ppidl; // [rsp+20h] [rbp-38h] BYREF
  _SHQUERYRBINFO pSHQueryRBInfo; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  memset(&pSHQueryRBInfo, 0, sizeof(pSHQueryRBInfo));
  v1 = SHQueryRecycleBinW(0, &pSHQueryRBInfo);
  if ( v1 < 0 )
  {
    v2 = 1664;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v1,
      (int)ppidl);
    return (unsigned int)v1;
  }
  if ( pSHQueryRBInfo.i64NumItems > 0 )
  {
    v1 = SHEmptyRecycleBinW(0, 0, 7u);
    if ( v1 < 0 )
    {
      v2 = 1667;
      goto LABEL_3;
    }
  }
  v4 = RegDeleteKeyValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CLSID\\{645FF040-5081-101B-9F08-00AA002F954E}",
         0);
  if ( v4 != 2 )
  {
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x68B,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)v4,
        (unsigned int)ppidl);
    ppidl = 0;
    v5 = SHGetSpecialFolderLocation(0, 10, &ppidl);
    v1 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v5,
        (int)ppidl);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
      return (unsigned int)v1;
    }
    SHChangeNotify(0x20000, 0, ppidl, ppidl);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
  }
  return 0;
}

```

## disassembly

```asm
0x1800396f0  push    rbx
0x1800396f2  sub     rsp, 50h
0x1800396f6  mov     rax, cs:__security_cookie
0x1800396fd  xor     rax, rsp
0x180039700  mov     [rsp+58h+var_18], rax
0x180039705  xorps   xmm0, xmm0
0x180039708  lea     rdx, [rsp+58h+pSHQueryRBInfo]; pSHQueryRBInfo
0x18003970d  xor     eax, eax
0x18003970f  xor     ecx, ecx; pszRootPath
0x180039711  movups  xmmword ptr [rsp+58h+pSHQueryRBInfo.cbSize], xmm0
0x180039716  mov     [rsp+58h+pSHQueryRBInfo.i64NumItems], rax
0x18003971b  call    cs:__imp_SHQueryRecycleBinW
0x180039721  mov     ebx, eax
0x180039723  test    eax, eax
0x180039725  jns     short loc_180039747
0x180039727  mov     edx, 680h; void *
0x18003972c  mov     rcx, [rsp+58h]; this
0x180039731  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180039738  mov     r9d, ebx; char *
0x18003973b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039740  mov     eax, ebx
0x180039742  jmp     loc_180039812
0x180039747  cmp     [rsp+58h+pSHQueryRBInfo.i64NumItems], 0
0x18003974d  jle     short loc_18003976A
0x18003974f  xor     edx, edx; pszRootPath
0x180039751  xor     ecx, ecx; hwnd
0x180039753  lea     r8d, [rdx+7]; dwFlags
0x180039757  call    cs:__imp_SHEmptyRecycleBinW
0x18003975d  mov     ebx, eax
0x18003975f  test    eax, eax
0x180039761  jns     short loc_18003976A
0x180039763  mov     edx, 683h
0x180039768  jmp     short loc_18003972C
0x18003976a  xor     r8d, r8d; lpValueName
0x18003976d  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039774  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003977b  call    cs:__imp_RegDeleteKeyValueW
0x180039781  cmp     eax, 2
0x180039784  jz      loc_180039810
0x18003978a  test    eax, eax
0x18003978c  jz      short loc_1800397A8
0x18003978e  mov     rcx, [rsp+58h]; this
0x180039793  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003979a  mov     r9d, eax; char *
0x18003979d  mov     edx, 68Bh; void *
0x1800397a2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800397a8  lea     r8, [rsp+58h+ppidl]; ppidl
0x1800397ad  mov     [rsp+58h+ppidl], 0; int
0x1800397b6  mov     edx, 0Ah; csidl
0x1800397bb  xor     ecx, ecx; hwnd
0x1800397bd  call    cs:__imp_SHGetSpecialFolderLocation
0x1800397c3  mov     ebx, eax
0x1800397c5  test    eax, eax
0x1800397c7  jns     short loc_1800397F1
0x1800397c9  mov     rcx, [rsp+58h]; this
0x1800397ce  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800397d5  mov     r9d, eax; char *
0x1800397d8  mov     edx, 68Dh; void *
0x1800397dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800397e2  lea     rcx, [rsp+58h+ppidl]
0x1800397e7  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800397ec  jmp     loc_180039740
0x1800397f1  mov     r8, [rsp+58h+ppidl]; dwItem1
0x1800397f6  xor     edx, edx; uFlags
0x1800397f8  mov     r9, r8; dwItem2
0x1800397fb  mov     ecx, 20000h; wEventId
0x180039800  call    cs:__imp_SHChangeNotify
0x180039806  lea     rcx, [rsp+58h+ppidl]
0x18003980b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180039810  xor     eax, eax
0x180039812  mov     rcx, [rsp+58h+var_18]
0x180039817  xor     rcx, rsp; StackCookie
0x18003981a  call    __security_check_cookie
0x18003981f  add     rsp, 50h
0x180039823  pop     rbx
0x180039824  retn
```
