# CDiskProtection::VcfCreateRegistryKey(CDiskProtection::SCacheFileData const *)

- ea: `0x14000c5e8`
- end: `0x14000c874`
- name: `?VcfCreateRegistryKey@CDiskProtection@@IEAAJPEBUSCacheFileData@1@@Z`
- size: `652`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, const struct CDiskProtection::SCacheFileData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1400087b0`

## callees

- `0x14000c5e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000c858`
- `ADVAPI32!RegCloseKey` at `0x14000c858`
- `ADVAPI32!RegDeleteValueW` at `0x14000c82c`
- `ADVAPI32!RegDeleteValueW` at `0x14000c83d`
- `ADVAPI32!RegDeleteValueW` at `0x14000c84e`
- `ADVAPI32!RegDeleteValueW` at `0x14000c82c`
- `ADVAPI32!RegDeleteValueW` at `0x14000c83d`
- `ADVAPI32!RegDeleteValueW` at `0x14000c84e`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c651`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c651`
- `ADVAPI32!RegSetValueExW` at `0x14000c6c7`
- `ADVAPI32!RegSetValueExW` at `0x14000c788`
- `ADVAPI32!RegSetValueExW` at `0x14000c6c7`
- `ADVAPI32!RegSetValueExW` at `0x14000c788`
- `KERNEL32!IsDebuggerPresent` at `0x14000c71c`
- `KERNEL32!IsDebuggerPresent` at `0x14000c7dd`
- `KERNEL32!IsDebuggerPresent` at `0x14000c71c`
- `KERNEL32!IsDebuggerPresent` at `0x14000c7dd`

## string_xrefs

- `0x14000c6ef`: `CDiskProtection::VcfCreateRegistryKey`
- `0x14000c7b0`: `CDiskProtection::VcfCreateRegistryKey`
- `0x14000c6c0`: `CacheFileStartByte`
- `0x14000c836`: `CacheFileStartByte`
- `0x14000c776`: `CacheFileGuid`
- `0x14000c847`: `CacheFileGuid`
- `0x14000c61c`: `SYSTEM\CurrentControlSet\Services\VCF\Parameters`

## pseudocode

```c
__int64 __fastcall CDiskProtection::VcfCreateRegistryKey(
        CDiskProtection *this,
        const struct CDiskProtection::SCacheFileData *a2)
{
  LSTATUS v3; // eax
  const unsigned __int16 *v4; // r9
  signed int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  HKEY v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-20h]
  __int64 v13; // [rsp+38h] [rbp-18h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  __int64 Data; // [rsp+90h] [rbp+40h] BYREF

  hKey = 0;
  Data = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\VCF\\Parameters",
         0,
         0,
         0,
         3u,
         0,
         &hKey,
         0);
  v5 = v3;
  if ( !v3 )
  {
    v5 = RegUtil::SetStringValue((RegUtil *)hKey, (HKEY)L"BackingStore", *((const unsigned __int16 **)a2 + 21), v4);
    if ( v5 < 0 )
      goto LABEL_21;
    Data = *(_QWORD *)(*((_QWORD *)a2 + 18) + 24LL) * *((unsigned int *)a2 + 13);
    v6 = RegSetValueExW(hKey, L"CacheFileStartByte", 0, 3u, (const BYTE *)&Data, 8u);
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      else
        v5 = v6;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0xF2Cu,
        L"CDiskProtection::VcfCreateRegistryKey",
        L"CBRAEx",
        L"lr == 0L",
        v5);
      if ( IsDebuggerPresent() )
      {
        v7 = 3884;
LABEL_11:
        LODWORD(v13) = v5;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v7,
          L"CDiskProtection::VcfCreateRegistryKey",
          L"CBRAEx",
          L"lr == 0L",
          v13);
        goto LABEL_21;
      }
      v8 = 3884;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"CacheFileGuid", 0, 3u, (const BYTE *)a2 + 204, 0x10u);
      if ( !v9 )
        goto LABEL_21;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      else
        v5 = v9;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0xF33u,
        L"CDiskProtection::VcfCreateRegistryKey",
        L"CBRAEx",
        L"lr == 0L",
        v5);
      if ( IsDebuggerPresent() )
      {
        v7 = 3891;
        goto LABEL_11;
      }
      v8 = 3891;
    }
    LODWORD(v12) = v5;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::VcfCreateRegistryKey",
      L"CBRAEx",
      L"lr == 0L",
      v12);
    goto LABEL_21;
  }
  if ( v3 > 0 )
    v5 = (unsigned __int16)v3 | 0x80070000;
