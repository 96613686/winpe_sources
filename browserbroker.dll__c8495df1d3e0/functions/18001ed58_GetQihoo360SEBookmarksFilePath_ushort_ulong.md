# GetQihoo360SEBookmarksFilePath(ushort *,ulong)

- ea: `0x18001ed58`
- end: `0x18001ef1b`
- name: `?GetQihoo360SEBookmarksFilePath@@YAJPEAGK@Z`
- size: `451`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, service_task`

## callers

- `0x18000c640`
- `0x18001f5b4`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006c90`
- `0x18000d17c`
- `0x18001ed58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001ee8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001ee8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee6f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001edd7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ee0e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001eed3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001eeec`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001edd7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ee0e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001eed3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001eeec`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ee67`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001eec0`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ee67`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001eec0`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001ed9d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001ed9d`

## pseudocode

```c
__int64 __fastcall GetQihoo360SEBookmarksFilePath(unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  DWORD PrivateProfileStringW; // ebx
  PWSTR ppszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszMore[8]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v8[512]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR ReturnedString[264]; // [rsp+460h] [rbp+360h] BYREF

  ppszPath[0] = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0x15000u, 0, ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(a1, 0x104u, ppszPath[0]);
    if ( v2 >= 0 )
    {
      v2 = PathCchAppend(a1, 0x104u, L"360se6\\apps\\data\\users");
      if ( v2 >= 0 )
      {
        v2 = StringCchCopyW(pszPath, 0x104u, a1);
        if ( v2 >= 0 )
        {
          v2 = PathCchAppend(pszPath, 0x104u, L"login.ini");
          if ( v2 >= 0 )
          {
            wcscpy(pszMore, L"default");
            memset_0(v8, 0, 0x1F8u);
            PrivateProfileStringW = GetPrivateProfileStringW(
                                      L"NowLogin",
                                      L"IsLogined",
                                      0,
                                      ReturnedString,
                                      0x104u,
                                      pszPath);
            if ( GetLastError() != 2 && PrivateProfileStringW && !(unsigned int)_o__wcsicmp(ReturnedString, L"1") )
              GetPrivateProfileStringW(L"NowLogin", L"UserMd5", L"default", pszMore, 0x104u, pszPath);
            v2 = PathCchAppend(a1, 0x104u, pszMore);
            if ( v2 >= 0 )
              v2 = PathCchAppend(a1, 0x104u, L"360sefav.db");
          }
        }
      }
    }
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001ed58  push    rbp
0x18001ed5a  push    rbx
0x18001ed5b  push    rsi
0x18001ed5c  push    rdi
0x18001ed5d  lea     rbp, [rsp-588h]
0x18001ed65  sub     rsp, 688h
0x18001ed6c  mov     rax, cs:__security_cookie
0x18001ed73  xor     rax, rsp
0x18001ed76  mov     [rbp+5A0h+var_30], rax
0x18001ed7d  mov     rdi, rcx
0x18001ed80  mov     [rsp+6A0h+ppszPath], 0
0x18001ed89  lea     rcx, FOLDERID_RoamingAppData; rfid
0x18001ed90  xor     r8d, r8d; hToken
0x18001ed93  lea     r9, [rsp+6A0h+ppszPath]; ppszPath
0x18001ed98  mov     edx, 15000h; dwFlags
0x18001ed9d  call    cs:__imp_SHGetKnownFolderPath
0x18001eda3  mov     ebx, eax
0x18001eda5  test    eax, eax
0x18001eda7  js      loc_18001EEF4
0x18001edad  mov     r8, [rsp+6A0h+ppszPath]; unsigned __int16 *
0x18001edb2  mov     esi, 104h
0x18001edb7  mov     edx, esi; unsigned __int64
0x18001edb9  mov     rcx, rdi; unsigned __int16 *
0x18001edbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001edc1  mov     ebx, eax
0x18001edc3  test    eax, eax
0x18001edc5  js      loc_18001EEF4
0x18001edcb  lea     r8, a360se6AppsData; "360se6\\apps\\data\\users"
0x18001edd2  mov     edx, esi; cchPath
0x18001edd4  mov     rcx, rdi; pszPath
0x18001edd7  call    cs:__imp_PathCchAppend
0x18001eddd  mov     ebx, eax
0x18001eddf  test    eax, eax
0x18001ede1  js      loc_18001EEF4
0x18001ede7  mov     r8, rdi; unsigned __int16 *
0x18001edea  lea     rcx, [rsp+6A0h+pszPath]; unsigned __int16 *
0x18001edef  mov     edx, esi; unsigned __int64
0x18001edf1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001edf6  mov     ebx, eax
0x18001edf8  test    eax, eax
0x18001edfa  js      loc_18001EEF4
0x18001ee00  lea     r8, aLoginIni; "login.ini"
0x18001ee07  mov     edx, esi; cchPath
0x18001ee09  lea     rcx, [rsp+6A0h+pszPath]; pszPath
0x18001ee0e  call    cs:__imp_PathCchAppend
0x18001ee14  mov     ebx, eax
0x18001ee16  test    eax, eax
0x18001ee18  js      loc_18001EEF4
0x18001ee1e  movups  xmm0, xmmword ptr cs:aDefault; "default"
0x18001ee25  xor     edx, edx; Val
0x18001ee27  lea     rcx, [rbp+5A0h+var_440]; void *
0x18001ee2e  mov     r8d, 1F8h; Size
0x18001ee34  movdqu  xmmword ptr [rbp+5A0h+pszMore], xmm0
0x18001ee3c  call    memset_0
0x18001ee41  lea     rax, [rsp+6A0h+pszPath]
0x18001ee46  xor     r8d, r8d; lpDefault
0x18001ee49  mov     [rsp+6A0h+lpFileName], rax; lpFileName
0x18001ee4e  lea     r9, [rbp+5A0h+ReturnedString]; lpReturnedString
0x18001ee55  lea     rdx, aIslogined; "IsLogined"
0x18001ee5c  mov     [rsp+6A0h+nSize], esi; nSize
0x18001ee60  lea     rcx, aNowlogin; "NowLogin"
0x18001ee67  call    cs:__imp_GetPrivateProfileStringW
0x18001ee6d  mov     ebx, eax
0x18001ee6f  call    cs:__imp_GetLastError
0x18001ee75  cmp     eax, 2
0x18001ee78  jz      short loc_18001EEC6
0x18001ee7a  test    ebx, ebx
0x18001ee7c  jz      short loc_18001EEC6
0x18001ee7e  lea     rdx, psz; "1"
0x18001ee85  lea     rcx, [rbp+5A0h+ReturnedString]
0x18001ee8c  call    cs:__imp__o__wcsicmp
0x18001ee92  test    eax, eax
0x18001ee94  jnz     short loc_18001EEC6
0x18001ee96  lea     rax, [rsp+6A0h+pszPath]
0x18001ee9b  mov     [rsp+6A0h+lpFileName], rax; lpFileName
0x18001eea0  lea     r9, [rbp+5A0h+pszMore]; lpReturnedString
0x18001eea7  lea     r8, aDefault; "default"
0x18001eeae  mov     [rsp+6A0h+nSize], esi; nSize
0x18001eeb2  lea     rdx, aUsermd5; "UserMd5"
0x18001eeb9  lea     rcx, aNowlogin; "NowLogin"
0x18001eec0  call    cs:__imp_GetPrivateProfileStringW
0x18001eec6  lea     r8, [rbp+5A0h+pszMore]; pszMore
0x18001eecd  mov     rdx, rsi; cchPath
0x18001eed0  mov     rcx, rdi; pszPath
0x18001eed3  call    cs:__imp_PathCchAppend
0x18001eed9  mov     ebx, eax
0x18001eedb  test    eax, eax
0x18001eedd  js      short loc_18001EEF4
0x18001eedf  lea     r8, a360sefavDb; "360sefav.db"
0x18001eee6  mov     rdx, rsi; cchPath
0x18001eee9  mov     rcx, rdi; pszPath
0x18001eeec  call    cs:__imp_PathCchAppend
0x18001eef2  mov     ebx, eax
0x18001eef4  lea     rcx, [rsp+6A0h+ppszPath]
0x18001eef9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001eefe  mov     eax, ebx
0x18001ef00  mov     rcx, [rbp+5A0h+var_30]
0x18001ef07  xor     rcx, rsp; StackCookie
0x18001ef0a  call    __security_check_cookie
0x18001ef0f  add     rsp, 688h
0x18001ef16  pop     rdi
0x18001ef17  pop     rsi
0x18001ef18  pop     rbx
0x18001ef19  pop     rbp
0x18001ef1a  retn
```
