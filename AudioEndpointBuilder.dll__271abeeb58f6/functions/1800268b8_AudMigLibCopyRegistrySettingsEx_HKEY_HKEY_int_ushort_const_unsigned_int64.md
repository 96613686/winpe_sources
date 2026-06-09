# AudMigLibCopyRegistrySettingsEx(HKEY__ *,HKEY__ *,int,ushort const * *,unsigned __int64)

- ea: `0x1800268b8`
- end: `0x180026ec2`
- name: `?AudMigLibCopyRegistrySettingsEx@@YAJPEAUHKEY__@@0HPEAPEBG_K@Z`
- size: `1546`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, __int64, const unsigned __int16 **, unsigned __int64 cbMaxValueNameLen)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a928`

## callees

- `0x1800268b8`
- `0x180029024`
- `0x180034810`
- `0x180034c5c`
- `0x180036e74`
- `0x18003f7a4`
- `0x18005a928`
- `0x18005ad50`
- `0x18005ad94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026d73`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026d73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026ad4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026ad4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026970`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026e9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026dc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026dc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026a98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026a98`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180026a70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180026a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026e39`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AudMigLibCopyRegistrySettingsEx(
        HKEY hKey,
        HKEY a2,
        __int64 a3,
        const unsigned __int16 **a4,
        unsigned __int64 cbMaxValueNameLen)
{
  DWORD v5; // r12d
  int v6; // r14d
  LSTATUS v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  WCHAR *v12; // rsi
  DWORD i; // edi
  LSTATUS v14; // eax
  int v15; // r8d
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  _QWORD *v18; // rcx
  int v19; // edx
  unsigned __int16 *v20; // r13
  void *v21; // r14
  HKEY v22; // rsi
  int v23; // eax
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  DWORD cbData; // [rsp+68h] [rbp-21h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-1Dh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-11h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp-Dh] BYREF
  DWORD Type; // [rsp+80h] [rbp-9h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp-1h] BYREF
  DWORD cchName; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp+Fh]
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+5Fh] BYREF
  HKEY v38; // [rsp+F0h] [rbp+67h]
  DWORD cbMaxValueLen; // [rsp+100h] [rbp+77h] BYREF
  int v40; // [rsp+104h] [rbp+7Bh]

  v40 = HIDWORD(a4);
  v38 = a2;
  v5 = 0;
  cValues = 0;
  v6 = a3;
  LODWORD(cbMaxValueNameLen) = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  phkResult = 0;
  hKeya = 0;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL && (unsigned __int64)a2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = RegQueryInfoKeyW(
           hKey,
           0,
           0,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           0,
           &cValues,
           (LPDWORD)&cbMaxValueNameLen,
           &cbMaxValueLen,
           0,
           0);
    v11 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v11 = (unsigned __int16)v9 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v10, v11);
      }
      goto LABEL_87;
    }
    v36 = 0;
    v12 = 0;
    v11 = 0;
    if ( v6 )
    {
      v36 = AudMigLibAllocMemForSubKey(&cbMaxSubKeyLen);
      v12 = v36;
      if ( v36 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= cSubKeys )
            goto LABEL_50;
          cchName = cbMaxSubKeyLen;
          v14 = RegEnumKeyExW(hKey, i, v12, &cchName, 0, 0, 0, 0);
          v11 = v14;
          if ( v14 )
          {
            if ( v14 > 0 )
              v11 = (unsigned __int16)v14 | 0x80070000;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = 20;
              goto LABEL_49;
            }
            goto LABEL_82;
          }
          v16 = RegOpenKeyExW(hKey, v12, 0, 0x20019u, &phkResult);
          v11 = v16;
          if ( v16 )
            break;
          v17 = RegCreateKeyExW(a2, v12, 0, 0, 0, 0x20006u, 0, &hKeya, 0);
          v11 = v17;
          if ( v17 )
          {
            if ( v17 > 0 )
              v11 = (unsigned __int16)v17 | 0x80070000;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = 22;
LABEL_49:
              WPP_SF_SD(v18[2], v19, v15, (_DWORD)v12, v11);
              goto LABEL_82;
            }
            goto LABEL_82;
          }
          v11 = AudMigLibCopyRegistrySettings(phkResult, hKeya, v6);
          if ( (v11 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids);
            }
            goto LABEL_82;
          }
          if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
          }
          if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(hKeya);
            hKeya = 0;
          }
        }
        if ( v16 > 0 )
          v11 = (unsigned __int16)v16 | 0x80070000;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 21;
          goto LABEL_49;
        }
