# DeleteDeviceEntry

- ea: `0x14006fc98`
- end: `0x140070019`
- name: `DeleteDeviceEntry`
- size: `897`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007d9e4`
- `0x14007e844`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x14006fc98`
- `0x140070020`
- `0x1400708c4`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006fef8`
- `ADVAPI32!RegCloseKey` at `0x14006ffe6`
- `ADVAPI32!RegCloseKey` at `0x14006fef8`
- `ADVAPI32!RegCloseKey` at `0x14006ffe6`
- `ADVAPI32!RegDeleteValueW` at `0x14006fe24`
- `ADVAPI32!RegDeleteValueW` at `0x14006fe24`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14006febc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14006febc`
- `ADVAPI32!RegDeleteKeyW` at `0x14006ffae`
- `ADVAPI32!RegDeleteKeyW` at `0x14006ffae`
- `KERNEL32!GetLastError` at `0x14006fd9b`
- `KERNEL32!GetLastError` at `0x14006ff38`
- `KERNEL32!GetLastError` at `0x14006fd9b`
- `KERNEL32!GetLastError` at `0x14006ff38`

## pseudocode

```c
__int64 __fastcall DeleteDeviceEntry(int a1)
{
  int v2; // eax
  DWORD v3; // ebx
  HKEY v5; // rax
  HKEY v6; // rsi
  DWORD LastError; // eax
  unsigned int v8; // edi
  CMapDeviceId *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v15[31]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[233]; // [rsp+AEh] [rbp-52h] BYREF

  cbMaxValueLen = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v2 = StringCchPrintfW(v15, 0x104u, L"%s\\%010lu", L"Software\\Microsoft\\Fax\\Devices", a1);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids,
        (unsigned int)v2);
    }
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v3;
    return v3;
  }
  v5 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v15, 0, 0x2001Fu);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, LastError);
    }
    return v8;
  }
  if ( !(unsigned int)DeleteRegistryKey(v5, L"{F10A5326-0261-4715-B367-2970427BBD99}")
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  if ( RegDeleteValueW(v6, L"Permanent Lineid")
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  cSubKeys = 0;
  cValues = 0;
  v8 = RegQueryInfoKeyW(v6, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_50;
    }
    v10 = 23;
    goto LABEL_49;
  }
  RegCloseKey(v6);
  if ( cSubKeys || cValues )
    return v8;
  v6 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Devices", 0, 0x30006u);
  if ( !v6 )
  {
    v11 = GetLastError();
    v3 = v11;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, v11);
    }
    return v3;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, SubKey);
  }
  v8 = RegDeleteKeyW(v6, SubKey);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 26;
LABEL_49:
      WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
    }
  }
LABEL_50:
  RegCloseKey(v6);
  return v8;
}

```

## disassembly

