# MoveDeviceRegIntoDeviceCache

- ea: `0x140082be8`
- end: `0x140083041`
- name: `MoveDeviceRegIntoDeviceCache`
- size: `1113`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004ee48`
- `0x14004f428`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140074230`
- `0x140074808`
- `0x140074f18`
- `0x140075070`
- `0x1400801a4`
- `0x140082be8`
- `0x140084e04`
- `0x140084f5c`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140082e19`
- `ADVAPI32!RegCloseKey` at `0x140082e19`
- `KERNEL32!GetLastError` at `0x140082e3f`
- `KERNEL32!GetLastError` at `0x140082e3f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140082fcd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140082fcd`

## string_xrefs

- `0x140082c74`: `Software\Microsoft\Fax\Devices Cache`
- `0x140082d80`: `Software\Microsoft\Fax\Devices Cache`
- `0x140082ebb`: `Software\Microsoft\Fax\Devices Cache`

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
0x140082be8  mov     [rsp-8+arg_18], rbx
0x140082bed  push    rbp
0x140082bee  push    rsi
0x140082bef  push    rdi
0x140082bf0  push    r12
0x140082bf2  push    r13
0x140082bf4  push    r14
0x140082bf6  push    r15
0x140082bf8  lea     rbp, [rsp-370h]
0x140082c00  sub     rsp, 470h
0x140082c07  mov     rax, cs:__security_cookie
0x140082c0e  xor     rax, rsp
0x140082c11  mov     [rbp+3A0h+var_40], rax
0x140082c18  mov     esi, r8d
0x140082c1b  mov     qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140082c24  mov     edi, edx
0x140082c26  mov     r14d, ecx
0x140082c29  mov     rcx, cs:WPP_GLOBAL_Control
0x140082c30  lea     r12, WPP_GLOBAL_Control
0x140082c37  lea     r13, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140082c3e  mov     r15b, 2
0x140082c41  cmp     rcx, r12
0x140082c44  jz      short loc_140082C63
0x140082c46  test    [rcx+1Ch], r15b
0x140082c4a  jz      short loc_140082C63
0x140082c4c  cmp     byte ptr [rcx+19h], 5
0x140082c50  jb      short loc_140082C63
0x140082c52  mov     rcx, [rcx+10h]
0x140082c56  mov     edx, 84h
0x140082c5b  mov     r8, r13
0x140082c5e  call    WPP_SF_
0x140082c63  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140082c6a  mov     edx, 104h; unsigned __int64
0x140082c6f  mov     [rsp+4A0h+var_478], rax
0x140082c74  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140082c7b  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x140082c82  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082c86  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x140082c8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082c90  mov     ebx, eax
0x140082c92  test    eax, eax
0x140082c94  jns     short loc_140082CDA
0x140082c96  mov     rcx, cs:WPP_GLOBAL_Control
0x140082c9d  cmp     rcx, r12
0x140082ca0  jz      short loc_140082CC2
0x140082ca2  test    [rcx+1Ch], r15b
0x140082ca6  jz      short loc_140082CC2
0x140082ca8  cmp     [rcx+19h], r15b
0x140082cac  jb      short loc_140082CC2
0x140082cae  mov     edx, 85h
0x140082cb3  mov     rcx, [rcx+10h]
0x140082cb7  mov     r9d, ebx
0x140082cba  mov     r8, r13
0x140082cbd  call    WPP_SF_d
0x140082cc2  mov     eax, ebx
0x140082cc4  and     eax, 1FFF0000h
0x140082cc9  cmp     eax, 70000h
0x140082cce  jnz     short loc_140082CD3
0x140082cd0  movzx   ebx, bx
0x140082cd3  mov     eax, ebx
0x140082cd5  jmp     loc_140083016
0x140082cda  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140082ce1  mov     edx, 104h; unsigned __int64
0x140082ce6  mov     [rsp+4A0h+var_478], rax
0x140082ceb  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x140082cf2  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x140082cf9  mov     dword ptr [rsp+4A0h+var_480], r14d
0x140082cfe  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x140082d05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082d0a  mov     ebx, eax
0x140082d0c  test    eax, eax
0x140082d0e  jns     short loc_140082D2F
0x140082d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140082d17  cmp     rcx, r12
0x140082d1a  jz      short loc_140082CC2
0x140082d1c  test    [rcx+1Ch], r15b
0x140082d20  jz      short loc_140082CC2
0x140082d22  cmp     [rcx+19h], r15b
0x140082d26  jb      short loc_140082CC2
0x140082d28  mov     edx, 86h
0x140082d2d  jmp     short loc_140082CB3
0x140082d2f  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x140082d36  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x140082d3b  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x140082d40  mov     ebx, eax
0x140082d42  test    eax, eax
0x140082d44  jz      short loc_140082D80
0x140082d46  mov     rcx, cs:WPP_GLOBAL_Control
0x140082d4d  cmp     rcx, r12
0x140082d50  jz      short loc_140082CD3
0x140082d52  test    [rcx+1Ch], r15b
0x140082d56  jz      loc_140082CD3
0x140082d5c  cmp     [rcx+19h], r15b
0x140082d60  jb      loc_140082CD3
0x140082d66  mov     rcx, [rcx+10h]
0x140082d6a  mov     edx, 87h
0x140082d6f  mov     r9d, eax
0x140082d72  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082d76  call    WPP_SF_lL
0x140082d7b  jmp     loc_140082CD3
0x140082d80  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140082d87  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082d8b  lea     r8, aS08lx; "%s\\%08lx"
0x140082d92  mov     edx, 104h; unsigned __int64
0x140082d97  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x140082d9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082da1  test    eax, eax
0x140082da3  jns     short loc_140082DE2
0x140082da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140082dac  cmp     rcx, r12
0x140082daf  jz      loc_140082E70
0x140082db5  test    [rcx+1Ch], r15b
0x140082db9  jz      loc_140082E70
0x140082dbf  cmp     [rcx+19h], r15b
0x140082dc3  jb      loc_140082E70
0x140082dc9  mov     rcx, [rcx+10h]
0x140082dcd  mov     edx, 88h
0x140082dd2  mov     r9d, eax
0x140082dd5  mov     r8, r13
0x140082dd8  call    WPP_SF_d
0x140082ddd  jmp     loc_140082E70
0x140082de2  mov     r9d, 20006h
0x140082de8  lea     rdx, [rsp+4A0h+var_460]
0x140082ded  xor     r8d, r8d
0x140082df0  mov     rcx, 0FFFFFFFF80000002h
0x140082df7  call    OpenRegistryKey
0x140082dfc  mov     rbx, rax
0x140082dff  test    rax, rax
0x140082e02  jz      short loc_140082E27
0x140082e04  mov     r8d, esi
0x140082e07  lea     rdx, aManualanswer; "ManualAnswer"
0x140082e0e  mov     rcx, rax
0x140082e11  call    SetRegistryDword
0x140082e16  mov     rcx, rbx; hKey
0x140082e19  call    cs:__imp_RegCloseKey
0x140082e20  nop     dword ptr [rax+rax+00h]
0x140082e25  jmp     short loc_140082E70
0x140082e27  mov     rax, cs:WPP_GLOBAL_Control
0x140082e2e  cmp     rax, r12
0x140082e31  jz      short loc_140082E70
0x140082e33  test    [rax+1Ch], r15b
0x140082e37  jz      short loc_140082E70
0x140082e39  cmp     [rax+19h], r15b
0x140082e3d  jb      short loc_140082E70
0x140082e3f  call    cs:__imp_GetLastError
0x140082e46  nop     dword ptr [rax+rax+00h]
0x140082e4b  lea     rcx, [rsp+4A0h+var_460]
0x140082e50  mov     edx, 89h
0x140082e55  mov     [rsp+4A0h+var_480], rcx
0x140082e5a  mov     r9d, eax
0x140082e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e64  mov     r8, r13
0x140082e67  mov     rcx, [rcx+10h]
0x140082e6b  call    WPP_SF_DS
0x140082e70  mov     ecx, r14d
0x140082e73  call    DeleteDeviceEntry
0x140082e78  mov     bl, 3
0x140082e7a  test    eax, eax
0x140082e7c  jz      short loc_140082EAA
0x140082e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e85  cmp     rcx, r12
0x140082e88  jz      short loc_140082EAA
0x140082e8a  test    [rcx+1Ch], r15b
0x140082e8e  jz      short loc_140082EAA
0x140082e90  cmp     [rcx+19h], bl
0x140082e93  jb      short loc_140082EAA
0x140082e95  mov     rcx, [rcx+10h]
0x140082e99  mov     edx, 8Ah
0x140082e9e  mov     r9d, eax
0x140082ea1  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082ea5  call    WPP_SF_lL
0x140082eaa  lea     rax, aTapiData; "TAPI Data"
0x140082eb1  mov     esi, 104h
0x140082eb6  mov     [rsp+4A0h+var_478], rax
0x140082ebb  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140082ec2  mov     edx, esi; unsigned __int64
0x140082ec4  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082ec8  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x140082ecf  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x140082ed4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082ed9  test    eax, eax
0x140082edb  js      loc_140082F65
0x140082ee1  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x140082ee8  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082eec  lea     r8, aS08lx; "%s\\%08lx"
0x140082ef3  mov     edx, esi; unsigned __int64
0x140082ef5  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x140082efc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140082f01  test    eax, eax
0x140082f03  js      short loc_140082F46
0x140082f05  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x140082f0c  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x140082f11  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x140082f16  test    eax, eax
0x140082f18  jz      short loc_140082F91
0x140082f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082f21  cmp     rcx, r12
0x140082f24  jz      short loc_140082F91
0x140082f26  test    [rcx+1Ch], r15b
0x140082f2a  jz      short loc_140082F91
0x140082f2c  cmp     [rcx+19h], bl
0x140082f2f  jb      short loc_140082F91
0x140082f31  mov     rcx, [rcx+10h]
0x140082f35  lea     edx, [rsi-79h]
0x140082f38  mov     r9d, eax
0x140082f3b  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082f3f  call    WPP_SF_lL
0x140082f44  jmp     short loc_140082F91
0x140082f46  mov     rcx, cs:WPP_GLOBAL_Control
0x140082f4d  cmp     rcx, r12
0x140082f50  jz      short loc_140082F91
0x140082f52  test    [rcx+1Ch], r15b
0x140082f56  jz      short loc_140082F91
0x140082f58  cmp     [rcx+19h], r15b
0x140082f5c  jb      short loc_140082F91
0x140082f5e  mov     edx, 8Ch
0x140082f63  jmp     short loc_140082F82
0x140082f65  mov     rcx, cs:WPP_GLOBAL_Control
0x140082f6c  cmp     rcx, r12
0x140082f6f  jz      short loc_140082F91
0x140082f71  test    [rcx+1Ch], r15b
0x140082f75  jz      short loc_140082F91
0x140082f77  cmp     [rcx+19h], r15b
0x140082f7b  jb      short loc_140082F91
0x140082f7d  mov     edx, 8Dh
0x140082f82  mov     rcx, [rcx+10h]
0x140082f86  mov     r9d, eax
0x140082f89  mov     r8, r13
0x140082f8c  call    WPP_SF_d
0x140082f91  mov     ecx, edi
0x140082f93  call    DeleteTapiEntry
0x140082f98  test    eax, eax
0x140082f9a  jz      short loc_140082FC8
0x140082f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140082fa3  cmp     rcx, r12
0x140082fa6  jz      short loc_140082FC8
0x140082fa8  test    [rcx+1Ch], r15b
0x140082fac  jz      short loc_140082FC8
0x140082fae  cmp     [rcx+19h], bl
0x140082fb1  jb      short loc_140082FC8
0x140082fb3  mov     rcx, [rcx+10h]
0x140082fb7  mov     edx, 8Eh
0x140082fbc  mov     r9d, eax
0x140082fbf  mov     dword ptr [rsp+4A0h+var_480], edi
0x140082fc3  call    WPP_SF_lL
0x140082fc8  lea     rcx, [rsp+4A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140082fcd  call    cs:__imp_GetSystemTimeAsFileTime
0x140082fd4  nop     dword ptr [rax+rax+00h]
0x140082fd9  mov     rdx, qword ptr [rsp+4A0h+SystemTimeAsFileTime.dwLowDateTime]
0x140082fde  mov     ecx, edi
0x140082fe0  call    UpdateLastDetectedTime
0x140082fe5  test    eax, eax
0x140082fe7  jnz     short loc_140083014
0x140082fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ff0  cmp     rcx, r12
0x140082ff3  jz      short loc_140083014
0x140082ff5  test    [rcx+1Ch], r15b
0x140082ff9  jz      short loc_140083014
0x140082ffb  cmp     [rcx+19h], bl
0x140082ffe  jb      short loc_140083014
0x140083000  mov     rcx, [rcx+10h]
0x140083004  mov     edx, 8Fh
0x140083009  mov     r9d, edi
0x14008300c  mov     r8, r13
0x14008300f  call    WPP_SF_d
0x140083014  xor     eax, eax
0x140083016  mov     rcx, [rbp+3A0h+var_40]
0x14008301d  xor     rcx, rsp; StackCookie
0x140083020  call    __security_check_cookie
0x140083025  mov     rbx, [rsp+4A0h+arg_18]
0x14008302d  add     rsp, 470h
0x140083034  pop     r15
0x140083036  pop     r14
0x140083038  pop     r13
0x14008303a  pop     r12
0x14008303c  pop     rdi
0x14008303d  pop     rsi
0x14008303e  pop     rbp
0x14008303f  retn
```
