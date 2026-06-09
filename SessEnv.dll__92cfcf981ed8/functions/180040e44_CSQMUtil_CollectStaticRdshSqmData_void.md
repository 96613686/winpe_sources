# CSQMUtil::CollectStaticRdshSqmData(void)

- ea: `0x180040e44`
- end: `0x180041126`
- name: `?CollectStaticRdshSqmData@CSQMUtil@@SAJXZ`
- size: `738`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041900`

## callees

- `0x180003f30`
- `0x180004f50`
- `0x180005190`
- `0x180012be0`
- `0x18001a280`
- `0x18001ace4`
- `0x180040e44`
- `0x1800411cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040fbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040fbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004100d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041079`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004100d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800410e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800410e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ec1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ec1`

## string_xrefs

- `0x180040f04`: `objCRegistry.OpenKey failed: 0x%x in %s`
- `0x180040f4f`: `objCRegistry.GetFirstSubKey failed: 0x%x in %s`
- `0x180040fdd`: `LoadableProtocol_Object`

## pseudocode

```c
__int64 CSQMUtil::CollectStaticRdshSqmData(void)
{
  int v0; // eax
  signed int v1; // ebx
  int NextSubKey; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  int PublishAppList; // eax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+58h] [rbp-A8h]
  HKEY v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  int v16; // [rsp+6Ch] [rbp-94h]
  BYTE Data[2]; // [rsp+70h] [rbp-90h] BYREF

  v12[0] = &CRegistry::`vftable';
  v15 = -1;
  v16 = -1;
  v12[1] = 0;
  v13 = 0;
  v14 = 0;
  cbData = 0;
  String1 = 0;
  hKey = 0;
  LocalFree(hMem);
  *(_QWORD *)&CSQMUtil::WRdsRdshSQMData = 0;
  v0 = CRegistry::OpenKey(
         (CRegistry *)v12,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0x20019u,
         phkResult);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
    v15 = 0;
    NextSubKey = CRegistry::GetNextSubKey((CRegistry *)v12, &String1, &cbData);
    v1 = NextSubKey;
    if ( NextSubKey > 0 )
      v1 = (unsigned __int16)NextSubKey | 0x80070000;
    if ( v1 >= 0 )
    {
      while ( !CRegistry::GetNextSubKey((CRegistry *)v12, &String1, &cbData) )
      {
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        if ( wcsicmp(String1, L"Console") )
        {
          v3 = RegOpenKeyExW(v14, String1, 0, 0x20019u, &hKey);
          v1 = v3;
          if ( v3 > 0 )
            v1 = (unsigned __int16)v3 | 0x80070000;
          if ( v1 < 0 )
          {
            _DbgPrintMessage(
              8,
              "RegWinStationQueryValueW failed: 0x%x in %s",
              (unsigned int)v1,
              "CSQMUtil::CollectStaticRdshSqmData");
            goto LABEL_33;
          }
          cbData = 520;
          *(_WORD *)Data = 0;
          v4 = RegQueryValueExW(hKey, L"LoadableProtocol_Object", 0, 0, Data, &cbData);
          v1 = v4;
          if ( v4 == 2 )
          {
            v1 = 0;
          }
          else if ( v4 > 0 )
          {
            v1 = (unsigned __int16)v4 | 0x80070000;
          }
          if ( v1 < 0 )
          {
LABEL_29:
            _DbgPrintMessage(
              8,
              "RegQueryValueEx failed: 0x%x in %s",
              (unsigned int)v1,
              "CSQMUtil::CollectStaticRdshSqmData");
            goto LABEL_33;
          }
          if ( !*(_WORD *)Data || wcsicmp(L"{5828227c-20cf-4408-b73f-73ab70b8849f}", (const wchar_t *)Data) )
          {
            *((_DWORD *)&CSQMUtil::WRdsRdshSQMData + 1) = 1;
          }
          else
          {
            cbData = 4;
            v5 = RegQueryValueExW(hKey, L"UserAuthentication", 0, 0, &CSQMUtil::WRdsRdshSQMData, &cbData);
            v1 = v5;
            if ( v5 == 2 )
            {
              v1 = 0;
            }
            else if ( v5 > 0 )
            {
              v1 = (unsigned __int16)v5 | 0x80070000;
            }
            if ( v1 < 0 )
              goto LABEL_29;
          }
        }
      }
      PublishAppList = CSQMUtil::GetPublishAppList();
      _DbgPrintMessage(8, "CSQMUtil::GetPublishAppList() failed with 0x%08X", PublishAppList);
      v1 = 0;
    }
    else
    {
      _DbgPrintMessage(
        8,
        "objCRegistry.GetFirstSubKey failed: 0x%x in %s",
        (unsigned int)v1,
        "CSQMUtil::CollectStaticRdshSqmData");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "objCRegistry.OpenKey failed: 0x%x in %s",
      (unsigned int)v1,
      "CSQMUtil::CollectStaticRdshSqmData");
  }
