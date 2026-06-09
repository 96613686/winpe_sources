# FillEbrefdlgFromReg

- ea: `0x18011a904`
- end: `0x18011ad7f`
- name: `FillEbrefdlgFromReg`
- size: `1147`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180116a74`

## callees

- `0x180111368`
- `0x1801124d4`
- `0x180119a94`
- `0x18011a904`
- `0x180212378`
- `0x18021279c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!wcscpy_s` at `0x18011ab1f`
- `MSVCR100!wcscpy_s` at `0x18011ab1f`
- `MSVCR100!strtoul` at `0x18011ab6e`
- `MSVCR100!strtoul` at `0x18011abb6`
- `MSVCR100!strtoul` at `0x18011ab6e`
- `MSVCR100!strtoul` at `0x18011abb6`
- `MSVCR100!_ultoa_s` at `0x18011aa73`
- `MSVCR100!_ultoa_s` at `0x18011aa73`
- `MSVCR100!atoi` at `0x18011aad0`
- `MSVCR100!atoi` at `0x18011aad0`
- `ADVAPI32!RegEnumKeyA` at `0x18011a994`
- `ADVAPI32!RegEnumKeyA` at `0x18011aa02`
- `ADVAPI32!RegEnumKeyA` at `0x18011a994`
- `ADVAPI32!RegEnumKeyA` at `0x18011aa02`
- `ADVAPI32!RegOpenKeyA` at `0x18011a94b`
- `ADVAPI32!RegOpenKeyA` at `0x18011a9b6`
- `ADVAPI32!RegOpenKeyA` at `0x18011aa24`
- `ADVAPI32!RegOpenKeyA` at `0x18011aa8d`
- `ADVAPI32!RegOpenKeyA` at `0x18011a94b`
- `ADVAPI32!RegOpenKeyA` at `0x18011a9b6`
- `ADVAPI32!RegOpenKeyA` at `0x18011aa24`
- `ADVAPI32!RegOpenKeyA` at `0x18011aa8d`
- `ADVAPI32!RegCloseKey` at `0x18011ad26`
- `ADVAPI32!RegCloseKey` at `0x18011ad3e`
- `ADVAPI32!RegCloseKey` at `0x18011ad51`
- `ADVAPI32!RegCloseKey` at `0x18011ad60`
- `ADVAPI32!RegCloseKey` at `0x18011ad26`
- `ADVAPI32!RegCloseKey` at `0x18011ad3e`
- `ADVAPI32!RegCloseKey` at `0x18011ad51`
- `ADVAPI32!RegCloseKey` at `0x18011ad60`
- `ADVAPI32!RegQueryValueA` at `0x18011aac2`
- `ADVAPI32!RegQueryValueA` at `0x18011aac2`

## pseudocode

```c
__int64 __fastcall FillEbrefdlgFromReg(__int64 a1, unsigned int a2, __int64 a3)
{
  int v4; // [rsp+20h] [rbp-1350h]
  int v5; // [rsp+20h] [rbp-1350h]
  int v6; // [rsp+28h] [rbp-1348h]
  int BestLcidMatch; // [rsp+60h] [rbp-1310h]
  __int16 v8; // [rsp+64h] [rbp-130Ch]
  __int16 v9; // [rsp+68h] [rbp-1308h]
  LONG cbData; // [rsp+6Ch] [rbp-1304h] BYREF
  __int16 v11; // [rsp+70h] [rbp-1300h]
  DWORD dwIndex; // [rsp+74h] [rbp-12FCh]
  DWORD i; // [rsp+78h] [rbp-12F8h]
  unsigned int Value; // [rsp+7Ch] [rbp-12F4h] BYREF
  int RegisteredPath; // [rsp+80h] [rbp-12F0h]
  CHAR Name[64]; // [rsp+90h] [rbp-12E0h] BYREF
  WCHAR Destination[256]; // [rsp+D0h] [rbp-12A0h] BYREF
  wchar_t v18[2048]; // [rsp+2D0h] [rbp-10A0h] BYREF
  char *EndPtr; // [rsp+12D0h] [rbp-A0h] BYREF
  HKEY v20; // [rsp+12D8h] [rbp-98h] BYREF
  HKEY v21; // [rsp+12E0h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+12E8h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+12F0h] [rbp-80h] BYREF
  CLSID v24; // [rsp+1300h] [rbp-70h] BYREF
  CLSID v25; // [rsp+1310h] [rbp-60h] BYREF
  CLSID pclsid; // [rsp+1320h] [rbp-50h] BYREF
  CHAR SubKey[16]; // [rsp+1330h] [rbp-40h] BYREF
  char Buffer[16]; // [rsp+1340h] [rbp-30h] BYREF
  CHAR Data[16]; // [rsp+1350h] [rbp-20h] BYREF

  BestLcidMatch = 0;
  if ( RegOpenKeyA(HKEY_CLASSES_ROOT, "TypeLib", &phkResult) )
    return 2147647516LL;
  for ( dwIndex = 0; BestLcidMatch >= 0 && !RegEnumKeyA(phkResult, dwIndex, Name, 0x40u); ++dwIndex )
  {
    if ( RegOpenKeyA(phkResult, Name, &hKey) )
    {
      BestLcidMatch = -2147319780;
      break;
    }
    for ( i = 0; !RegEnumKeyA(hKey, i, SubKey, 0xAu); ++i )
    {
      if ( RegOpenKeyA(hKey, SubKey, &v20) )
      {
        BestLcidMatch = -2147319780;
        break;
      }
      BestLcidMatch = GetBestLcidMatch(v20, a2, &Value);
      if ( BestLcidMatch < 0 )
      {
        BestLcidMatch = 0;
      }
      else
      {
        _ultoa_s(Value, Buffer, 0xAu, 16);
        if ( !RegOpenKeyA(v20, Buffer, &v21) )
        {
          v11 = 0;
          cbData = 16;
          if ( !RegQueryValueA(v20, "FLAGS", Data, &cbData) )
            v11 = atoi(Data);
          cbData = 512;
          oRegQueryValue(v20, &strIn, Destination, &cbData);
          if ( !cbData )
            wcscpy_s(Destination, 0x100u, &strIn);
          if ( (v11 & 7) == 0 )
          {
            cbData = 4096;
            CLSIDFromStringA(Name, &pclsid);
            v8 = strtoul(SubKey, &EndPtr, 16);
            if ( *EndPtr == 46 )
            {
              ++EndPtr;
              v9 = strtoul(EndPtr, &EndPtr, 16);
              RegisteredPath = GetRegisteredPath(v21, (wchar_t *)L"win64", v18, &cbData, 0);
              if ( RegisteredPath )
              {
                if ( RegisteredPath == -2147319780
                  && !(unsigned int)GetRegisteredPath(v21, (wchar_t *)L"win32", v18, &cbData, 0) )
                {
                  v25 = pclsid;
                  LOWORD(v6) = v9;
                  LOWORD(v5) = v8;
                  AddAvailEbref(a3, v18, 2, &v25, v5, v6, Value, Destination, 0, 0, 0, 0);
                }
              }
              else
              {
                v24 = pclsid;
                LOWORD(v6) = v9;
                LOWORD(v4) = v8;
                AddAvailEbref(a3, v18, 2, &v24, v4, v6, Value, Destination, 0, 0, 0, a1);
              }
            }
          }
          RegCloseKey(v21);
        }
      }
      RegCloseKey(v20);
    }
    RegCloseKey(hKey);
  }
  RegCloseKey(phkResult);
  return (unsigned int)BestLcidMatch;
}

