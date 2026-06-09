# GetDTCRegistryInt(ushort const *,ulong)

- ea: `0x18004dd04`
- end: `0x18004de0c`
- name: `?GetDTCRegistryInt@@YAKPEBGK@Z`
- size: `264`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e078`

## callees

- `0x180003cf0`
- `0x18004dd04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ddcd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ddcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dd53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dd53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ddfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ddfc`

## string_xrefs

- `0x18004dd76`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x18004dd64`: `RegOpenKeyExW failed. %s is set to default`
- `0x18004dd87`: `GetDTCRegistryInt`

## pseudocode

```c
__int64 __fastcall GetDTCRegistryInt(const unsigned __int16 *a1)
{
  const wchar_t *v1; // rax
  __int64 v2; // r9
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  int v5; // [rsp+64h] [rbp+1Ch]
  unsigned int Data; // [rsp+68h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

  v5 = HIDWORD(a1);
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey) )
  {
    v1 = L"RegOpenKeyExW failed. %s is set to default";
    v2 = 384;
LABEL_3:
    Data = 0;
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
      v2,
      L"GetDTCRegistryInt",
      0,
      v1,
      L"AllowOnlySchannelSecureRpcCalls");
    goto LABEL_8;
  }
  if ( RegQueryValueExW(hKey, L"AllowOnlySchannelSecureRpcCalls", 0, &Type, (LPBYTE)&Data, &cbData) )
  {
    v1 = L"RegQueryValueExW failed. %s is set to default";
    v2 = 397;
    goto LABEL_3;
  }
  if ( Type != 4 )
    Data = 0;
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18004dd04  mov     [rsp-10h+Data], edx
0x18004dd08  mov     qword ptr [rsp-10h+Type], rcx
0x18004dd0d  push    rbp
0x18004dd0e  push    rbx
0x18004dd0f  mov     rbp, rsp
0x18004dd12  sub     rsp, 48h
0x18004dd16  lea     rax, [rbp+hKey]
0x18004dd1a  mov     [rbp+hKey], 0
0x18004dd22  mov     r9d, 20119h; samDesired
0x18004dd28  mov     [rsp+48h+phkResult], rax; phkResult
0x18004dd2d  xor     r8d, r8d; ulOptions
0x18004dd30  mov     [rbp+Type], 0
0x18004dd37  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x18004dd3e  mov     [rbp+Data], 0
0x18004dd45  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004dd4c  mov     [rbp+cbData], 4
0x18004dd53  call    cs:__imp_RegOpenKeyExW
0x18004dd59  lea     rbx, aAllowonlyschan; "AllowOnlySchannelSecureRpcCalls"
0x18004dd60  test    eax, eax
0x18004dd62  jz      short loc_18004DDAD
0x18004dd64  lea     rax, aRegopenkeyexwF; "RegOpenKeyExW failed. %s is set to defa"...
0x18004dd6b  mov     r9d, 180h
0x18004dd71  mov     [rsp+48h+var_10], rbx
0x18004dd76  lea     r8, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004dd7d  mov     [rsp+48h+var_18], rax
0x18004dd82  mov     edx, 4
0x18004dd87  lea     rax, aGetdtcregistry; "GetDTCRegistryInt"
0x18004dd8e  mov     [rsp+48h+lpcbData], 0
0x18004dd97  mov     [rsp+48h+phkResult], rax
0x18004dd9c  mov     [rbp+Data], 0
0x18004dda3  lea     ecx, [rdx+0Bh]
0x18004dda6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004ddab  jmp     short loc_18004DDF3
0x18004ddad  mov     rcx, [rbp+hKey]; hKey
0x18004ddb1  lea     rax, [rbp+cbData]
0x18004ddb5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18004ddba  lea     r9, [rbp+Type]; lpType
0x18004ddbe  lea     rax, [rbp+Data]
0x18004ddc2  xor     r8d, r8d; lpReserved
0x18004ddc5  mov     rdx, rbx; lpValueName
0x18004ddc8  mov     [rsp+48h+phkResult], rax; lpData
0x18004ddcd  call    cs:__imp_RegQueryValueExW
0x18004ddd3  test    eax, eax
0x18004ddd5  jz      short loc_18004DDE6
0x18004ddd7  lea     rax, aRegqueryvaluee; "RegQueryValueExW failed. %s is set to d"...
0x18004ddde  mov     r9d, 18Dh
0x18004dde4  jmp     short loc_18004DD71
0x18004dde6  cmp     [rbp+Type], 4
0x18004ddea  jz      short loc_18004DDF3
0x18004ddec  mov     [rbp+Data], 0
0x18004ddf3  mov     rcx, [rbp+hKey]; hKey
0x18004ddf7  test    rcx, rcx
0x18004ddfa  jz      short loc_18004DE02
0x18004ddfc  call    cs:__imp_RegCloseKey
0x18004de02  mov     eax, [rbp+Data]
0x18004de05  add     rsp, 48h
0x18004de09  pop     rbx
0x18004de0a  pop     rbp
0x18004de0b  retn
```
