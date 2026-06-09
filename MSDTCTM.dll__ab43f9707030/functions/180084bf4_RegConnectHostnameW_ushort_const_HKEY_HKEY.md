# RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)

- ea: `0x180084bf4`
- end: `0x180084db7`
- name: `?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z`
- size: `451`
- prototype: `int(const unsigned __int16 *, HKEY, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800849ac`

## callees

- `0x1800063b0`
- `0x180084bf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084c9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180084c9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084c8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084d0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084c8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084d0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084c57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084c57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084d9c`
- `ADVAPI32!RegConnectRegistryW` at `0x180084c2a`
- `ADVAPI32!RegConnectRegistryW` at `0x180084d3f`
- `ADVAPI32!RegConnectRegistryW` at `0x180084c2a`
- `ADVAPI32!RegConnectRegistryW` at `0x180084d3f`

## string_xrefs

- `0x180084cbc`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x180084d64`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x180084caa`: `(LPWSTR) CoTaskMemAlloc(CustomHostNameSize)`

## pseudocode

```c
__int64 __fastcall RegConnectHostnameW(const unsigned __int16 *a1, HKEY a2, HKEY *a3)
{
  unsigned int v5; // ebx
  BYTE *v6; // rdi
  int v7; // eax
  BYTE *v8; // rax
  char *v9; // rsi
  int v10; // r8d
  int v11; // ecx
  LPDWORD lpcbData; // [rsp+28h] [rbp-30h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-30h]
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v16; // [rsp+6Ch] [rbp+14h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v16 = HIDWORD(a2);
  cbData = 0;
  hKey = 0;
  v5 = RegConnectRegistryW(a1, HKEY_LOCAL_MACHINE, a3);
  if ( v5
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    && !RegQueryValueExW(hKey, L"CustomHostName", 0, 0, 0, &cbData) )
  {
    v6 = (BYTE *)CoTaskMemAlloc(cbData);
    if ( v6 )
    {
      v7 = RegQueryValueExW(hKey, L"CustomHostName", 0, 0, v6, &cbData);
      v5 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        LODWORD(lpcbDataa) = v7;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
          1297,
          L"RegConnectHostnameW",
          lpcbDataa,
          L"RegQueryValueExW(hkey, CustomHostNameKey, NULL, NULL, (LPBYTE)customHostName, &CustomHostNameSize)");
      }
      else
      {
        v8 = v6;
        v9 = (char *)((char *)a1 - (char *)v6);
        do
        {
          v10 = *(unsigned __int16 *)&v9[(_QWORD)v8];
          v11 = *(unsigned __int16 *)v8 - v10;
          if ( v11 )
            break;
          v8 += 2;
        }
        while ( v10 );
        if ( !v11 )
          v5 = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, a3);
      }
      CoTaskMemFree(v6);
    }
    else
    {
      LODWORD(lpcbData) = -2147024882;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
        1280,
        L"RegConnectHostnameW",
        lpcbData,
        L"(LPWSTR) CoTaskMemAlloc(CustomHostNameSize)");
      v5 = 14;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180084bf4  mov     rax, rsp
0x180084bf7  mov     [rax+8], rbx
0x180084bfb  mov     [rax+18h], rbp
0x180084bff  mov     [rax+10h], rdx
0x180084c03  push    rsi
0x180084c04  push    rdi
0x180084c05  push    r15
0x180084c07  sub     rsp, 40h
0x180084c0b  mov     r15, 0FFFFFFFF80000002h
0x180084c12  mov     dword ptr [rax+10h], 0
0x180084c19  mov     rdx, r15; hKey
0x180084c1c  mov     qword ptr [rax+20h], 0
0x180084c24  mov     rbp, r8
0x180084c27  mov     rsi, rcx
0x180084c2a  call    cs:__imp_RegConnectRegistryW
0x180084c30  mov     ebx, eax
0x180084c32  test    eax, eax
0x180084c34  jz      loc_180084D92
0x180084c3a  lea     rax, [rsp+58h+hKey]
0x180084c3f  mov     r9d, 20119h; samDesired
0x180084c45  xor     r8d, r8d; ulOptions
0x180084c48  mov     [rsp+58h+phkResult], rax; phkResult
0x180084c4d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\MSDTC"
0x180084c54  mov     rcx, r15; hKey
0x180084c57  call    cs:__imp_RegOpenKeyExW
0x180084c5d  test    eax, eax
0x180084c5f  jnz     loc_180084D92
0x180084c65  mov     rcx, [rsp+58h+hKey]; hKey
0x180084c6a  lea     rax, [rsp+58h+cbData]
0x180084c6f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180084c74  lea     rdx, aCustomhostname; "CustomHostName"
0x180084c7b  xor     r9d, r9d; lpType
0x180084c7e  mov     [rsp+58h+phkResult], 0; lpData
0x180084c87  xor     r8d, r8d; lpReserved
0x180084c8a  call    cs:__imp_RegQueryValueExW
0x180084c90  test    eax, eax
0x180084c92  jnz     loc_180084D92
0x180084c98  mov     ecx, [rsp+58h+cbData]; cb
0x180084c9c  call    cs:__imp_CoTaskMemAlloc
0x180084ca2  mov     rdi, rax
0x180084ca5  test    rax, rax
0x180084ca8  jnz     short loc_180084CEA
0x180084caa  lea     rax, aLpwstrCotaskme; "(LPWSTR) CoTaskMemAlloc(CustomHostNameS"...
0x180084cb1  mov     r9d, 500h
0x180084cb7  mov     [rsp+58h+var_28], rax
0x180084cbc  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x180084cc3  lea     rax, aRegconnecthost; "RegConnectHostnameW"
0x180084cca  mov     dword ptr [rsp+58h+lpcbData], 8007000Eh
0x180084cd2  lea     edx, [rdi+1]
0x180084cd5  mov     [rsp+58h+phkResult], rax
0x180084cda  lea     ecx, [rdi+7]
0x180084cdd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180084ce2  lea     ebx, [rdi+0Eh]
0x180084ce5  jmp     loc_180084D92
0x180084cea  mov     rcx, [rsp+58h+hKey]; hKey
0x180084cef  lea     rax, [rsp+58h+cbData]
0x180084cf4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180084cf9  lea     rdx, aCustomhostname; "CustomHostName"
0x180084d00  xor     r9d, r9d; lpType
0x180084d03  mov     [rsp+58h+phkResult], rdi; lpData
0x180084d08  xor     r8d, r8d; lpReserved
0x180084d0b  call    cs:__imp_RegQueryValueExW
0x180084d11  mov     ebx, eax
0x180084d13  test    eax, eax
0x180084d15  jnz     short loc_180084D49
0x180084d17  mov     rax, rdi
0x180084d1a  sub     rsi, rdi
0x180084d1d  movzx   ecx, word ptr [rax]
0x180084d20  movzx   r8d, word ptr [rax+rsi]
0x180084d25  sub     ecx, r8d
0x180084d28  jnz     short loc_180084D33
0x180084d2a  add     rax, 2
0x180084d2e  test    r8d, r8d
0x180084d31  jnz     short loc_180084D1D
0x180084d33  test    ecx, ecx
0x180084d35  jnz     short loc_180084D89
0x180084d37  mov     r8, rbp; phkResult
0x180084d3a  mov     rdx, r15; hKey
0x180084d3d  xor     ecx, ecx; lpMachineName
0x180084d3f  call    cs:__imp_RegConnectRegistryW
0x180084d45  mov     ebx, eax
0x180084d47  jmp     short loc_180084D89
0x180084d49  jle     short loc_180084D53
0x180084d4b  movzx   eax, ax
0x180084d4e  or      eax, 80070000h
0x180084d53  lea     rcx, aRegqueryvaluee_1; "RegQueryValueExW(hkey, CustomHostNameKe"...
0x180084d5a  mov     edx, 1
0x180084d5f  mov     [rsp+58h+var_28], rcx
0x180084d64  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x180084d6b  mov     dword ptr [rsp+58h+lpcbData], eax
0x180084d6f  mov     r9d, 511h
0x180084d75  lea     rax, aRegconnecthost; "RegConnectHostnameW"
0x180084d7c  lea     ecx, [rdx+6]
0x180084d7f  mov     [rsp+58h+phkResult], rax
0x180084d84  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180084d89  mov     rcx, rdi; pv
0x180084d8c  call    cs:__imp_CoTaskMemFree
0x180084d92  mov     rcx, [rsp+58h+hKey]; hKey
0x180084d97  test    rcx, rcx
0x180084d9a  jz      short loc_180084DA2
0x180084d9c  call    cs:__imp_RegCloseKey
0x180084da2  mov     rbp, [rsp+58h+arg_10]
0x180084da7  mov     eax, ebx
0x180084da9  mov     rbx, [rsp+58h+arg_0]
0x180084dae  add     rsp, 40h
0x180084db2  pop     r15
0x180084db4  pop     rdi
0x180084db5  pop     rsi
0x180084db6  retn
```
