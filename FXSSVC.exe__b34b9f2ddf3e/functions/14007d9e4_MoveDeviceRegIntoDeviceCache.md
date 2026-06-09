# MoveDeviceRegIntoDeviceCache

- ea: `0x14007d9e4`
- end: `0x14007de2a`
- name: `MoveDeviceRegIntoDeviceCache`
- size: `1094`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004be04`
- `0x14004c3cc`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x14006fc98`
- `0x140070220`
- `0x1400708c4`
- `0x1400709fc`
- `0x14007b150`
- `0x14007d9e4`
- `0x14007fa8c`
- `0x14007fbd8`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007dc15`
- `ADVAPI32!RegCloseKey` at `0x14007dc15`
- `KERNEL32!GetLastError` at `0x14007dc35`
- `KERNEL32!GetLastError` at `0x14007dc35`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14007ddbd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14007ddbd`

## string_xrefs

- `0x14007da70`: `Software\Microsoft\Fax\Devices Cache`
- `0x14007db7c`: `Software\Microsoft\Fax\Devices Cache`
- `0x14007dcab`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall MoveDeviceRegIntoDeviceCache(int a1, unsigned int a2, int a3)
{
  int v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  HKEY v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  HKEY v14; // rax
  HKEY v15; // rbx
  DWORD LastError; // eax
  unsigned int v17; // eax
  __int64 v18; // r8
  int v19; // eax
  HKEY v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // r8
  CMapDeviceId *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+20h] [rbp-E0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v32[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33[264]; // [rsp+250h] [rbp+150h] BYREF

  SystemTimeAsFileTime = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v6 = StringCchPrintfW(
         v32,
         0x104u,
         L"%s\\%08lx\\%s",
         L"Software\\Microsoft\\Fax\\Devices Cache",
         a2,
         L"{F10A5326-0261-4715-B367-2970427BBD99}");
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v8 = 133;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, (unsigned int)v6);
LABEL_11:
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v6;
    return (unsigned int)v6;
  }
  LODWORD(v27) = a1;
  v6 = StringCchPrintfW(
         v33,
         0x104u,
         L"%s\\%010lu\\%s",
         L"Software\\Microsoft\\Fax\\Devices",
         v27,
         L"{F10A5326-0261-4715-B367-2970427BBD99}");
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v8 = 134;
    goto LABEL_10;
  }
  v11 = FaxCopyRegSubkeys(v32, v10, v33);
  v6 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, v12, v11, a2);
    }
    return (unsigned int)v6;
  }
  LODWORD(v28) = a2;
  v13 = StringCchPrintfW(v32, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\Devices Cache", v28);
  if ( v13 >= 0 )
  {
    v14 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v32, 0, 0x20006u);
    v15 = v14;
    if ( v14 )
    {
      SetRegistryDword(v14, L"ManualAnswer", a3);
      RegCloseKey(v15);
    }
    else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        LastError,
        (__int64)v32);
    }
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      136,
      &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
      (unsigned int)v13);
  }
  v17 = DeleteDeviceEntry(a1);
  if ( v17
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, v18, v17, a2);
  }
  LODWORD(v29) = a2;
  v19 = StringCchPrintfW(v32, 0x104u, L"%s\\%08lx\\%s", L"Software\\Microsoft\\Fax\\Devices Cache", v29, L"TAPI Data");
  if ( v19 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v24 = 141;
    goto LABEL_55;
  }
  LODWORD(v30) = a2;
  v19 = StringCchPrintfW(v33, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\TAPIDevices", v30);
  if ( v19 >= 0 )
  {
    v21 = FaxCopyRegSubkeys(v32, v20, v33);
    if ( v21
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, v22, v21, a2);
    }
    goto LABEL_56;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = 140;
LABEL_55:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, (unsigned int)v19);
  }