LABEL_82:
        CoTaskMemFree(v12);
      }
      else
      {
        v11 = -2147024882;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids);
        }
      }
      goto LABEL_87;
    }
LABEL_50:
    v20 = AudMigLibAllocMemForSubKey((unsigned int *)&cbMaxValueNameLen);
    if ( !v20 )
    {
      v11 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids);
      }
      goto LABEL_81;
    }
    v21 = CoTaskMemAlloc(cbMaxValueLen);
    if ( !v21 )
    {
      v11 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids);
      }
      goto LABEL_79;
    }
    if ( !cValues )
    {
LABEL_79:
      CoTaskMemFree(v20);
      if ( v21 )
        CoTaskMemFree(v21);
LABEL_81:
      if ( v12 )
        goto LABEL_82;
      goto LABEL_87;
    }
    v22 = v38;
    while ( 1 )
    {
      cchValueName = cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      memset_0(v20, 0, 2LL * (unsigned int)cbMaxValueNameLen);
      memset_0(v21, 0, cbMaxValueLen);
      v23 = RegEnumValueW(hKey, v5, v20, &cchValueName, 0, &Type, (LPBYTE)v21, &cbData);
      if ( v23 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        v26 = 26;
      }
      else
      {
        v23 = RegSetValueExW(v22, v20, 0, Type, (const BYTE *)v21, cbData);
        if ( !v23 )
          goto LABEL_77;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        v26 = 27;
      }
      WPP_SF_L(v25[2], v26, v24, (unsigned int)v23);
LABEL_77:
      if ( ++v5 >= cValues )
      {
        v12 = v36;
        goto LABEL_79;
      }
    }
  }
  v11 = -2147024809;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return v11;
  }
  WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, hKey, a2);
LABEL_87:
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( (unsigned __int64)hKeya - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKeya);
  return v11;
}