LABEL_33:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CRegistry::~CRegistry((CRegistry *)v12);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180040e44  mov     [rsp-8+arg_0], rbx
0x180040e49  mov     [rsp-8+arg_8], rsi
0x180040e4e  push    rbp
0x180040e4f  lea     rbp, [rsp-190h]
0x180040e57  sub     rsp, 290h
0x180040e5e  mov     rax, cs:__security_cookie
0x180040e65  xor     rax, rsp
0x180040e68  mov     [rbp+190h+var_10], rax
0x180040e6f  mov     rcx, cs:hMem; hMem
0x180040e76  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180040e7d  mov     [rsp+290h+var_248], rax
0x180040e82  or      eax, 0FFFFFFFFh
0x180040e85  mov     [rsp+290h+var_228], eax
0x180040e89  mov     [rsp+290h+var_224], eax
0x180040e8d  mov     [rsp+290h+var_240], 0
0x180040e96  mov     [rsp+290h+var_238], 0
0x180040e9e  mov     [rsp+290h+var_230], 0
0x180040ea7  mov     [rsp+290h+cbData], 0
0x180040eaf  mov     [rsp+290h+String1], 0
0x180040eb8  mov     [rsp+290h+hKey], 0
0x180040ec1  call    cs:__imp_LocalFree
0x180040ec7  mov     r9d, 20019h; unsigned int
0x180040ecd  mov     cs:?WRdsRdshSQMData@CSQMUtil@@0U_WRDS_RDSH_SQMDATA@@A, 0; _WRDS_RDSH_SQMDATA CSQMUtil::WRdsRdshSQMData
0x180040ed8  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Ter"...
0x180040edf  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180040ee6  lea     rcx, [rsp+290h+var_248]; this
0x180040eeb  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180040ef0  mov     ebx, eax
0x180040ef2  mov     esi, 80070000h
0x180040ef7  test    eax, eax
0x180040ef9  jle     short loc_180040F00
0x180040efb  movzx   ebx, ax
0x180040efe  or      ebx, esi
0x180040f00  test    ebx, ebx
0x180040f02  jns     short loc_180040F24
0x180040f04  lea     rdx, aObjcregistryOp; "objCRegistry.OpenKey failed: 0x%x in %s"
0x180040f0b  mov     r8d, ebx
0x180040f0e  lea     r9, aCsqmutilCollec_0; "CSQMUtil::CollectStaticRdshSqmData"
0x180040f15  mov     ecx, 8; int
0x180040f1a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180040f1f  jmp     loc_1800410DD
0x180040f24  lea     r8, [rsp+290h+cbData]; unsigned int *
0x180040f29  mov     [rsp+290h+var_228], 0
0x180040f31  lea     rdx, [rsp+290h+String1]; unsigned __int16 **
0x180040f36  lea     rcx, [rsp+290h+var_248]; this
0x180040f3b  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x180040f40  mov     ebx, eax
0x180040f42  test    eax, eax
0x180040f44  jle     short loc_180040F4B
0x180040f46  movzx   ebx, ax
0x180040f49  or      ebx, esi
0x180040f4b  test    ebx, ebx
0x180040f4d  jns     short loc_180040F58
0x180040f4f  lea     rdx, aObjcregistryGe; "objCRegistry.GetFirstSubKey failed: 0x%"...
0x180040f56  jmp     short loc_180040F0B
0x180040f58  lea     r8, [rsp+290h+cbData]; unsigned int *
0x180040f5d  lea     rdx, [rsp+290h+String1]; unsigned __int16 **
0x180040f62  lea     rcx, [rsp+290h+var_248]; this
0x180040f67  call    ?GetNextSubKey@CRegistry@@QEAAKPEAPEAGPEAK@Z; CRegistry::GetNextSubKey(ushort * *,ulong *)
0x180040f6c  test    eax, eax
0x180040f6e  jnz     loc_1800410C2
0x180040f74  mov     rcx, [rsp+290h+hKey]; hKey
0x180040f79  test    rcx, rcx
0x180040f7c  jz      short loc_180040F8D
0x180040f7e  call    cs:__imp_RegCloseKey
0x180040f84  mov     [rsp+290h+hKey], 0
0x180040f8d  mov     rcx, [rsp+290h+String1]; String1
0x180040f92  lea     rdx, aConsole; "Console"
0x180040f99  call    _wcsicmp
0x180040f9e  test    eax, eax
0x180040fa0  jz      short loc_180040F58
0x180040fa2  mov     rdx, [rsp+290h+String1]; lpSubKey
0x180040fa7  lea     rax, [rsp+290h+hKey]
0x180040fac  mov     rcx, [rsp+290h+var_230]; hKey
0x180040fb1  mov     r9d, 20019h; samDesired
0x180040fb7  xor     r8d, r8d; ulOptions
0x180040fba  mov     [rsp+290h+phkResult], rax; phkResult
0x180040fbf  call    cs:__imp_RegOpenKeyExW
0x180040fc5  mov     ebx, eax
0x180040fc7  test    eax, eax
0x180040fc9  jle     short loc_180040FD0
0x180040fcb  movzx   ebx, ax
0x180040fce  or      ebx, esi
0x180040fd0  test    ebx, ebx
0x180040fd2  js      loc_1800410B6
0x180040fd8  mov     rcx, [rsp+290h+hKey]; hKey
0x180040fdd  lea     rdx, aLoadableprotoc; "LoadableProtocol_Object"
0x180040fe4  xor     eax, eax
0x180040fe6  mov     [rsp+290h+cbData], 208h
0x180040fee  mov     word ptr [rsp+290h+Data], ax
0x180040ff3  xor     r9d, r9d; lpType
0x180040ff6  lea     rax, [rsp+290h+cbData]
0x180040ffb  xor     r8d, r8d; lpReserved
0x180040ffe  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180041003  lea     rax, [rsp+290h+Data]
0x180041008  mov     [rsp+290h+phkResult], rax; lpData
0x18004100d  call    cs:__imp_RegQueryValueExW
0x180041013  mov     ebx, eax
0x180041015  cmp     eax, 2
0x180041018  jnz     short loc_18004101E
0x18004101a  xor     ebx, ebx
0x18004101c  jmp     short loc_180041027
0x18004101e  test    eax, eax
0x180041020  jle     short loc_180041027
0x180041022  movzx   ebx, ax
0x180041025  or      ebx, esi
0x180041027  test    ebx, ebx
0x180041029  js      short loc_18004109B
0x18004102b  xor     eax, eax
0x18004102d  cmp     ax, word ptr [rsp+290h+Data]
0x180041032  jz      short loc_1800410A7
0x180041034  lea     rdx, [rsp+290h+Data]; String2
0x180041039  lea     rcx, a5828227c20cf44; "{5828227c-20cf-4408-b73f-73ab70b8849f}"
0x180041040  call    _wcsicmp
0x180041045  test    eax, eax
0x180041047  jnz     short loc_1800410A7
0x180041049  mov     rcx, [rsp+290h+hKey]; hKey
0x18004104e  lea     rax, [rsp+290h+cbData]
0x180041053  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180041058  lea     rdx, aUserauthentica; "UserAuthentication"
0x18004105f  lea     rax, ?WRdsRdshSQMData@CSQMUtil@@0U_WRDS_RDSH_SQMDATA@@A; _WRDS_RDSH_SQMDATA CSQMUtil::WRdsRdshSQMData
0x180041066  mov     [rsp+290h+cbData], 4
0x18004106e  xor     r9d, r9d; lpType
0x180041071  mov     [rsp+290h+phkResult], rax; lpData
0x180041076  xor     r8d, r8d; lpReserved
0x180041079  call    cs:__imp_RegQueryValueExW
0x18004107f  mov     ebx, eax
0x180041081  cmp     eax, 2
0x180041084  jnz     short loc_18004108A
0x180041086  xor     ebx, ebx
0x180041088  jmp     short loc_180041093
0x18004108a  test    eax, eax
0x18004108c  jle     short loc_180041093
0x18004108e  movzx   ebx, ax
0x180041091  or      ebx, esi
0x180041093  test    ebx, ebx
0x180041095  jns     loc_180040F58
0x18004109b  lea     rdx, aRegqueryvaluee_3; "RegQueryValueEx failed: 0x%x in %s"
0x1800410a2  jmp     loc_180040F0B
0x1800410a7  mov     dword ptr cs:?WRdsRdshSQMData@CSQMUtil@@0U_WRDS_RDSH_SQMDATA@@A+4, 1; _WRDS_RDSH_SQMDATA CSQMUtil::WRdsRdshSQMData
0x1800410b1  jmp     loc_180040F58
0x1800410b6  lea     rdx, aRegwinstationq; "RegWinStationQueryValueW failed: 0x%x i"...
0x1800410bd  jmp     loc_180040F0B
0x1800410c2  call    ?GetPublishAppList@CSQMUtil@@CAJXZ; CSQMUtil::GetPublishAppList(void)
0x1800410c7  mov     r8d, eax
0x1800410ca  lea     rdx, aCsqmutilGetpub_0; "CSQMUtil::GetPublishAppList() failed wi"...
0x1800410d1  mov     ecx, 8; int
0x1800410d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800410db  xor     ebx, ebx
0x1800410dd  mov     rcx, [rsp+290h+hKey]; hKey
0x1800410e2  test    rcx, rcx
0x1800410e5  jz      short loc_1800410F6
0x1800410e7  call    cs:__imp_RegCloseKey
0x1800410ed  mov     [rsp+290h+hKey], 0
0x1800410f6  lea     rcx, [rsp+290h+var_248]; this
0x1800410fb  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180041100  mov     eax, ebx
0x180041102  mov     rcx, [rbp+190h+var_10]
0x180041109  xor     rcx, rsp; StackCookie
0x18004110c  call    __security_check_cookie
0x180041111  lea     r11, [rsp+290h+var_s0]
0x180041119  mov     rbx, [r11+10h]
0x18004111d  mov     rsi, [r11+18h]
0x180041121  mov     rsp, r11
0x180041124  pop     rbp
0x180041125  retn
```
