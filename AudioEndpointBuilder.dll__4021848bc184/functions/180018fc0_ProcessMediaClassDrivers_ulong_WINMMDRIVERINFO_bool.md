# ProcessMediaClassDrivers(ulong,_WINMMDRIVERINFO *,bool)

- ea: `0x180018fc0`
- end: `0x180019614`
- name: `?ProcessMediaClassDrivers@@YAJKPEAU_WINMMDRIVERINFO@@_N@Z`
- size: `1620`
- prototype: `__int64 __fastcall(unsigned int, struct _WINMMDRIVERINFO *, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038d98`

## callees

- `0x180010b70`
- `0x180010da8`
- `0x180018fc0`
- `0x18001961c`
- `0x18001baa0`
- `0x180033464`
- `0x18003e920`
- `0x18003f7a4`
- `0x18005a824`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001927e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001927e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001923d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001923d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019593`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800195a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800195a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001920c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001920c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800192a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800192c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001933c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001934a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001949f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001955d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001957b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001959e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019181`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800192a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800192c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001933c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001934a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001949f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001955d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001957b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001959e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001913c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001913c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800193e8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019439`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800193e8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019439`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180019307`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180019307`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800190aa`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800190aa`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001903f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001903f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019358`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800194ad`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019609`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019358`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800194ad`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180019609`
- `DEVOBJ!DevObjGetClassDevs` at `0x180019070`
- `DEVOBJ!DevObjGetClassDevs` at `0x180019070`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800190f1`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800190f1`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800191bb`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800191bb`

## string_xrefs

