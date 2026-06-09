# _QueryAutoLogonState

- ea: `0x180038c34`
- end: `0x1800392d6`
- name: `_QueryAutoLogonState`
- size: `1698`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180038b98`

## callees

- `0x18001f524`
- `0x180038c34`
- `0x180039418`
- `0x180039bb0`
- `0x18003fa40`
- `0x180046b44`
- `0x180047bb4`
- `0x18004f478`
- `0x180065c38`
- `0x18006c000`
- `0x18009212c`
- `0x180092444`
- `0x1800924a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038d87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038e41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038ec4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038d87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038e41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038ec4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038cbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038cbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038fa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038fa9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038d11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038f7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038d11`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038f7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800390d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039167`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800392bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800390d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180039167`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800392bb`
- `SHCORE!SHCreateThread` at `0x1800391d1`
- `SHCORE!SHCreateThread` at `0x1800391d1`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180038c8b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180038c8b`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x1800391fa`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetAsyncKeyState` at `0x1800391fa`

## pseudocode

```c
__int64 __fastcall QueryAutoLogonState(char a1, char a2, int a3)
{
  int v4; // r15d
  unsigned __int8 v5; // r13
  int v6; // r14d
  int v7; // esi
  unsigned int v9; // ebx
  int SystemMetrics; // eax
  int v11; // edx
  int v12; // ecx
  LSTATUS v13; // eax
  __int64 v14; // rdx
  LSTATUS ValueW; // eax
  signed int v16; // edi
  signed int v17; // ecx
  bool v18; // zf
  LSTATUS v19; // eax
  __int64 v20; // rdx
  HKEY v21; // rcx
  unsigned int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  char v30; // di
  unsigned int v31; // r9d
  int v32; // eax
  unsigned int pvData; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh] BYREF
  int pData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pcbData[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v40; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwDisposition[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v42[512]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[512]; // [rsp+290h] [rbp+190h] BYREF

  *(_DWORD *)Data = a3;
  v34 = 0;
  pData = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v9 = 4;
  SystemMetrics = GetSystemMetrics(4096);
  v12 = 0;
  if ( !SystemMetrics )
  {
    hKey = 0;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 7u, &hKey);
    v12 = 0;
    if ( !v13 )
    {
      v40 = 0;
      dwDisposition[0] = 0;
      if ( RegCreateKeyExW(hKey, L"AutoLogonChecked", 0, 0, 1u, 3u, 0, &v40, dwDisposition) )
      {
LABEL_49:
        RegCloseKey(hKey);
        goto LABEL_50;
      }
      if ( dwDisposition[0] != 2 )
      {
        v5 = 1;
        if ( a1 )
        {
          if ( (unsigned __int8)IsSingleUserNoPassword(v43, v14, v42) )
          {
            v9 = 17;
LABEL_48:
            RegCloseKey(v40);
            goto LABEL_49;
          }
        }
      }
      pdwType = 0;
      pcbData[0] = 4;
      ValueW = RegGetValueW(hKey, 0, L"AutoAdminLogon", 0x10000012u, &pdwType, &pvData, pcbData);
      LOWORD(v16) = 13;
      v17 = ValueW;
      if ( ValueW )
      {
        if ( ValueW == 234 )
        {
          LOWORD(v17) = 13;
        }
        else if ( ValueW <= 0 )
        {
          goto LABEL_19;
        }
      }
      else
      {
        LOWORD(v17) = 13;
        if ( pdwType == 4 )
        {
          if ( pvData <= 1 )
          {
            v17 = 0;
            LOBYTE(v4) = pvData == 1;
LABEL_19:
            if ( v17 < 0 || !v4 )
              goto LABEL_48;
            pcbData[0] = 0;
            pdwType = 4;
            if ( !RegGetValueW(hKey, 0, L"SystemAutoLogon", 0x10000012u, pcbData, &pvData, &pdwType) )
            {
              if ( pcbData[0] == 4 )
              {
                v18 = pvData == 1;
                if ( pvData > 1 )
                  goto LABEL_29;
                goto LABEL_28;
              }
              if ( pdwType == 4 && (unsigned __int16)(pvData - 48) <= 1u )
              {
                v18 = (_WORD)pvData == 49;
LABEL_28:
                LOBYTE(v6) = v18;
              }
            }
LABEL_29:
            pcbData[0] = 0;
            pdwType = 4;
            v19 = RegGetValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\ClearAutologon",
                    L"Enabled",
                    0x10000012u,
                    pcbData,
                    &pvData,
                    &pdwType);
            if ( v19 )
            {
              if ( v19 != 234 )
              {
                v16 = v19;
                if ( v19 <= 0 )
                {
LABEL_39:
                  if ( v16 >= 0 && v7 )
                  {
                    CleanupAutoLogon(0);
                    *(_DWORD *)Data = 0;
                    *(_QWORD *)pcbData = 0;
                    if ( !RegCreateKeyExW(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\ClearAutologon",
                            0,
                            0,
                            0,
                            2u,
                            0,
                            (PHKEY)pcbData,
                            0) )
                    {
                      RegSetValueExW(*(HKEY *)pcbData, L"Enabled", 0, 4u, Data, 4u);
                      v21 = *(HKEY *)pcbData;
                      if ( *(_QWORD *)pcbData != -2147483646 )
                        RegCloseKey(*(HKEY *)pcbData);
                    }
                    if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 2) != 0 )
                      McTemplateU0q_EventWriteTransfer(v21, v20, 3);
                    LOBYTE(v7) = 0;
                    goto LABEL_47;
                  }
                  if ( !_IsSystemConfiguredAutoLogon() && !IsUserOOBE() && _AreEASPoliciesBeingEnforced() )
                  {
                    ((void (*)(void))CleanupAutoLogon)();
                    if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 2) != 0 )
                      McTemplateU0q_EventWriteTransfer(v25, v24, 4);
                    LOBYTE(v7) = pData;
                    goto LABEL_47;
                  }
                  if ( v5 )
                  {
                    pvData = 0;
                    if ( SHRegGetDWORD(hKey, 0, L"AutoLogonCount", &pvData) < 0 )
                    {
                      LOBYTE(v7) = pData;
                    }
                    else
                    {
                      LOBYTE(v7) = pvData;
                      if ( !pvData )
                      {
                        ((void (*)(void))CleanupAutoLogon)();
                        RegDeleteValueW(hKey, L"ForceAutoLockOnLogon");
                        if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 2) != 0 )
                          McTemplateU0q_EventWriteTransfer(v27, v26, 5);
                        goto LABEL_47;
                      }
                      SHRegSetDWORD(hKey, 0, L"AutoLogonCount", --pvData);
                    }
                  }
                  else if ( (int)SHRegGetBOOLWithREGSAM(hKey, 0, L"ForceAutoLogon", v23, &v34) >= 0 && v34 )
                  {
                    LOBYTE(v7) = 0;
                  }
                  else
                  {
                    LOBYTE(v7) = 0;
                    pcbData[0] = 0;
                    v9 = 2;
                    if ( SHRegGetDWORD(
                           HKEY_LOCAL_MACHINE,
                           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                           L"ForceAutoLockOnLogon",
                           pcbData) >= 0 )
                    {
                      if ( pcbData[0] )
                      {
                        ((void (*)(void))CleanupAutoLogon)();
                        RegDeleteValueW(hKey, L"ForceAutoLockOnLogon");
                        if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 2) != 0 )
                          McTemplateU0q_EventWriteTransfer(v29, v28, 1);
                      }
                    }
                    if ( (unsigned __int8)v6 != 1 )
                      goto LABEL_47;
                  }
                  if ( _IsSystemConfiguredAutoLogon() || (v30 = 1, IsUserOOBE()) )
                    v30 = 0;
                  pData = 0;
                  pcbData[0] = 0;
                  pdwType = 0;
                  if ( a2 )
                  {
                    if ( !SHCreateThread(CSecureLockAction::CheckCompletion, &pData, 0, s_CheckShiftKeyThreadStartProc)
                      || (v32 = 1, !pData) )
                    {
                      v32 = 0;
                    }
                    pData = v32;
                    if ( !v32 )
                      goto LABEL_93;
                  }
                  else
                  {
                    if ( GetAsyncKeyState(16) >= 0 )
                    {
                      pData = 0;
LABEL_93:
                      if ( v30
                        && (Data[0] & 2) != 0
                        && a2
                        && SHRegGetDWORD(v40, 0, L"AutoLogonSkip", &pdwType) >= 0
                        && pdwType == 1 )
                      {
                        v9 = 2;
                      }
                      else
                      {
                        v9 = (v6 << 6) | 0x21;
                        _UpdateAutologonSID();
                      }
                      RegDeleteValueW(v40, L"AutoLogonSkip");
LABEL_47:
                      LOBYTE(v6) = v34;
                      goto LABEL_48;
                    }
                    pData = 1;
                  }
                  if ( (int)SHRegGetBOOLWithREGSAM(hKey, 0, L"IgnoreShiftOverride", v31, (int *)pcbData) < 0
                    || !pcbData[0] )
                  {
                    v9 = 2;
                    if ( v30 && (Data[0] & 4) != 0 && a2 )
                      SHRegSetDWORD(v40, 0, L"AutoLogonSkip", 1u);
                    goto LABEL_47;
                  }
                  goto LABEL_93;
                }
              }
            }
            else if ( pcbData[0] == 4 )
            {
              if ( pvData <= 1 )
              {
                v16 = 0;
                LOBYTE(v7) = pvData == 1;
                goto LABEL_39;
              }
            }
            else if ( pdwType == 4 && (unsigned __int16)(pvData - 48) <= 1u )
            {
              v16 = 0;
              LOBYTE(v7) = (_WORD)pvData == 49;
              goto LABEL_39;
            }
            v16 = (unsigned __int16)v16 | 0x80070000;
            goto LABEL_39;
          }
        }
        else if ( pcbData[0] == 4 && (unsigned __int16)(pvData - 48) <= 1u )
        {
          v17 = 0;
          LOBYTE(v4) = (_WORD)pvData == 49;
          goto LABEL_19;
        }
      }
      v17 = (unsigned __int16)v17 | 0x80070000;
      goto LABEL_19;
    }
  }
