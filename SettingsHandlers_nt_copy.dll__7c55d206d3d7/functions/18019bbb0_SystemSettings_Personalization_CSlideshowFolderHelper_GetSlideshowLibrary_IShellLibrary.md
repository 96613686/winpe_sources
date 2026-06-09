# SystemSettings::Personalization::CSlideshowFolderHelper::_GetSlideshowLibrary(IShellLibrary * *)

- ea: `0x18019bbb0`
- end: `0x18019bdf1`
- name: `?_GetSlideshowLibrary@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAPEAUIShellLibrary@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowFolderHelper *__hidden this, struct IShellLibrary **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180199cb0`
- `0x18019b540`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001a64c`
- `0x1800234f8`
- `0x18019bbb0`
- `0x18019c4e4`
- `0x18019c5a4`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bd7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019bd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019bcb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019bcb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019bd51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019bd51`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18019bd6a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18019bd6a`
- `SHELL32!SHCreateItemFromParsingName` at `0x18019bcf1`
- `SHELL32!SHCreateItemFromParsingName` at `0x18019bcf1`
- `SHELL32!SHGetKnownFolderPath` at `0x18019bc3f`
- `SHELL32!SHGetKnownFolderPath` at `0x18019bc3f`

## pseudocode

```c
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::_GetSlideshowLibrary(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        LPVOID *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  LPVOID v8; // rcx
  LPVOID v10; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR PathName[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[524]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR pszPath[2]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v16[524]; // [rsp+264h] [rbp+164h] BYREF

  *a2 = 0;
  v10 = 0;
  *(_DWORD *)PathName = 0;
  memset_0(v14, 0, 0x204u);
  *(_DWORD *)pszPath = 0;
  memset_0(v16, 0, 0x204u);
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v4 >= 0 )
  {
    v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 696);
    v4 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", ppszPath, v5);
    if ( v4 >= 0 )
      v4 = StringCchPrintfW(pszPath, 0x104u, L"%s\\%s", PathName, L"Slideshow.library-ms");
    CoTaskMemFree(ppszPath);
    if ( v4 >= 0 )
    {
      v10 = 0;
      ppv = 0;
      if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
      {
        v4 = SHLoadLibraryFromItem(ppv, v6, v7, &v10);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v4 >= 0 )
          goto LABEL_7;
      }
      v4 = CoCreateInstance(&CLSID_ShellLibrary, 0, 1u, &GUID_11a66efa_382e_451a_9234_1e0e12ef3085, &v10);
      if ( v4 >= 0 )
      {
        if ( CreateDirectoryW(PathName, 0) || GetLastError() == 183 )
        {
          v4 = SHSaveLibraryInFolderPath(v10, PathName);
          if ( v4 >= 0 )
          {
LABEL_7:
            v8 = 0;
            *a2 = v10;
            goto LABEL_14;
          }
        }
        else
        {
          v4 = -2147467259;
        }
      }
    }
  }
  v8 = v10;
