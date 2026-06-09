# RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)

- ea: `0x1800709bc`
- end: `0x180070b7e`
- name: `?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z`
- size: `450`
- prototype: `int(const unsigned __int16 *, HKEY, HKEY *)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009f80`
- `0x180018ba0`
- `0x1800527b0`
- `0x1800528d0`
- `0x180052bf0`
- `0x180052fbc`
- `0x1800530b0`
- `0x180053200`
- `0x180070740`
- `0x180078e20`

## callees

- `0x180003cf0`
- `0x1800709bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070b53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070b53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070a4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070ad5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070a4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180070ad5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070a18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070b63`
- `ADVAPI32!RegConnectRegistryW` at `0x1800709e7`
- `ADVAPI32!RegConnectRegistryW` at `0x180070b06`
- `ADVAPI32!RegConnectRegistryW` at `0x1800709e7`
- `ADVAPI32!RegConnectRegistryW` at `0x180070b06`

## string_xrefs

- `0x180070a83`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x180070b2b`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x180070a71`: `(LPWSTR) CoTaskMemAlloc(CustomHostNameSize)`

## pseudocode

```c
__int64 __fastcall RegConnectHostnameW(const unsigned __int16 *a1, HKEY a2, HKEY *a3)
{
  unsigned int v6; // ebx
  BYTE *v7; // rdi
  int v8; // eax
  BYTE *v9; // rax
  char *v10; // rsi
  int v11; // edx
  int v12; // ecx
  LPDWORD lpcbData; // [rsp+28h] [rbp-40h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  cbData = 0;
  hKey = 0;
  v6 = RegConnectRegistryW(a1, a2, a3);
  if ( v6
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    && !RegQueryValueExW(hKey, L"CustomHostName", 0, 0, 0, &cbData) )
  {
    v7 = (BYTE *)CoTaskMemAlloc(cbData);
    if ( v7 )
    {
      v8 = RegQueryValueExW(hKey, L"CustomHostName", 0, 0, v7, &cbData);
      v6 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        LODWORD(lpcbDataa) = v8;
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
        v9 = v7;
        v10 = (char *)((char *)a1 - (char *)v7);
        do
        {
          v11 = *(unsigned __int16 *)&v10[(_QWORD)v9];
          v12 = *(unsigned __int16 *)v9 - v11;
          if ( v12 )
            break;
          v9 += 2;
        }
        while ( v11 );
        if ( !v12 )
          v6 = RegConnectRegistryW(0, a2, a3);
      }
      CoTaskMemFree(v7);
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
      v6 = 14;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800709bc  mov     rax, rsp
0x1800709bf  mov     [rax+8], rbx
0x1800709c3  mov     [rax+10h], rbp
0x1800709c7  push    rsi
0x1800709c8  push    rdi
0x1800709c9  push    r14
0x1800709cb  sub     rsp, 50h
0x1800709cf  mov     rbp, r8
0x1800709d2  mov     dword ptr [rax+20h], 0
0x1800709d9  mov     r14, rdx
0x1800709dc  mov     qword ptr [rax-28h], 0
0x1800709e4  mov     rsi, rcx
0x1800709e7  call    cs:__imp_RegConnectRegistryW
0x1800709ed  mov     ebx, eax
0x1800709ef  test    eax, eax
0x1800709f1  jz      loc_180070B59
0x1800709f7  lea     rax, [rsp+68h+hKey]
0x1800709fc  mov     r9d, 20119h; samDesired
0x180070a02  xor     r8d, r8d; ulOptions
0x180070a05  mov     [rsp+68h+phkResult], rax; phkResult
0x180070a0a  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\MSDTC"
0x180070a11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070a18  call    cs:__imp_RegOpenKeyExW
0x180070a1e  test    eax, eax
0x180070a20  jnz     loc_180070B59
0x180070a26  mov     rcx, [rsp+68h+hKey]; hKey
0x180070a2b  lea     rax, [rsp+68h+cbData]
0x180070a33  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180070a38  lea     rdx, aCustomhostname; "CustomHostName"
0x180070a3f  xor     r9d, r9d; lpType
0x180070a42  mov     [rsp+68h+phkResult], 0; lpData
0x180070a4b  xor     r8d, r8d; lpReserved
0x180070a4e  call    cs:__imp_RegQueryValueExW
0x180070a54  test    eax, eax
0x180070a56  jnz     loc_180070B59
0x180070a5c  mov     ecx, [rsp+68h+cbData]; cb
0x180070a63  call    cs:__imp_CoTaskMemAlloc
0x180070a69  mov     rdi, rax
0x180070a6c  test    rax, rax
0x180070a6f  jnz     short loc_180070AB1
0x180070a71  lea     rax, aLpwstrCotaskme; "(LPWSTR) CoTaskMemAlloc(CustomHostNameS"...
0x180070a78  mov     r9d, 500h
0x180070a7e  mov     [rsp+68h+var_38], rax
0x180070a83  lea     r8, aComComplusDtcS_13; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x180070a8a  lea     rax, aRegconnecthost; "RegConnectHostnameW"
0x180070a91  mov     dword ptr [rsp+68h+lpcbData], 8007000Eh
0x180070a99  lea     edx, [rdi+1]
0x180070a9c  mov     [rsp+68h+phkResult], rax
0x180070aa1  lea     ecx, [rdi+7]
0x180070aa4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180070aa9  lea     ebx, [rdi+0Eh]
0x180070aac  jmp     loc_180070B59
0x180070ab1  mov     rcx, [rsp+68h+hKey]; hKey
0x180070ab6  lea     rax, [rsp+68h+cbData]
0x180070abe  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180070ac3  lea     rdx, aCustomhostname; "CustomHostName"
0x180070aca  xor     r9d, r9d; lpType
0x180070acd  mov     [rsp+68h+phkResult], rdi; lpData
0x180070ad2  xor     r8d, r8d; lpReserved
0x180070ad5  call    cs:__imp_RegQueryValueExW
0x180070adb  mov     ebx, eax
0x180070add  test    eax, eax
0x180070adf  jnz     short loc_180070B10
0x180070ae1  mov     rax, rdi
0x180070ae4  sub     rsi, rdi
0x180070ae7  movzx   ecx, word ptr [rax]
0x180070aea  movzx   edx, word ptr [rax+rsi]
0x180070aee  sub     ecx, edx
0x180070af0  jnz     short loc_180070AFA
0x180070af2  add     rax, 2
0x180070af6  test    edx, edx
0x180070af8  jnz     short loc_180070AE7
0x180070afa  test    ecx, ecx
0x180070afc  jnz     short loc_180070B50
0x180070afe  mov     r8, rbp; phkResult
0x180070b01  mov     rdx, r14; hKey
0x180070b04  xor     ecx, ecx; lpMachineName
0x180070b06  call    cs:__imp_RegConnectRegistryW
0x180070b0c  mov     ebx, eax
0x180070b0e  jmp     short loc_180070B50
0x180070b10  jle     short loc_180070B1A
0x180070b12  movzx   eax, ax
0x180070b15  or      eax, 80070000h
0x180070b1a  lea     rcx, aRegqueryvaluee_1; "RegQueryValueExW(hkey, CustomHostNameKe"...
0x180070b21  mov     edx, 1
0x180070b26  mov     [rsp+68h+var_38], rcx
0x180070b2b  lea     r8, aComComplusDtcS_13; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x180070b32  mov     dword ptr [rsp+68h+lpcbData], eax
0x180070b36  mov     r9d, 511h
0x180070b3c  lea     rax, aRegconnecthost; "RegConnectHostnameW"
0x180070b43  lea     ecx, [rdx+6]
0x180070b46  mov     [rsp+68h+phkResult], rax
0x180070b4b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180070b50  mov     rcx, rdi; pv
0x180070b53  call    cs:__imp_CoTaskMemFree
0x180070b59  mov     rcx, [rsp+68h+hKey]; hKey
0x180070b5e  test    rcx, rcx
0x180070b61  jz      short loc_180070B69
0x180070b63  call    cs:__imp_RegCloseKey
0x180070b69  mov     rbp, [rsp+68h+arg_8]
0x180070b6e  mov     eax, ebx
0x180070b70  mov     rbx, [rsp+68h+arg_0]
0x180070b75  add     rsp, 50h
0x180070b79  pop     r14
0x180070b7b  pop     rdi
0x180070b7c  pop     rsi
0x180070b7d  retn
```
