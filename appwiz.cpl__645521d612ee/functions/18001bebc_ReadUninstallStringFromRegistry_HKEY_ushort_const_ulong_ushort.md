# ReadUninstallStringFromRegistry(HKEY__ *,ushort const *,ulong,ushort * *)

- ea: `0x18001bebc`
- end: `0x18001bf7a`
- name: `?ReadUninstallStringFromRegistry@@YAJPEAUHKEY__@@PEBGKPEAPEAG@Z`
- size: `190`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bc50`

## callees

- `0x18001bebc`
- `0x180044db4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bef6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bef6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf69`

## string_xrefs

- `0x18001bee7`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x18001bf33`: `UninstallString`
- `0x18001bf3e`: `ModifyPath`

## pseudocode

```c
__int64 __fastcall ReadUninstallStringFromRegistry(HKEY a1, const unsigned __int16 *a2, int a3, unsigned __int16 **a4)
{
  unsigned int v7; // edi
  const WCHAR *v8; // rdx
  unsigned __int16 *LocalizedStringFromRegistry; // rax
  unsigned __int16 *v10; // rbx
  HKEY hkey; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  v7 = -2147467259;
  if ( !RegOpenKeyExW(a1, L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0x20019u, &hKey) )
  {
    hkey = 0;
    if ( !RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hkey) )
    {
      v8 = L"UninstallString";
      if ( a3 )
        v8 = L"ModifyPath";
      LocalizedStringFromRegistry = GetLocalizedStringFromRegistry(hkey, v8);
      *a4 = LocalizedStringFromRegistry;
      v10 = LocalizedStringFromRegistry;
      RegCloseKey(hkey);
      v7 = v10 == 0 ? 0x80004005 : 0;
    }
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x18001bebc  push    rbx
0x18001bebe  push    rbp
0x18001bebf  push    rsi
0x18001bec0  push    rdi
0x18001bec1  sub     rsp, 48h
0x18001bec5  mov     rsi, r9
0x18001bec8  mov     [rsp+68h+hKey], 0
0x18001bed1  mov     ebx, r8d
0x18001bed4  lea     rax, [rsp+68h+hKey]
0x18001bed9  mov     rbp, rdx
0x18001bedc  mov     [rsp+68h+phkResult], rax; phkResult
0x18001bee1  mov     r9d, 20019h; samDesired
0x18001bee7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001beee  xor     r8d, r8d; ulOptions
0x18001bef1  mov     edi, 80004005h
0x18001bef6  call    cs:__imp_RegOpenKeyExW
0x18001befc  test    eax, eax
0x18001befe  jnz     short loc_18001BF6F
0x18001bf00  mov     rcx, [rsp+68h+hKey]; hKey
0x18001bf05  lea     rax, [rsp+68h+hkey]
0x18001bf0a  mov     r9d, 20019h; samDesired
0x18001bf10  mov     [rsp+68h+phkResult], rax; phkResult
0x18001bf15  xor     r8d, r8d; ulOptions
0x18001bf18  mov     [rsp+68h+hkey], 0
0x18001bf21  mov     rdx, rbp; lpSubKey
0x18001bf24  call    cs:__imp_RegOpenKeyExW
0x18001bf2a  test    eax, eax
0x18001bf2c  jnz     short loc_18001BF64
0x18001bf2e  mov     rcx, [rsp+68h+hkey]; hkey
0x18001bf33  lea     rdx, aUninstallstrin; "UninstallString"
0x18001bf3a  test    ebx, ebx
0x18001bf3c  jz      short loc_18001BF45
0x18001bf3e  lea     rdx, aModifypath; "ModifyPath"
0x18001bf45  call    ?GetLocalizedStringFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; GetLocalizedStringFromRegistry(HKEY__ *,ushort const *)
0x18001bf4a  mov     [rsi], rax
0x18001bf4d  mov     rbx, rax
0x18001bf50  mov     rcx, [rsp+68h+hkey]; hKey
0x18001bf55  call    cs:__imp_RegCloseKey
0x18001bf5b  neg     rbx
0x18001bf5e  sbb     ecx, ecx
0x18001bf60  not     ecx
0x18001bf62  and     edi, ecx
0x18001bf64  mov     rcx, [rsp+68h+hKey]; hKey
0x18001bf69  call    cs:__imp_RegCloseKey
0x18001bf6f  mov     eax, edi
0x18001bf71  add     rsp, 48h
0x18001bf75  pop     rdi
0x18001bf76  pop     rsi
0x18001bf77  pop     rbp
0x18001bf78  pop     rbx
0x18001bf79  retn
```
