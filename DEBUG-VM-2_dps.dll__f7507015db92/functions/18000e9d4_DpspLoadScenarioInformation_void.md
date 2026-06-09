# DpspLoadScenarioInformation(void)

- ea: `0x18000e9d4`
- end: `0x18000ed86`
- name: `?DpspLoadScenarioInformation@@YAJXZ`
- size: `946`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18000f940`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009044`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x18000cce4`
- `0x18000ce94`
- `0x18000d298`
- `0x18000d880`
- `0x18000dc30`
- `0x18000e254`
- `0x18000e9d4`
- `0x180012b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed62`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000eb86`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000eb86`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ea98`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ea98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ebad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ebad`

## pseudocode

```c
__int64 DpspLoadScenarioInformation(void)
{
  WCHAR *v0; // rsi
  struct __SCENARIOINFO *v1; // rdi
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  DWORD v5; // r13d
  struct __SCENARIOINFO *v6; // rax
  void *v7; // rax
  int v8; // eax
  int v9; // r8d
  int v10; // eax
  int v11; // eax
  HKEY phkResult; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-1Dh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-11h] BYREF
  struct __SCENARIOINFO *v18; // [rsp+80h] [rbp-9h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-1h] BYREF
  __int128 v20; // [rsp+90h] [rbp+7h] BYREF

  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v0 = 0;
  v18 = 0;
  v1 = 0;
  ftLastWriteTime = 0;
  v20 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WDI\\Scenarios", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 || !hKey )
  {
    hKey = 0;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_34:
    if ( v1 )
      DpspFreeSpecificScenarioInfo(&v18);
  }
  else
  {
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_36;
    }
    ++cbMaxSubKeyLen;
    if ( cbMaxSubKeyLen != (2 * cbMaxSubKeyLen) >> 1 )
    {
      v3 = -2147024362;
      goto LABEL_36;
    }
    v0 = (WCHAR *)WdipAlloc(2 * cbMaxSubKeyLen);
    if ( !v0 )
    {
      v3 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
        (int)L"DpspLoadScenarioInformation",
        1485,
        (int)L"Error = %d",
        14);
      goto LABEL_36;
    }
    v3 = 0;
    v5 = 0;
    if ( cSubKeys )
    {
      while ( 1 )
      {
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        if ( v1 )
        {
          DpspFreeSpecificScenarioInfo(&v18);
          v1 = 0;
          v18 = 0;
        }
        cchName = cbMaxSubKeyLen;
        if ( RegEnumKeyExW(hKey, v5, v0, &cchName, 0, 0, 0, &ftLastWriteTime) )
          goto LABEL_30;
        if ( RegOpenKeyExW(hKey, v0, 0, 0x20019u, &phkResult) )
          goto LABEL_30;
        v3 = WdipStringToGuid(v0, &v20);
        if ( v3 < 0 )
          goto LABEL_30;
        v6 = (struct __SCENARIOINFO *)WdipAlloc(504);
        v18 = v6;
        v1 = v6;
        if ( !v6 )
          goto LABEL_30;
        memset_0(v6, 0, 0x1F8u);
        *((_DWORD *)v1 + 10) = -1;
        *((_DWORD *)v1 + 4) = 16;
        v7 = (void *)WdipAlloc(256);
        *((_QWORD *)v1 + 6) = v7;
        if ( !v7 )
          goto LABEL_30;
        memset_0(v7, 0, 0x100u);
        *(_OWORD *)v1 = v20;
        v8 = DpspEnumerateScenarioPolicy(phkResult, v1);
        LOBYTE(v3) = v8;
        if ( v8 >= 0 )
        {
          v10 = DpspEnumerateScenarioConfig(phkResult);
          LOBYTE(v3) = v10;
          if ( v10 >= 0 )
          {
            v11 = DpspEnumerateScenarioInstrumentation(phkResult, v1);
            LOBYTE(v3) = v11;
            if ( v11 >= 0 )
            {
              v3 = DpspEnumerateScenarioSessions(phkResult, v1);
              if ( v3 >= 0 )
              {
                DpspEnumerateScenarioResourceInformation(phkResult, v1);
                *((_QWORD *)v1 + 62) = g_pScenarioHead;
                g_pScenarioHead = v1;
                v1 = 0;
                v18 = 0;
                goto LABEL_30;
              }
              DpspRaiseMisconfigurationEvent(&v20);
              v9 = 1580;
            }
            else
            {
              DpspRaiseMisconfigurationEvent(&v20);
              v9 = 1571;
            }
          }
          else
          {
            DpspRaiseMisconfigurationEvent(&v20);
            v9 = 1562;
          }
        }
        else
        {
          DpspRaiseMisconfigurationEvent(&v20);
          v9 = 1553;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (int)L"DpspLoadScenarioInformation",
          v9,
          (int)L"Error = %d",
          v3);
        v3 = 0;
LABEL_30:
        if ( ++v5 >= cSubKeys )
          goto LABEL_34;
      }
    }
  }
