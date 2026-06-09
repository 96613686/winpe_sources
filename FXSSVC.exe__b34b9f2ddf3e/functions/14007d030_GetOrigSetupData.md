# GetOrigSetupData

- ea: `0x14007d030`
- end: `0x14007d2c9`
- name: `GetOrigSetupData`
- size: `665`
- prototype: `__int64 __fastcall(DWORD cbData)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400492fc`
- `0x14004a434`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140067168`
- `0x14006f808`
- `0x140070684`
- `0x1400708c4`
- `0x14007d030`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007d24a`
- `ADVAPI32!RegCloseKey` at `0x14007d24a`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007d263`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007d263`
- `KERNEL32!GetLastError` at `0x14007d17e`
- `KERNEL32!GetLastError` at `0x14007d17e`
- `KERNEL32!SetLastError` at `0x14007d10d`
- `KERNEL32!SetLastError` at `0x14007d10d`

## pseudocode

```c
__int64 __fastcall GetOrigSetupData(DWORD cbData, __int64 a2)
{
  int v4; // eax
  DWORD v5; // ebx
  int v7; // edi
  HKEY v8; // rbx
  DWORD LastError; // eax
  int RegistryDwordDefault; // eax
  int v11; // eax
  unsigned int v12; // eax
  DWORD cbDataa; // [rsp+20h] [rbp-248h]
  DWORD cbDatab; // [rsp+20h] [rbp-248h]
  BYTE Data[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[256]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, sizeof(SubKey));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v4 = StringCchPrintfW(SubKey, 0x100u, L"%s\\%010d", L"Software\\Microsoft\\Fax\\Setup\\Original Setup Data", cbData);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v4);
    }
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v5 = (unsigned __int16)v5;
    SetLastError(v5);
    return 0;
  }
  v7 = 1;
  v8 = OpenRegistryKey(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u);
  if ( !v8 )
  {
    v7 = 0;
    v8 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Setup\\Original Setup Data", 0, 0x20019u);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
      return 0;
    }
  }
  *(_QWORD *)(a2 + 16) = StringDup((unsigned __int16 *)&Class);
  *(_QWORD *)a2 = GetRegistryStringValue(v8, 1u, L"CSID", L"Fax", cbDataa);
  *(_QWORD *)(a2 + 8) = GetRegistryStringValue(v8, 1u, L"TSID", L"Fax", cbDatab);
  *(_DWORD *)Data = 0;
  RegistryDwordDefault = GetRegistryDwordDefault(v8, L"Rings", Data, 0);
  *(_DWORD *)(a2 + 24) = RegistryDwordDefault != 0 ? *(_DWORD *)Data : 0;
  *(_DWORD *)Data = 0;
  v11 = GetRegistryDwordDefault(v8, L"Flags", Data, 0);
  *(_DWORD *)(a2 + 28) = v11 != 0 ? *(_DWORD *)Data : 0;
  RegCloseKey(v8);
  if ( v7 == 1 )
  {
    v12 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v12);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14007d030  mov     [rsp+arg_10], rbx
0x14007d035  mov     [rsp+arg_18], rsi
0x14007d03a  push    rdi
0x14007d03b  push    r12
0x14007d03d  push    r14
0x14007d03f  sub     rsp, 250h
0x14007d046  mov     rax, cs:__security_cookie
0x14007d04d  xor     rax, rsp
0x14007d050  mov     [rsp+268h+var_28], rax
0x14007d058  mov     rsi, rdx
0x14007d05b  mov     ebx, ecx
0x14007d05d  xor     edx, edx; Val
0x14007d05f  lea     rcx, [rsp+268h+SubKey]; void *
0x14007d064  mov     r8d, 200h; Size
0x14007d06a  call    memset_0
0x14007d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d076  lea     r14, WPP_GLOBAL_Control
0x14007d07d  cmp     rcx, r14
0x14007d080  jz      short loc_14007D0A3
0x14007d082  test    byte ptr [rcx+1Ch], 2
0x14007d086  jz      short loc_14007D0A3
0x14007d088  cmp     byte ptr [rcx+19h], 5
0x14007d08c  jb      short loc_14007D0A3
0x14007d08e  mov     rcx, [rcx+10h]
0x14007d092  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007d099  mov     edx, 24h ; '$'
0x14007d09e  call    WPP_SF_
0x14007d0a3  lea     r9, aSoftwareMicros_6; "Software\\Microsoft\\Fax\\Setup\\Origin"...
0x14007d0aa  mov     [rsp+268h+cbData], ebx; cbData
0x14007d0ae  lea     r8, aS010d; "%s\\%010d"
0x14007d0b5  mov     edx, 100h; unsigned __int64
0x14007d0ba  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x14007d0bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007d0c4  mov     ebx, eax
0x14007d0c6  test    eax, eax
0x14007d0c8  jns     short loc_14007D11A
0x14007d0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d0d1  cmp     rcx, r14
0x14007d0d4  jz      short loc_14007D0FA
0x14007d0d6  test    byte ptr [rcx+1Ch], 2
0x14007d0da  jz      short loc_14007D0FA
0x14007d0dc  cmp     byte ptr [rcx+19h], 2
0x14007d0e0  jb      short loc_14007D0FA
0x14007d0e2  mov     rcx, [rcx+10h]
0x14007d0e6  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007d0ed  mov     edx, 25h ; '%'
0x14007d0f2  mov     r9d, eax
0x14007d0f5  call    WPP_SF_d
0x14007d0fa  mov     eax, ebx
0x14007d0fc  and     eax, 1FFF0000h
0x14007d101  cmp     eax, 70000h
0x14007d106  jnz     short loc_14007D10B
0x14007d108  movzx   ebx, bx
0x14007d10b  mov     ecx, ebx; dwErrCode
0x14007d10d  call    cs:__imp_SetLastError
0x14007d113  xor     eax, eax
0x14007d115  jmp     loc_14007D2A0
0x14007d11a  mov     r12, 0FFFFFFFF80000002h
0x14007d121  lea     rdx, [rsp+268h+SubKey]
0x14007d126  mov     rcx, r12
0x14007d129  mov     r9d, 20019h
0x14007d12f  xor     r8d, r8d
0x14007d132  mov     edi, 1
0x14007d137  call    OpenRegistryKey
0x14007d13c  mov     rbx, rax
0x14007d13f  test    rax, rax
0x14007d142  jnz     short loc_14007D1A6
0x14007d144  mov     r9d, 20019h
0x14007d14a  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Fax\\Setup\\Origin"...
0x14007d151  xor     r8d, r8d
0x14007d154  mov     rcx, r12
0x14007d157  xor     edi, edi
0x14007d159  call    OpenRegistryKey
0x14007d15e  mov     rbx, rax
0x14007d161  test    rax, rax
0x14007d164  jnz     short loc_14007D1A6
0x14007d166  mov     rax, cs:WPP_GLOBAL_Control
0x14007d16d  cmp     rax, r14
0x14007d170  jz      short loc_14007D113
0x14007d172  test    byte ptr [rax+1Ch], 2
0x14007d176  jz      short loc_14007D113
0x14007d178  cmp     byte ptr [rax+19h], 2
0x14007d17c  jb      short loc_14007D113
0x14007d17e  call    cs:__imp_GetLastError
0x14007d184  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d18b  lea     edx, [rdi+26h]
0x14007d18e  mov     r9d, eax
0x14007d191  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007d198  mov     rcx, [rcx+10h]
0x14007d19c  call    WPP_SF_d
0x14007d1a1  jmp     loc_14007D113
0x14007d1a6  lea     rcx, Class; unsigned __int16 *
0x14007d1ad  call    StringDup
0x14007d1b2  lea     r9, SubsystemName; "Fax"
0x14007d1b9  mov     [rsi+10h], rax
0x14007d1bd  lea     r8, aCsid; "CSID"
0x14007d1c4  mov     edx, 1; dwType
0x14007d1c9  mov     rcx, rbx; hKey
0x14007d1cc  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007d1d1  lea     r9, SubsystemName; "Fax"
0x14007d1d8  mov     [rsi], rax
0x14007d1db  lea     r8, aTsid; "TSID"
0x14007d1e2  mov     edx, 1; dwType
0x14007d1e7  mov     rcx, rbx; hKey
0x14007d1ea  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007d1ef  xor     r9d, r9d
0x14007d1f2  mov     [rsi+8], rax
0x14007d1f6  lea     r8, [rsp+268h+Data]; lpData
0x14007d1fb  mov     dword ptr [rsp+268h+Data], 0
0x14007d203  lea     rdx, aRings; "Rings"
0x14007d20a  mov     rcx, rbx; hKey
0x14007d20d  call    GetRegistryDwordDefault
0x14007d212  neg     eax
0x14007d214  lea     r8, [rsp+268h+Data]; lpData
0x14007d219  lea     rdx, aFlags; "Flags"
0x14007d220  sbb     ecx, ecx
0x14007d222  xor     r9d, r9d
0x14007d225  and     ecx, dword ptr [rsp+268h+Data]
0x14007d229  mov     [rsi+18h], ecx
0x14007d22c  mov     rcx, rbx; hKey
0x14007d22f  mov     dword ptr [rsp+268h+Data], 0
0x14007d237  call    GetRegistryDwordDefault
0x14007d23c  neg     eax
0x14007d23e  mov     rcx, rbx; hKey
0x14007d241  sbb     edx, edx
0x14007d243  and     edx, dword ptr [rsp+268h+Data]
0x14007d247  mov     [rsi+1Ch], edx
0x14007d24a  call    cs:__imp_RegCloseKey
0x14007d250  cmp     edi, 1
0x14007d253  jnz     short loc_14007D29B
0x14007d255  xor     r9d, r9d; Reserved
0x14007d258  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x14007d25d  xor     r8d, r8d; samDesired
0x14007d260  mov     rcx, r12; hKey
0x14007d263  call    cs:__imp_RegDeleteKeyExW
0x14007d269  test    eax, eax
0x14007d26b  jz      short loc_14007D29B
0x14007d26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d274  cmp     rcx, r14
0x14007d277  jz      short loc_14007D29B
0x14007d279  test    byte ptr [rcx+1Ch], 2
0x14007d27d  jz      short loc_14007D29B
0x14007d27f  cmp     byte ptr [rcx+19h], 2
0x14007d283  jb      short loc_14007D29B
0x14007d285  mov     rcx, [rcx+10h]
0x14007d289  lea     edx, [rdi+26h]
0x14007d28c  mov     r9d, eax
0x14007d28f  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007d296  call    WPP_SF_d
0x14007d29b  mov     eax, 1
0x14007d2a0  mov     rcx, [rsp+268h+var_28]
0x14007d2a8  xor     rcx, rsp; StackCookie
0x14007d2ab  call    __security_check_cookie
0x14007d2b0  lea     r11, [rsp+268h+var_18]
0x14007d2b8  mov     rbx, [r11+30h]
0x14007d2bc  mov     rsi, [r11+38h]
0x14007d2c0  mov     rsp, r11
0x14007d2c3  pop     r14
0x14007d2c5  pop     r12
0x14007d2c7  pop     rdi
0x14007d2c8  retn
```
