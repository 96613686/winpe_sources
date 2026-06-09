# DisplayClusterRegKeyInfo(HKEY__ *,ushort *,ushort *)

- ea: `0x18001ebdc`
- end: `0x18001efbd`
- name: `?DisplayClusterRegKeyInfo@@YAJPEAUHKEY__@@PEAG1@Z`
- size: `993`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019c70`
- `0x18001d978`
- `0x180023160`
- `0x180023b7c`

## callees

- `0x1800063b0`
- `0x18001ebdc`
- `0x1800206c4`
- `0x180025104`
- `0x18008353c`
- `0x1800846c0`
- `0x18008571c`
- `0x1800858a4`
- `0x180085974`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef7f`
- `msvcrt!_wcsicmp` at `0x18001edd7`
- `msvcrt!_wcsicmp` at `0x18001edd7`
- `MTXCLU!MtxCluGetNameFromResourceIdStringNonAdmin` at `0x18001eded`
- `MTXCLU!MtxCluGetNameFromResourceIdStringNonAdmin` at `0x18001eded`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001ef8f`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001ef8f`
- `CLUSAPI!ClusterRegOpenKey` at `0x18001ecd7`
- `CLUSAPI!ClusterRegOpenKey` at `0x18001ecd7`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x18001ed23`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x18001ed23`
- `CLUSAPI!ClusterRegEnumValue` at `0x18001edb0`
- `CLUSAPI!ClusterRegEnumValue` at `0x18001edb0`

## string_xrefs

- `0x18001ef4b`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001ecee`: `ClusterRegOpenKey failed`
- `0x18001ee85`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18001ec6d`: `DisplayClusterRegKeyInfo (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3184): DisplayClusterRegKeyInfo: NULL != pwszMappingType`
- `0x18001ec7f`: `DisplayClusterRegKeyInfo (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3185): DisplayClusterRegKeyInfo: NULL != pwszMappingName`
- `0x18001eeff`: `DisplayClusterRegKeyInfo (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3245): DisplayClusterRegKeyInfo: MAX_PATH > bytesCount`

## pseudocode

