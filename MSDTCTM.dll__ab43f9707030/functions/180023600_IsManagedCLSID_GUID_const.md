# IsManagedCLSID(_GUID const &)

- ea: `0x180023600`
- end: `0x180023802`
- name: `?IsManagedCLSID@@YA_NAEBU_GUID@@@Z`
- size: `514`
- prototype: `bool __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fdb8`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x180023600`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180023688`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180023688`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023760`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023718`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800237d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800237d5`
- `msvcrt!wcsrchr` at `0x18002378f`
- `msvcrt!wcsrchr` at `0x1800237a1`
- `msvcrt!wcsrchr` at `0x18002378f`
- `msvcrt!wcsrchr` at `0x1800237a1`
- `msvcrt!_wcsicmp` at `0x1800237bf`
- `msvcrt!_wcsicmp` at `0x1800237bf`

## string_xrefs

- `0x1800236a4`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`
- `0x1800236b4`: `IsManagedCLSID`
- `0x18002372c`: `RegOpenKeyExW`
- `0x1800237b8`: `mscoree.dll`
- `0x1800236d7`: `CLSID\%s\InprocServer32`

## pseudocode

```c
bool __fastcall IsManagedCLSID(GUID *rguid)
{
  bool v2; // di
  int v3; // eax
  const wchar_t *v4; // rcx
  __int64 v5; // r9
  wchar_t *v6; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[63]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v14; // [rsp+11Eh] [rbp+1Eh] BYREF
  wchar_t Data[264]; // [rsp+120h] [rbp+20h] BYREF

  hKey = 0;
  v2 = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  Type = 0;
  memset_0(SubKey, 0, 0x80u);
  memset_0(sz, 0, sizeof(sz));
  v3 = StringFromGUID2(rguid, sz, 40);
  if ( v3 < 0 )
  {
    v4 = L"StringFromGUID2";
    v5 = 238;
LABEL_3:
    LODWORD(lpcbData) = v3;
    TraceStringInline(3, 1, L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp", v5, L"IsManagedCLSID", lpcbData, v4);
    goto LABEL_18;
  }
  v3 = StringCchPrintfW(SubKey, 0x40u, L"CLSID\\%s\\InprocServer32", sz);
  if ( v3 < 0 )
  {
    v4 = L"StringCchPrintf";
    v5 = 245;
    goto LABEL_3;
  }
  v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey);
  if ( v3 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = L"RegOpenKeyExW";
    v5 = 257;
    goto LABEL_3;
  }
  v3 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
  if ( v3 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = L"RegQueryValueExW";
    v5 = 270;
    goto LABEL_3;
  }
  v6 = wcsrchr(Data, 0x5Cu);
  if ( !v6 )
  {
    v6 = wcsrchr(Data, 0x2Fu);
    if ( !v6 )
      v6 = (wchar_t *)&v14;
  }
  v2 = _wcsicmp(v6 + 1, L"mscoree.dll") == 0;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180023600  mov     [rsp-8+arg_8], rbx
0x180023605  mov     [rsp-8+arg_10], rdi
0x18002360a  push    rbp
0x18002360b  lea     rbp, [rsp-240h]
0x180023613  sub     rsp, 340h
0x18002361a  mov     rax, cs:__security_cookie
0x180023621  xor     rax, rsp
0x180023624  mov     [rbp+240h+var_10], rax
0x18002362b  mov     rbx, rcx
0x18002362e  mov     [rsp+340h+hKey], 0
0x180023637  mov     edi, 20Ah
0x18002363c  lea     rcx, [rbp+240h+Data]; void *
0x180023640  mov     r8d, edi; Size
0x180023643  xor     edx, edx; Val
0x180023645  call    memset_0
0x18002364a  xor     edx, edx; Val
0x18002364c  mov     [rsp+340h+cbData], edi
0x180023650  mov     r8d, 80h; Size
0x180023656  mov     [rsp+340h+Type], 0
0x18002365e  lea     rcx, [rbp+240h+SubKey]; void *
0x180023662  call    memset_0
0x180023667  xor     edx, edx; Val
0x180023669  lea     rcx, [rsp+340h+sz]; void *
0x18002366e  lea     r8d, [rdx+50h]; Size
0x180023672  call    memset_0
0x180023677  mov     r8d, 28h ; '('; cchMax
0x18002367d  lea     rdx, [rsp+340h+sz]; lpsz
0x180023682  mov     rcx, rbx; rguid
0x180023685  xor     dil, dil
0x180023688  call    cs:__imp_StringFromGUID2
0x18002368e  test    eax, eax
0x180023690  jns     short loc_1800236CD
0x180023692  lea     rcx, aStringfromguid; "StringFromGUID2"
0x180023699  mov     r9d, 0EEh
0x18002369f  mov     [rsp+340h+var_310], rcx
0x1800236a4  lea     r8, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtc\\src\\ini"...
0x1800236ab  mov     dword ptr [rsp+340h+lpcbData], eax
0x1800236af  mov     edx, 1
0x1800236b4  lea     rax, aIsmanagedclsid; "IsManagedCLSID"
0x1800236bb  mov     [rsp+340h+phkResult], rax
0x1800236c0  lea     ecx, [rdx+2]
0x1800236c3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800236c8  jmp     loc_1800237CB
0x1800236cd  lea     r9, [rsp+340h+sz]
0x1800236d2  mov     edx, 40h ; '@'; unsigned __int64
0x1800236d7  lea     r8, aClsidSInprocse; "CLSID\\%s\\InprocServer32"
0x1800236de  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x1800236e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800236e7  test    eax, eax
0x1800236e9  jns     short loc_1800236FA
0x1800236eb  lea     rcx, aStringcchprint_1; "StringCchPrintf"
0x1800236f2  mov     r9d, 0F5h
0x1800236f8  jmp     short loc_18002369F
0x1800236fa  lea     rax, [rsp+340h+hKey]
0x1800236ff  mov     r9d, 1; samDesired
0x180023705  xor     r8d, r8d; ulOptions
0x180023708  mov     [rsp+340h+phkResult], rax; phkResult
0x18002370d  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x180023711  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180023718  call    cs:__imp_RegOpenKeyExW
0x18002371e  test    eax, eax
0x180023720  jz      short loc_18002373E
0x180023722  jle     short loc_18002372C
0x180023724  movzx   eax, ax
0x180023727  or      eax, 80070000h
0x18002372c  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x180023733  mov     r9d, 101h
0x180023739  jmp     loc_18002369F
0x18002373e  mov     rcx, [rsp+340h+hKey]; hKey
0x180023743  lea     rax, [rsp+340h+cbData]
0x180023748  mov     [rsp+340h+lpcbData], rax; lpcbData
0x18002374d  lea     r9, [rsp+340h+Type]; lpType
0x180023752  lea     rax, [rbp+240h+Data]
0x180023756  xor     r8d, r8d; lpReserved
0x180023759  xor     edx, edx; lpValueName
0x18002375b  mov     [rsp+340h+phkResult], rax; lpData
0x180023760  call    cs:__imp_RegQueryValueExW
0x180023766  test    eax, eax
0x180023768  jz      short loc_180023786
0x18002376a  jle     short loc_180023774
0x18002376c  movzx   eax, ax
0x18002376f  or      eax, 80070000h
0x180023774  lea     rcx, aRegqueryvaluee_0; "RegQueryValueExW"
0x18002377b  mov     r9d, 10Eh
0x180023781  jmp     loc_18002369F
0x180023786  mov     edx, 5Ch ; '\'; Ch
0x18002378b  lea     rcx, [rbp+240h+Data]; Str
0x18002378f  call    cs:__imp_wcsrchr
0x180023795  test    rax, rax
0x180023798  jnz     short loc_1800237B4
0x18002379a  lea     edx, [rax+2Fh]; Ch
0x18002379d  lea     rcx, [rbp+240h+Data]; Str
0x1800237a1  call    cs:__imp_wcsrchr
0x1800237a7  test    rax, rax
0x1800237aa  jnz     short loc_1800237B4
0x1800237ac  lea     rax, [rbp+240h+Data]
0x1800237b0  sub     rax, 2
0x1800237b4  lea     rcx, [rax+2]; String1
0x1800237b8  lea     rdx, aMscoreeDll; "mscoree.dll"
0x1800237bf  call    cs:__imp__wcsicmp
0x1800237c5  test    eax, eax
0x1800237c7  setz    dil
0x1800237cb  mov     rcx, [rsp+340h+hKey]; hKey
0x1800237d0  test    rcx, rcx
0x1800237d3  jz      short loc_1800237DB
0x1800237d5  call    cs:__imp_RegCloseKey
0x1800237db  mov     al, dil
0x1800237de  mov     rcx, [rbp+240h+var_10]
0x1800237e5  xor     rcx, rsp; StackCookie
0x1800237e8  call    __security_check_cookie
0x1800237ed  lea     r11, [rsp+340h+var_s0]
0x1800237f5  mov     rbx, [r11+18h]
0x1800237f9  mov     rdi, [r11+20h]
0x1800237fd  mov     rsp, r11
0x180023800  pop     rbp
0x180023801  retn
```