LABEL_21:
  v10 = hKey;
  if ( hKey )
  {
    if ( v5 < 0 )
    {
      RegDeleteValueW(hKey, L"BackingStore");
      RegDeleteValueW(hKey, L"CacheFileStartByte");
      RegDeleteValueW(hKey, L"CacheFileGuid");
      v10 = hKey;
    }
    RegCloseKey(v10);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000c5e8  mov     r11, rsp
0x14000c5eb  mov     [r11+10h], rbx
0x14000c5ef  mov     [r11+8], rcx
0x14000c5f3  push    rbp
0x14000c5f4  push    rsi
0x14000c5f5  push    rdi
0x14000c5f6  push    r14
0x14000c5f8  push    r15
0x14000c5fa  mov     rbp, rsp
0x14000c5fd  sub     rsp, 50h
0x14000c601  mov     qword ptr [r11-38h], 0
0x14000c609  lea     rax, [rbp+hKey]
0x14000c60d  mov     [r11-40h], rax
0x14000c611  mov     rdi, rdx
0x14000c614  mov     qword ptr [r11-48h], 0
0x14000c61c  lea     rdx, ?s_szDriverParametersKeyName@CDiskProtection@@1QBGB; "SYSTEM\\CurrentControlSet\\Services\\VC"...
0x14000c623  mov     esi, 3
0x14000c628  mov     [rbp+hKey], 0
0x14000c630  mov     [rsp+50h+samDesired], esi; samDesired
0x14000c634  xor     r9d, r9d; lpClass
0x14000c637  xor     r8d, r8d; Reserved
0x14000c63a  mov     [rsp+50h+dwOptions], 0; dwOptions
0x14000c642  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000c649  mov     [rbp+Data], 0
0x14000c651  call    cs:__imp_RegCreateKeyExW
0x14000c657  mov     ebx, eax
0x14000c659  test    eax, eax
0x14000c65b  jz      short loc_14000C671
0x14000c65d  jle     loc_14000C818
0x14000c663  movzx   ebx, ax
0x14000c666  or      ebx, 80070000h
0x14000c66c  jmp     loc_14000C818
0x14000c671  mov     r8, [rdi+0A8h]; unsigned __int16 *
0x14000c678  lea     rdx, ?s_szBackingStore@CDiskProtection@@1QBGB; "BackingStore"
0x14000c67f  mov     rcx, [rbp+hKey]; this
0x14000c683  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x14000c688  mov     ebx, eax
0x14000c68a  test    eax, eax
0x14000c68c  js      loc_14000C818
0x14000c692  mov     rcx, [rdi+90h]
0x14000c699  lea     rax, [rbp+Data]
0x14000c69d  mov     edx, [rdi+34h]
0x14000c6a0  mov     r9d, esi; dwType
0x14000c6a3  mov     [rsp+50h+samDesired], 8; cbData
0x14000c6ab  xor     r8d, r8d; Reserved
0x14000c6ae  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14000c6b3  imul    rdx, [rcx+18h]
0x14000c6b8  mov     rcx, [rbp+hKey]; hKey
0x14000c6bc  mov     [rbp+Data], rdx
0x14000c6c0  lea     rdx, aCachefilestart; "CacheFileStartByte"
0x14000c6c7  call    cs:__imp_RegSetValueExW
0x14000c6cd  test    eax, eax
0x14000c6cf  jz      loc_14000C763
0x14000c6d5  jg      short loc_14000C6DB
0x14000c6d7  mov     ebx, eax
0x14000c6d9  jmp     short loc_14000C6E4
0x14000c6db  movzx   ebx, ax
0x14000c6de  or      ebx, 80070000h
0x14000c6e4  lea     r15, aCbraex; "CBRAEx"
0x14000c6eb  mov     [rsp+50h+samDesired], ebx; int
0x14000c6ef  lea     rsi, aCdiskprotectio_100; "CDiskProtection::VcfCreateRegistryKey"
0x14000c6f6  mov     r9, r15; unsigned __int16 *
0x14000c6f9  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000c700  mov     r8, rsi; unsigned __int16 *
0x14000c703  lea     r14, aLr0l; "lr == 0L"
0x14000c70a  mov     rcx, rdi; unsigned __int16 *
0x14000c70d  mov     edx, 0F2Ch; unsigned int
0x14000c712  mov     qword ptr [rsp+50h+dwOptions], r14; unsigned __int16 *
0x14000c717  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000c71c  call    cs:__imp_IsDebuggerPresent
0x14000c722  test    eax, eax
0x14000c724  jz      short loc_14000C758
0x14000c726  mov     r9d, 0F2Ch
0x14000c72c  mov     dword ptr [rsp+50h+var_18], ebx
0x14000c730  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000c737  mov     [rsp+50h+var_20], r14
0x14000c73c  mov     r8, rdi
0x14000c73f  mov     qword ptr [rsp+50h+samDesired], r15
0x14000c744  mov     ecx, 2; unsigned __int8
0x14000c749  mov     qword ptr [rsp+50h+dwOptions], rsi
0x14000c74e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000c753  jmp     loc_14000C818
0x14000c758  mov     r8d, 0F2Ch
0x14000c75e  jmp     loc_14000C7F8
0x14000c763  mov     rcx, [rbp+hKey]; hKey
0x14000c767  lea     rax, [rdi+0CCh]
0x14000c76e  mov     [rsp+50h+samDesired], 10h; cbData
0x14000c776  lea     rdx, aCachefileguid; "CacheFileGuid"
0x14000c77d  mov     r9d, esi; dwType
0x14000c780  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14000c785  xor     r8d, r8d; Reserved
0x14000c788  call    cs:__imp_RegSetValueExW
0x14000c78e  test    eax, eax
0x14000c790  jz      loc_14000C818
0x14000c796  jg      short loc_14000C79C
0x14000c798  mov     ebx, eax
0x14000c79a  jmp     short loc_14000C7A5
0x14000c79c  movzx   ebx, ax
0x14000c79f  or      ebx, 80070000h
0x14000c7a5  lea     r15, aCbraex; "CBRAEx"
0x14000c7ac  mov     [rsp+50h+samDesired], ebx; int
0x14000c7b0  lea     rsi, aCdiskprotectio_100; "CDiskProtection::VcfCreateRegistryKey"
0x14000c7b7  mov     r9, r15; unsigned __int16 *
0x14000c7ba  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000c7c1  mov     r8, rsi; unsigned __int16 *
0x14000c7c4  lea     r14, aLr0l; "lr == 0L"
0x14000c7cb  mov     rcx, rdi; unsigned __int16 *
0x14000c7ce  mov     edx, 0F33h; unsigned int
0x14000c7d3  mov     qword ptr [rsp+50h+dwOptions], r14; unsigned __int16 *
0x14000c7d8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000c7dd  call    cs:__imp_IsDebuggerPresent
0x14000c7e3  test    eax, eax
0x14000c7e5  jz      short loc_14000C7F2
0x14000c7e7  mov     r9d, 0F33h
0x14000c7ed  jmp     loc_14000C72C
0x14000c7f2  mov     r8d, 0F33h
0x14000c7f8  mov     dword ptr [rsp+50h+var_20], ebx
0x14000c7fc  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000c803  mov     qword ptr [rsp+50h+samDesired], r14
0x14000c808  mov     r9, rsi
0x14000c80b  mov     rdx, rdi
0x14000c80e  mov     qword ptr [rsp+50h+dwOptions], r15
0x14000c813  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000c818  mov     rcx, [rbp+hKey]; hKey
0x14000c81c  test    rcx, rcx
0x14000c81f  jz      short loc_14000C85E
0x14000c821  test    ebx, ebx
0x14000c823  jns     short loc_14000C858
0x14000c825  lea     rdx, ?s_szBackingStore@CDiskProtection@@1QBGB; "BackingStore"
0x14000c82c  call    cs:__imp_RegDeleteValueW
0x14000c832  mov     rcx, [rbp+hKey]; hKey
0x14000c836  lea     rdx, aCachefilestart; "CacheFileStartByte"
0x14000c83d  call    cs:__imp_RegDeleteValueW
0x14000c843  mov     rcx, [rbp+hKey]; hKey
0x14000c847  lea     rdx, aCachefileguid; "CacheFileGuid"
0x14000c84e  call    cs:__imp_RegDeleteValueW
0x14000c854  mov     rcx, [rbp+hKey]; hKey
0x14000c858  call    cs:__imp_RegCloseKey
0x14000c85e  mov     eax, ebx
0x14000c860  mov     rbx, [rsp+50h+arg_8]
0x14000c868  add     rsp, 50h
0x14000c86c  pop     r15
0x14000c86e  pop     r14
0x14000c870  pop     rdi
0x14000c871  pop     rsi
0x14000c872  pop     rbp
0x14000c873  retn
```