```c
__int64 __fastcall DisplayClusterRegKeyInfo(HKEY hKey, unsigned __int16 *a2, unsigned __int16 *a3)
{
  signed int StringW; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  LONG v9; // eax
  LONG v10; // eax
  DWORD i; // esi
  signed int v12; // eax
  wchar_t v13; // dx
  __int64 v14; // rax
  int v15; // eax
  unsigned __int16 *v16; // rdi
  unsigned __int16 *v17; // rcx
  LPDWORD lpcbMaxValueLen; // [rsp+28h] [rbp-D8h]
  DWORD cValues; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwType; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszSubKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[272]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szValueName[264]; // [rsp+180h] [rbp+80h] BYREF

  lpszSubKey = 0;
  phkResult = 0;
  cValues = 0;
  szValueName[0] = 0;
  memset_0(&szValueName[1], 0, 0x206u);
  cchValueName = 260;
  memset_0(Data, 0, 0x104u);
  cbData = 260;
  dwType = 0;
  Src = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"DisplayClusterRegKeyInfo (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3184): DisplayClusterRegKeyInfo: NULL != pwszMappingType");
  if ( !a3 )
    DtcInternalErrorW(
      L"DisplayClusterRegKeyInfo (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3185): DisplayClusterRegKeyInfo: NULL != pwszMappingName");
  StringW = MakeStringW((unsigned __int16 **)&lpszSubKey, L"%s\\%s\\%s", L"MSDTC\\TMMapping", a2, a3);
  if ( StringW < 0 )
  {
    v7 = L"MakeStringW failed";
    v8 = 3190;
LABEL_44:
    LODWORD(lpcbMaxValueLen) = StringW;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      v8,
      L"DisplayClusterRegKeyInfo",
      lpcbMaxValueLen,
      v7);
    goto LABEL_45;
  }
  v9 = ClusterRegOpenKey(hKey, lpszSubKey, 0x109u, &phkResult);
  StringW = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      StringW = (unsigned __int16)v9 | 0x80070000;
    v7 = L"ClusterRegOpenKey failed";
    v8 = 3198;
    goto LABEL_44;
  }
  v10 = ClusterRegQueryInfoKey(phkResult, 0, 0, &cValues, 0, 0, 0, 0);
  StringW = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      StringW = (unsigned __int16)v10 | 0x80070000;
    v7 = L"ClusterRegQueryInfoKey failed";
    v8 = 3207;
    goto LABEL_44;
  }
  StringW = DisplayRegKey((unsigned __int16 *)lpszSubKey, cValues);
  if ( StringW < 0 )
  {
    v7 = L"DisplayRegKey failed";
    v8 = 3215;
    goto LABEL_44;
  }
  for ( i = 0; i < cValues; ++i )
  {
    v12 = ClusterRegEnumValue(phkResult, i, szValueName, &cchValueName, &dwType, Data, &cbData);
    if ( v12 != 234 )
    {
      if ( v12 )
      {
        if ( v12 > 0 )
          StringW = (unsigned __int16)v12 | 0x80070000;
        else
          StringW = v12;
        v7 = L"ClusterRegEnumValue failed";
        v8 = 3228;
        goto LABEL_44;
      }
      if ( !_wcsicmp(szValueName, L"ClusterResourceId") )
      {
        StringW = MtxCluGetNameFromResourceIdStringNonAdmin(0, Data, &Src);
        if ( StringW < 0 )
        {
          v7 = L"MtxCluGetNameFromResourceIdStringNonAdmin failed";
          v8 = 3239;
          goto LABEL_44;
        }
        memset_0(Data, 0, 0x104u);
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)Src + v14) );
        if ( (unsigned __int64)(2 * v14) >= 0x104 )
          DtcInternalErrorW(
            L"DisplayClusterRegKeyInfo (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3245): DisplayClusterRegKeyInfo: MAX"
             "_PATH > bytesCount");
        memcpy_0(Data, Src, 2 * v14);
      }
      v24 = 0;
      if ( dwType == 4 )
        v15 = MakeStringW(&v24, L"ValueName: %s\nValue Type: %d\nValue: %d\n", szValueName);
      else
        v15 = MakeStringW(&v24, L"ValueName: %s\nValue Type: %d\nValue: %s\n", szValueName);
      StringW = v15;
      if ( v15 >= 0 )
      {
        v16 = v24;
        v17 = 0;
      }
      else
      {
        v16 = 0;
        TraceFileW(v15, L"FormatRegValue failed", L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", 0x141u);
        v17 = v24;
      }
      CoTaskMemFree(v17);
      if ( StringW >= 0 )
        OutputString(v16);
      CoTaskMemFree(v16);
      if ( StringW < 0 )
      {
        v7 = L"DisplayRegValue failed";
        v8 = 3253;
        goto LABEL_44;
      }
    }
    wmemset(szValueName, v13, 0x104u);
    cchValueName = 260;
    memset_0(Data, 0, 0x104u);
    cbData = 260;
    dwType = 0;
  }
LABEL_45:
  CoTaskMemFree((LPVOID)lpszSubKey);
  CoTaskMemFree(Src);
  if ( phkResult )
    ClusterRegCloseKey(phkResult);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x18001ebdc  mov     [rsp-8+arg_18], rbx
0x18001ebe1  push    rbp
0x18001ebe2  push    rsi
0x18001ebe3  push    rdi
0x18001ebe4  push    r12
0x18001ebe6  push    r15
0x18001ebe8  lea     rbp, [rsp-2A0h]
0x18001ebf0  sub     rsp, 3A0h
0x18001ebf7  mov     rax, cs:__security_cookie
0x18001ebfe  xor     rax, rsp
0x18001ec01  mov     [rbp+2C0h+var_30], rax
0x18001ec08  xor     r15d, r15d
0x18001ec0b  mov     rbx, r8
0x18001ec0e  mov     rdi, rdx
0x18001ec11  mov     [rsp+3C0h+lpszSubKey], r15
0x18001ec16  mov     rsi, rcx
0x18001ec19  mov     [rsp+3C0h+phkResult], r15
0x18001ec1e  xor     edx, edx; Val
0x18001ec20  mov     [rsp+3C0h+cValues], r15d
0x18001ec25  mov     r8d, 206h; Size
0x18001ec2b  mov     [rbp+2C0h+szValueName], r15w
0x18001ec33  lea     rcx, [rbp+2C0h+var_23E]; void *
0x18001ec3a  call    memset_0
0x18001ec3f  mov     r12d, 104h
0x18001ec45  lea     rcx, [rsp+3C0h+Data]; void *
0x18001ec4a  mov     r8d, r12d; Size
0x18001ec4d  mov     [rsp+3C0h+cchValueName], r12d
0x18001ec52  xor     edx, edx; Val
0x18001ec54  call    memset_0
0x18001ec59  mov     [rsp+3C0h+cbData], r12d
0x18001ec5e  mov     [rsp+3C0h+dwType], r15d
0x18001ec63  mov     [rsp+3C0h+Src], r15
0x18001ec68  test    rdi, rdi
0x18001ec6b  jnz     short loc_18001EC7A
0x18001ec6d  lea     rcx, aDisplaycluster_3; "DisplayClusterRegKeyInfo (com\\complus"...
0x18001ec74  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001ec7a  test    rbx, rbx
0x18001ec7d  jnz     short loc_18001EC8C
0x18001ec7f  lea     rcx, aDisplaycluster; "DisplayClusterRegKeyInfo (com\\complus"...
0x18001ec86  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001ec8c  mov     r9, rdi
0x18001ec8f  mov     [rsp+3C0h+lpcchMaxValueNameLen], rbx
0x18001ec94  lea     r8, szSubKey; "MSDTC\\TMMapping"
0x18001ec9b  lea     rdx, aSSS; "%s\\%s\\%s"
0x18001eca2  lea     rcx, [rsp+3C0h+lpszSubKey]; unsigned __int16 **
0x18001eca7  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001ecac  mov     ebx, eax
0x18001ecae  test    eax, eax
0x18001ecb0  jns     short loc_18001ECC4
0x18001ecb2  lea     rax, aMakestringwFai; "MakeStringW failed"
0x18001ecb9  mov     r9d, 0C76h
0x18001ecbf  jmp     loc_18001EF46
0x18001ecc4  mov     rdx, [rsp+3C0h+lpszSubKey]; lpszSubKey
0x18001ecc9  lea     r9, [rsp+3C0h+phkResult]; phkResult
0x18001ecce  mov     r8d, 109h; samDesired
0x18001ecd4  mov     rcx, rsi; hKey
0x18001ecd7  call    cs:__imp_ClusterRegOpenKey
0x18001ecdd  mov     ebx, eax
0x18001ecdf  test    eax, eax
0x18001ece1  jz      short loc_18001ED00
0x18001ece3  jle     short loc_18001ECEE
0x18001ece5  movzx   ebx, ax
0x18001ece8  or      ebx, 80070000h
0x18001ecee  lea     rax, aClusterregopen; "ClusterRegOpenKey failed"
0x18001ecf5  mov     r9d, 0C7Eh
0x18001ecfb  jmp     loc_18001EF46
0x18001ed00  mov     rcx, [rsp+3C0h+phkResult]; hKey
0x18001ed05  lea     r9, [rsp+3C0h+cValues]; lpcValues
0x18001ed0a  mov     [rsp+3C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001ed0f  xor     r8d, r8d; lpcchMaxSubKeyLen
0x18001ed12  mov     [rsp+3C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001ed17  xor     edx, edx; lpcSubKeys
0x18001ed19  mov     [rsp+3C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001ed1e  mov     [rsp+3C0h+lpcchMaxValueNameLen], r15; lpcchMaxValueNameLen
0x18001ed23  call    cs:__imp_ClusterRegQueryInfoKey
0x18001ed29  mov     ebx, eax
0x18001ed2b  test    eax, eax
0x18001ed2d  jz      short loc_18001ED4C
0x18001ed2f  jle     short loc_18001ED3A
0x18001ed31  movzx   ebx, ax
0x18001ed34  or      ebx, 80070000h
0x18001ed3a  lea     rax, aClusterregquer_0; "ClusterRegQueryInfoKey failed"
0x18001ed41  mov     r9d, 0C87h
0x18001ed47  jmp     loc_18001EF46
0x18001ed4c  mov     edx, [rsp+3C0h+cValues]; unsigned int
0x18001ed50  mov     rcx, [rsp+3C0h+lpszSubKey]; unsigned __int16 *
0x18001ed55  call    ?DisplayRegKey@@YAJPEAGK@Z; DisplayRegKey(ushort *,ulong)
0x18001ed5a  mov     ebx, eax
0x18001ed5c  test    eax, eax
0x18001ed5e  jns     short loc_18001ED72
0x18001ed60  lea     rax, aDisplayregkeyF; "DisplayRegKey failed"
0x18001ed67  mov     r9d, 0C8Fh
0x18001ed6d  jmp     loc_18001EF46
0x18001ed72  mov     esi, r15d
0x18001ed75  cmp     esi, [rsp+3C0h+cValues]
0x18001ed79  jnb     loc_18001EF6F
0x18001ed7f  mov     rcx, [rsp+3C0h+phkResult]; hKey
0x18001ed84  lea     rax, [rsp+3C0h+cbData]
0x18001ed89  mov     [rsp+3C0h+lpcbSecurityDescriptor], rax; lpcbData
0x18001ed8e  lea     r9, [rsp+3C0h+cchValueName]; lpcchValueName
0x18001ed93  lea     rax, [rsp+3C0h+Data]
0x18001ed98  mov     edx, esi; dwIndex
0x18001ed9a  mov     [rsp+3C0h+lpcbMaxValueLen], rax; lpData
0x18001ed9f  lea     r8, [rbp+2C0h+szValueName]; lpszValueName
0x18001eda6  lea     rax, [rsp+3C0h+dwType]
0x18001edab  mov     [rsp+3C0h+lpcchMaxValueNameLen], rax; lpdwType
0x18001edb0  call    cs:__imp_ClusterRegEnumValue
0x18001edb6  cmp     eax, 0EAh
0x18001edbb  jz      loc_18001EECB
0x18001edc1  test    eax, eax
0x18001edc3  jnz     loc_18001EF2A
0x18001edc9  lea     rdx, aClusterresourc_1; "ClusterResourceId"
0x18001edd0  lea     rcx, [rbp+2C0h+szValueName]; String1
0x18001edd7  call    cs:__imp__wcsicmp
0x18001eddd  test    eax, eax
0x18001eddf  jnz     short loc_18001EE36
0x18001ede1  lea     r8, [rsp+3C0h+Src]
0x18001ede6  xor     ecx, ecx
0x18001ede8  lea     rdx, [rsp+3C0h+Data]
0x18001eded  call    cs:__imp_MtxCluGetNameFromResourceIdStringNonAdmin
0x18001edf3  mov     ebx, eax
0x18001edf5  test    eax, eax
0x18001edf7  js      loc_18001EF0C
0x18001edfd  mov     r8, r12; Size
0x18001ee00  lea     rcx, [rsp+3C0h+Data]; void *
0x18001ee05  xor     edx, edx; Val
0x18001ee07  call    memset_0
0x18001ee0c  mov     rdx, [rsp+3C0h+Src]; Src
0x18001ee11  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee15  inc     rax
0x18001ee18  cmp     [rdx+rax*2], r15w
0x18001ee1d  jnz     short loc_18001EE15
0x18001ee1f  lea     r8, [rax+rax]; Size
0x18001ee23  cmp     r8, r12
0x18001ee26  jnb     loc_18001EEFF
0x18001ee2c  lea     rcx, [rsp+3C0h+Data]; void *
0x18001ee31  call    memcpy_0
0x18001ee36  mov     r9d, [rsp+3C0h+dwType]
0x18001ee3b  lea     r8, [rbp+2C0h+szValueName]
0x18001ee42  mov     [rsp+3C0h+var_370], r15
0x18001ee47  lea     rcx, [rsp+3C0h+var_370]; unsigned __int16 **
0x18001ee4c  cmp     r9d, 4
0x18001ee50  jnz     short loc_18001EE63
0x18001ee52  mov     eax, dword ptr [rsp+3C0h+Data]
0x18001ee56  lea     rdx, aValuenameSValu; "ValueName: %s\nValue Type: %d\nValue: %"...
0x18001ee5d  mov     dword ptr [rsp+3C0h+lpcchMaxValueNameLen], eax
0x18001ee61  jmp     short loc_18001EE74
0x18001ee63  lea     rax, [rsp+3C0h+Data]
0x18001ee68  mov     [rsp+3C0h+lpcchMaxValueNameLen], rax
0x18001ee6d  lea     rdx, aValuenameSValu_0; "ValueName: %s\nValue Type: %d\nValue: %"...
0x18001ee74  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001ee79  mov     ebx, eax
0x18001ee7b  test    eax, eax
0x18001ee7d  jns     short loc_18001EEA4
0x18001ee7f  mov     r9d, 141h; unsigned int
0x18001ee85  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18001ee8c  lea     rdx, aFormatregvalue; "FormatRegValue failed"
0x18001ee93  mov     ecx, eax; int
0x18001ee95  mov     rdi, r15
0x18001ee98  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001ee9d  mov     rcx, [rsp+3C0h+var_370]
0x18001eea2  jmp     short loc_18001EEAC
0x18001eea4  mov     rdi, [rsp+3C0h+var_370]
0x18001eea9  mov     rcx, r15; pv
0x18001eeac  call    cs:__imp_CoTaskMemFree
0x18001eeb2  test    ebx, ebx
0x18001eeb4  js      short loc_18001EEBE
0x18001eeb6  mov     rcx, rdi; unsigned __int16 *
0x18001eeb9  call    ?OutputString@@YAXPEAG@Z; OutputString(ushort *)
0x18001eebe  mov     rcx, rdi; pv
0x18001eec1  call    cs:__imp_CoTaskMemFree
0x18001eec7  test    ebx, ebx
0x18001eec9  js      short loc_18001EF1B
0x18001eecb  mov     r8, r12; N
0x18001eece  lea     rcx, [rbp+2C0h+szValueName]; S
0x18001eed5  call    wmemset
0x18001eeda  mov     r8, r12; Size
0x18001eedd  mov     [rsp+3C0h+cchValueName], r12d
0x18001eee2  xor     edx, edx; Val
0x18001eee4  lea     rcx, [rsp+3C0h+Data]; void *
0x18001eee9  call    memset_0
0x18001eeee  inc     esi
0x18001eef0  mov     [rsp+3C0h+cbData], r12d
0x18001eef5  mov     [rsp+3C0h+dwType], r15d
0x18001eefa  jmp     loc_18001ED75
0x18001eeff  lea     rcx, aDisplaycluster_1; "DisplayClusterRegKeyInfo (com\\complus"...
0x18001ef06  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001ef0c  lea     rax, aMtxclugetnamef; "MtxCluGetNameFromResourceIdStringNonAdm"...
0x18001ef13  mov     r9d, 0CA7h
0x18001ef19  jmp     short loc_18001EF46
0x18001ef1b  lea     rax, aDisplayregvalu; "DisplayRegValue failed"
0x18001ef22  mov     r9d, 0CB5h
0x18001ef28  jmp     short loc_18001EF46
0x18001ef2a  jg      short loc_18001EF30
0x18001ef2c  mov     ebx, eax
0x18001ef2e  jmp     short loc_18001EF39
0x18001ef30  movzx   ebx, ax
0x18001ef33  or      ebx, 80070000h
0x18001ef39  lea     rax, aClusterregenum_0; "ClusterRegEnumValue failed"
0x18001ef40  mov     r9d, 0C9Ch
0x18001ef46  mov     [rsp+3C0h+lpcbSecurityDescriptor], rax
0x18001ef4b  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001ef52  mov     edx, 1
0x18001ef57  mov     dword ptr [rsp+3C0h+lpcbMaxValueLen], ebx
0x18001ef5b  lea     rax, aDisplaycluster_2; "DisplayClusterRegKeyInfo"
0x18001ef62  mov     [rsp+3C0h+lpcchMaxValueNameLen], rax
0x18001ef67  lea     ecx, [rdx+2]
0x18001ef6a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ef6f  mov     rcx, [rsp+3C0h+lpszSubKey]; pv
0x18001ef74  call    cs:__imp_CoTaskMemFree
0x18001ef7a  mov     rcx, [rsp+3C0h+Src]; pv
0x18001ef7f  call    cs:__imp_CoTaskMemFree
0x18001ef85  mov     rcx, [rsp+3C0h+phkResult]; hKey
0x18001ef8a  test    rcx, rcx
0x18001ef8d  jz      short loc_18001EF95
0x18001ef8f  call    cs:__imp_ClusterRegCloseKey
0x18001ef95  mov     eax, ebx
0x18001ef97  mov     rcx, [rbp+2C0h+var_30]
0x18001ef9e  xor     rcx, rsp; StackCookie
0x18001efa1  call    __security_check_cookie
0x18001efa6  mov     rbx, [rsp+3C0h+arg_18]
0x18001efae  add     rsp, 3A0h
0x18001efb5  pop     r15
0x18001efb7  pop     r12
0x18001efb9  pop     rdi
0x18001efba  pop     rsi
0x18001efbb  pop     rbp
0x18001efbc  retn
```
