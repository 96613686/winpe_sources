# AddNewProviderToRegistry

- ea: `0x140080d28`
- end: `0x140081196`
- name: `AddNewProviderToRegistry`
- size: `1134`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d310`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140074004`
- `0x140075070`
- `0x140080d28`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400810fb`
- `ADVAPI32!RegCloseKey` at `0x140081144`
- `ADVAPI32!RegCloseKey` at `0x1400810fb`
- `ADVAPI32!RegCloseKey` at `0x140081144`
- `ADVAPI32!RegOpenKeyExW` at `0x140080db0`
- `ADVAPI32!RegOpenKeyExW` at `0x140080db0`
- `ADVAPI32!RegCreateKeyExW` at `0x140080e32`
- `ADVAPI32!RegCreateKeyExW` at `0x140080e32`
- `ADVAPI32!RegDeleteKeyExW` at `0x140081079`
- `ADVAPI32!RegDeleteKeyExW` at `0x140081079`
- `KERNEL32!GetLastError` at `0x140080eac`
- `KERNEL32!GetLastError` at `0x140080f09`
- `KERNEL32!GetLastError` at `0x140080f6a`
- `KERNEL32!GetLastError` at `0x140080fc6`
- `KERNEL32!GetLastError` at `0x140081016`
- `KERNEL32!GetLastError` at `0x140080eac`
- `KERNEL32!GetLastError` at `0x140080f09`
- `KERNEL32!GetLastError` at `0x140080f6a`
- `KERNEL32!GetLastError` at `0x140080fc6`
- `KERNEL32!GetLastError` at `0x140081016`

## pseudocode

```c
__int64 __fastcall AddNewProviderToRegistry(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v9; // ebx
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  LSTATUS v13; // eax
  DWORD LastError; // eax
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  int phkResultc; // [rsp+20h] [rbp-40h]
  HKEY v25; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF

  hKey = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Device Providers", 0, 0x20006u, &hKey);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 106;
      v12 = v9;
LABEL_64:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v12);
      return v9;
    }
    return v9;
  }
  v13 = RegCreateKeyExW(hKey, a1, 0, 0, 0, 0x2000000u, 0, &v25, 0);
  v9 = v13;
  if ( !v13 )
  {
    if ( SetRegistryStringValue(v25, 1u, L"FriendlyName", a2, phkResult) )
    {
      if ( SetRegistryStringValue(v25, 2u, L"ImageName", a3, phkResulta) )
      {
        if ( SetRegistryStringValue(v25, 1u, L"ProviderName", a4, phkResultb) )
        {
          if ( SetRegistryStringValue(v25, 1u, L"GUID", a1, phkResultc) )
          {
            if ( (unsigned int)SetRegistryDword(v25, L"APIVersion", a5) )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, a2);
              }
              goto LABEL_52;
            }
            LastError = GetLastError();
            v9 = LastError;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 112;
              goto LABEL_40;
            }
          }
          else
          {
            LastError = GetLastError();
            v9 = LastError;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 111;
              goto LABEL_40;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 110;
            goto LABEL_40;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 109;
          goto LABEL_40;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 108;
LABEL_40:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
    }
    if ( !v9 )
      goto LABEL_52;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
      (_DWORD)a2,
      v13);
  }
LABEL_42:
  if ( !hKey )
    goto LABEL_58;
  v17 = RegDeleteKeyExW(hKey, a1, 0, 0);
  if ( v17
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v17);
  }
LABEL_52:
  if ( hKey )
  {
    v18 = RegCloseKey(hKey);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v18);
      }
    }
  }