LABEL_36:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  WdipFree(v0);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e9d4  push    rbp
0x18000e9d6  push    rbx
0x18000e9d7  push    rsi
0x18000e9d8  push    rdi
0x18000e9d9  push    r13
0x18000e9db  push    r14
0x18000e9dd  lea     rbp, [rsp-2Fh]
0x18000e9e2  sub     rsp, 0B8h
0x18000e9e9  mov     rax, cs:__security_cookie
0x18000e9f0  xor     rax, rsp
0x18000e9f3  mov     [rbp+57h+var_40], rax
0x18000e9f7  xor     r14d, r14d
0x18000e9fa  lea     rax, [rbp+57h+hKey]
0x18000e9fe  xorps   xmm0, xmm0
0x18000ea01  mov     [rbp+57h+hKey], r14
0x18000ea05  mov     r9d, 20019h; samDesired
0x18000ea0b  mov     [rbp+57h+var_80], r14
0x18000ea0f  xor     r8d, r8d; ulOptions
0x18000ea12  mov     [rbp+57h+cSubKeys], r14d
0x18000ea16  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\WDI"...
0x18000ea1d  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18000ea21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea28  mov     [rbp+57h+cchName], r14d
0x18000ea2c  mov     esi, r14d
0x18000ea2f  mov     [rbp+57h+var_60], r14
0x18000ea33  mov     edi, r14d
0x18000ea36  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r14
0x18000ea3a  movups  [rbp+57h+var_50], xmm0
0x18000ea3e  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000ea43  call    cs:__imp_RegOpenKeyExW
0x18000ea49  mov     ebx, eax
0x18000ea4b  test    eax, eax
0x18000ea4d  jnz     loc_18000ED1F
0x18000ea53  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ea57  test    rcx, rcx
0x18000ea5a  jz      loc_18000ED1F
0x18000ea60  mov     [rsp+0E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000ea65  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000ea69  mov     [rsp+0E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000ea6e  xor     r9d, r9d; lpReserved
0x18000ea71  mov     [rsp+0E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000ea76  xor     r8d, r8d; lpcchClass
0x18000ea79  mov     [rsp+0E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000ea7e  xor     edx, edx; lpClass
0x18000ea80  mov     [rsp+0E0h+lpcValues], r14; lpcValues
0x18000ea85  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000ea8a  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000ea8f  lea     rax, [rbp+57h+cSubKeys]
0x18000ea93  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x18000ea98  call    cs:__imp_RegQueryInfoKeyW
0x18000ea9e  mov     ebx, eax
0x18000eaa0  test    eax, eax
0x18000eaa2  jz      short loc_18000EAB8
0x18000eaa4  jle     loc_18000ED3E
0x18000eaaa  movzx   ebx, ax
0x18000eaad  or      ebx, 80070000h
0x18000eab3  jmp     loc_18000ED3E
0x18000eab8  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18000eabb  inc     ecx
0x18000eabd  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18000eac0  lea     edx, [rcx+rcx]
0x18000eac3  mov     eax, edx
0x18000eac5  shr     eax, 1
0x18000eac7  cmp     ecx, eax
0x18000eac9  jz      short loc_18000EAD5
0x18000eacb  mov     ebx, 80070216h
0x18000ead0  jmp     loc_18000ED3E
0x18000ead5  mov     ecx, edx
0x18000ead7  call    WdipAlloc
0x18000eadc  mov     rsi, rax
0x18000eadf  test    rax, rax
0x18000eae2  jnz     short loc_18000EB16
0x18000eae4  lea     r9, aErrorD; "Error = %d"
0x18000eaeb  mov     dword ptr [rsp+0E0h+phkResult], 0Eh; Args
0x18000eaf3  mov     r8d, 5CDh; int
0x18000eaf9  lea     rdx, aDpsploadscenar; "DpspLoadScenarioInformation"
0x18000eb00  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000eb07  mov     ebx, 8007000Eh
0x18000eb0c  call    WdipTraceError
0x18000eb11  jmp     loc_18000ED3E
0x18000eb16  mov     ebx, r14d
0x18000eb19  mov     r13d, r14d
0x18000eb1c  cmp     [rbp+57h+cSubKeys], r14d
0x18000eb20  jbe     loc_18000ED3E
0x18000eb26  lea     r14, aErrorD; "Error = %d"
0x18000eb2d  mov     rcx, [rbp+57h+var_80]; hKey
0x18000eb31  test    rcx, rcx
0x18000eb34  jz      short loc_18000EB44
0x18000eb36  call    cs:__imp_RegCloseKey
0x18000eb3c  mov     [rbp+57h+var_80], 0
0x18000eb44  test    rdi, rdi
0x18000eb47  jz      short loc_18000EB58
0x18000eb49  lea     rcx, [rbp+57h+var_60]; struct __SCENARIOINFO **
0x18000eb4d  call    ?DpspFreeSpecificScenarioInfo@@YAXPEAPEAU__SCENARIOINFO@@@Z; DpspFreeSpecificScenarioInfo(__SCENARIOINFO * *)
0x18000eb52  xor     edi, edi
0x18000eb54  mov     [rbp+57h+var_60], rdi
0x18000eb58  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000eb5b  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000eb5f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000eb63  mov     r8, rsi; lpName
0x18000eb66  mov     [rbp+57h+cchName], eax
0x18000eb69  mov     edx, r13d; dwIndex
0x18000eb6c  lea     rax, [rbp+57h+ftLastWriteTime]
0x18000eb70  mov     [rsp+0E0h+lpcValues], rax; lpftLastWriteTime
0x18000eb75  xor     eax, eax
0x18000eb77  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpcchClass
0x18000eb7c  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpClass
0x18000eb81  mov     [rsp+0E0h+phkResult], rax; lpReserved
0x18000eb86  call    cs:__imp_RegEnumKeyExW
0x18000eb8c  test    eax, eax
0x18000eb8e  jnz     loc_18000ED0D
0x18000eb94  mov     rcx, [rbp+57h+hKey]; hKey
0x18000eb98  lea     rax, [rbp+57h+var_80]
0x18000eb9c  mov     r9d, 20019h; samDesired
0x18000eba2  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18000eba7  xor     r8d, r8d; ulOptions
0x18000ebaa  mov     rdx, rsi; lpSubKey
0x18000ebad  call    cs:__imp_RegOpenKeyExW
0x18000ebb3  test    eax, eax
0x18000ebb5  jnz     loc_18000ED0D
0x18000ebbb  lea     rdx, [rbp+57h+var_50]
0x18000ebbf  mov     rcx, rsi
0x18000ebc2  call    WdipStringToGuid
0x18000ebc7  mov     ebx, eax
0x18000ebc9  test    eax, eax
0x18000ebcb  js      loc_18000ED0D
0x18000ebd1  mov     ecx, 1F8h
0x18000ebd6  call    WdipAlloc
0x18000ebdb  mov     [rbp+57h+var_60], rax
0x18000ebdf  mov     rdi, rax
0x18000ebe2  test    rax, rax
0x18000ebe5  jz      loc_18000ED0D
0x18000ebeb  xor     edx, edx; Val
0x18000ebed  mov     r8d, 1F8h; Size
0x18000ebf3  mov     rcx, rax; void *
0x18000ebf6  call    memset_0
0x18000ebfb  mov     dword ptr [rdi+28h], 0FFFFFFFFh
0x18000ec02  mov     ecx, 100h
0x18000ec07  mov     dword ptr [rdi+10h], 10h
0x18000ec0e  call    WdipAlloc
0x18000ec13  mov     [rdi+30h], rax
0x18000ec17  test    rax, rax
0x18000ec1a  jz      loc_18000ED0D
0x18000ec20  xor     edx, edx; Val
0x18000ec22  mov     r8d, 100h; Size
0x18000ec28  mov     rcx, rax; void *
0x18000ec2b  call    memset_0
0x18000ec30  movups  xmm0, [rbp+57h+var_50]
0x18000ec34  mov     rdx, rdi; struct __SCENARIOINFO *
0x18000ec37  movdqu  xmmword ptr [rdi], xmm0
0x18000ec3b  mov     rcx, [rbp+57h+var_80]; HKEY
0x18000ec3f  call    ?DpspEnumerateScenarioPolicy@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z; DpspEnumerateScenarioPolicy(HKEY__ *,__SCENARIOINFO *)
0x18000ec44  mov     ebx, eax
0x18000ec46  test    eax, eax
0x18000ec48  jns     short loc_18000EC7D
0x18000ec4a  lea     rcx, [rbp+57h+var_50]
0x18000ec4e  call    DpspRaiseMisconfigurationEvent
0x18000ec53  mov     r8d, 611h; int
0x18000ec59  movzx   eax, bx
0x18000ec5c  lea     rdx, aDpsploadscenar; "DpspLoadScenarioInformation"
0x18000ec63  mov     r9, r14; int
0x18000ec66  mov     dword ptr [rsp+0E0h+phkResult], eax; Args
0x18000ec6a  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000ec71  call    WdipTraceError
0x18000ec76  xor     ebx, ebx
0x18000ec78  jmp     loc_18000ED0D
0x18000ec7d  mov     rcx, [rbp+57h+var_80]; hKey
0x18000ec81  call    ?DpspEnumerateScenarioConfig@@YAJPEAUHKEY__@@@Z; DpspEnumerateScenarioConfig(HKEY__ *)
0x18000ec86  mov     ebx, eax
0x18000ec88  test    eax, eax
0x18000ec8a  jns     short loc_18000EC9D
0x18000ec8c  lea     rcx, [rbp+57h+var_50]
0x18000ec90  call    DpspRaiseMisconfigurationEvent
0x18000ec95  mov     r8d, 61Ah
0x18000ec9b  jmp     short loc_18000EC59
0x18000ec9d  mov     rcx, [rbp+57h+var_80]; HKEY
0x18000eca1  mov     rdx, rdi; struct __SCENARIOINFO *
0x18000eca4  call    ?DpspEnumerateScenarioInstrumentation@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z; DpspEnumerateScenarioInstrumentation(HKEY__ *,__SCENARIOINFO *)
0x18000eca9  mov     ebx, eax
0x18000ecab  test    eax, eax
0x18000ecad  jns     short loc_18000ECC0
0x18000ecaf  lea     rcx, [rbp+57h+var_50]
0x18000ecb3  call    DpspRaiseMisconfigurationEvent
0x18000ecb8  mov     r8d, 623h
0x18000ecbe  jmp     short loc_18000EC59
0x18000ecc0  mov     rcx, [rbp+57h+var_80]; HKEY
0x18000ecc4  mov     rdx, rdi; struct __SCENARIOINFO *
0x18000ecc7  call    ?DpspEnumerateScenarioSessions@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z; DpspEnumerateScenarioSessions(HKEY__ *,__SCENARIOINFO *)
0x18000eccc  mov     ebx, eax
0x18000ecce  test    eax, eax
0x18000ecd0  jns     short loc_18000ECE6
0x18000ecd2  lea     rcx, [rbp+57h+var_50]
0x18000ecd6  call    DpspRaiseMisconfigurationEvent
0x18000ecdb  mov     r8d, 62Ch
0x18000ece1  jmp     loc_18000EC59
0x18000ece6  mov     rcx, [rbp+57h+var_80]; HKEY
0x18000ecea  mov     rdx, rdi; struct __SCENARIOINFO *
0x18000eced  call    ?DpspEnumerateScenarioResourceInformation@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z; DpspEnumerateScenarioResourceInformation(HKEY__ *,__SCENARIOINFO *)
0x18000ecf2  mov     rax, cs:g_pScenarioHead
0x18000ecf9  mov     [rdi+1F0h], rax
0x18000ed00  mov     cs:g_pScenarioHead, rdi
0x18000ed07  xor     edi, edi
0x18000ed09  mov     [rbp+57h+var_60], rdi
0x18000ed0d  inc     r13d
0x18000ed10  cmp     r13d, [rbp+57h+cSubKeys]
0x18000ed14  jb      loc_18000EB2D
0x18000ed1a  xor     r14d, r14d
0x18000ed1d  jmp     short loc_18000ED30
0x18000ed1f  mov     [rbp+57h+hKey], r14
0x18000ed23  test    eax, eax
0x18000ed25  jle     short loc_18000ED30
0x18000ed27  movzx   ebx, ax
0x18000ed2a  or      ebx, 80070000h
0x18000ed30  test    rdi, rdi
0x18000ed33  jz      short loc_18000ED3E
0x18000ed35  lea     rcx, [rbp+57h+var_60]; struct __SCENARIOINFO **
0x18000ed39  call    ?DpspFreeSpecificScenarioInfo@@YAXPEAPEAU__SCENARIOINFO@@@Z; DpspFreeSpecificScenarioInfo(__SCENARIOINFO * *)
0x18000ed3e  mov     rcx, [rbp+57h+var_80]; hKey
0x18000ed42  test    rcx, rcx
0x18000ed45  jz      short loc_18000ED51
0x18000ed47  call    cs:__imp_RegCloseKey
0x18000ed4d  mov     [rbp+57h+var_80], r14
0x18000ed51  mov     rcx, rsi
0x18000ed54  call    WdipFree
0x18000ed59  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ed5d  test    rcx, rcx
0x18000ed60  jz      short loc_18000ED68
0x18000ed62  call    cs:__imp_RegCloseKey
0x18000ed68  mov     eax, ebx
0x18000ed6a  mov     rcx, [rbp+57h+var_40]
0x18000ed6e  xor     rcx, rsp; StackCookie
0x18000ed71  call    __security_check_cookie
0x18000ed76  add     rsp, 0B8h
0x18000ed7d  pop     r14
0x18000ed7f  pop     r13
0x18000ed81  pop     rdi
0x18000ed82  pop     rsi
0x18000ed83  pop     rbx
0x18000ed84  pop     rbp
0x18000ed85  retn
```