LABEL_50:
  if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 0x10) != 0 )
    McTemplateU0qqqqq_EventWriteTransfer(v12, v11, v5, v4, v6, v7, v9);
  return v9;
}

```

## disassembly

```asm
0x180038c34  push    rbp
0x180038c36  push    rbx
0x180038c37  push    rsi
0x180038c38  push    rdi
0x180038c39  push    r12
0x180038c3b  push    r13
0x180038c3d  push    r14
0x180038c3f  push    r15
0x180038c41  lea     rbp, [rsp-3A8h]
0x180038c49  sub     rsp, 4A8h
0x180038c50  mov     rax, cs:__security_cookie
0x180038c57  xor     rax, rsp
0x180038c5a  mov     [rbp+3E0h+var_50], rax
0x180038c61  xor     eax, eax
0x180038c63  mov     dword ptr [rsp+4E0h+Data], r8d
0x180038c68  mov     dil, cl
0x180038c6b  mov     [rsp+4E0h+var_48C], eax
0x180038c6f  mov     ecx, 1000h; nIndex
0x180038c74  mov     [rsp+4E0h+pData], eax
0x180038c78  mov     r15d, eax
0x180038c7b  mov     r13b, al
0x180038c7e  mov     r14d, eax
0x180038c81  mov     esi, eax
0x180038c83  mov     r12b, dl
0x180038c86  mov     ebx, 4
0x180038c8b  call    cs:__imp_GetSystemMetrics
0x180038c91  xor     ecx, ecx
0x180038c93  test    eax, eax
0x180038c95  jnz     loc_180038FF0
0x180038c9b  mov     [rsp+4E0h+hKey], rcx
0x180038ca0  lea     rax, [rsp+4E0h+hKey]
0x180038ca5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038cac  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180038cb1  lea     r9d, [rbx+3]; samDesired
0x180038cb5  xor     r8d, r8d; ulOptions
0x180038cb8  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180038cbf  call    cs:__imp_RegOpenKeyExW
0x180038cc5  xor     ecx, ecx
0x180038cc7  test    eax, eax
0x180038cc9  jnz     loc_180038FF0
0x180038ccf  lea     rax, [rbp+3E0h+dwDisposition]
0x180038cd3  mov     [rsp+4E0h+var_468], rcx
0x180038cd8  mov     [rsp+4E0h+lpdwDisposition], rax; lpdwDisposition
0x180038cdd  lea     rdx, aAutologoncheck; "AutoLogonChecked"
0x180038ce4  lea     rax, [rsp+4E0h+var_468]
0x180038ce9  mov     [rbp+3E0h+dwDisposition], ecx
0x180038cec  mov     [rsp+4E0h+var_4A8], rax; phkResult
0x180038cf1  xor     r9d, r9d; lpClass
0x180038cf4  mov     [rsp+4E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180038cf9  xor     r8d, r8d; Reserved
0x180038cfc  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180038d01  mov     [rsp+4E0h+samDesired], 3; samDesired
0x180038d09  mov     dword ptr [rsp+4E0h+phkResult], 1; dwOptions
0x180038d11  call    cs:__imp_RegCreateKeyExW
0x180038d17  xor     ecx, ecx
0x180038d19  test    eax, eax
0x180038d1b  jnz     loc_180038FE5
0x180038d21  cmp     [rbp+3E0h+dwDisposition], 2
0x180038d25  jz      short loc_180038D4D
0x180038d27  mov     r13b, 1
0x180038d2a  test    dil, dil
0x180038d2d  jz      short loc_180038D4D
0x180038d2f  lea     r8, [rbp+3E0h+var_450]
0x180038d33  lea     rcx, [rbp+3E0h+var_250]
0x180038d3a  call    _IsSingleUserNoPassword
0x180038d3f  xor     ecx, ecx
0x180038d41  test    al, al
0x180038d43  jz      short loc_180038D4D
0x180038d45  lea     ebx, [rcx+11h]
0x180038d48  jmp     loc_180038FDA
0x180038d4d  lea     rax, [rsp+4E0h+pcbData]
0x180038d52  mov     [rsp+4E0h+pdwType], ecx
0x180038d56  mov     rcx, [rsp+4E0h+hKey]; hkey
0x180038d5b  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x180038d62  mov     [rsp+4E0h+lpSecurityAttributes], rax; pcbData
0x180038d67  mov     r9d, 10000012h; dwFlags
0x180038d6d  lea     rax, [rsp+4E0h+pvData]
0x180038d72  mov     [rsp+4E0h+pcbData], ebx
0x180038d76  mov     qword ptr [rsp+4E0h+samDesired], rax; pvData
0x180038d7b  xor     edx, edx; lpSubKey
0x180038d7d  lea     rax, [rsp+4E0h+pdwType]
0x180038d82  mov     [rsp+4E0h+phkResult], rax; pdwType
0x180038d87  call    cs:__imp_RegGetValueW
0x180038d8d  mov     edi, 0Dh
0x180038d92  xor     edx, edx; lpSubKey
0x180038d94  mov     ecx, eax
0x180038d96  lea     r9d, [rdi+24h]
0x180038d9a  test    eax, eax
0x180038d9c  jnz     short loc_180038DE0
0x180038d9e  mov     ecx, edi
0x180038da0  cmp     [rsp+4E0h+pdwType], ebx
0x180038da4  jnz     short loc_180038DB7
0x180038da6  lea     eax, [rdi-0Ch]
0x180038da9  cmp     [rsp+4E0h+pvData], eax
0x180038dad  ja      short loc_180038DEF
0x180038daf  mov     ecx, edx
0x180038db1  setz    r15b
0x180038db5  jmp     short loc_180038DF8
0x180038db7  cmp     [rsp+4E0h+pcbData], ebx
0x180038dbb  jnz     short loc_180038DEF
0x180038dbd  movzx   eax, word ptr [rsp+4E0h+pvData]
0x180038dc2  mov     r8d, 1
0x180038dc8  sub     ax, 30h ; '0'
0x180038dcc  cmp     ax, r8w
0x180038dd0  ja      short loc_180038DEF
0x180038dd2  cmp     r9w, word ptr [rsp+4E0h+pvData]
0x180038dd8  mov     ecx, edx
0x180038dda  setz    r15b
0x180038dde  jmp     short loc_180038DF8
0x180038de0  cmp     eax, 0EAh
0x180038de5  jnz     short loc_180038DEB
0x180038de7  mov     ecx, edi
0x180038de9  jmp     short loc_180038DEF
0x180038deb  test    eax, eax
0x180038ded  jle     short loc_180038DF8
0x180038def  movzx   ecx, cx
0x180038df2  or      ecx, 80070000h
0x180038df8  test    ecx, ecx
0x180038dfa  js      loc_180038FDA
0x180038e00  test    r15d, r15d
0x180038e03  jz      loc_180038FDA
0x180038e09  mov     rcx, [rsp+4E0h+hKey]; hkey
0x180038e0e  lea     rax, [rsp+4E0h+pdwType]
0x180038e13  mov     [rsp+4E0h+lpSecurityAttributes], rax; pcbData
0x180038e18  lea     r8, aSystemautologo; "SystemAutoLogon"
0x180038e1f  lea     rax, [rsp+4E0h+pvData]
0x180038e24  mov     [rsp+4E0h+pcbData], edx
0x180038e28  mov     qword ptr [rsp+4E0h+samDesired], rax; pvData
0x180038e2d  mov     r9d, 10000012h; dwFlags
0x180038e33  lea     rax, [rsp+4E0h+pcbData]
0x180038e38  mov     [rsp+4E0h+pdwType], ebx
0x180038e3c  mov     [rsp+4E0h+phkResult], rax; pdwType
0x180038e41  call    cs:__imp_RegGetValueW
0x180038e47  xor     ecx, ecx
0x180038e49  test    eax, eax
0x180038e4b  jnz     short loc_180038E83
0x180038e4d  cmp     [rsp+4E0h+pcbData], ebx
0x180038e51  jnz     short loc_180038E5E
0x180038e53  lea     eax, [rcx+1]
0x180038e56  cmp     [rsp+4E0h+pvData], eax
0x180038e5a  ja      short loc_180038E83
0x180038e5c  jmp     short loc_180038E7F
0x180038e5e  cmp     [rsp+4E0h+pdwType], ebx
0x180038e62  jnz     short loc_180038E83
0x180038e64  movzx   eax, word ptr [rsp+4E0h+pvData]
0x180038e69  mov     edx, 1
0x180038e6e  sub     ax, 30h ; '0'
0x180038e72  cmp     ax, dx
0x180038e75  ja      short loc_180038E83
0x180038e77  lea     eax, [rdx+30h]
0x180038e7a  cmp     ax, word ptr [rsp+4E0h+pvData]
0x180038e7f  setz    r14b
0x180038e83  lea     rax, [rsp+4E0h+pdwType]
0x180038e88  mov     [rsp+4E0h+pcbData], ecx
0x180038e8c  mov     [rsp+4E0h+lpSecurityAttributes], rax; pcbData
0x180038e91  lea     r8, aEnabled; "Enabled"
0x180038e98  lea     rax, [rsp+4E0h+pvData]
0x180038e9d  mov     [rsp+4E0h+pdwType], ebx
0x180038ea1  mov     qword ptr [rsp+4E0h+samDesired], rax; pvData
0x180038ea6  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038ead  lea     rax, [rsp+4E0h+pcbData]
0x180038eb2  mov     r9d, 10000012h; dwFlags
0x180038eb8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180038ebf  mov     [rsp+4E0h+phkResult], rax; pdwType
0x180038ec4  call    cs:__imp_RegGetValueW
0x180038eca  xor     ecx, ecx
0x180038ecc  test    eax, eax
0x180038ece  jnz     short loc_180038F10
0x180038ed0  cmp     [rsp+4E0h+pcbData], ebx
0x180038ed4  jnz     short loc_180038EE7
0x180038ed6  lea     eax, [rcx+1]
0x180038ed9  cmp     [rsp+4E0h+pvData], eax
0x180038edd  ja      short loc_180038F1D
0x180038edf  mov     edi, ecx
0x180038ee1  setz    sil
0x180038ee5  jmp     short loc_180038F26
0x180038ee7  cmp     [rsp+4E0h+pdwType], ebx
0x180038eeb  jnz     short loc_180038F1D
0x180038eed  movzx   eax, word ptr [rsp+4E0h+pvData]
0x180038ef2  mov     edx, 1
0x180038ef7  sub     ax, 30h ; '0'
0x180038efb  cmp     ax, dx
0x180038efe  ja      short loc_180038F1D
0x180038f00  lea     eax, [rdx+30h]
0x180038f03  mov     edi, ecx
0x180038f05  cmp     ax, word ptr [rsp+4E0h+pvData]
0x180038f0a  setz    sil
0x180038f0e  jmp     short loc_180038F26
0x180038f10  cmp     eax, 0EAh
0x180038f15  jz      short loc_180038F1D
0x180038f17  mov     edi, eax
0x180038f19  test    eax, eax
0x180038f1b  jle     short loc_180038F26
0x180038f1d  movzx   edi, di
0x180038f20  or      edi, 80070000h
0x180038f26  test    edi, edi
0x180038f28  js      loc_180039037
0x180038f2e  xor     edi, edi
0x180038f30  test    esi, esi
0x180038f32  jz      loc_180039039
0x180038f38  call    _CleanupAutoLogon
0x180038f3d  mov     [rsp+4E0h+lpdwDisposition], rdi; lpdwDisposition
0x180038f42  lea     rax, [rsp+4E0h+pcbData]
0x180038f47  mov     [rsp+4E0h+var_4A8], rax; phkResult
0x180038f4c  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038f53  mov     [rsp+4E0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180038f58  mov     rsi, 0FFFFFFFF80000002h
0x180038f5f  mov     [rsp+4E0h+samDesired], 2; samDesired
0x180038f67  xor     r9d, r9d; lpClass
0x180038f6a  xor     r8d, r8d; Reserved
0x180038f6d  mov     dword ptr [rsp+4E0h+phkResult], edi; dwOptions
0x180038f71  mov     rcx, rsi; hKey
0x180038f74  mov     dword ptr [rsp+4E0h+Data], edi
0x180038f78  mov     qword ptr [rsp+4E0h+pcbData], rdi
0x180038f7d  call    cs:__imp_RegCreateKeyExW
0x180038f83  test    eax, eax
0x180038f85  jnz     short loc_180038FBF
0x180038f87  lea     rax, [rsp+4E0h+Data]
0x180038f8c  mov     [rsp+4E0h+samDesired], ebx; cbData
0x180038f90  mov     ecx, ebx
0x180038f92  mov     [rsp+4E0h+phkResult], rax; lpData
0x180038f97  mov     rcx, qword ptr [rsp+4E0h+pcbData]; hKey
0x180038f9c  lea     rdx, aEnabled; "Enabled"
0x180038fa3  mov     r9d, ebx; dwType
0x180038fa6  xor     r8d, r8d; Reserved
0x180038fa9  call    cs:__imp_RegSetValueExW
0x180038faf  mov     rcx, qword ptr [rsp+4E0h+pcbData]; hKey
0x180038fb4  cmp     rcx, rsi
0x180038fb7  jz      short loc_180038FBF
0x180038fb9  call    cs:__imp_RegCloseKey
0x180038fbf  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 2
0x180038fc6  jz      short loc_180038FD3
0x180038fc8  mov     r8d, 3
0x180038fce  call    McTemplateU0q_EventWriteTransfer
0x180038fd3  mov     esi, edi
0x180038fd5  mov     r14d, [rsp+4E0h+var_48C]
0x180038fda  mov     rcx, [rsp+4E0h+var_468]; hKey
0x180038fdf  call    cs:__imp_RegCloseKey
0x180038fe5  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180038fea  call    cs:__imp_RegCloseKey
0x180038ff0  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 10h
0x180038ff7  jz      short loc_180039012
0x180038ff9  mov     dword ptr [rsp+4E0h+lpSecurityAttributes], ebx
0x180038ffd  mov     r9d, r15d
0x180039000  mov     [rsp+4E0h+samDesired], esi
0x180039004  movzx   r8d, r13b
0x180039008  mov     dword ptr [rsp+4E0h+phkResult], r14d
0x18003900d  call    McTemplateU0qqqqq_EventWriteTransfer
0x180039012  mov     eax, ebx
0x180039014  mov     rcx, [rbp+3E0h+var_50]
0x18003901b  xor     rcx, rsp; StackCookie
0x18003901e  call    __security_check_cookie
0x180039023  add     rsp, 4A8h
0x18003902a  pop     r15
0x18003902c  pop     r14
0x18003902e  pop     r13
0x180039030  pop     r12
0x180039032  pop     rdi
0x180039033  pop     rsi
0x180039034  pop     rbx
0x180039035  pop     rbp
0x180039036  retn
0x180039037  xor     edi, edi
0x180039039  call    ?_IsSystemConfiguredAutoLogon@@YA_NXZ; _IsSystemConfiguredAutoLogon(void)
0x18003903e  test    al, al
0x180039040  jnz     short loc_180039073
0x180039042  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x180039047  test    al, al
0x180039049  jnz     short loc_180039073
0x18003904b  call    ?_AreEASPoliciesBeingEnforced@@YA_NXZ; _AreEASPoliciesBeingEnforced(void)
0x180039050  test    al, al
0x180039052  jz      short loc_180039073
0x180039054  call    _CleanupAutoLogon
0x180039059  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 2
0x180039060  jz      short loc_18003906A
0x180039062  mov     r8d, ebx
0x180039065  call    McTemplateU0q_EventWriteTransfer
0x18003906a  mov     esi, [rsp+4E0h+pData]
0x18003906e  jmp     loc_180038FD5
0x180039073  mov     rcx, [rsp+4E0h+hKey]; HKEY
0x180039078  xor     edx, edx; unsigned __int16 *
0x18003907a  test    r13b, r13b
0x18003907d  jz      short loc_1800390F9
0x18003907f  lea     r9, [rsp+4E0h+pvData]; unsigned int *
0x180039084  mov     [rsp+4E0h+pvData], edi
0x180039088  lea     r8, aAutologoncount; "AutoLogonCount"
0x18003908f  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180039094  test    eax, eax
0x180039096  js      loc_18003918C
0x18003909c  mov     esi, [rsp+4E0h+pvData]
0x1800390a0  test    esi, esi
0x1800390a2  jz      short loc_1800390C5
0x1800390a4  mov     rcx, [rsp+4E0h+hKey]; HKEY
0x1800390a9  lea     r9d, [rsi-1]; unsigned int
0x1800390ad  lea     r8, aAutologoncount; "AutoLogonCount"
0x1800390b4  mov     [rsp+4E0h+pvData], r9d
0x1800390b9  xor     edx, edx; unsigned __int16 *
0x1800390bb  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800390c0  jmp     loc_180039190
0x1800390c5  call    _CleanupAutoLogon
  ... truncated ...
```