```

## disassembly

```asm
0x18011a904  mov     [rsp-8+arg_10], r8
0x18011a909  mov     [rsp-8+arg_8], edx
0x18011a90d  mov     [rsp-8+arg_0], rcx
0x18011a912  push    rbp
0x18011a913  mov     rbp, rsp
0x18011a916  mov     eax, 1370h
0x18011a91b  call    _alloca_probe
0x18011a920  sub     rsp, rax
0x18011a923  mov     rax, cs:__security_cookie
0x18011a92a  xor     rax, rsp
0x18011a92d  mov     [rbp+var_10], rax
0x18011a931  mov     [rsp+1370h+var_1310], 0
0x18011a939  lea     r8, [rbp+phkResult]; phkResult
0x18011a93d  lea     rdx, aTypelib_0; "TypeLib"
0x18011a944  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18011a94b  call    cs:__imp_RegOpenKeyA
0x18011a951  test    eax, eax
0x18011a953  jz      short loc_18011A95F
0x18011a955  mov     eax, 8002801Ch
0x18011a95a  jmp     loc_18011AD6A
0x18011a95f  mov     [rsp+1370h+dwIndex], 0
0x18011a967  jmp     short loc_18011A973
0x18011a969  mov     eax, [rsp+1370h+dwIndex]
0x18011a96d  inc     eax
0x18011a96f  mov     [rsp+1370h+dwIndex], eax
0x18011a973  cmp     [rsp+1370h+var_1310], 0
0x18011a978  jl      loc_18011AD5C
0x18011a97e  mov     r9d, 40h ; '@'; cchName
0x18011a984  lea     r8, [rsp+1370h+Name]; lpName
0x18011a98c  mov     edx, [rsp+1370h+dwIndex]; dwIndex
0x18011a990  mov     rcx, [rbp+phkResult]; hKey
0x18011a994  call    cs:__imp_RegEnumKeyA
0x18011a99a  test    eax, eax
0x18011a99c  jnz     loc_18011AD5C
0x18011a9a2  lea     r8, [rsp+1370h+hKey]; phkResult
0x18011a9aa  lea     rdx, [rsp+1370h+Name]; lpSubKey
0x18011a9b2  mov     rcx, [rbp+phkResult]; hKey
0x18011a9b6  call    cs:__imp_RegOpenKeyA
0x18011a9bc  test    eax, eax
0x18011a9be  jz      short loc_18011A9CD
0x18011a9c0  mov     [rsp+1370h+var_1310], 8002801Ch
0x18011a9c8  jmp     loc_18011AD5C
0x18011a9cd  mov     [rsp+1370h+var_12F8], 0
0x18011a9d5  jmp     short loc_18011A9E1
0x18011a9d7  mov     eax, [rsp+1370h+var_12F8]
0x18011a9db  inc     eax
0x18011a9dd  mov     [rsp+1370h+var_12F8], eax
0x18011a9e1  cmp     [rsp+1370h+var_1310], 0
0x18011a9e6  jl      loc_18011AD49
0x18011a9ec  mov     r9d, 0Ah; cchName
0x18011a9f2  lea     r8, [rbp+SubKey]; lpName
0x18011a9f6  mov     edx, [rsp+1370h+var_12F8]; dwIndex
0x18011a9fa  mov     rcx, [rsp+1370h+hKey]; hKey
0x18011aa02  call    cs:__imp_RegEnumKeyA
0x18011aa08  test    eax, eax
0x18011aa0a  jnz     loc_18011AD49
0x18011aa10  lea     r8, [rsp+1370h+var_98]; phkResult
0x18011aa18  lea     rdx, [rbp+SubKey]; lpSubKey
0x18011aa1c  mov     rcx, [rsp+1370h+hKey]; hKey
0x18011aa24  call    cs:__imp_RegOpenKeyA
0x18011aa2a  test    eax, eax
0x18011aa2c  jz      short loc_18011AA3B
0x18011aa2e  mov     [rsp+1370h+var_1310], 8002801Ch
0x18011aa36  jmp     loc_18011AD49
0x18011aa3b  lea     r8, [rsp+1370h+Value]; unsigned int *
0x18011aa40  mov     edx, [rbp+arg_8]; unsigned int
0x18011aa43  mov     rcx, [rsp+1370h+var_98]; HKEY
0x18011aa4b  call    ?GetBestLcidMatch@@YAJPEAUHKEY__@@KPEAK@Z; GetBestLcidMatch(HKEY__ *,ulong,ulong *)
0x18011aa50  mov     [rsp+1370h+var_1310], eax
0x18011aa54  cmp     [rsp+1370h+var_1310], 0
0x18011aa59  jl      loc_18011AD2E
0x18011aa5f  mov     r9d, 10h; Radix
0x18011aa65  mov     r8d, 0Ah; BufferCount
0x18011aa6b  lea     rdx, [rbp+Buffer]; Buffer
0x18011aa6f  mov     ecx, [rsp+1370h+Value]; Value
0x18011aa73  call    cs:__imp__ultoa_s
0x18011aa79  lea     r8, [rsp+1370h+var_90]; phkResult
0x18011aa81  lea     rdx, [rbp+Buffer]; lpSubKey
0x18011aa85  mov     rcx, [rsp+1370h+var_98]; hKey
0x18011aa8d  call    cs:__imp_RegOpenKeyA
0x18011aa93  test    eax, eax
0x18011aa95  jnz     loc_18011AD2C
0x18011aa9b  xor     eax, eax
0x18011aa9d  mov     [rsp+1370h+var_1300], ax
0x18011aaa2  mov     [rsp+1370h+cbData], 10h
0x18011aaaa  lea     r9, [rsp+1370h+cbData]; lpcbData
0x18011aaaf  lea     r8, [rbp+Data]; lpData
0x18011aab3  lea     rdx, aFlags; "FLAGS"
0x18011aaba  mov     rcx, [rsp+1370h+var_98]; hKey
0x18011aac2  call    cs:__imp_RegQueryValueA
0x18011aac8  test    eax, eax
0x18011aaca  jnz     short loc_18011AADB
0x18011aacc  lea     rcx, [rbp+Data]; String
0x18011aad0  call    cs:__imp_atoi
0x18011aad6  mov     [rsp+1370h+var_1300], ax
0x18011aadb  mov     [rsp+1370h+cbData], 200h
0x18011aae3  lea     r9, [rsp+1370h+cbData]; lpcbData
0x18011aae8  lea     r8, [rsp+1370h+Destination]; lpData
0x18011aaf0  lea     rdx, strIn; lpSubKey
0x18011aaf7  mov     rcx, [rsp+1370h+var_98]; hKey
0x18011aaff  call    oRegQueryValue
0x18011ab04  cmp     [rsp+1370h+cbData], 0
0x18011ab09  jnz     short loc_18011AB25
0x18011ab0b  lea     r8, strIn; Source
0x18011ab12  mov     edx, 100h; SizeInWords
0x18011ab17  lea     rcx, [rsp+1370h+Destination]; Destination
0x18011ab1f  call    cs:__imp_wcscpy_s
0x18011ab25  movzx   eax, [rsp+1370h+var_1300]
0x18011ab2a  and     eax, 7
0x18011ab2d  test    eax, eax
0x18011ab2f  jnz     loc_18011AD1E
0x18011ab35  mov     [rsp+1370h+cbData], 1000h
0x18011ab3d  xor     eax, eax
0x18011ab3f  mov     [rsp+1370h+var_130C], ax
0x18011ab44  xor     eax, eax
0x18011ab46  mov     [rsp+1370h+var_1308], ax
0x18011ab4b  lea     rdx, [rbp+pclsid]; pclsid
0x18011ab4f  lea     rcx, [rsp+1370h+Name]; lpMultiByteStr
0x18011ab57  call    CLSIDFromStringA
0x18011ab5c  mov     r8d, 10h; Radix
0x18011ab62  lea     rdx, [rsp+1370h+EndPtr]; EndPtr
0x18011ab6a  lea     rcx, [rbp+SubKey]; String
0x18011ab6e  call    cs:__imp_strtoul
0x18011ab74  mov     [rsp+1370h+var_130C], ax
0x18011ab79  mov     rax, [rsp+1370h+EndPtr]
0x18011ab81  movsx   eax, byte ptr [rax]
0x18011ab84  cmp     eax, 2Eh ; '.'
0x18011ab87  jnz     loc_18011AD1E
0x18011ab8d  mov     rax, [rsp+1370h+EndPtr]
0x18011ab95  inc     rax
0x18011ab98  mov     [rsp+1370h+EndPtr], rax
0x18011aba0  mov     r8d, 10h; Radix
0x18011aba6  lea     rdx, [rsp+1370h+EndPtr]; EndPtr
0x18011abae  mov     rcx, [rsp+1370h+EndPtr]; String
0x18011abb6  call    cs:__imp_strtoul
0x18011abbc  mov     [rsp+1370h+var_1308], ax
0x18011abc1  mov     [rsp+1370h+var_1350], 0; int
0x18011abc9  lea     r9, [rsp+1370h+cbData]; int *
0x18011abce  lea     r8, [rsp+1370h+var_10A0]; wchar_t *
0x18011abd6  lea     rdx, aWin64_0; "win64"
0x18011abdd  mov     rcx, [rsp+1370h+var_90]; HKEY
0x18011abe5  call    ?GetRegisteredPath@@YAJPEAUHKEY__@@PEA_W1PEAJH@Z; GetRegisteredPath(HKEY__ *,wchar_t *,wchar_t *,long *,int)
0x18011abea  mov     [rsp+1370h+var_12F0], eax
0x18011abf1  cmp     [rsp+1370h+var_12F0], 0
0x18011abf9  jnz     short loc_18011AC70
0x18011abfb  movups  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x18011abff  movdqu  [rbp+var_70], xmm0
0x18011ac04  mov     rax, [rbp+arg_0]
0x18011ac08  mov     [rsp+1370h+var_1318], rax
0x18011ac0d  mov     [rsp+1370h+var_1320], 0
0x18011ac16  mov     [rsp+1370h+var_1328], 0
0x18011ac1e  mov     [rsp+1370h+var_1330], 0
0x18011ac27  lea     rax, [rsp+1370h+Destination]
0x18011ac2f  mov     [rsp+1370h+var_1338], rax
0x18011ac34  mov     eax, [rsp+1370h+Value]
0x18011ac38  mov     [rsp+1370h+var_1340], eax
0x18011ac3c  movzx   eax, [rsp+1370h+var_1308]
0x18011ac41  mov     [rsp+1370h+var_1348], ax
0x18011ac46  movzx   eax, [rsp+1370h+var_130C]
0x18011ac4b  mov     word ptr [rsp+1370h+var_1350], ax
0x18011ac50  lea     r9, [rbp+var_70]
0x18011ac54  mov     r8d, 2
0x18011ac5a  lea     rdx, [rsp+1370h+var_10A0]
0x18011ac62  mov     rcx, [rbp+arg_10]
0x18011ac66  call    ?AddAvailEbref@@YAJPEAUEBREFDLG@@PEA_WW4EBREFSRC@@U_GUID@@GGK1PEAUITypeLib@@HPEAIPEAVGEN_PROJECT@@@Z; AddAvailEbref(EBREFDLG *,wchar_t *,EBREFSRC,_GUID,ushort,ushort,ulong,wchar_t *,ITypeLib *,int,uint *,GEN_PROJECT *)
0x18011ac6b  jmp     loc_18011AD1E
0x18011ac70  cmp     [rsp+1370h+var_12F0], 8002801Ch
0x18011ac7b  jnz     loc_18011AD1E
0x18011ac81  mov     [rsp+1370h+var_1350], 0; int
0x18011ac89  lea     r9, [rsp+1370h+cbData]; int *
0x18011ac8e  lea     r8, [rsp+1370h+var_10A0]; wchar_t *
0x18011ac96  lea     rdx, aWin32_0; "win32"
0x18011ac9d  mov     rcx, [rsp+1370h+var_90]; HKEY
0x18011aca5  call    ?GetRegisteredPath@@YAJPEAUHKEY__@@PEA_W1PEAJH@Z; GetRegisteredPath(HKEY__ *,wchar_t *,wchar_t *,long *,int)
0x18011acaa  test    eax, eax
0x18011acac  jnz     short loc_18011AD1E
0x18011acae  movups  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x18011acb2  movdqu  [rbp+var_60], xmm0
0x18011acb7  mov     [rsp+1370h+var_1318], 0
0x18011acc0  mov     [rsp+1370h+var_1320], 0
0x18011acc9  mov     [rsp+1370h+var_1328], 0
0x18011acd1  mov     [rsp+1370h+var_1330], 0
0x18011acda  lea     rax, [rsp+1370h+Destination]
0x18011ace2  mov     [rsp+1370h+var_1338], rax
0x18011ace7  mov     eax, [rsp+1370h+Value]
0x18011aceb  mov     [rsp+1370h+var_1340], eax
0x18011acef  movzx   eax, [rsp+1370h+var_1308]
0x18011acf4  mov     [rsp+1370h+var_1348], ax
0x18011acf9  movzx   eax, [rsp+1370h+var_130C]
0x18011acfe  mov     word ptr [rsp+1370h+var_1350], ax
0x18011ad03  lea     r9, [rbp+var_60]
0x18011ad07  mov     r8d, 2
0x18011ad0d  lea     rdx, [rsp+1370h+var_10A0]
0x18011ad15  mov     rcx, [rbp+arg_10]
0x18011ad19  call    ?AddAvailEbref@@YAJPEAUEBREFDLG@@PEA_WW4EBREFSRC@@U_GUID@@GGK1PEAUITypeLib@@HPEAIPEAVGEN_PROJECT@@@Z; AddAvailEbref(EBREFDLG *,wchar_t *,EBREFSRC,_GUID,ushort,ushort,ulong,wchar_t *,ITypeLib *,int,uint *,GEN_PROJECT *)
0x18011ad1e  mov     rcx, [rsp+1370h+var_90]; hKey
0x18011ad26  call    cs:__imp_RegCloseKey
0x18011ad2c  jmp     short loc_18011AD36
0x18011ad2e  mov     [rsp+1370h+var_1310], 0
0x18011ad36  mov     rcx, [rsp+1370h+var_98]; hKey
0x18011ad3e  call    cs:__imp_RegCloseKey
0x18011ad44  jmp     loc_18011A9D7
0x18011ad49  mov     rcx, [rsp+1370h+hKey]; hKey
0x18011ad51  call    cs:__imp_RegCloseKey
0x18011ad57  jmp     loc_18011A969
0x18011ad5c  mov     rcx, [rbp+phkResult]; hKey
0x18011ad60  call    cs:__imp_RegCloseKey
0x18011ad66  mov     eax, [rsp+1370h+var_1310]
0x18011ad6a  mov     rcx, [rbp+var_10]
0x18011ad6e  xor     rcx, rsp; StackCookie
0x18011ad71  call    __security_check_cookie
0x18011ad76  add     rsp, 1370h
0x18011ad7d  pop     rbp
0x18011ad7e  retn
```
