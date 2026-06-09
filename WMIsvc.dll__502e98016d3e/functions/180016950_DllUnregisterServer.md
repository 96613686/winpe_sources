# DllUnregisterServer

- ea: `0x180016950`
- end: `0x180016a5d`
- name: `DllUnregisterServer`
- size: `269`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b08`
- `0x180016950`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169f6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180016a10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180016a2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169f6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180016a10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180016a2a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016977`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800169c7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180016977`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800169c7`

## string_xrefs

- `0x180016987`: `software\classes\CLSID\%s`
- `0x1800169d7`: `software\classes\CLSID\%s`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LPOLESTR lpsz[10]; // [rsp+20h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-228h] BYREF

  StringFromCLSID(&CLSID_WbemLevel1Login, lpsz);
  StringCchPrintfW(SubKey, 0x104u, L"software\\classes\\CLSID\\%s", lpsz);
  if ( RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0) )
    return -2147467259;
  StringFromCLSID(&CLSID_WbemBackupRestore, lpsz);
  StringCchPrintfW(SubKey, 0x104u, L"software\\classes\\CLSID\\%s", lpsz);
  if ( RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0)
    || RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"Software\\classes\\AppID\\{8BC3F05E-D86B-11D0-A075-00C04FB68820}", 0, 0) )
  {
    return -2147467259;
  }
  else
  {
    return RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"Software\\classes\\AppID\\winmgmt", 0, 0) != 0 ? 0x80004005 : 0;
  }
}

```

## disassembly

```asm
0x180016950  push    rbx
0x180016952  sub     rsp, 290h
0x180016959  mov     rax, cs:__security_cookie
0x180016960  xor     rax, rsp
0x180016963  mov     [rsp+298h+var_18], rax
0x18001696b  lea     rdx, [rsp+298h+lpsz]; lplpsz
0x180016970  lea     rcx, CLSID_WbemLevel1Login; rclsid
0x180016977  call    cs:__imp_StringFromCLSID
0x18001697d  lea     r9, [rsp+298h+lpsz]
0x180016982  mov     edx, 104h; unsigned __int64
0x180016987  lea     r8, aSoftwareClasse_1; "software\\classes\\CLSID\\%s"
0x18001698e  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x180016993  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016998  mov     rbx, 0FFFFFFFF80000002h
0x18001699f  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x1800169a4  mov     rcx, rbx; hKey
0x1800169a7  xor     r9d, r9d; Reserved
0x1800169aa  xor     r8d, r8d; samDesired
0x1800169ad  call    cs:__imp_RegDeleteKeyExW
0x1800169b3  test    eax, eax
0x1800169b5  jnz     loc_180016A3F
0x1800169bb  lea     rdx, [rsp+298h+lpsz]; lplpsz
0x1800169c0  lea     rcx, CLSID_WbemBackupRestore; rclsid
0x1800169c7  call    cs:__imp_StringFromCLSID
0x1800169cd  lea     r9, [rsp+298h+lpsz]
0x1800169d2  mov     edx, 104h; unsigned __int64
0x1800169d7  lea     r8, aSoftwareClasse_1; "software\\classes\\CLSID\\%s"
0x1800169de  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x1800169e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800169e8  xor     r9d, r9d; Reserved
0x1800169eb  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x1800169f0  xor     r8d, r8d; samDesired
0x1800169f3  mov     rcx, rbx; hKey
0x1800169f6  call    cs:__imp_RegDeleteKeyExW
0x1800169fc  test    eax, eax
0x1800169fe  jnz     short loc_180016A3F
0x180016a00  xor     r9d, r9d; Reserved
0x180016a03  lea     rdx, aSoftwareClasse_2; "Software\\classes\\AppID\\{8BC3F05E-D86"...
0x180016a0a  xor     r8d, r8d; samDesired
0x180016a0d  mov     rcx, rbx; hKey
0x180016a10  call    cs:__imp_RegDeleteKeyExW
0x180016a16  test    eax, eax
0x180016a18  jnz     short loc_180016A3F
0x180016a1a  xor     r9d, r9d; Reserved
0x180016a1d  lea     rdx, aSoftwareClasse_0; "Software\\classes\\AppID\\winmgmt"
0x180016a24  xor     r8d, r8d; samDesired
0x180016a27  mov     rcx, rbx; hKey
0x180016a2a  call    cs:__imp_RegDeleteKeyExW
0x180016a30  xor     ecx, ecx
0x180016a32  sub     ecx, eax
0x180016a34  neg     ecx
0x180016a36  sbb     eax, eax
0x180016a38  and     eax, 80004005h
0x180016a3d  jmp     short loc_180016A44
0x180016a3f  mov     eax, 80004005h
0x180016a44  mov     rcx, [rsp+298h+var_18]
0x180016a4c  xor     rcx, rsp; StackCookie
0x180016a4f  call    __security_check_cookie
0x180016a54  add     rsp, 290h
0x180016a5b  pop     rbx
0x180016a5c  retn
```