- `0x18001931c`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180019453`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180019473`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x180019500`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`
- `0x18001953f`: `avcore\audiocore\server\audioendpointbuilder\dll\winmm.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ProcessMediaClassDrivers(unsigned int a1, struct _WINMMDRIVERINFO *a2, char a3)
{
  char v3; // si
  __int64 v4; // rbx
  int v5; // edi
  __int64 DeviceInfoList; // rax
  __int64 v7; // r14
  unsigned int v8; // r13d
  HKEY v9; // r15
  LSTATUS v10; // r12d
  HKEY *v11; // rbx
  HKEY v12; // rsi
  HKEY v13; // r14
  DWORD i; // ebx
  size_t v15; // rdx
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rsi
  struct _WINMMDRIVERINFO *v20; // r12
  char *v21; // rdi
  unsigned int v23; // eax
  unsigned int v24; // ebx
  int AliasString; // eax
  int v26; // edi
  __int64 v27; // rax
  bool v28; // zf
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  signed int j; // r8d
  __int64 v33; // rdx
  int v34; // eax
  DWORD LastError; // edi
  __int64 v36; // r10
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-B0h]
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h]
  struct _WINMMDRIVERINFO *v45; // [rsp+60h] [rbp-A0h]
  size_t v46; // [rsp+68h] [rbp-98h]
  HKEY *p_hKey; // [rsp+70h] [rbp-90h]
  HKEY v48; // [rsp+78h] [rbp-88h] BYREF
  char v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  _OWORD v51[3]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Source[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v53; // [rsp+C8h] [rbp-38h]
  __int16 v54; // [rsp+CCh] [rbp-34h]
  WCHAR ValueName[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+D8h] [rbp-28h]
  __int16 v57; // [rsp+DCh] [rbp-24h]
  WCHAR Name[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v3 = a3;
  v42 = a1;
  v45 = a2;
  v4 = 8LL * a1;
  v44 = v4;
  v46 = wcsnlen_s(*(const wchar_t **)((char *)&aliasTypes + v4), (size_t)a2);
  v5 = v46;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v50 = DeviceInfoList;
  v7 = DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_MEDIA, 0, 0, 0, 0) )
    {
      v8 = 0;
      memset(v51, 0, sizeof(v51));
      LODWORD(v51[0]) = 48;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
LABEL_4:
            if ( !(unsigned int)DevObjEnumDeviceInfo(v7, v8, v51) )
              goto LABEL_75;
            ++v8;
            memset_0(Name, 0, 0x208u);
            hKey = 0;
            v9 = (HKEY)DevObjOpenDevRegKey(v7, v51, 1, 0, 2, 2);
            if ( v9 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
              break;
            if ( hKey )
              RegCloseKey(hKey);
            RegCloseKey(HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL);
          }
          v48 = 0;
          p_hKey = &hKey;
          v49 = 1;
          v10 = RegOpenKeyExW(v9, *(LPCWSTR *)((char *)&aliasTypesPath + v4), 0, 0xF003Fu, &v48);
          if ( v49 )
          {
            v11 = p_hKey;
            v12 = v48;
            v13 = *p_hKey;
            if ( *p_hKey )
            {
              LastError = GetLastError();
              RegCloseKey(v13);
              SetLastError(LastError);
              v5 = v46;
            }
            v7 = v50;
            *v11 = v12;
            v4 = v44;
            v3 = a3;
          }
          if ( !v10 )
            break;
          if ( hKey )
            RegCloseKey(hKey);
          if ( v9 )
            goto LABEL_14;
        }
        for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x104u); ++i )
        {
          pcbData = 14;
          *(_QWORD *)Source = 0;
          v53 = 0;
          v54 = 0;
          if ( RegGetValueW(hKey, Name, L"Alias", 2u, 0, Source, &pcbData) )
          {
            if ( v3 )
            {
              for ( j = 1; j <= 9; ++j )
              {
                if ( !*((_BYTE *)v45 + 522 * j) )
                {
                  v34 = WriteAlias(v42, v45, j, hKey, Name);
                  v26 = v34;
                  if ( v34 >= 0 )
                    goto LABEL_25;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x10F,
                    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
                    (const char *)(unsigned int)v34,
                    phkResultb);
                  if ( hKey )
                    RegCloseKey(hKey);
                  if ( !v9 )
                    goto LABEL_53;
                  goto LABEL_52;
                }
              }
            }
            goto LABEL_25;
          }
          v16 = wcsnlen_s(Source, v15);
          if ( v3 )
            goto LABEL_25;
          if ( v16 != v5 + 1 )
            goto LABEL_31;
          v17 = _o__wtoi(&Source[v5]);
          v19 = v17;
          if ( v17 - 1 > 8 )
            goto LABEL_31;
          v20 = v45;
          v21 = (char *)v45 + 522 * (int)v17;
          if ( *v21 && !v21[1] && !(unsigned int)_o__wcsicmp(v21 + 2, Name) )
          {
            v21[1] = 1;
            goto LABEL_25;
          }
          if ( *((_BYTE *)v20 + 522 * (int)v19) )
          {
LABEL_31:
            v23 = RegDeleteKeyValueW(hKey, Name, L"Alias");
            if ( v23 )
            {
              v24 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x101,
                      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
                      (const char *)v23,
                      phkResult);
              if ( hKey )
                RegCloseKey(hKey);
              if ( v9 )
                RegCloseKey(v9);
              if ( v7 )
                DevObjDestroyDeviceInfoList(v7);
              return v24;
            }
            goto LABEL_25;
          }
          *(_QWORD *)ValueName = 0;
          v56 = 0;
          v57 = 0;
          AliasString = GetAliasString(v42, ValueName, v18, v19);
          v26 = AliasString;
          if ( AliasString < 0 )
          {
            v33 = 114;
LABEL_62:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
              (const char *)(unsigned int)AliasString,
              phkResult);
LABEL_49:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFB,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
              (const char *)(unsigned int)v26,
              phkResulta);
            if ( hKey )
              RegCloseKey(hKey);
            if ( v9 )
LABEL_52:
              RegCloseKey(v9);
LABEL_53:
            if ( v7 )
              DevObjDestroyDeviceInfoList(v7);
            return (unsigned int)v26;
          }
          v27 = -1;
          do
            v28 = Name[++v27] == 0;
          while ( !v28 );
          v29 = RegSetKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
                  ValueName,
                  1u,
                  Name,
                  2 * v27 + 2);
          if ( v29 )
          {
            v31 = 123;
LABEL_48:
            v26 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v31,
                    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\winmm.cpp",
                    (const char *)v29,
                    phkResult);
            if ( v26 < 0 )
              goto LABEL_49;
            goto LABEL_25;
          }
          v30 = -1;
          do
            v28 = Name[++v30] == 0;
          while ( !v28 );
          v29 = RegSetKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Drivers32",
                  ValueName,
                  1u,
                  Name,
                  2 * v30 + 2);
          if ( v29 )
          {
            v31 = 125;
            goto LABEL_48;
          }
          *((_BYTE *)v20 + 522 * v19) = 1;
          AliasString = StringCchCopyW((unsigned __int16 *)v20 + 261 * v19 + 1, 0x104u, Name);
          v26 = AliasString;
          if ( AliasString < 0 )
          {
            v33 = 130;
            goto LABEL_62;
          }
          *((_BYTE *)v20 + v36 + 1) = 1;
LABEL_25:
          v5 = v46;
          v3 = a3;
        }
        if ( hKey )
          RegCloseKey(hKey);
        v4 = v44;
        if ( !v9 )
          goto LABEL_4;
LABEL_14:
        RegCloseKey(v9);
      }
    }
LABEL_75:
    if ( v7 )
      DevObjDestroyDeviceInfoList(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180018fc0  mov     [rsp-8+arg_10], rbx
0x180018fc5  push    rbp
0x180018fc6  push    rsi
0x180018fc7  push    rdi
0x180018fc8  push    r12
0x180018fca  push    r13
0x180018fcc  push    r14
0x180018fce  push    r15
0x180018fd0  lea     rbp, [rsp-200h]
0x180018fd8  sub     rsp, 300h
0x180018fdf  mov     rax, cs:__security_cookie
0x180018fe6  xor     rax, rsp
0x180018fe9  mov     [rbp+230h+var_40], rax
0x180018ff0  mov     eax, ecx
0x180018ff2  movzx   esi, r8b
0x180018ff6  mov     [rsp+330h+var_2E0], eax
0x180018ffa  mov     [rsp+330h+var_2F0], r8b
0x180018fff  mov     [rsp+330h+var_2D0], rdx
0x180019004  lea     rbx, ds:0[rax*8]
0x18001900c  lea     rax, __ImageBase
0x180019013  mov     [rsp+330h+var_2D8], rbx
0x180019018  mov     rcx, [rbx+rax+6AD20h]; Source
0x180019020  call    wcsnlen_s
0x180019025  xor     r12d, r12d
0x180019028  mov     [rsp+330h+var_2C8], rax
0x18001902d  xor     r9d, r9d
0x180019030  mov     [rsp+330h+phkResult], r12
0x180019035  xor     r8d, r8d
0x180019038  xor     edx, edx
0x18001903a  xor     ecx, ecx
0x18001903c  mov     rdi, rax
0x18001903f  call    cs:__imp_DevObjCreateDeviceInfoList
0x180019045  mov     [rbp+230h+var_2A8], rax
0x180019049  mov     r14, rax
0x18001904c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019050  jz      loc_1800192CB
0x180019056  mov     [rsp+330h+pvData], r12
0x18001905b  lea     rdx, GUID_DEVCLASS_MEDIA
0x180019062  xor     r9d, r9d
0x180019065  mov     [rsp+330h+phkResult], r12
0x18001906a  xor     r8d, r8d
0x18001906d  mov     rcx, rax
0x180019070  call    cs:__imp_DevObjGetClassDevs
0x180019076  test    eax, eax
0x180019078  jz      loc_1800195FD
0x18001907e  xorps   xmm0, xmm0
0x180019081  mov     r13d, r12d
0x180019084  movups  [rbp+230h+var_2A0], xmm0
0x180019088  mov     dword ptr [rbp+230h+var_2A0], 30h ; '0'
0x18001908f  movups  [rbp+230h+var_290], xmm0
0x180019093  movups  [rbp+230h+var_280], xmm0
0x180019097  nop     word ptr [rax+rax+00000000h]
0x1800190a0  lea     r8, [rbp+230h+var_2A0]
0x1800190a4  mov     edx, r13d
0x1800190a7  mov     rcx, r14
0x1800190aa  call    cs:__imp_DevObjEnumDeviceInfo
0x1800190b0  test    eax, eax
0x1800190b2  jz      loc_1800195FD
0x1800190b8  xor     edx, edx; Val
0x1800190ba  lea     rcx, [rbp+230h+Name]; void *
0x1800190be  mov     r8d, 208h; Size
0x1800190c4  inc     r13d
0x1800190c7  call    memset_0
0x1800190cc  xor     r9d, r9d
0x1800190cf  mov     dword ptr [rsp+330h+pvData], 2
0x1800190d7  mov     r8d, 1
0x1800190dd  mov     [rsp+330h+hKey], r12
0x1800190e2  lea     rdx, [rbp+230h+var_2A0]
0x1800190e6  mov     dword ptr [rsp+330h+phkResult], 2
0x1800190ee  mov     rcx, r14
0x1800190f1  call    cs:__imp_DevObjOpenDevRegKey
0x1800190f7  mov     r15, rax
0x1800190fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800190fe  jz      loc_180019571
0x180019104  lea     rax, [rsp+330h+hKey]
0x180019109  mov     [rsp+330h+var_2B8], r12
0x18001910e  mov     [rsp+330h+var_2C0], rax
0x180019113  mov     r9d, 0F003Fh; samDesired
0x180019119  lea     rax, [rsp+330h+var_2B8]
0x18001911e  mov     [rbp+230h+var_2B0], 1
0x180019122  mov     [rsp+330h+phkResult], rax; phkResult
0x180019127  xor     r8d, r8d; ulOptions
0x18001912a  lea     rax, __ImageBase
0x180019131  mov     rcx, r15; hKey
0x180019134  mov     rdx, [rbx+rax+6AD00h]; lpSubKey
0x18001913c  call    cs:__imp_RegOpenKeyExW
0x180019142  cmp     [rbp+230h+var_2B0], 0
0x180019146  mov     r12d, eax
0x180019149  jz      short loc_180019172
0x18001914b  mov     rbx, [rsp+330h+var_2C0]
0x180019150  mov     rsi, [rsp+330h+var_2B8]
0x180019155  mov     r14, [rbx]
0x180019158  test    r14, r14
0x18001915b  jnz     loc_180019593
0x180019161  mov     r14, [rbp+230h+var_2A8]
0x180019165  mov     [rbx], rsi
0x180019168  mov     rbx, [rsp+330h+var_2D8]
0x18001916d  movzx   esi, [rsp+330h+var_2F0]
0x180019172  test    r12d, r12d
0x180019175  jz      short loc_1800191A4
0x180019177  mov     rcx, [rsp+330h+hKey]; hKey
0x18001917c  test    rcx, rcx
0x18001917f  jz      short loc_180019187
0x180019181  call    cs:__imp_RegCloseKey
0x180019187  mov     r12d, 0
0x18001918d  test    r15, r15
0x180019190  jz      loc_1800190A0
0x180019196  mov     rcx, r15; hKey
0x180019199  call    cs:__imp_RegCloseKey
0x18001919f  jmp     loc_1800190A0
0x1800191a4  xor     r12d, r12d
0x1800191a7  mov     ebx, r12d
0x1800191aa  mov     rcx, [rsp+330h+hKey]; hKey
0x1800191af  lea     r8, [rbp+230h+Name]; lpName
0x1800191b3  mov     r9d, 104h; cchName
0x1800191b9  mov     edx, ebx; dwIndex
0x1800191bb  call    cs:__imp_RegEnumKeyW
0x1800191c1  mov     rcx, [rsp+330h+hKey]; hKey
0x1800191c6  test    eax, eax
0x1800191c8  jnz     loc_1800192A4
0x1800191ce  xor     eax, eax
0x1800191d0  mov     [rsp+330h+var_2DC], 0Eh
0x1800191d8  mov     qword ptr [rbp+230h+Source], rax
0x1800191dc  lea     r8, aAlias; "Alias"
0x1800191e3  mov     [rbp+230h+var_268], eax
0x1800191e6  lea     rdx, [rbp+230h+Name]; lpSubKey
0x1800191ea  mov     [rbp+230h+var_264], ax
0x1800191ee  mov     r9d, 2; dwFlags
0x1800191f4  lea     rax, [rsp+330h+var_2DC]
0x1800191f9  mov     [rsp+330h+pcbData], rax; pcbData
0x1800191fe  lea     rax, [rbp+230h+Source]
0x180019202  mov     [rsp+330h+pvData], rax; pvData
0x180019207  mov     [rsp+330h+phkResult], r12; int
0x18001920c  call    cs:__imp_RegGetValueW
0x180019212  test    eax, eax
0x180019214  jnz     loc_1800194BA
0x18001921a  lea     rcx, [rbp+230h+Source]; Source
0x18001921e  call    wcsnlen_s
0x180019223  test    sil, sil
0x180019226  jnz     short loc_180019290
0x180019228  lea     ecx, [rdi+1]
0x18001922b  cmp     eax, ecx
0x18001922d  jnz     loc_1800192F7
0x180019233  mov     eax, edi
0x180019235  lea     rcx, [rbp+230h+Source]
0x180019239  lea     rcx, [rcx+rax*2]
0x18001923d  call    cs:__imp__o__wtoi
0x180019243  mov     esi, eax
0x180019245  lea     ecx, [rsi-1]
0x180019248  cmp     ecx, 8
0x18001924b  ja      loc_1800192F7
0x180019251  mov     r12, [rsp+330h+var_2D0]
0x180019256  movsxd  rcx, esi
0x180019259  imul    rdi, rcx, 20Ah
0x180019260  add     rdi, r12
0x180019263  cmp     byte ptr [rdi], 0
0x180019266  jz      loc_180019365
0x18001926c  cmp     byte ptr [rdi+1], 0
0x180019270  jnz     loc_180019365
0x180019276  lea     rcx, [rdi+2]
0x18001927a  lea     rdx, [rbp+230h+Name]
0x18001927e  call    cs:__imp__o__wcsicmp
0x180019284  test    eax, eax
0x180019286  jnz     loc_180019365
0x18001928c  mov     byte ptr [rdi+1], 1
0x180019290  mov     rdi, [rsp+330h+var_2C8]
0x180019295  inc     ebx
0x180019297  movzx   esi, [rsp+330h+var_2F0]
0x18001929c  xor     r12d, r12d
0x18001929f  jmp     loc_1800191AA
0x1800192a4  test    rcx, rcx
0x1800192a7  jz      short loc_1800192AF
0x1800192a9  call    cs:__imp_RegCloseKey
0x1800192af  mov     rbx, [rsp+330h+var_2D8]
0x1800192b4  test    r15, r15
0x1800192b7  jz      loc_1800190A0
0x1800192bd  mov     rcx, r15; hKey
0x1800192c0  call    cs:__imp_RegCloseKey
0x1800192c6  jmp     loc_1800190A0
0x1800192cb  xor     eax, eax
0x1800192cd  mov     rcx, [rbp+230h+var_40]
0x1800192d4  xor     rcx, rsp; StackCookie
0x1800192d7  call    __security_check_cookie
0x1800192dc  mov     rbx, [rsp+330h+arg_10]
0x1800192e4  add     rsp, 300h
0x1800192eb  pop     r15
0x1800192ed  pop     r14
0x1800192ef  pop     r13
0x1800192f1  pop     r12
0x1800192f3  pop     rdi
0x1800192f4  pop     rsi
0x1800192f5  pop     rbp
0x1800192f6  retn
0x1800192f7  mov     rcx, [rsp+330h+hKey]; hKey
0x1800192fc  lea     r8, aAlias; "Alias"
0x180019303  lea     rdx, [rbp+230h+Name]; lpSubKey
0x180019307  call    cs:__imp_RegDeleteKeyValueW
0x18001930d  test    eax, eax
0x18001930f  jz      loc_180019290
0x180019315  mov     rcx, [rbp+238h]; this
0x18001931c  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x180019323  mov     r9d, eax; char *
0x180019326  mov     edx, 101h; void *
0x18001932b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019330  mov     rcx, [rsp+330h+hKey]; hKey
0x180019335  mov     ebx, eax
0x180019337  test    rcx, rcx
0x18001933a  jz      short loc_180019342
0x18001933c  call    cs:__imp_RegCloseKey
0x180019342  test    r15, r15
0x180019345  jz      short loc_180019350
0x180019347  mov     rcx, r15; hKey
0x18001934a  call    cs:__imp_RegCloseKey
0x180019350  test    r14, r14
0x180019353  jz      short loc_18001935E
0x180019355  mov     rcx, r14
0x180019358  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001935e  mov     eax, ebx
0x180019360  jmp     loc_1800192CD
0x180019365  movsxd  rax, esi
0x180019368  imul    rcx, rax, 20Ah
0x18001936f  cmp     byte ptr [rcx+r12], 0
0x180019374  jnz     short loc_1800192F7
0x180019376  mov     ecx, [rsp+330h+var_2E0]; unsigned int
0x18001937a  lea     rdx, [rbp+230h+ValueName]; unsigned __int16 *
0x18001937e  xor     eax, eax
0x180019380  mov     r9d, esi; unsigned int
0x180019383  mov     qword ptr [rbp+230h+ValueName], rax
0x180019387  mov     [rbp+230h+var_258], eax
0x18001938a  mov     [rbp+230h+var_254], ax
0x18001938e  call    ?GetAliasString@@YAJKPEAGKK@Z; GetAliasString(ulong,ushort *,ulong,ulong)
0x180019393  mov     edi, eax
0x180019395  test    eax, eax
0x180019397  js      loc_1800194F4
0x18001939d  lea     rcx, [rbp+230h+Name]
0x1800193a1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800193a8  nop     dword ptr [rax+rax+00000000h]
0x1800193b0  cmp     word ptr [rcx+rax*2+2], 0
0x1800193b6  lea     rax, [rax+1]
0x1800193ba  jnz     short loc_1800193B0
0x1800193bc  lea     eax, ds:2[rax*2]
0x1800193c3  mov     r9d, 1; dwType
0x1800193c9  mov     dword ptr [rsp+330h+pvData], eax; cbData
0x1800193cd  lea     r8, [rbp+230h+ValueName]; lpValueName
0x1800193d1  lea     rax, [rbp+230h+Name]
0x1800193d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800193dc  lea     rdx, ?driver32Path@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800193e3  mov     [rsp+330h+phkResult], rax; lpData
0x1800193e8  call    cs:__imp_RegSetKeyValueW
0x1800193ee  test    eax, eax
0x1800193f0  jnz     loc_1800195B6
0x1800193f6  lea     rcx, [rbp+230h+Name]
0x1800193fa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019401  cmp     word ptr [rcx+rax*2+2], 0
0x180019407  lea     rax, [rax+1]
0x18001940b  jnz     short loc_180019401
0x18001940d  lea     eax, ds:2[rax*2]
0x180019414  mov     r9d, 1; dwType
0x18001941a  mov     dword ptr [rsp+330h+pvData], eax; cbData
0x18001941e  lea     r8, [rbp+230h+ValueName]; lpValueName
0x180019422  lea     rax, [rbp+230h+Name]
0x180019426  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001942d  lea     rdx, ?driver32WowPath@@3QBGB; "SOFTWARE\\WOW6432Node\\Microsoft\\Windo"...
0x180019434  mov     [rsp+330h+phkResult], rax; int
0x180019439  call    cs:__imp_RegSetKeyValueW
0x18001943f  test    eax, eax
0x180019441  jz      loc_1800195C0
0x180019447  mov     edx, 7Dh ; '}'; void *
0x18001944c  mov     rcx, [rbp+238h]; this
0x180019453  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x18001945a  mov     r9d, eax; char *
0x18001945d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019462  mov     edi, eax
0x180019464  test    eax, eax
0x180019466  jns     loc_180019290
0x18001946c  mov     rcx, [rbp+238h]; this
0x180019473  lea     r8, aAvcoreAudiocor_0; "avcore\\audiocore\\server\\audioendpoin"...
0x18001947a  mov     r9d, edi; char *
0x18001947d  mov     edx, 0FBh; void *
0x180019482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019487  mov     rcx, [rsp+330h+hKey]; hKey
0x18001948c  test    rcx, rcx
0x18001948f  jz      short loc_180019497
0x180019491  call    cs:__imp_RegCloseKey
0x180019497  test    r15, r15
0x18001949a  jz      short loc_1800194A5
0x18001949c  mov     rcx, r15; hKey
0x18001949f  call    cs:__imp_RegCloseKey
0x1800194a5  test    r14, r14
0x1800194a8  jz      short loc_1800194B3
0x1800194aa  mov     rcx, r14
0x1800194ad  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800194b3  mov     eax, edi
0x1800194b5  jmp     loc_1800192CD
0x1800194ba  test    sil, sil
0x1800194bd  jz      loc_180019290
0x1800194c3  mov     r8d, 1; unsigned int
0x1800194c9  nop     dword ptr [rax+00000000h]
0x1800194d0  cmp     r8d, 9
0x1800194d4  jg      loc_180019290
  ... truncated ...
```