LABEL_56:
  v25 = DeleteTapiEntry(a2);
  if ( v25
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, v26, v25, a2);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))UpdateLastDetectedTime)(a2, SystemTimeAsFileTime)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x14007d9e4  mov     [rsp-8+arg_18], rbx
0x14007d9e9  push    rbp
0x14007d9ea  push    rsi
0x14007d9eb  push    rdi
0x14007d9ec  push    r12
0x14007d9ee  push    r13
0x14007d9f0  push    r14
0x14007d9f2  push    r15
0x14007d9f4  lea     rbp, [rsp-370h]
0x14007d9fc  sub     rsp, 470h
0x14007da03  mov     rax, cs:__security_cookie
0x14007da0a  xor     rax, rsp
0x14007da0d  mov     [rbp+3A0h+var_40], rax
0x14007da14  mov     esi, r8d
0x14007da17  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14007da20  mov     edi, edx
0x14007da22  mov     r14d, ecx
0x14007da25  mov     rcx, cs:WPP_GLOBAL_Control
0x14007da2c  lea     r12, WPP_GLOBAL_Control
0x14007da33  lea     r13, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007da3a  mov     r15b, 2
0x14007da3d  cmp     rcx, r12
0x14007da40  jz      short loc_14007DA5F
0x14007da42  test    [rcx+1Ch], r15b
0x14007da46  jz      short loc_14007DA5F
0x14007da48  cmp     byte ptr [rcx+19h], 5
0x14007da4c  jb      short loc_14007DA5F
0x14007da4e  mov     rcx, [rcx+10h]
0x14007da52  mov     edx, 84h
0x14007da57  mov     r8, r13
0x14007da5a  call    WPP_SF_
0x14007da5f  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007da66  mov     edx, 104h; unsigned __int64
0x14007da6b  mov     [rsp+4A0h+var_478], rax
0x14007da70  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007da77  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x14007da7e  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007da82  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x14007da87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007da8c  mov     ebx, eax
0x14007da8e  test    eax, eax
0x14007da90  jns     short loc_14007DAD6
0x14007da92  mov     rcx, cs:WPP_GLOBAL_Control
0x14007da99  cmp     rcx, r12
0x14007da9c  jz      short loc_14007DABE
0x14007da9e  test    [rcx+1Ch], r15b
0x14007daa2  jz      short loc_14007DABE
0x14007daa4  cmp     [rcx+19h], r15b
0x14007daa8  jb      short loc_14007DABE
0x14007daaa  mov     edx, 85h
0x14007daaf  mov     rcx, [rcx+10h]
0x14007dab3  mov     r9d, ebx
0x14007dab6  mov     r8, r13
0x14007dab9  call    WPP_SF_d
0x14007dabe  mov     eax, ebx
0x14007dac0  and     eax, 1FFF0000h
0x14007dac5  cmp     eax, 70000h
0x14007daca  jnz     short loc_14007DACF
0x14007dacc  movzx   ebx, bx
0x14007dacf  mov     eax, ebx
0x14007dad1  jmp     loc_14007DE00
0x14007dad6  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007dadd  mov     edx, 104h; unsigned __int64
0x14007dae2  mov     [rsp+4A0h+var_478], rax
0x14007dae7  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007daee  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x14007daf5  mov     dword ptr [rsp+4A0h+var_480], r14d
0x14007dafa  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x14007db01  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007db06  mov     ebx, eax
0x14007db08  test    eax, eax
0x14007db0a  jns     short loc_14007DB2B
0x14007db0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007db13  cmp     rcx, r12
0x14007db16  jz      short loc_14007DABE
0x14007db18  test    [rcx+1Ch], r15b
0x14007db1c  jz      short loc_14007DABE
0x14007db1e  cmp     [rcx+19h], r15b
0x14007db22  jb      short loc_14007DABE
0x14007db24  mov     edx, 86h
0x14007db29  jmp     short loc_14007DAAF
0x14007db2b  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x14007db32  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x14007db37  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x14007db3c  mov     ebx, eax
0x14007db3e  test    eax, eax
0x14007db40  jz      short loc_14007DB7C
0x14007db42  mov     rcx, cs:WPP_GLOBAL_Control
0x14007db49  cmp     rcx, r12
0x14007db4c  jz      short loc_14007DACF
0x14007db4e  test    [rcx+1Ch], r15b
0x14007db52  jz      loc_14007DACF
0x14007db58  cmp     [rcx+19h], r15b
0x14007db5c  jb      loc_14007DACF
0x14007db62  mov     rcx, [rcx+10h]
0x14007db66  mov     edx, 87h
0x14007db6b  mov     r9d, eax
0x14007db6e  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007db72  call    WPP_SF_lL
0x14007db77  jmp     loc_14007DACF
0x14007db7c  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007db83  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007db87  lea     r8, aS08lx; "%s\\%08lx"
0x14007db8e  mov     edx, 104h; unsigned __int64
0x14007db93  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x14007db98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007db9d  test    eax, eax
0x14007db9f  jns     short loc_14007DBDE
0x14007dba1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dba8  cmp     rcx, r12
0x14007dbab  jz      loc_14007DC60
0x14007dbb1  test    [rcx+1Ch], r15b
0x14007dbb5  jz      loc_14007DC60
0x14007dbbb  cmp     [rcx+19h], r15b
0x14007dbbf  jb      loc_14007DC60
0x14007dbc5  mov     rcx, [rcx+10h]
0x14007dbc9  mov     edx, 88h
0x14007dbce  mov     r9d, eax
0x14007dbd1  mov     r8, r13
0x14007dbd4  call    WPP_SF_d
0x14007dbd9  jmp     loc_14007DC60
0x14007dbde  mov     r9d, 20006h
0x14007dbe4  lea     rdx, [rsp+4A0h+var_460]
0x14007dbe9  xor     r8d, r8d
0x14007dbec  mov     rcx, 0FFFFFFFF80000002h
0x14007dbf3  call    OpenRegistryKey
0x14007dbf8  mov     rbx, rax
0x14007dbfb  test    rax, rax
0x14007dbfe  jz      short loc_14007DC1D
0x14007dc00  mov     r8d, esi
0x14007dc03  lea     rdx, aManualanswer; "ManualAnswer"
0x14007dc0a  mov     rcx, rax
0x14007dc0d  call    SetRegistryDword
0x14007dc12  mov     rcx, rbx; hKey
0x14007dc15  call    cs:__imp_RegCloseKey
0x14007dc1b  jmp     short loc_14007DC60
0x14007dc1d  mov     rax, cs:WPP_GLOBAL_Control
0x14007dc24  cmp     rax, r12
0x14007dc27  jz      short loc_14007DC60
0x14007dc29  test    [rax+1Ch], r15b
0x14007dc2d  jz      short loc_14007DC60
0x14007dc2f  cmp     [rax+19h], r15b
0x14007dc33  jb      short loc_14007DC60
0x14007dc35  call    cs:__imp_GetLastError
0x14007dc3b  lea     rcx, [rsp+4A0h+var_460]
0x14007dc40  mov     edx, 89h
0x14007dc45  mov     [rsp+4A0h+var_480], rcx
0x14007dc4a  mov     r9d, eax
0x14007dc4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dc54  mov     r8, r13
0x14007dc57  mov     rcx, [rcx+10h]
0x14007dc5b  call    WPP_SF_DS
0x14007dc60  mov     ecx, r14d
0x14007dc63  call    DeleteDeviceEntry
0x14007dc68  mov     bl, 3
0x14007dc6a  test    eax, eax
0x14007dc6c  jz      short loc_14007DC9A
0x14007dc6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dc75  cmp     rcx, r12
0x14007dc78  jz      short loc_14007DC9A
0x14007dc7a  test    [rcx+1Ch], r15b
0x14007dc7e  jz      short loc_14007DC9A
0x14007dc80  cmp     [rcx+19h], bl
0x14007dc83  jb      short loc_14007DC9A
0x14007dc85  mov     rcx, [rcx+10h]
0x14007dc89  mov     edx, 8Ah
0x14007dc8e  mov     r9d, eax
0x14007dc91  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007dc95  call    WPP_SF_lL
0x14007dc9a  lea     rax, aTapiData; "TAPI Data"
0x14007dca1  mov     esi, 104h
0x14007dca6  mov     [rsp+4A0h+var_478], rax
0x14007dcab  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007dcb2  mov     edx, esi; unsigned __int64
0x14007dcb4  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007dcb8  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x14007dcbf  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x14007dcc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007dcc9  test    eax, eax
0x14007dccb  js      loc_14007DD55
0x14007dcd1  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x14007dcd8  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007dcdc  lea     r8, aS08lx; "%s\\%08lx"
0x14007dce3  mov     edx, esi; unsigned __int64
0x14007dce5  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x14007dcec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007dcf1  test    eax, eax
0x14007dcf3  js      short loc_14007DD36
0x14007dcf5  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x14007dcfc  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x14007dd01  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x14007dd06  test    eax, eax
0x14007dd08  jz      short loc_14007DD81
0x14007dd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd11  cmp     rcx, r12
0x14007dd14  jz      short loc_14007DD81
0x14007dd16  test    [rcx+1Ch], r15b
0x14007dd1a  jz      short loc_14007DD81
0x14007dd1c  cmp     [rcx+19h], bl
0x14007dd1f  jb      short loc_14007DD81
0x14007dd21  mov     rcx, [rcx+10h]
0x14007dd25  lea     edx, [rsi-79h]
0x14007dd28  mov     r9d, eax
0x14007dd2b  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007dd2f  call    WPP_SF_lL
0x14007dd34  jmp     short loc_14007DD81
0x14007dd36  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd3d  cmp     rcx, r12
0x14007dd40  jz      short loc_14007DD81
0x14007dd42  test    [rcx+1Ch], r15b
0x14007dd46  jz      short loc_14007DD81
0x14007dd48  cmp     [rcx+19h], r15b
0x14007dd4c  jb      short loc_14007DD81
0x14007dd4e  mov     edx, 8Ch
0x14007dd53  jmp     short loc_14007DD72
0x14007dd55  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd5c  cmp     rcx, r12
0x14007dd5f  jz      short loc_14007DD81
0x14007dd61  test    [rcx+1Ch], r15b
0x14007dd65  jz      short loc_14007DD81
0x14007dd67  cmp     [rcx+19h], r15b
0x14007dd6b  jb      short loc_14007DD81
0x14007dd6d  mov     edx, 8Dh
0x14007dd72  mov     rcx, [rcx+10h]
0x14007dd76  mov     r9d, eax
0x14007dd79  mov     r8, r13
0x14007dd7c  call    WPP_SF_d
0x14007dd81  mov     ecx, edi
0x14007dd83  call    DeleteTapiEntry
0x14007dd88  test    eax, eax
0x14007dd8a  jz      short loc_14007DDB8
0x14007dd8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd93  cmp     rcx, r12
0x14007dd96  jz      short loc_14007DDB8
0x14007dd98  test    [rcx+1Ch], r15b
0x14007dd9c  jz      short loc_14007DDB8
0x14007dd9e  cmp     [rcx+19h], bl
0x14007dda1  jb      short loc_14007DDB8
0x14007dda3  mov     rcx, [rcx+10h]
0x14007dda7  mov     edx, 8Eh
0x14007ddac  mov     r9d, eax
0x14007ddaf  mov     dword ptr [rsp+4A0h+var_480], edi
0x14007ddb3  call    WPP_SF_lL
0x14007ddb8  lea     rcx, [rsp+4A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14007ddbd  call    cs:__imp_GetSystemTimeAsFileTime
0x14007ddc3  mov     rdx, qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime]
0x14007ddc8  mov     ecx, edi
0x14007ddca  call    UpdateLastDetectedTime
0x14007ddcf  test    eax, eax
0x14007ddd1  jnz     short loc_14007DDFE
0x14007ddd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ddda  cmp     rcx, r12
0x14007dddd  jz      short loc_14007DDFE
0x14007dddf  test    [rcx+1Ch], r15b
0x14007dde3  jz      short loc_14007DDFE
0x14007dde5  cmp     [rcx+19h], bl
0x14007dde8  jb      short loc_14007DDFE
0x14007ddea  mov     rcx, [rcx+10h]
0x14007ddee  mov     edx, 8Fh
0x14007ddf3  mov     r9d, edi
0x14007ddf6  mov     r8, r13
0x14007ddf9  call    WPP_SF_d
0x14007ddfe  xor     eax, eax
0x14007de00  mov     rcx, [rbp+3A0h+var_40]
0x14007de07  xor     rcx, rsp; StackCookie
0x14007de0a  call    __security_check_cookie
0x14007de0f  mov     rbx, [rsp+4A0h+arg_18]
0x14007de17  add     rsp, 470h
0x14007de1e  pop     r15
0x14007de20  pop     r14
0x14007de22  pop     r13
0x14007de24  pop     r12
0x14007de26  pop     rdi
0x14007de27  pop     rsi
0x14007de28  pop     rbp
0x14007de29  retn
```