LABEL_14:
  v10 = 0;
  if ( v8 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18019bbb0  mov     [rsp-8+arg_10], rbx
0x18019bbb5  push    rbp
0x18019bbb6  push    rsi
0x18019bbb7  push    rdi
0x18019bbb8  lea     rbp, [rsp-380h]
0x18019bbc0  sub     rsp, 480h
0x18019bbc7  mov     rax, cs:__security_cookie
0x18019bbce  xor     rax, rsp
0x18019bbd1  mov     [rbp+390h+var_20], rax
0x18019bbd8  mov     rdi, rdx
0x18019bbdb  mov     qword ptr [rdx], 0
0x18019bbe2  mov     rsi, rcx
0x18019bbe5  mov     [rsp+490h+var_460], 0
0x18019bbee  mov     ebx, 204h
0x18019bbf3  mov     dword ptr [rsp+490h+PathName], 0
0x18019bbfb  mov     r8d, ebx; Size
0x18019bbfe  lea     rcx, [rsp+490h+var_43C]; void *
0x18019bc03  xor     edx, edx; Val
0x18019bc05  call    memset_0
0x18019bc0a  mov     r8d, ebx; Size
0x18019bc0d  mov     dword ptr [rbp+390h+pszPath], 0
0x18019bc17  xor     edx, edx; Val
0x18019bc19  lea     rcx, [rbp+390h+var_22C]; void *
0x18019bc20  call    memset_0
0x18019bc25  lea     r9, [rsp+490h+ppszPath]; ppszPath
0x18019bc2a  mov     [rsp+490h+ppszPath], 0
0x18019bc33  xor     r8d, r8d; hToken
0x18019bc36  lea     rcx, FOLDERID_LocalAppData; rfid
0x18019bc3d  xor     edx, edx; dwFlags
0x18019bc3f  call    cs:__imp_SHGetKnownFolderPath
0x18019bc46  nop     dword ptr [rax+rax+00h]
0x18019bc4b  mov     ebx, eax
0x18019bc4d  test    eax, eax
0x18019bc4f  js      loc_18019BDAD
0x18019bc55  lea     rcx, [rsi+2B8h]
0x18019bc5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019bc61  mov     r9, [rsp+490h+ppszPath]
0x18019bc66  lea     r8, aSS; "%s\\%s"
0x18019bc6d  mov     esi, 104h
0x18019bc72  mov     [rsp+490h+var_470], rax
0x18019bc77  mov     edx, esi; unsigned __int64
0x18019bc79  lea     rcx, [rsp+490h+PathName]; unsigned __int16 *
0x18019bc7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019bc83  mov     ebx, eax
0x18019bc85  test    eax, eax
0x18019bc87  js      short loc_18019BCB1
0x18019bc89  lea     rax, aSlideshowLibra; "Slideshow.library-ms"
0x18019bc90  mov     edx, esi; unsigned __int64
0x18019bc92  lea     r9, [rsp+490h+PathName]
0x18019bc97  mov     [rsp+490h+var_470], rax
0x18019bc9c  lea     r8, aSS; "%s\\%s"
0x18019bca3  lea     rcx, [rbp+390h+pszPath]; unsigned __int16 *
0x18019bcaa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019bcaf  mov     ebx, eax
0x18019bcb1  mov     rcx, [rsp+490h+ppszPath]; pv
0x18019bcb6  call    cs:__imp_CoTaskMemFree
0x18019bcbd  nop     dword ptr [rax+rax+00h]
0x18019bcc2  test    ebx, ebx
0x18019bcc4  js      loc_18019BDAD
0x18019bcca  lea     r9, [rsp+490h+ppv]; ppv
0x18019bccf  mov     [rsp+490h+var_460], 0
0x18019bcd8  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18019bcdf  mov     [rsp+490h+ppv], 0
0x18019bce8  xor     edx, edx; pbc
0x18019bcea  lea     rcx, [rbp+390h+pszPath]; pszPath
0x18019bcf1  call    cs:__imp_SHCreateItemFromParsingName
0x18019bcf8  nop     dword ptr [rax+rax+00h]
0x18019bcfd  test    eax, eax
0x18019bcff  js      short loc_18019BD33
0x18019bd01  mov     rcx, [rsp+490h+ppv]
0x18019bd06  lea     r9, [rsp+490h+var_460]
0x18019bd0b  call    SHLoadLibraryFromItem
0x18019bd10  mov     rcx, [rsp+490h+ppv]
0x18019bd15  mov     ebx, eax
0x18019bd17  mov     rax, [rcx]
0x18019bd1a  mov     rax, [rax+10h]
0x18019bd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019bd23  test    ebx, ebx
0x18019bd25  js      short loc_18019BD33
0x18019bd27  mov     rax, [rsp+490h+var_460]
0x18019bd2c  xor     ecx, ecx
0x18019bd2e  mov     [rdi], rax
0x18019bd31  jmp     short loc_18019BDB2
0x18019bd33  xor     edx, edx; pUnkOuter
0x18019bd35  lea     rax, [rsp+490h+var_460]
0x18019bd3a  lea     r9, _GUID_11a66efa_382e_451a_9234_1e0e12ef3085; riid
0x18019bd41  mov     [rsp+490h+var_470], rax; ppv
0x18019bd46  lea     rcx, CLSID_ShellLibrary; rclsid
0x18019bd4d  lea     r8d, [rdx+1]; dwClsContext
0x18019bd51  call    cs:__imp_CoCreateInstance
0x18019bd58  nop     dword ptr [rax+rax+00h]
0x18019bd5d  mov     ebx, eax
0x18019bd5f  test    eax, eax
0x18019bd61  js      short loc_18019BDAD
0x18019bd63  xor     edx, edx; lpSecurityAttributes
0x18019bd65  lea     rcx, [rsp+490h+PathName]; lpPathName
0x18019bd6a  call    cs:__imp_CreateDirectoryW
0x18019bd71  nop     dword ptr [rax+rax+00h]
0x18019bd76  test    eax, eax
0x18019bd78  jnz     short loc_18019BD94
0x18019bd7a  call    cs:__imp_GetLastError
0x18019bd81  nop     dword ptr [rax+rax+00h]
0x18019bd86  cmp     eax, 0B7h
0x18019bd8b  jz      short loc_18019BD94
0x18019bd8d  mov     ebx, 80004005h
0x18019bd92  jmp     short loc_18019BDAD
0x18019bd94  mov     rcx, [rsp+490h+var_460]
0x18019bd99  lea     rdx, [rsp+490h+PathName]
0x18019bd9e  call    SHSaveLibraryInFolderPath
0x18019bda3  mov     ebx, eax
0x18019bda5  test    eax, eax
0x18019bda7  jns     loc_18019BD27
0x18019bdad  mov     rcx, [rsp+490h+var_460]
0x18019bdb2  mov     [rsp+490h+var_460], 0
0x18019bdbb  test    rcx, rcx
0x18019bdbe  jz      short loc_18019BDCC
0x18019bdc0  mov     rax, [rcx]
0x18019bdc3  mov     rax, [rax+10h]
0x18019bdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019bdcc  mov     eax, ebx
0x18019bdce  mov     rcx, [rbp+390h+var_20]
0x18019bdd5  xor     rcx, rsp; StackCookie
0x18019bdd8  call    __security_check_cookie
0x18019bddd  mov     rbx, [rsp+490h+arg_10]
0x18019bde5  add     rsp, 480h
0x18019bdec  pop     rdi
0x18019bded  pop     rsi
0x18019bdee  pop     rbp
0x18019bdef  retn
```