```

## disassembly

```asm
0x1800268b8  mov     r11, rsp
0x1800268bb  mov     [r11+18h], rbx
0x1800268bf  mov     [r11+20h], r9
0x1800268c3  mov     [r11+10h], rdx
0x1800268c7  push    rbp
0x1800268c8  push    rsi
0x1800268c9  push    rdi
0x1800268ca  push    r12
0x1800268cc  push    r13
0x1800268ce  push    r14
0x1800268d0  push    r15
0x1800268d2  lea     rbp, [r11-57h]
0x1800268d6  sub     rsp, 0A0h
0x1800268dd  xor     r12d, r12d
0x1800268e0  lea     rax, [rcx-1]
0x1800268e4  mov     [rbp+4Fh+cValues], r12d
0x1800268e8  mov     r14d, r8d
0x1800268eb  mov     [rbp+4Fh+cbMaxValueNameLen], r12d
0x1800268ef  mov     r13, rdx
0x1800268f2  mov     [rbp+4Fh+cbMaxValueLen], r12d
0x1800268f6  mov     r15, rcx
0x1800268f9  mov     [rbp+4Fh+cSubKeys], r12d
0x1800268fd  mov     [rbp+4Fh+cbMaxSubKeyLen], r12d
0x180026901  mov     [rbp+4Fh+cchValueName], r12d
0x180026905  mov     [rbp+4Fh+cbData], r12d
0x180026909  mov     [rbp+4Fh+Type], r12d
0x18002690d  mov     [rbp+4Fh+phkResult], r12
0x180026911  mov     [rbp+4Fh+hKey], r12
0x180026915  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026919  ja      loc_180026E41
0x18002691f  lea     rax, [rdx-1]
0x180026923  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026927  ja      loc_180026E41
0x18002692d  mov     [r11-80h], r12
0x180026931  lea     rax, [rbp+4Fh+cbMaxValueLen]
0x180026935  mov     [rsp+50h], r12; lpcbSecurityDescriptor
0x18002693a  xor     r9d, r9d; lpReserved
0x18002693d  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180026942  xor     r8d, r8d; lpcchClass
0x180026945  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x180026949  xor     edx, edx; lpClass
0x18002694b  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180026950  lea     rax, [rbp+4Fh+cValues]
0x180026954  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x180026959  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x18002695d  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180026962  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180026967  lea     rax, [rbp+4Fh+cSubKeys]
0x18002696b  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x180026970  call    cs:__imp_RegQueryInfoKeyW
0x180026976  mov     ebx, eax
0x180026978  test    eax, eax
0x18002697a  jz      short loc_1800269CB
0x18002697c  jle     short loc_180026987
0x18002697e  movzx   ebx, ax
0x180026981  or      ebx, 80070000h
0x180026987  mov     rcx, cs:WPP_GLOBAL_Control
0x18002698e  lea     rdi, WPP_GLOBAL_Control
0x180026995  cmp     rcx, rdi
0x180026998  jz      loc_180026E79
0x18002699e  test    dword ptr [rcx+1Ch], 80000h
0x1800269a5  jz      loc_180026E79
0x1800269ab  cmp     byte ptr [rcx+19h], 2
0x1800269af  jb      loc_180026E79
0x1800269b5  mov     rcx, [rcx+10h]
0x1800269b9  mov     edx, 12h
0x1800269be  mov     r9d, ebx
0x1800269c1  call    WPP_SF_L
0x1800269c6  jmp     loc_180026E79
0x1800269cb  mov     [rbp+4Fh+var_40], r12
0x1800269cf  mov     rsi, r12
0x1800269d2  mov     ebx, r12d
0x1800269d5  test    r14d, r14d
0x1800269d8  jz      loc_180026C4F
0x1800269de  lea     rcx, [rbp+4Fh+cbMaxSubKeyLen]; unsigned int *
0x1800269e2  call    ?AudMigLibAllocMemForSubKey@@YAPEAGPEAK@Z; AudMigLibAllocMemForSubKey(ulong *)
0x1800269e7  mov     [rbp+4Fh+var_40], rax
0x1800269eb  mov     rsi, rax
0x1800269ee  test    rax, rax
0x1800269f1  jnz     short loc_180026A3E
0x1800269f3  mov     ebx, 8007000Eh
0x1800269f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ff  lea     rdi, WPP_GLOBAL_Control
0x180026a06  cmp     rcx, rdi
0x180026a09  jz      loc_180026E79
0x180026a0f  test    dword ptr [rcx+1Ch], 80000h
0x180026a16  jz      loc_180026E79
0x180026a1c  cmp     byte ptr [rcx+19h], 2
0x180026a20  jb      loc_180026E79
0x180026a26  mov     rcx, [rcx+10h]
0x180026a2a  lea     edx, [rax+13h]
0x180026a2d  lea     r8, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids
0x180026a34  call    WPP_SF_
0x180026a39  jmp     loc_180026E79
0x180026a3e  mov     edi, r12d
0x180026a41  cmp     edi, [rbp+4Fh+cSubKeys]
0x180026a44  jnb     loc_180026C4F
0x180026a4a  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x180026a4d  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x180026a51  mov     [rsp+0D0h+lpcValues], r12; lpftLastWriteTime
0x180026a56  mov     r8, rsi; lpName
0x180026a59  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcchClass
0x180026a5e  mov     edx, edi; dwIndex
0x180026a60  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; lpClass
0x180026a65  mov     rcx, r15; hKey
0x180026a68  mov     [rsp+0D0h+lpcSubKeys], r12; lpReserved
0x180026a6d  mov     [rbp+4Fh+cchName], eax
0x180026a70  call    cs:__imp_RegEnumKeyExW
0x180026a76  mov     ebx, eax
0x180026a78  test    eax, eax
0x180026a7a  jnz     loc_180026BFC
0x180026a80  lea     rax, [rbp+4Fh+phkResult]
0x180026a84  mov     r9d, 20019h; samDesired
0x180026a8a  xor     r8d, r8d; ulOptions
0x180026a8d  mov     [rsp+0D0h+lpcSubKeys], rax; phkResult
0x180026a92  mov     rdx, rsi; lpSubKey
0x180026a95  mov     rcx, r15; hKey
0x180026a98  call    cs:__imp_RegOpenKeyExW
0x180026a9e  mov     ebx, eax
0x180026aa0  test    eax, eax
0x180026aa2  jnz     loc_180026BBC
0x180026aa8  mov     [rsp+0D0h+lpcbMaxValueNameLen], r12; lpdwDisposition
0x180026aad  lea     rax, [rbp+4Fh+hKey]
0x180026ab1  mov     [rsp+0D0h+lpcValues], rax; phkResult
0x180026ab6  xor     r9d, r9d; lpClass
0x180026ab9  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpSecurityAttributes
0x180026abe  xor     r8d, r8d; Reserved
0x180026ac1  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 20006h; samDesired
0x180026ac9  mov     rdx, rsi; lpSubKey
0x180026acc  mov     rcx, r13; hKey
0x180026acf  mov     dword ptr [rsp+0D0h+lpcSubKeys], r12d; dwOptions
0x180026ad4  call    cs:__imp_RegCreateKeyExW
0x180026ada  mov     ebx, eax
0x180026adc  test    eax, eax
0x180026ade  jnz     loc_180026B7C
0x180026ae4  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x180026ae8  mov     r8d, r14d; int
0x180026aeb  mov     rcx, [rbp+4Fh+phkResult]; HKEY
0x180026aef  call    ?AudMigLibCopyRegistrySettings@@YAJPEAUHKEY__@@0H@Z; AudMigLibCopyRegistrySettings(HKEY__ *,HKEY__ *,int)
0x180026af4  mov     ebx, eax
0x180026af6  test    eax, eax
0x180026af8  js      short loc_180026B31
0x180026afa  mov     rcx, [rbp+4Fh+phkResult]; hKey
0x180026afe  lea     rdx, [rcx-1]
0x180026b02  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026b06  ja      short loc_180026B12
0x180026b08  call    cs:__imp_RegCloseKey
0x180026b0e  mov     [rbp+4Fh+phkResult], r12
0x180026b12  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180026b16  lea     rax, [rcx-1]
0x180026b1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026b1e  ja      short loc_180026B2A
0x180026b20  call    cs:__imp_RegCloseKey
0x180026b26  mov     [rbp+4Fh+hKey], r12
0x180026b2a  inc     edi
0x180026b2c  jmp     loc_180026A41
0x180026b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b38  lea     rdi, WPP_GLOBAL_Control
0x180026b3f  cmp     rcx, rdi
0x180026b42  jz      loc_180026E36
0x180026b48  test    dword ptr [rcx+1Ch], 80000h
0x180026b4f  jz      loc_180026E36
0x180026b55  cmp     byte ptr [rcx+19h], 2
0x180026b59  jb      loc_180026E36
0x180026b5f  mov     rcx, [rcx+10h]
0x180026b63  lea     r8, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids
0x180026b6a  mov     edx, 17h
0x180026b6f  mov     r9d, eax
0x180026b72  call    WPP_SF_d
0x180026b77  jmp     loc_180026E36
0x180026b7c  jle     short loc_180026B87
0x180026b7e  movzx   ebx, ax
0x180026b81  or      ebx, 80070000h
0x180026b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b8e  lea     rdi, WPP_GLOBAL_Control
0x180026b95  cmp     rcx, rdi
0x180026b98  jz      loc_180026E36
0x180026b9e  test    dword ptr [rcx+1Ch], 80000h
0x180026ba5  jz      loc_180026E36
0x180026bab  cmp     byte ptr [rcx+19h], 2
0x180026baf  jb      loc_180026E36
0x180026bb5  mov     edx, 16h
0x180026bba  jmp     short loc_180026C3A
0x180026bbc  jle     short loc_180026BC7
0x180026bbe  movzx   ebx, ax
0x180026bc1  or      ebx, 80070000h
0x180026bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bce  lea     rdi, WPP_GLOBAL_Control
0x180026bd5  cmp     rcx, rdi
0x180026bd8  jz      loc_180026E36
0x180026bde  test    dword ptr [rcx+1Ch], 80000h
0x180026be5  jz      loc_180026E36
0x180026beb  cmp     byte ptr [rcx+19h], 2
0x180026bef  jb      loc_180026E36
0x180026bf5  mov     edx, 15h
0x180026bfa  jmp     short loc_180026C3A
0x180026bfc  jle     short loc_180026C07
0x180026bfe  movzx   ebx, ax
0x180026c01  or      ebx, 80070000h
0x180026c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c0e  lea     rdi, WPP_GLOBAL_Control
0x180026c15  cmp     rcx, rdi
0x180026c18  jz      loc_180026E36
0x180026c1e  test    dword ptr [rcx+1Ch], 80000h
0x180026c25  jz      loc_180026E36
0x180026c2b  cmp     byte ptr [rcx+19h], 2
0x180026c2f  jb      loc_180026E36
0x180026c35  mov     edx, 14h
0x180026c3a  mov     rcx, [rcx+10h]
0x180026c3e  mov     r9, rsi
0x180026c41  mov     dword ptr [rsp+0D0h+lpcSubKeys], ebx
0x180026c45  call    WPP_SF_SD
0x180026c4a  jmp     loc_180026E36
0x180026c4f  lea     rcx, [rbp+4Fh+cbMaxValueNameLen]; unsigned int *
0x180026c53  call    ?AudMigLibAllocMemForSubKey@@YAPEAGPEAK@Z; AudMigLibAllocMemForSubKey(ulong *)
0x180026c58  mov     r13, rax
0x180026c5b  test    rax, rax
0x180026c5e  jnz     short loc_180026CAB
0x180026c60  mov     ebx, 8007000Eh
0x180026c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c6c  lea     rdi, WPP_GLOBAL_Control
0x180026c73  cmp     rcx, rdi
0x180026c76  jz      loc_180026E31
0x180026c7c  test    dword ptr [rcx+1Ch], 80000h
0x180026c83  jz      loc_180026E31
0x180026c89  cmp     byte ptr [rcx+19h], 2
0x180026c8d  jb      loc_180026E31
0x180026c93  mov     rcx, [rcx+10h]
0x180026c97  lea     edx, [rax+18h]
0x180026c9a  lea     r8, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids
0x180026ca1  call    WPP_SF_
0x180026ca6  jmp     loc_180026E31
0x180026cab  mov     ecx, [rbp+4Fh+cbMaxValueLen]; cb
0x180026cae  call    cs:__imp_CoTaskMemAlloc
0x180026cb4  mov     r14, rax
0x180026cb7  test    rax, rax
0x180026cba  jnz     short loc_180026D07
0x180026cbc  mov     ebx, 8007000Eh
0x180026cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cc8  lea     rdi, WPP_GLOBAL_Control
0x180026ccf  cmp     rcx, rdi
0x180026cd2  jz      loc_180026E1A
0x180026cd8  test    dword ptr [rcx+1Ch], 80000h
0x180026cdf  jz      loc_180026E1A
0x180026ce5  cmp     byte ptr [rcx+19h], 2
0x180026ce9  jb      loc_180026E1A
0x180026cef  mov     rcx, [rcx+10h]
0x180026cf3  lea     edx, [rax+19h]
0x180026cf6  lea     r8, WPP_19514f2e9ea33877b06d3299a9c779a8_Traceguids
0x180026cfd  call    WPP_SF_
0x180026d02  jmp     loc_180026E1A
0x180026d07  cmp     [rbp+4Fh+cValues], r12d
0x180026d0b  jbe     loc_180026E1A
0x180026d11  mov     rsi, [rbp+4Fh+arg_8]
0x180026d15  lea     rdi, WPP_GLOBAL_Control
0x180026d1c  mov     ecx, [rbp+4Fh+cbMaxValueNameLen]
0x180026d1f  xor     edx, edx; Val
0x180026d21  mov     eax, [rbp+4Fh+cbMaxValueLen]
0x180026d24  mov     r8d, ecx
0x180026d27  mov     [rbp+4Fh+cchValueName], ecx
0x180026d2a  add     r8, r8; Size
0x180026d2d  mov     rcx, r13; void *
0x180026d30  mov     [rbp+4Fh+cbData], eax
0x180026d33  call    memset_0
0x180026d38  mov     r8d, [rbp+4Fh+cbMaxValueLen]; Size
0x180026d3c  xor     edx, edx; Val
0x180026d3e  mov     rcx, r14; void *
0x180026d41  call    memset_0
0x180026d46  lea     rax, [rbp+4Fh+cbData]
0x180026d4a  mov     r8, r13; lpValueName
0x180026d4d  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x180026d52  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x180026d56  lea     rax, [rbp+4Fh+Type]
0x180026d5a  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x180026d5f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x180026d64  mov     edx, r12d; dwIndex
0x180026d67  mov     rcx, r15; hKey
0x180026d6a  mov     [rsp+0D0h+lpcSubKeys], 0; lpReserved
0x180026d73  call    cs:__imp_RegEnumValueW
0x180026d79  test    eax, eax
0x180026d7b  jz      short loc_180026DAB
0x180026d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d84  cmp     rcx, rdi
0x180026d87  jz      short loc_180026E06
0x180026d89  test    dword ptr [rcx+1Ch], 80000h
0x180026d90  jz      short loc_180026E06
0x180026d92  cmp     byte ptr [rcx+19h], 2
0x180026d96  jb      short loc_180026E06
0x180026d98  test    eax, eax
0x180026d9a  jle     short loc_180026DA4
0x180026d9c  movzx   eax, ax
0x180026d9f  or      eax, 80070000h
0x180026da4  mov     edx, 1Ah
0x180026da9  jmp     short loc_180026DFA
0x180026dab  mov     eax, [rbp+4Fh+cbData]
0x180026dae  xor     r8d, r8d; Reserved
0x180026db1  mov     r9d, [rbp+4Fh+Type]; dwType
0x180026db5  mov     rdx, r13; lpValueName
0x180026db8  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; cbData
0x180026dbc  mov     rcx, rsi; hKey
  ... truncated ...
```
