# Windows::Globalization::Spelling::UserDictionaries::IsNetworkPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007f12c`
- end: `0x18007f1c8`
- name: `?IsNetworkPath@UserDictionaries@Spelling@Globalization@Windows@@CA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ec68`

## callees

- `0x180035dd8`
- `0x180061320`
- `0x18007f12c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18007f1a9`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18007f1a9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18007f14e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18007f14e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18007f169`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18007f169`

## pseudocode

```c
bool __fastcall Windows::Globalization::Spelling::UserDictionaries::IsNetworkPath(const WCHAR *pszPath)
{
  LPCWSTR v1; // rbx
  int DriveNumberW; // eax
  wchar_t Buffer[4]; // [rsp+20h] [rbp-28h] BYREF
  WCHAR RootPathName[4]; // [rsp+28h] [rbp-20h] BYREF

  v1 = pszPath;
  if ( *((_QWORD *)pszPath + 3) > 7u )
    pszPath = *(const WCHAR **)pszPath;
  if ( PathIsUNCW(pszPath) )
    return 1;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(LPCWSTR *)v1;
  DriveNumberW = PathGetDriveNumberW(v1);
  if ( DriveNumberW < 0 )
    return 0;
  *(_QWORD *)Buffer = 0;
  StringCchPrintfW(Buffer, 4u, L"%c:\\", (unsigned int)(DriveNumberW + 65));
  *(_QWORD *)RootPathName = *(_QWORD *)Buffer;
  return GetDriveTypeW(RootPathName) == 4;
}

```

## disassembly

```asm
0x18007f12c  push    rbx
0x18007f12e  sub     rsp, 40h
0x18007f132  mov     rax, cs:__security_cookie
0x18007f139  xor     rax, rsp
0x18007f13c  mov     [rsp+48h+var_18], rax
0x18007f141  cmp     qword ptr [rcx+18h], 7
0x18007f146  mov     rbx, rcx
0x18007f149  jbe     short loc_18007F14E
0x18007f14b  mov     rcx, [rcx]; pszPath
0x18007f14e  call    cs:__imp_PathIsUNCW
0x18007f154  test    eax, eax
0x18007f156  jz      short loc_18007F15C
0x18007f158  mov     al, 1
0x18007f15a  jmp     short loc_18007F1B5
0x18007f15c  cmp     qword ptr [rbx+18h], 7
0x18007f161  jbe     short loc_18007F166
0x18007f163  mov     rbx, [rbx]
0x18007f166  mov     rcx, rbx; pszPath
0x18007f169  call    cs:__imp_PathGetDriveNumberW
0x18007f16f  test    eax, eax
0x18007f171  jns     short loc_18007F177
0x18007f173  xor     al, al
0x18007f175  jmp     short loc_18007F1B5
0x18007f177  lea     r9d, [rax+41h]
0x18007f17b  mov     qword ptr [rsp+48h+Buffer], 0
0x18007f184  lea     r8, aC_0; "%c:\\"
0x18007f18b  mov     edx, 4; unsigned __int64
0x18007f190  lea     rcx, [rsp+48h+Buffer]; Buffer
0x18007f195  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f19a  mov     rax, qword ptr [rsp+48h+Buffer]
0x18007f19f  lea     rcx, [rsp+48h+RootPathName]; lpRootPathName
0x18007f1a4  mov     qword ptr [rsp+48h+RootPathName], rax
0x18007f1a9  call    cs:__imp_GetDriveTypeW
0x18007f1af  cmp     eax, 4
0x18007f1b2  setz    al
0x18007f1b5  mov     rcx, [rsp+48h+var_18]
0x18007f1ba  xor     rcx, rsp; StackCookie
0x18007f1bd  call    __security_check_cookie
0x18007f1c2  add     rsp, 40h
0x18007f1c6  pop     rbx
0x18007f1c7  retn
```
