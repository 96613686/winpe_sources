# IkeRasGetVpnIkeDllName

- ea: `0x180097c54`
- end: `0x180097d5b`
- name: `IkeRasGetVpnIkeDllName`
- size: `263`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180097428`

## callees

- `0x1800061ec`
- `0x18004aa3c`
- `0x180050850`
- `0x18005453c`
- `0x180097c54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097d34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097cf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097cbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097cbc`

## string_xrefs

- `0x180097c98`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x180097cc6`: `RegOpenKeyExW`
- `0x180097d16`: `vpnikeapi.dll`
- `0x180097ceb`: `VpnIkeDll`
- `0x180097c75`: `IkeRasGetVpnIkeDllName`
- `0x180097d3c`: `IkeRasGetVpnIkeDllName`

## pseudocode

```c
__int64 __fastcall IkeRasGetVpnIkeDllName(BYTE *pszDest)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  const char *v4; // rdx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  Type = 1;
  cbData = 520;
  TraceLogHelper("IkeRasGetVpnIkeDllName", 1);
  *(_WORD *)pszDest = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v4 = "RegOpenKeyExW";
  }
  else
  {
    v2 = RegQueryValueExW(hKey, L"VpnIkeDll", 0, &Type, pszDest, &cbData);
    if ( !v2 )
      goto LABEL_7;
    v4 = "RegQueryValueExW";
  }
  if ( WfpReportSysErrorAsWinError(v3, v4, v2, 1) )
    StringCchCopyW((STRSAFE_LPWSTR)pszDest, 0x104u, L"vpnikeapi.dll");
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return TraceLogHelper("IkeRasGetVpnIkeDllName", 0);
}

```

## disassembly

```asm
0x180097c54  push    rbx
0x180097c56  sub     rsp, 50h
0x180097c5a  mov     rax, cs:__security_cookie
0x180097c61  xor     rax, rsp
0x180097c64  mov     [rsp+58h+var_18], rax
0x180097c69  mov     rbx, rcx
0x180097c6c  mov     [rsp+58h+hKey], 0
0x180097c75  lea     rcx, aIkerasgetvpnik; "IkeRasGetVpnIkeDllName"
0x180097c7c  mov     [rsp+58h+Type], 1
0x180097c84  mov     edx, 1
0x180097c89  mov     [rsp+58h+cbData], 208h
0x180097c91  call    TraceLogHelper
0x180097c96  xor     eax, eax
0x180097c98  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x180097c9f  mov     [rbx], ax
0x180097ca2  mov     r9d, 20019h; samDesired
0x180097ca8  lea     rax, [rsp+58h+hKey]
0x180097cad  xor     r8d, r8d; ulOptions
0x180097cb0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097cb7  mov     [rsp+58h+phkResult], rax; phkResult
0x180097cbc  call    cs:__imp_RegOpenKeyExW
0x180097cc2  test    eax, eax
0x180097cc4  jz      short loc_180097CCF
0x180097cc6  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180097ccd  jmp     short loc_180097D03
0x180097ccf  mov     rcx, [rsp+58h+hKey]; hKey
0x180097cd4  lea     rax, [rsp+58h+cbData]
0x180097cd9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180097cde  lea     r9, [rsp+58h+Type]; lpType
0x180097ce3  xor     r8d, r8d; lpReserved
0x180097ce6  mov     [rsp+58h+phkResult], rbx; lpData
0x180097ceb  lea     rdx, aVpnikedll; "VpnIkeDll"
0x180097cf2  call    cs:__imp_RegQueryValueExW
0x180097cf8  test    eax, eax
0x180097cfa  jz      short loc_180097D2A
0x180097cfc  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180097d03  mov     r9d, 1
0x180097d09  mov     r8d, eax
0x180097d0c  call    WfpReportSysErrorAsWinError
0x180097d11  test    rax, rax
0x180097d14  jz      short loc_180097D2A
0x180097d16  lea     r8, aVpnikeapiDll; "vpnikeapi.dll"
0x180097d1d  mov     edx, 104h; cchDest
0x180097d22  mov     rcx, rbx; pszDest
0x180097d25  call    StringCchCopyW
0x180097d2a  mov     rcx, [rsp+58h+hKey]; hKey
0x180097d2f  test    rcx, rcx
0x180097d32  jz      short loc_180097D3A
0x180097d34  call    cs:__imp_RegCloseKey
0x180097d3a  xor     edx, edx
0x180097d3c  lea     rcx, aIkerasgetvpnik; "IkeRasGetVpnIkeDllName"
0x180097d43  call    TraceLogHelper
0x180097d48  mov     rcx, [rsp+58h+var_18]
0x180097d4d  xor     rcx, rsp; StackCookie
0x180097d50  call    __security_check_cookie
0x180097d55  add     rsp, 50h
0x180097d59  pop     rbx
0x180097d5a  retn
```