```asm
0x14006fc98  mov     [rsp-8+arg_8], rbx
0x14006fc9d  mov     [rsp-8+arg_10], rsi
0x14006fca2  push    rbp
0x14006fca3  push    rdi
0x14006fca4  push    r12
0x14006fca6  push    r13
0x14006fca8  push    r14
0x14006fcaa  lea     rbp, [rsp-190h]
0x14006fcb2  sub     rsp, 290h
0x14006fcb9  mov     rax, cs:__security_cookie
0x14006fcc0  xor     rax, rsp
0x14006fcc3  mov     [rbp+1B0h+var_30], rax
0x14006fcca  mov     ebx, ecx
0x14006fccc  mov     [rsp+2B0h+cbMaxValueLen], 0
0x14006fcd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fcdb  lea     r12, WPP_GLOBAL_Control
0x14006fce2  lea     r13, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14006fce9  mov     r14b, 2
0x14006fcec  cmp     rcx, r12
0x14006fcef  jz      short loc_14006FD0E
0x14006fcf1  test    [rcx+1Ch], r14b
0x14006fcf5  jz      short loc_14006FD0E
0x14006fcf7  cmp     byte ptr [rcx+19h], 5
0x14006fcfb  jb      short loc_14006FD0E
0x14006fcfd  mov     rcx, [rcx+10h]
0x14006fd01  mov     edx, 12h
0x14006fd06  mov     r8, r13
0x14006fd09  call    WPP_SF_
0x14006fd0e  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14006fd15  mov     dword ptr [rsp+2B0h+lpcSubKeys], ebx
0x14006fd19  lea     r8, aS010lu; "%s\\%010lu"
0x14006fd20  mov     edx, 104h; unsigned __int64
0x14006fd25  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x14006fd2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006fd2f  mov     ebx, eax
0x14006fd31  test    eax, eax
0x14006fd33  jns     short loc_14006FD79
0x14006fd35  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fd3c  cmp     rcx, r12
0x14006fd3f  jz      short loc_14006FD61
0x14006fd41  test    [rcx+1Ch], r14b
0x14006fd45  jz      short loc_14006FD61
0x14006fd47  cmp     [rcx+19h], r14b
0x14006fd4b  jb      short loc_14006FD61
0x14006fd4d  mov     rcx, [rcx+10h]
0x14006fd51  mov     edx, 13h
0x14006fd56  mov     r9d, eax
0x14006fd59  mov     r8, r13
0x14006fd5c  call    WPP_SF_d
0x14006fd61  mov     eax, ebx
0x14006fd63  and     eax, 1FFF0000h
0x14006fd68  cmp     eax, 70000h
0x14006fd6d  jnz     short loc_14006FD72
0x14006fd6f  movzx   ebx, bx
0x14006fd72  mov     eax, ebx
0x14006fd74  jmp     loc_14006FFEE
0x14006fd79  mov     r9d, 2001Fh
0x14006fd7f  lea     rdx, [rsp+2B0h+var_240]
0x14006fd84  xor     r8d, r8d
0x14006fd87  mov     rcx, 0FFFFFFFF80000002h
0x14006fd8e  call    OpenRegistryKey
0x14006fd93  mov     rsi, rax
0x14006fd96  test    rax, rax
0x14006fd99  jnz     short loc_14006FDDF
0x14006fd9b  call    cs:__imp_GetLastError
0x14006fda1  mov     edi, eax
0x14006fda3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fdaa  cmp     rcx, r12
0x14006fdad  jz      loc_14006FFEC
0x14006fdb3  test    [rcx+1Ch], r14b
0x14006fdb7  jz      loc_14006FFEC
0x14006fdbd  mov     bl, 3
0x14006fdbf  cmp     [rcx+19h], bl
0x14006fdc2  jb      loc_14006FFEC
0x14006fdc8  mov     rcx, [rcx+10h]
0x14006fdcc  lea     edx, [rsi+14h]
0x14006fdcf  mov     r9d, eax
0x14006fdd2  mov     r8, r13
0x14006fdd5  call    WPP_SF_d
0x14006fdda  jmp     loc_14006FFEC
0x14006fddf  lea     rdx, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14006fde6  mov     rcx, rsi
0x14006fde9  call    DeleteRegistryKey
0x14006fdee  mov     bl, 3
0x14006fdf0  test    eax, eax
0x14006fdf2  jnz     short loc_14006FE1A
0x14006fdf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fdfb  cmp     rcx, r12
0x14006fdfe  jz      short loc_14006FE1A
0x14006fe00  test    [rcx+1Ch], r14b
0x14006fe04  jz      short loc_14006FE1A
0x14006fe06  cmp     [rcx+19h], bl
0x14006fe09  jb      short loc_14006FE1A
0x14006fe0b  mov     rcx, [rcx+10h]
0x14006fe0f  lea     edx, [rax+15h]
0x14006fe12  mov     r8, r13
0x14006fe15  call    WPP_SF_
0x14006fe1a  lea     rdx, aPermanentLinei; "Permanent Lineid"
0x14006fe21  mov     rcx, rsi; hKey
0x14006fe24  call    cs:__imp_RegDeleteValueW
0x14006fe2a  test    eax, eax
0x14006fe2c  jz      short loc_14006FE56
0x14006fe2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fe35  cmp     rcx, r12
0x14006fe38  jz      short loc_14006FE56
0x14006fe3a  test    [rcx+1Ch], r14b
0x14006fe3e  jz      short loc_14006FE56
0x14006fe40  cmp     [rcx+19h], bl
0x14006fe43  jb      short loc_14006FE56
0x14006fe45  mov     rcx, [rcx+10h]
0x14006fe49  mov     edx, 16h
0x14006fe4e  mov     r8, r13
0x14006fe51  call    WPP_SF_
0x14006fe56  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14006fe5f  lea     rax, [rsp+2B0h+cbMaxValueLen]
0x14006fe64  mov     [rsp+2B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x14006fe6d  xor     r9d, r9d; lpReserved
0x14006fe70  mov     [rsp+2B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14006fe75  xor     r8d, r8d; lpcchClass
0x14006fe78  mov     [rsp+2B0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x14006fe81  lea     rax, [rsp+2B0h+cValues]
0x14006fe86  mov     [rsp+2B0h+lpcValues], rax; lpcValues
0x14006fe8b  xor     edx, edx; lpClass
0x14006fe8d  mov     [rsp+2B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14006fe96  lea     rax, [rsp+2B0h+cSubKeys]
0x14006fe9b  mov     [rsp+2B0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x14006fea4  mov     rcx, rsi; hKey
0x14006fea7  mov     [rsp+2B0h+lpcSubKeys], rax; lpcSubKeys
0x14006feac  mov     [rsp+2B0h+cSubKeys], 0
0x14006feb4  mov     [rsp+2B0h+cValues], 0
0x14006febc  call    cs:__imp_RegQueryInfoKeyW
0x14006fec2  mov     edi, eax
0x14006fec4  test    eax, eax
0x14006fec6  jz      short loc_14006FEF5
0x14006fec8  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fecf  cmp     rcx, r12
0x14006fed2  jz      loc_14006FFE3
0x14006fed8  test    [rcx+1Ch], r14b
0x14006fedc  jz      loc_14006FFE3
0x14006fee2  cmp     [rcx+19h], bl
0x14006fee5  jb      loc_14006FFE3
0x14006feeb  mov     edx, 17h
0x14006fef0  jmp     loc_14006FFD7
0x14006fef5  mov     rcx, rsi; hKey
0x14006fef8  call    cs:__imp_RegCloseKey
0x14006fefe  cmp     [rsp+2B0h+cSubKeys], 0
0x14006ff03  jnz     loc_14006FFEC
0x14006ff09  cmp     [rsp+2B0h+cValues], 0
0x14006ff0e  jnz     loc_14006FFEC
0x14006ff14  mov     r9d, 30006h
0x14006ff1a  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14006ff21  xor     r8d, r8d
0x14006ff24  mov     rcx, 0FFFFFFFF80000002h
0x14006ff2b  call    OpenRegistryKey
0x14006ff30  mov     rsi, rax
0x14006ff33  test    rax, rax
0x14006ff36  jnz     short loc_14006FF7B
0x14006ff38  call    cs:__imp_GetLastError
0x14006ff3e  mov     ebx, eax
0x14006ff40  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ff47  cmp     rcx, r12
0x14006ff4a  jz      loc_14006FD72
0x14006ff50  test    [rcx+1Ch], r14b
0x14006ff54  jz      loc_14006FD72
0x14006ff5a  cmp     [rcx+19h], r14b
0x14006ff5e  jb      loc_14006FD72
0x14006ff64  mov     rcx, [rcx+10h]
0x14006ff68  lea     edx, [rsi+18h]
0x14006ff6b  mov     r9d, eax
0x14006ff6e  mov     r8, r13
0x14006ff71  call    WPP_SF_d
0x14006ff76  jmp     loc_14006FD72
0x14006ff7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ff82  cmp     rcx, r12
0x14006ff85  jz      short loc_14006FFA7
0x14006ff87  test    [rcx+1Ch], r14b
0x14006ff8b  jz      short loc_14006FFA7
0x14006ff8d  cmp     [rcx+19h], bl
0x14006ff90  jb      short loc_14006FFA7
0x14006ff92  mov     rcx, [rcx+10h]
0x14006ff96  lea     r9, [rbp+1B0h+SubKey]
0x14006ff9a  mov     edx, 19h
0x14006ff9f  mov     r8, r13
0x14006ffa2  call    WPP_SF_S
0x14006ffa7  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x14006ffab  mov     rcx, rsi; hKey
0x14006ffae  call    cs:__imp_RegDeleteKeyW
0x14006ffb4  mov     edi, eax
0x14006ffb6  test    eax, eax
0x14006ffb8  jz      short loc_14006FFE3
0x14006ffba  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ffc1  cmp     rcx, r12
0x14006ffc4  jz      short loc_14006FFE3
0x14006ffc6  test    [rcx+1Ch], r14b
0x14006ffca  jz      short loc_14006FFE3
0x14006ffcc  cmp     [rcx+19h], r14b
0x14006ffd0  jb      short loc_14006FFE3
0x14006ffd2  mov     edx, 1Ah
0x14006ffd7  mov     rcx, [rcx+10h]
0x14006ffdb  mov     r8, r13
0x14006ffde  call    WPP_SF_
0x14006ffe3  mov     rcx, rsi; hKey
0x14006ffe6  call    cs:__imp_RegCloseKey
0x14006ffec  mov     eax, edi
0x14006ffee  mov     rcx, [rbp+1B0h+var_30]
0x14006fff5  xor     rcx, rsp; StackCookie
0x14006fff8  call    __security_check_cookie
0x14006fffd  lea     r11, [rsp+2B0h+var_20]
0x140070005  mov     rbx, [r11+38h]
0x140070009  mov     rsi, [r11+40h]
0x14007000d  mov     rsp, r11
0x140070010  pop     r14
0x140070012  pop     r13
0x140070014  pop     r12
0x140070016  pop     rdi
0x140070017  pop     rbp
0x140070018  retn
```
