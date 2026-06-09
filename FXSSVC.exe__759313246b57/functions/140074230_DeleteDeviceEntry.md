# DeleteDeviceEntry

- ea: `0x140074230`
- end: `0x1400745dc`
- name: `DeleteDeviceEntry`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140082be8`
- `0x140083acc`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140074230`
- `0x1400745e4`
- `0x140074f18`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400744a2`
- `ADVAPI32!RegCloseKey` at `0x1400745a2`
- `ADVAPI32!RegCloseKey` at `0x1400744a2`
- `ADVAPI32!RegCloseKey` at `0x1400745a2`
- `ADVAPI32!RegDeleteValueW` at `0x1400743c2`
- `ADVAPI32!RegDeleteValueW` at `0x1400743c2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140074460`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140074460`
- `ADVAPI32!RegDeleteKeyW` at `0x140074564`
- `ADVAPI32!RegDeleteKeyW` at `0x140074564`
- `KERNEL32!GetLastError` at `0x140074333`
- `KERNEL32!GetLastError` at `0x1400744e8`
- `KERNEL32!GetLastError` at `0x140074333`
- `KERNEL32!GetLastError` at `0x1400744e8`

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
0x140074230  mov     [rsp-8+arg_8], rbx
0x140074235  mov     [rsp-8+arg_10], rsi
0x14007423a  push    rbp
0x14007423b  push    rdi
0x14007423c  push    r12
0x14007423e  push    r13
0x140074240  push    r14
0x140074242  lea     rbp, [rsp-190h]
0x14007424a  sub     rsp, 290h
0x140074251  mov     rax, cs:__security_cookie
0x140074258  xor     rax, rsp
0x14007425b  mov     [rbp+1B0h+var_30], rax
0x140074262  mov     ebx, ecx
0x140074264  mov     [rsp+2B0h+cbMaxValueLen], 0
0x14007426c  mov     rcx, cs:WPP_GLOBAL_Control
0x140074273  lea     r12, WPP_GLOBAL_Control
0x14007427a  lea     r13, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x140074281  mov     r14b, 2
0x140074284  cmp     rcx, r12
0x140074287  jz      short loc_1400742A6
0x140074289  test    [rcx+1Ch], r14b
0x14007428d  jz      short loc_1400742A6
0x14007428f  cmp     byte ptr [rcx+19h], 5
0x140074293  jb      short loc_1400742A6
0x140074295  mov     rcx, [rcx+10h]
0x140074299  mov     edx, 12h
0x14007429e  mov     r8, r13
0x1400742a1  call    WPP_SF_
0x1400742a6  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x1400742ad  mov     dword ptr [rsp+2B0h+lpcSubKeys], ebx
0x1400742b1  lea     r8, aS010lu; "%s\\%010lu"
0x1400742b8  mov     edx, 104h; unsigned __int64
0x1400742bd  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x1400742c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400742c7  mov     ebx, eax
0x1400742c9  test    eax, eax
0x1400742cb  jns     short loc_140074311
0x1400742cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400742d4  cmp     rcx, r12
0x1400742d7  jz      short loc_1400742F9
0x1400742d9  test    [rcx+1Ch], r14b
0x1400742dd  jz      short loc_1400742F9
0x1400742df  cmp     [rcx+19h], r14b
0x1400742e3  jb      short loc_1400742F9
0x1400742e5  mov     rcx, [rcx+10h]
0x1400742e9  mov     edx, 13h
0x1400742ee  mov     r9d, eax
0x1400742f1  mov     r8, r13
0x1400742f4  call    WPP_SF_d
0x1400742f9  mov     eax, ebx
0x1400742fb  and     eax, 1FFF0000h
0x140074300  cmp     eax, 70000h
0x140074305  jnz     short loc_14007430A
0x140074307  movzx   ebx, bx
0x14007430a  mov     eax, ebx
0x14007430c  jmp     loc_1400745B0
0x140074311  mov     r9d, 2001Fh
0x140074317  lea     rdx, [rsp+2B0h+var_240]
0x14007431c  xor     r8d, r8d
0x14007431f  mov     rcx, 0FFFFFFFF80000002h
0x140074326  call    OpenRegistryKey
0x14007432b  mov     rsi, rax
0x14007432e  test    rax, rax
0x140074331  jnz     short loc_14007437D
0x140074333  call    cs:__imp_GetLastError
0x14007433a  nop     dword ptr [rax+rax+00h]
0x14007433f  mov     edi, eax
0x140074341  mov     rcx, cs:WPP_GLOBAL_Control
0x140074348  cmp     rcx, r12
0x14007434b  jz      loc_1400745AE
0x140074351  test    [rcx+1Ch], r14b
0x140074355  jz      loc_1400745AE
0x14007435b  mov     bl, 3
0x14007435d  cmp     [rcx+19h], bl
0x140074360  jb      loc_1400745AE
0x140074366  mov     rcx, [rcx+10h]
0x14007436a  lea     edx, [rsi+14h]
0x14007436d  mov     r9d, eax
0x140074370  mov     r8, r13
0x140074373  call    WPP_SF_d
0x140074378  jmp     loc_1400745AE
0x14007437d  lea     rdx, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140074384  mov     rcx, rsi
0x140074387  call    DeleteRegistryKey
0x14007438c  mov     bl, 3
0x14007438e  test    eax, eax
0x140074390  jnz     short loc_1400743B8
0x140074392  mov     rcx, cs:WPP_GLOBAL_Control
0x140074399  cmp     rcx, r12
0x14007439c  jz      short loc_1400743B8
0x14007439e  test    [rcx+1Ch], r14b
0x1400743a2  jz      short loc_1400743B8
0x1400743a4  cmp     [rcx+19h], bl
0x1400743a7  jb      short loc_1400743B8
0x1400743a9  mov     rcx, [rcx+10h]
0x1400743ad  lea     edx, [rax+15h]
0x1400743b0  mov     r8, r13
0x1400743b3  call    WPP_SF_
0x1400743b8  lea     rdx, aPermanentLinei; "Permanent Lineid"
0x1400743bf  mov     rcx, rsi; hKey
0x1400743c2  call    cs:__imp_RegDeleteValueW
0x1400743c9  nop     dword ptr [rax+rax+00h]
0x1400743ce  test    eax, eax
0x1400743d0  jz      short loc_1400743FA
0x1400743d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400743d9  cmp     rcx, r12
0x1400743dc  jz      short loc_1400743FA
0x1400743de  test    [rcx+1Ch], r14b
0x1400743e2  jz      short loc_1400743FA
0x1400743e4  cmp     [rcx+19h], bl
0x1400743e7  jb      short loc_1400743FA
0x1400743e9  mov     rcx, [rcx+10h]
0x1400743ed  mov     edx, 16h
0x1400743f2  mov     r8, r13
0x1400743f5  call    WPP_SF_
0x1400743fa  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140074403  lea     rax, [rsp+2B0h+cbMaxValueLen]
0x140074408  mov     [rsp+2B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140074411  xor     r9d, r9d; lpReserved
0x140074414  mov     [rsp+2B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140074419  xor     r8d, r8d; lpcchClass
0x14007441c  mov     [rsp+2B0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140074425  lea     rax, [rsp+2B0h+cValues]
0x14007442a  mov     [rsp+2B0h+lpcValues], rax; lpcValues
0x14007442f  xor     edx, edx; lpClass
0x140074431  mov     [rsp+2B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14007443a  lea     rax, [rsp+2B0h+cSubKeys]
0x14007443f  mov     [rsp+2B0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x140074448  mov     rcx, rsi; hKey
0x14007444b  mov     [rsp+2B0h+lpcSubKeys], rax; lpcSubKeys
0x140074450  mov     [rsp+2B0h+cSubKeys], 0
0x140074458  mov     [rsp+2B0h+cValues], 0
0x140074460  call    cs:__imp_RegQueryInfoKeyW
0x140074467  nop     dword ptr [rax+rax+00h]
0x14007446c  mov     edi, eax
0x14007446e  test    eax, eax
0x140074470  jz      short loc_14007449F
0x140074472  mov     rcx, cs:WPP_GLOBAL_Control
0x140074479  cmp     rcx, r12
0x14007447c  jz      loc_14007459F
0x140074482  test    [rcx+1Ch], r14b
0x140074486  jz      loc_14007459F
0x14007448c  cmp     [rcx+19h], bl
0x14007448f  jb      loc_14007459F
0x140074495  mov     edx, 17h
0x14007449a  jmp     loc_140074593
0x14007449f  mov     rcx, rsi; hKey
0x1400744a2  call    cs:__imp_RegCloseKey
0x1400744a9  nop     dword ptr [rax+rax+00h]
0x1400744ae  cmp     [rsp+2B0h+cSubKeys], 0
0x1400744b3  jnz     loc_1400745AE
0x1400744b9  cmp     [rsp+2B0h+cValues], 0
0x1400744be  jnz     loc_1400745AE
0x1400744c4  mov     r9d, 30006h
0x1400744ca  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x1400744d1  xor     r8d, r8d
0x1400744d4  mov     rcx, 0FFFFFFFF80000002h
0x1400744db  call    OpenRegistryKey
0x1400744e0  mov     rsi, rax
0x1400744e3  test    rax, rax
0x1400744e6  jnz     short loc_140074531
0x1400744e8  call    cs:__imp_GetLastError
0x1400744ef  nop     dword ptr [rax+rax+00h]
0x1400744f4  mov     ebx, eax
0x1400744f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400744fd  cmp     rcx, r12
0x140074500  jz      loc_14007430A
0x140074506  test    [rcx+1Ch], r14b
0x14007450a  jz      loc_14007430A
0x140074510  cmp     [rcx+19h], r14b
0x140074514  jb      loc_14007430A
0x14007451a  mov     rcx, [rcx+10h]
0x14007451e  lea     edx, [rsi+18h]
0x140074521  mov     r9d, eax
0x140074524  mov     r8, r13
0x140074527  call    WPP_SF_d
0x14007452c  jmp     loc_14007430A
0x140074531  mov     rcx, cs:WPP_GLOBAL_Control
0x140074538  cmp     rcx, r12
0x14007453b  jz      short loc_14007455D
0x14007453d  test    [rcx+1Ch], r14b
0x140074541  jz      short loc_14007455D
0x140074543  cmp     [rcx+19h], bl
0x140074546  jb      short loc_14007455D
0x140074548  mov     rcx, [rcx+10h]
0x14007454c  lea     r9, [rbp+1B0h+SubKey]
0x140074550  mov     edx, 19h
0x140074555  mov     r8, r13
0x140074558  call    WPP_SF_S
0x14007455d  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x140074561  mov     rcx, rsi; hKey
0x140074564  call    cs:__imp_RegDeleteKeyW
0x14007456b  nop     dword ptr [rax+rax+00h]
0x140074570  mov     edi, eax
0x140074572  test    eax, eax
0x140074574  jz      short loc_14007459F
0x140074576  mov     rcx, cs:WPP_GLOBAL_Control
0x14007457d  cmp     rcx, r12
0x140074580  jz      short loc_14007459F
0x140074582  test    [rcx+1Ch], r14b
0x140074586  jz      short loc_14007459F
0x140074588  cmp     [rcx+19h], r14b
0x14007458c  jb      short loc_14007459F
0x14007458e  mov     edx, 1Ah
0x140074593  mov     rcx, [rcx+10h]
0x140074597  mov     r8, r13
0x14007459a  call    WPP_SF_
0x14007459f  mov     rcx, rsi; hKey
0x1400745a2  call    cs:__imp_RegCloseKey
0x1400745a9  nop     dword ptr [rax+rax+00h]
0x1400745ae  mov     eax, edi
0x1400745b0  mov     rcx, [rbp+1B0h+var_30]
0x1400745b7  xor     rcx, rsp; StackCookie
0x1400745ba  call    __security_check_cookie
0x1400745bf  lea     r11, [rsp+2B0h+var_20]
0x1400745c7  mov     rbx, [r11+38h]
0x1400745cb  mov     rsi, [r11+40h]
0x1400745cf  mov     rsp, r11
0x1400745d2  pop     r14
0x1400745d4  pop     r13
0x1400745d6  pop     r12
0x1400745d8  pop     rdi
0x1400745d9  pop     rbp
0x1400745da  retn
```
