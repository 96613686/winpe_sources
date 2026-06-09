# RemoveProviderFromRegistry

- ea: `0x14007e6f4`
- end: `0x14007e83d`
- name: `RemoveProviderFromRegistry`
- size: `329`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022190`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14007e6f4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007e7f1`
- `ADVAPI32!RegCloseKey` at `0x14007e7f1`
- `ADVAPI32!RegOpenKeyExW` at `0x14007e764`
- `ADVAPI32!RegOpenKeyExW` at `0x14007e764`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007e7ac`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007e7ac`

## pseudocode

```c
__int64 __fastcall RemoveProviderFromRegistry(LPCWSTR lpSubKey)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  LSTATUS v7; // eax
  unsigned int v8; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Device Providers", 0, 0x10000u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 118;
      v6 = v2;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v6);
    }
  }
  else
  {
    v7 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
    v3 = v7;
    if ( v7
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (_DWORD)lpSubKey,
        v7);
    }
    v8 = RegCloseKey(hKey);
    if ( v8 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 120;
        v6 = v8;
        goto LABEL_20;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14007e6f4  mov     [rsp+arg_0], rbx
0x14007e6f9  mov     [rsp+arg_10], rbp
0x14007e6fe  push    rdi
0x14007e6ff  sub     rsp, 30h
0x14007e703  mov     rdi, rcx
0x14007e706  mov     [rsp+38h+hKey], 0
0x14007e70f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e716  lea     rbp, WPP_GLOBAL_Control
0x14007e71d  cmp     rcx, rbp
0x14007e720  jz      short loc_14007E743
0x14007e722  test    byte ptr [rcx+1Ch], 2
0x14007e726  jz      short loc_14007E743
0x14007e728  cmp     byte ptr [rcx+19h], 5
0x14007e72c  jb      short loc_14007E743
0x14007e72e  mov     rcx, [rcx+10h]
0x14007e732  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007e739  mov     edx, 75h ; 'u'
0x14007e73e  call    WPP_SF_
0x14007e743  lea     rax, [rsp+38h+hKey]
0x14007e748  mov     r9d, 10000h; samDesired
0x14007e74e  xor     r8d, r8d; ulOptions
0x14007e751  mov     [rsp+38h+phkResult], rax; phkResult
0x14007e756  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Fax\\Device Provid"...
0x14007e75d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007e764  call    cs:__imp_RegOpenKeyExW
0x14007e76a  mov     ebx, eax
0x14007e76c  test    eax, eax
0x14007e76e  jz      short loc_14007E79E
0x14007e770  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e777  cmp     rcx, rbp
0x14007e77a  jz      loc_14007E82B
0x14007e780  test    byte ptr [rcx+1Ch], 2
0x14007e784  jz      loc_14007E82B
0x14007e78a  cmp     byte ptr [rcx+19h], 2
0x14007e78e  jb      loc_14007E82B
0x14007e794  mov     edx, 76h ; 'v'
0x14007e799  mov     r9d, eax
0x14007e79c  jmp     short loc_14007E81B
0x14007e79e  mov     rcx, [rsp+38h+hKey]; hKey
0x14007e7a3  xor     r9d, r9d; Reserved
0x14007e7a6  xor     r8d, r8d; samDesired
0x14007e7a9  mov     rdx, rdi; lpSubKey
0x14007e7ac  call    cs:__imp_RegDeleteKeyExW
0x14007e7b2  mov     ebx, eax
0x14007e7b4  test    eax, eax
0x14007e7b6  jz      short loc_14007E7EC
0x14007e7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e7bf  cmp     rcx, rbp
0x14007e7c2  jz      short loc_14007E7EC
0x14007e7c4  test    byte ptr [rcx+1Ch], 2
0x14007e7c8  jz      short loc_14007E7EC
0x14007e7ca  cmp     byte ptr [rcx+19h], 2
0x14007e7ce  jb      short loc_14007E7EC
0x14007e7d0  mov     rcx, [rcx+10h]
0x14007e7d4  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007e7db  mov     edx, 77h ; 'w'
0x14007e7e0  mov     dword ptr [rsp+38h+phkResult], eax
0x14007e7e4  mov     r9, rdi
0x14007e7e7  call    WPP_SF_Sd
0x14007e7ec  mov     rcx, [rsp+38h+hKey]; hKey
0x14007e7f1  call    cs:__imp_RegCloseKey
0x14007e7f7  test    eax, eax
0x14007e7f9  jz      short loc_14007E82B
0x14007e7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e802  cmp     rcx, rbp
0x14007e805  jz      short loc_14007E82B
0x14007e807  test    byte ptr [rcx+1Ch], 2
0x14007e80b  jz      short loc_14007E82B
0x14007e80d  cmp     byte ptr [rcx+19h], 2
0x14007e811  jb      short loc_14007E82B
0x14007e813  mov     edx, 78h ; 'x'
0x14007e818  mov     r9d, eax
0x14007e81b  mov     rcx, [rcx+10h]
0x14007e81f  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007e826  call    WPP_SF_d
0x14007e82b  mov     rbp, [rsp+38h+arg_10]
0x14007e830  mov     eax, ebx
0x14007e832  mov     rbx, [rsp+38h+arg_0]
0x14007e837  add     rsp, 30h
0x14007e83b  pop     rdi
0x14007e83c  retn
```