LABEL_58:
  if ( v25 )
  {
    v19 = RegCloseKey(v25);
    if ( v19 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 116;
        v12 = v19;
        goto LABEL_64;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140080d28  push    rbp
0x140080d2a  push    rbx
0x140080d2b  push    rsi
0x140080d2c  push    rdi
0x140080d2d  push    r12
0x140080d2f  push    r14
0x140080d31  push    r15
0x140080d33  mov     rbp, rsp
0x140080d36  sub     rsp, 60h
0x140080d3a  mov     r14, r9
0x140080d3d  mov     [rbp+hKey], 0
0x140080d45  mov     rsi, r8
0x140080d48  mov     [rbp+var_10], 0
0x140080d50  mov     rdi, rdx
0x140080d53  mov     r15, rcx
0x140080d56  mov     rcx, cs:WPP_GLOBAL_Control
0x140080d5d  lea     rax, WPP_GLOBAL_Control
0x140080d64  mov     r12d, 2
0x140080d6a  cmp     rcx, rax
0x140080d6d  jz      short loc_140080D90
0x140080d6f  test    [rcx+1Ch], r12b
0x140080d73  jz      short loc_140080D90
0x140080d75  cmp     byte ptr [rcx+19h], 5
0x140080d79  jb      short loc_140080D90
0x140080d7b  mov     rcx, [rcx+10h]
0x140080d7f  lea     edx, [r12+67h]
0x140080d84  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140080d8b  call    WPP_SF_
0x140080d90  lea     rax, [rbp+hKey]
0x140080d94  mov     r9d, 20006h; samDesired
0x140080d9a  xor     r8d, r8d; ulOptions
0x140080d9d  mov     [rsp+60h+phkResult], rax; phkResult
0x140080da2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Fax\\Device Provid"...
0x140080da9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140080db0  call    cs:__imp_RegOpenKeyExW
0x140080db7  nop     dword ptr [rax+rax+00h]
0x140080dbc  mov     ebx, eax
0x140080dbe  test    eax, eax
0x140080dc0  jz      short loc_140080DFA
0x140080dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140080dc9  lea     rax, WPP_GLOBAL_Control
0x140080dd0  cmp     rcx, rax
0x140080dd3  jz      loc_140081184
0x140080dd9  test    [rcx+1Ch], r12b
0x140080ddd  jz      loc_140081184
0x140080de3  cmp     [rcx+19h], r12b
0x140080de7  jb      loc_140081184
0x140080ded  mov     edx, 6Ah ; 'j'
0x140080df2  mov     r9d, ebx
0x140080df5  jmp     loc_140081174
0x140080dfa  mov     rcx, [rbp+hKey]; hKey
0x140080dfe  lea     rax, [rbp+var_10]
0x140080e02  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x140080e0b  xor     r9d, r9d; lpClass
0x140080e0e  mov     [rsp+60h+var_28], rax; phkResult
0x140080e13  xor     r8d, r8d; Reserved
0x140080e16  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140080e1f  mov     rdx, r15; lpSubKey
0x140080e22  mov     [rsp+60h+samDesired], 2000000h; samDesired
0x140080e2a  mov     dword ptr [rsp+60h+phkResult], 0; int
0x140080e32  call    cs:__imp_RegCreateKeyExW
0x140080e39  nop     dword ptr [rax+rax+00h]
0x140080e3e  mov     ebx, eax
0x140080e40  test    eax, eax
0x140080e42  jz      short loc_140080E90
0x140080e44  mov     rcx, cs:WPP_GLOBAL_Control
0x140080e4b  lea     rsi, WPP_GLOBAL_Control
0x140080e52  cmp     rcx, rsi
0x140080e55  jz      loc_140081063
0x140080e5b  test    [rcx+1Ch], r12b
0x140080e5f  jz      loc_140081063
0x140080e65  cmp     [rcx+19h], r12b
0x140080e69  jb      loc_140081063
0x140080e6f  mov     rcx, [rcx+10h]
0x140080e73  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140080e7a  mov     edx, 6Bh ; 'k'
0x140080e7f  mov     dword ptr [rsp+60h+phkResult], eax
0x140080e83  mov     r9, rdi
0x140080e86  call    WPP_SF_Sd
0x140080e8b  jmp     loc_140081063
0x140080e90  mov     rcx, [rbp+var_10]; HKEY
0x140080e94  lea     r8, aFriendlyname; "FriendlyName"
0x140080e9b  mov     r9, rdi; unsigned __int16 *
0x140080e9e  mov     edx, 1; unsigned int
0x140080ea3  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140080ea8  test    eax, eax
0x140080eaa  jnz     short loc_140080EEF
0x140080eac  call    cs:__imp_GetLastError
0x140080eb3  nop     dword ptr [rax+rax+00h]
0x140080eb8  mov     ebx, eax
0x140080eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140080ec1  lea     rsi, WPP_GLOBAL_Control
0x140080ec8  cmp     rcx, rsi
0x140080ecb  jz      loc_14008105B
0x140080ed1  test    [rcx+1Ch], r12b
0x140080ed5  jz      loc_14008105B
0x140080edb  cmp     [rcx+19h], r12b
0x140080edf  jb      loc_14008105B
0x140080ee5  mov     edx, 6Ch ; 'l'
0x140080eea  jmp     loc_140081048
0x140080eef  mov     rcx, [rbp+var_10]; HKEY
0x140080ef3  lea     r8, aImagename; "ImageName"
0x140080efa  mov     r9, rsi; unsigned __int16 *
0x140080efd  mov     edx, r12d; unsigned int
0x140080f00  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140080f05  test    eax, eax
0x140080f07  jnz     short loc_140080F4C
0x140080f09  call    cs:__imp_GetLastError
0x140080f10  nop     dword ptr [rax+rax+00h]
0x140080f15  mov     ebx, eax
0x140080f17  mov     rcx, cs:WPP_GLOBAL_Control
0x140080f1e  lea     rsi, WPP_GLOBAL_Control
0x140080f25  cmp     rcx, rsi
0x140080f28  jz      loc_14008105B
0x140080f2e  test    [rcx+1Ch], r12b
0x140080f32  jz      loc_14008105B
0x140080f38  cmp     [rcx+19h], r12b
0x140080f3c  jb      loc_14008105B
0x140080f42  mov     edx, 6Dh ; 'm'
0x140080f47  jmp     loc_140081048
0x140080f4c  mov     rcx, [rbp+var_10]; HKEY
0x140080f50  lea     r8, aProvidername; "ProviderName"
0x140080f57  mov     esi, 1
0x140080f5c  mov     r9, r14; unsigned __int16 *
0x140080f5f  mov     edx, esi; unsigned int
0x140080f61  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140080f66  test    eax, eax
0x140080f68  jnz     short loc_140080FAD
0x140080f6a  call    cs:__imp_GetLastError
0x140080f71  nop     dword ptr [rax+rax+00h]
0x140080f76  mov     ebx, eax
0x140080f78  mov     rcx, cs:WPP_GLOBAL_Control
0x140080f7f  lea     rsi, WPP_GLOBAL_Control
0x140080f86  cmp     rcx, rsi
0x140080f89  jz      loc_14008105B
0x140080f8f  test    [rcx+1Ch], r12b
0x140080f93  jz      loc_14008105B
0x140080f99  cmp     [rcx+19h], r12b
0x140080f9d  jb      loc_14008105B
0x140080fa3  mov     edx, 6Eh ; 'n'
0x140080fa8  jmp     loc_140081048
0x140080fad  mov     rcx, [rbp+var_10]; HKEY
0x140080fb1  lea     r8, aGuid_0; "GUID"
0x140080fb8  mov     r9, r15; unsigned __int16 *
0x140080fbb  mov     edx, esi; unsigned int
0x140080fbd  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140080fc2  test    eax, eax
0x140080fc4  jnz     short loc_140080FFA
0x140080fc6  call    cs:__imp_GetLastError
0x140080fcd  nop     dword ptr [rax+rax+00h]
0x140080fd2  mov     ebx, eax
0x140080fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140080fdb  lea     rsi, WPP_GLOBAL_Control
0x140080fe2  cmp     rcx, rsi
0x140080fe5  jz      short loc_14008105B
0x140080fe7  test    [rcx+1Ch], r12b
0x140080feb  jz      short loc_14008105B
0x140080fed  cmp     [rcx+19h], r12b
0x140080ff1  jb      short loc_14008105B
0x140080ff3  mov     edx, 6Fh ; 'o'
0x140080ff8  jmp     short loc_140081048
0x140080ffa  mov     r8d, [rbp+arg_20]
0x140080ffe  lea     rdx, aApiversion; "APIVersion"
0x140081005  mov     rcx, [rbp+var_10]
0x140081009  call    SetRegistryDword
0x14008100e  test    eax, eax
0x140081010  jnz     loc_1400810BB
0x140081016  call    cs:__imp_GetLastError
0x14008101d  nop     dword ptr [rax+rax+00h]
0x140081022  mov     ebx, eax
0x140081024  mov     rcx, cs:WPP_GLOBAL_Control
0x14008102b  lea     rsi, WPP_GLOBAL_Control
0x140081032  cmp     rcx, rsi
0x140081035  jz      short loc_14008105B
0x140081037  test    [rcx+1Ch], r12b
0x14008103b  jz      short loc_14008105B
0x14008103d  cmp     [rcx+19h], r12b
0x140081041  jb      short loc_14008105B
0x140081043  mov     edx, 70h ; 'p'
0x140081048  mov     rcx, [rcx+10h]
0x14008104c  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081053  mov     r9d, eax
0x140081056  call    WPP_SF_d
0x14008105b  test    ebx, ebx
0x14008105d  jz      loc_1400810F2
0x140081063  mov     rcx, [rbp+hKey]; hKey
0x140081067  test    rcx, rcx
0x14008106a  jz      loc_14008113B
0x140081070  xor     r9d, r9d; Reserved
0x140081073  xor     r8d, r8d; samDesired
0x140081076  mov     rdx, r15; lpSubKey
0x140081079  call    cs:__imp_RegDeleteKeyExW
0x140081080  nop     dword ptr [rax+rax+00h]
0x140081085  test    eax, eax
0x140081087  jz      short loc_1400810F2
0x140081089  mov     rcx, cs:WPP_GLOBAL_Control
0x140081090  cmp     rcx, rsi
0x140081093  jz      short loc_1400810F2
0x140081095  test    [rcx+1Ch], r12b
0x140081099  jz      short loc_1400810F2
0x14008109b  cmp     [rcx+19h], r12b
0x14008109f  jb      short loc_1400810F2
0x1400810a1  mov     rcx, [rcx+10h]
0x1400810a5  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400810ac  mov     edx, 72h ; 'r'
0x1400810b1  mov     r9d, eax
0x1400810b4  call    WPP_SF_d
0x1400810b9  jmp     short loc_1400810F2
0x1400810bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400810c2  lea     rsi, WPP_GLOBAL_Control
0x1400810c9  cmp     rcx, rsi
0x1400810cc  jz      short loc_1400810F2
0x1400810ce  test    [rcx+1Ch], r12b
0x1400810d2  jz      short loc_1400810F2
0x1400810d4  cmp     byte ptr [rcx+19h], 5
0x1400810d8  jb      short loc_1400810F2
0x1400810da  mov     rcx, [rcx+10h]
0x1400810de  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400810e5  mov     edx, 71h ; 'q'
0x1400810ea  mov     r9, rdi
0x1400810ed  call    WPP_SF_S
0x1400810f2  mov     rcx, [rbp+hKey]; hKey
0x1400810f6  test    rcx, rcx
0x1400810f9  jz      short loc_14008113B
0x1400810fb  call    cs:__imp_RegCloseKey
0x140081102  nop     dword ptr [rax+rax+00h]
0x140081107  test    eax, eax
0x140081109  jz      short loc_14008113B
0x14008110b  mov     rcx, cs:WPP_GLOBAL_Control
0x140081112  cmp     rcx, rsi
0x140081115  jz      short loc_14008113B
0x140081117  test    [rcx+1Ch], r12b
0x14008111b  jz      short loc_14008113B
0x14008111d  cmp     [rcx+19h], r12b
0x140081121  jb      short loc_14008113B
0x140081123  mov     rcx, [rcx+10h]
0x140081127  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008112e  mov     edx, 73h ; 's'
0x140081133  mov     r9d, eax
0x140081136  call    WPP_SF_d
0x14008113b  mov     rcx, [rbp+var_10]; hKey
0x14008113f  test    rcx, rcx
0x140081142  jz      short loc_140081184
0x140081144  call    cs:__imp_RegCloseKey
0x14008114b  nop     dword ptr [rax+rax+00h]
0x140081150  test    eax, eax
0x140081152  jz      short loc_140081184
0x140081154  mov     rcx, cs:WPP_GLOBAL_Control
0x14008115b  cmp     rcx, rsi
0x14008115e  jz      short loc_140081184
0x140081160  test    [rcx+1Ch], r12b
0x140081164  jz      short loc_140081184
0x140081166  cmp     [rcx+19h], r12b
0x14008116a  jb      short loc_140081184
0x14008116c  mov     edx, 74h ; 't'
0x140081171  mov     r9d, eax
0x140081174  mov     rcx, [rcx+10h]
0x140081178  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008117f  call    WPP_SF_d
0x140081184  mov     eax, ebx
0x140081186  add     rsp, 60h
0x14008118a  pop     r15
0x14008118c  pop     r14
0x14008118e  pop     r12
0x140081190  pop     rdi
0x140081191  pop     rsi
0x140081192  pop     rbx
0x140081193  pop     rbp
0x140081194  retn
```
