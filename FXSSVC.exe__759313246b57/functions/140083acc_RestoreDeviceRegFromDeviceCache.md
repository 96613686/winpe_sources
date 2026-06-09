# RestoreDeviceRegFromDeviceCache

- ea: `0x140083acc`
- end: `0x140083ffe`
- name: `RestoreDeviceRegFromDeviceCache`
- size: `1330`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400815a0`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140074084`
- `0x140074230`
- `0x140074f18`
- `0x140075070`
- `0x1400801a4`
- `0x140083acc`
- `0x140084f5c`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140083f17`
- `ADVAPI32!RegCloseKey` at `0x140083f72`
- `ADVAPI32!RegCloseKey` at `0x140083f17`
- `ADVAPI32!RegCloseKey` at `0x140083f72`
- `KERNEL32!GetLastError` at `0x140083cf5`
- `KERNEL32!GetLastError` at `0x140083d6b`
- `KERNEL32!GetLastError` at `0x140083ee7`
- `KERNEL32!GetLastError` at `0x140083cf5`
- `KERNEL32!GetLastError` at `0x140083d6b`
- `KERNEL32!GetLastError` at `0x140083ee7`

## string_xrefs

- `0x140083b50`: `Software\Microsoft\Fax\Devices Cache`
- `0x140083dd6`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall RestoreDeviceRegFromDeviceCache(int a1, unsigned int a2)
{
  int v4; // r12d
  signed int LastError; // ebx
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  HKEY v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  signed int v12; // edi
  HKEY v13; // rax
  HKEY v14; // rsi
  int v15; // edi
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  HKEY v18; // rax
  DWORD v19; // eax
  HKEY v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v24; // r8
  __int64 v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v30[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v31[264]; // [rsp+240h] [rbp+140h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  LastError = StringCchPrintfW(
                v30,
                0x104u,
                L"%s\\%08lx\\%s",
                L"Software\\Microsoft\\Fax\\Devices Cache",
                a2,
                L"{F10A5326-0261-4715-B367-2970427BBD99}");
  if ( LastError < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 145;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, (unsigned int)LastError);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  LODWORD(v26) = a1;
  LastError = StringCchPrintfW(
                v31,
                0x104u,
                L"%s\\%010lu\\%s",
                L"Software\\Microsoft\\Fax\\Devices",
                v26,
                L"{F10A5326-0261-4715-B367-2970427BBD99}");
  if ( LastError < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 146;
      goto LABEL_10;
    }
LABEL_11:
    if ( (LastError & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)LastError;
    goto LABEL_66;
  }
  v9 = FaxCopyRegSubkeys(v31, v8, v30);
  LastError = v9;
  if ( !v9 )
  {
    LODWORD(v27) = a1;
    v4 = 1;
    v11 = StringCchPrintfW(v30, 0x104u, L"%s\\%010lu", L"Software\\Microsoft\\Fax\\Devices", v27);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          148,
          &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
          (unsigned int)v11);
      }
      if ( (v12 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v12;
      else
        LastError = v12;
      goto LABEL_66;
    }
    v13 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v30, 0, 0x20006u);
    v14 = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          149,
          (unsigned int)&WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
          LastError,
          (__int64)v30);
      }
      goto LABEL_66;
    }
    if ( !(unsigned int)SetRegistryDword(v13, L"Permanent Lineid", a1) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          150,
          &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
          L"Permanent Lineid");
      }
      goto LABEL_65;
    }
    LODWORD(v28) = a2;
    v15 = StringCchPrintfW(v30, 0x104u, L"%s\\%08lx\\%s", L"Software\\Microsoft\\Fax\\Devices Cache", v28, L"TAPI Data");
    if ( v15 >= 0 )
    {
      LODWORD(v29) = a2;
      v15 = StringCchPrintfW(v31, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\TAPIDevices", v29);
      if ( v15 >= 0 )
      {
        v18 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v30, 0, 0x20019u);
        if ( v18 )
        {
          RegCloseKey(v18);
          v21 = FaxCopyRegSubkeys(v31, v20, v30);
          LastError = v21;
          if ( v21
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, v22, v21, a2);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v19 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v19);
        }
        goto LABEL_65;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v17 = 152;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v17 = 151;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, (unsigned int)v15);
LABEL_47:
    if ( (v15 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v15;
    else
      LastError = v15;
LABEL_65:
    RegCloseKey(v14);
LABEL_66:
    if ( LastError )
    {
      if ( v4 == 1 )
      {
        v23 = DeleteDeviceEntry(a1);
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, v24, v23, a1);
          }
        }
      }
    }
    goto LABEL_73;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_lL(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, v10, v9, a2);
  }
LABEL_73:
  DeleteCacheEntry(a2);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140083acc  mov     [rsp-8+arg_10], rbx
0x140083ad1  push    rbp
0x140083ad2  push    rsi
0x140083ad3  push    rdi
0x140083ad4  push    r12
0x140083ad6  push    r13
0x140083ad8  push    r14
0x140083ada  push    r15
0x140083adc  lea     rbp, [rsp-360h]
0x140083ae4  sub     rsp, 460h
0x140083aeb  mov     rax, cs:__security_cookie
0x140083af2  xor     rax, rsp
0x140083af5  mov     [rbp+390h+var_40], rax
0x140083afc  mov     r14d, edx
0x140083aff  mov     r15d, ecx
0x140083b02  xor     r12d, r12d
0x140083b05  mov     rcx, cs:WPP_GLOBAL_Control
0x140083b0c  lea     rsi, WPP_GLOBAL_Control
0x140083b13  lea     rdi, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083b1a  mov     r13b, 2
0x140083b1d  cmp     rcx, rsi
0x140083b20  jz      short loc_140083B3F
0x140083b22  test    [rcx+1Ch], r13b
0x140083b26  jz      short loc_140083B3F
0x140083b28  cmp     byte ptr [rcx+19h], 5
0x140083b2c  jb      short loc_140083B3F
0x140083b2e  mov     rcx, [rcx+10h]
0x140083b32  mov     edx, 90h
0x140083b37  mov     r8, rdi
0x140083b3a  call    WPP_SF_
0x140083b3f  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140083b46  mov     edx, 104h; unsigned __int64
0x140083b4b  mov     [rsp+490h+var_468], rax
0x140083b50  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140083b57  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x140083b5e  mov     dword ptr [rsp+490h+var_470], r14d
0x140083b63  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x140083b68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140083b6d  mov     ebx, eax
0x140083b6f  test    eax, eax
0x140083b71  jns     short loc_140083BB9
0x140083b73  mov     rcx, cs:WPP_GLOBAL_Control
0x140083b7a  cmp     rcx, rsi
0x140083b7d  jz      short loc_140083B9F
0x140083b7f  test    [rcx+1Ch], r13b
0x140083b83  jz      short loc_140083B9F
0x140083b85  cmp     [rcx+19h], r13b
0x140083b89  jb      short loc_140083B9F
0x140083b8b  mov     edx, 91h
0x140083b90  mov     rcx, [rcx+10h]
0x140083b94  mov     r9d, ebx
0x140083b97  mov     r8, rdi
0x140083b9a  call    WPP_SF_d
0x140083b9f  mov     eax, ebx
0x140083ba1  and     eax, 1FFF0000h
0x140083ba6  cmp     eax, 70000h
0x140083bab  jnz     loc_140083F85
0x140083bb1  movzx   ebx, bx
0x140083bb4  jmp     loc_140083F85
0x140083bb9  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140083bc0  mov     edx, 104h; unsigned __int64
0x140083bc5  mov     [rsp+490h+var_468], rax
0x140083bca  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x140083bd1  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x140083bd8  mov     dword ptr [rsp+490h+var_470], r15d
0x140083bdd  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x140083be4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140083be9  mov     ebx, eax
0x140083beb  test    eax, eax
0x140083bed  jns     short loc_140083C0E
0x140083bef  mov     rcx, cs:WPP_GLOBAL_Control
0x140083bf6  cmp     rcx, rsi
0x140083bf9  jz      short loc_140083B9F
0x140083bfb  test    [rcx+1Ch], r13b
0x140083bff  jz      short loc_140083B9F
0x140083c01  cmp     [rcx+19h], r13b
0x140083c05  jb      short loc_140083B9F
0x140083c07  mov     edx, 92h
0x140083c0c  jmp     short loc_140083B90
0x140083c0e  lea     r8, [rsp+490h+var_460]; unsigned __int16 *
0x140083c13  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x140083c1a  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x140083c1f  mov     ebx, eax
0x140083c21  test    eax, eax
0x140083c23  jz      short loc_140083C58
0x140083c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140083c2c  cmp     rcx, rsi
0x140083c2f  jz      loc_140083FC9
0x140083c35  test    [rcx+1Ch], r13b
0x140083c39  jz      loc_140083FC9
0x140083c3f  cmp     [rcx+19h], r13b
0x140083c43  jb      loc_140083FC9
0x140083c49  mov     edx, 93h
0x140083c4e  mov     dword ptr [rsp+490h+var_470], r14d
0x140083c53  jmp     loc_140083FBD
0x140083c58  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x140083c5f  mov     dword ptr [rsp+490h+var_470], r15d
0x140083c64  lea     r8, aS010lu; "%s\\%010lu"
0x140083c6b  mov     edx, 104h; unsigned __int64
0x140083c70  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x140083c75  mov     r12d, 1
0x140083c7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140083c80  mov     edi, eax
0x140083c82  test    eax, eax
0x140083c84  jns     short loc_140083CD3
0x140083c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140083c8d  cmp     rcx, rsi
0x140083c90  jz      short loc_140083CB6
0x140083c92  test    [rcx+1Ch], r13b
0x140083c96  jz      short loc_140083CB6
0x140083c98  cmp     [rcx+19h], r13b
0x140083c9c  jb      short loc_140083CB6
0x140083c9e  mov     rcx, [rcx+10h]
0x140083ca2  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083ca9  mov     edx, 94h
0x140083cae  mov     r9d, eax
0x140083cb1  call    WPP_SF_d
0x140083cb6  mov     eax, edi
0x140083cb8  and     eax, 1FFF0000h
0x140083cbd  cmp     eax, 70000h
0x140083cc2  jnz     short loc_140083CCC
0x140083cc4  movzx   ebx, di
0x140083cc7  jmp     loc_140083F85
0x140083ccc  mov     ebx, edi
0x140083cce  jmp     loc_140083F85
0x140083cd3  mov     r9d, 20006h
0x140083cd9  lea     rdx, [rsp+490h+var_460]
0x140083cde  xor     r8d, r8d
0x140083ce1  mov     rcx, 0FFFFFFFF80000002h
0x140083ce8  call    OpenRegistryKey
0x140083ced  mov     rsi, rax
0x140083cf0  test    rax, rax
0x140083cf3  jnz     short loc_140083D55
0x140083cf5  call    cs:__imp_GetLastError
0x140083cfc  nop     dword ptr [rax+rax+00h]
0x140083d01  mov     ebx, eax
0x140083d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140083d0a  lea     rsi, WPP_GLOBAL_Control
0x140083d11  cmp     rcx, rsi
0x140083d14  jz      loc_140083F85
0x140083d1a  test    [rcx+1Ch], r13b
0x140083d1e  jz      loc_140083F85
0x140083d24  cmp     [rcx+19h], r13b
0x140083d28  jb      loc_140083F85
0x140083d2e  mov     rcx, [rcx+10h]
0x140083d32  lea     rax, [rsp+490h+var_460]
0x140083d37  mov     edx, 95h
0x140083d3c  mov     [rsp+490h+var_470], rax
0x140083d41  mov     r9d, ebx
0x140083d44  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083d4b  call    WPP_SF_DS
0x140083d50  jmp     loc_140083F85
0x140083d55  mov     r8d, r15d
0x140083d58  lea     rdx, aPermanentLinei; "Permanent Lineid"
0x140083d5f  mov     rcx, rsi
0x140083d62  call    SetRegistryDword
0x140083d67  test    eax, eax
0x140083d69  jnz     short loc_140083DC5
0x140083d6b  call    cs:__imp_GetLastError
0x140083d72  nop     dword ptr [rax+rax+00h]
0x140083d77  mov     ebx, eax
0x140083d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140083d80  lea     rdx, WPP_GLOBAL_Control
0x140083d87  cmp     rcx, rdx
0x140083d8a  jz      loc_140083F6F
0x140083d90  test    [rcx+1Ch], r13b
0x140083d94  jz      loc_140083F6F
0x140083d9a  cmp     [rcx+19h], r13b
0x140083d9e  jb      loc_140083F6F
0x140083da4  mov     rcx, [rcx+10h]
0x140083da8  lea     r9, aPermanentLinei; "Permanent Lineid"
0x140083daf  mov     edx, 96h
0x140083db4  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083dbb  call    WPP_SF_S
0x140083dc0  jmp     loc_140083F6F
0x140083dc5  lea     rax, aTapiData; "TAPI Data"
0x140083dcc  mov     edx, 104h; unsigned __int64
0x140083dd1  mov     [rsp+490h+var_468], rax
0x140083dd6  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140083ddd  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x140083de4  mov     dword ptr [rsp+490h+var_470], r14d
0x140083de9  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x140083dee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140083df3  mov     edi, eax
0x140083df5  test    eax, eax
0x140083df7  jns     short loc_140083E4D
0x140083df9  mov     rcx, cs:WPP_GLOBAL_Control
0x140083e00  lea     rdx, WPP_GLOBAL_Control
0x140083e07  cmp     rcx, rdx
0x140083e0a  jz      short loc_140083E30
0x140083e0c  test    [rcx+1Ch], r13b
0x140083e10  jz      short loc_140083E30
0x140083e12  cmp     [rcx+19h], r13b
0x140083e16  jb      short loc_140083E30
0x140083e18  mov     edx, 97h
0x140083e1d  mov     rcx, [rcx+10h]
0x140083e21  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083e28  mov     r9d, edi
0x140083e2b  call    WPP_SF_d
0x140083e30  mov     eax, edi
0x140083e32  and     eax, 1FFF0000h
0x140083e37  cmp     eax, 70000h
0x140083e3c  jnz     short loc_140083E46
0x140083e3e  movzx   ebx, di
0x140083e41  jmp     loc_140083F6F
0x140083e46  mov     ebx, edi
0x140083e48  jmp     loc_140083F6F
0x140083e4d  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x140083e54  mov     dword ptr [rsp+490h+var_470], r14d
0x140083e59  lea     r8, aS08lx; "%s\\%08lx"
0x140083e60  mov     edx, 104h; unsigned __int64
0x140083e65  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x140083e6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140083e71  mov     edi, eax
0x140083e73  test    eax, eax
0x140083e75  jns     short loc_140083E9D
0x140083e77  mov     rcx, cs:WPP_GLOBAL_Control
0x140083e7e  lea     rdx, WPP_GLOBAL_Control
0x140083e85  cmp     rcx, rdx
0x140083e88  jz      short loc_140083E30
0x140083e8a  test    [rcx+1Ch], r13b
0x140083e8e  jz      short loc_140083E30
0x140083e90  cmp     [rcx+19h], r13b
0x140083e94  jb      short loc_140083E30
0x140083e96  mov     edx, 98h
0x140083e9b  jmp     short loc_140083E1D
0x140083e9d  mov     r9d, 20019h
0x140083ea3  lea     rdx, [rsp+490h+var_460]
0x140083ea8  xor     r8d, r8d
0x140083eab  mov     rcx, 0FFFFFFFF80000002h
0x140083eb2  call    OpenRegistryKey
0x140083eb7  test    rax, rax
0x140083eba  jnz     short loc_140083F14
0x140083ebc  mov     rax, cs:WPP_GLOBAL_Control
0x140083ec3  lea     rdx, WPP_GLOBAL_Control
0x140083eca  cmp     rax, rdx
0x140083ecd  jz      loc_140083F6F
0x140083ed3  test    [rax+1Ch], r13b
0x140083ed7  jz      loc_140083F6F
0x140083edd  cmp     byte ptr [rax+19h], 3
0x140083ee1  jb      loc_140083F6F
0x140083ee7  call    cs:__imp_GetLastError
0x140083eee  nop     dword ptr [rax+rax+00h]
0x140083ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140083efa  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140083f01  mov     edx, 99h
0x140083f06  mov     r9d, eax
0x140083f09  mov     rcx, [rcx+10h]
0x140083f0d  call    WPP_SF_d
0x140083f12  jmp     short loc_140083F6F
0x140083f14  mov     rcx, rax; hKey
0x140083f17  call    cs:__imp_RegCloseKey
0x140083f1e  nop     dword ptr [rax+rax+00h]
0x140083f23  lea     r8, [rsp+490h+var_460]; unsigned __int16 *
0x140083f28  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x140083f2f  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x140083f34  mov     ebx, eax
0x140083f36  test    eax, eax
0x140083f38  jz      short loc_140083F6F
0x140083f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140083f41  lea     rdx, WPP_GLOBAL_Control
0x140083f48  cmp     rcx, rdx
0x140083f4b  jz      short loc_140083F6F
0x140083f4d  test    [rcx+1Ch], r13b
0x140083f51  jz      short loc_140083F6F
0x140083f53  cmp     byte ptr [rcx+19h], 3
0x140083f57  jb      short loc_140083F6F
0x140083f59  mov     rcx, [rcx+10h]
0x140083f5d  mov     edx, 9Ah
0x140083f62  mov     r9d, eax
0x140083f65  mov     dword ptr [rsp+490h+var_470], r14d
0x140083f6a  call    WPP_SF_lL
0x140083f6f  mov     rcx, rsi; hKey
0x140083f72  call    cs:__imp_RegCloseKey
0x140083f79  nop     dword ptr [rax+rax+00h]
0x140083f7e  lea     rsi, WPP_GLOBAL_Control
0x140083f85  test    ebx, ebx
0x140083f87  jz      short loc_140083FC9
0x140083f89  cmp     r12d, 1
0x140083f8d  jnz     short loc_140083FC9
0x140083f8f  mov     ecx, r15d
0x140083f92  call    DeleteDeviceEntry
0x140083f97  test    eax, eax
0x140083f99  jz      short loc_140083FC9
0x140083f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140083fa2  cmp     rcx, rsi
0x140083fa5  jz      short loc_140083FC9
0x140083fa7  test    [rcx+1Ch], r13b
0x140083fab  jz      short loc_140083FC9
0x140083fad  cmp     [rcx+19h], r13b
0x140083fb1  jb      short loc_140083FC9
0x140083fb3  mov     edx, 9Bh
0x140083fb8  mov     dword ptr [rsp+490h+var_470], r15d
0x140083fbd  mov     rcx, [rcx+10h]
0x140083fc1  mov     r9d, eax
0x140083fc4  call    WPP_SF_lL
0x140083fc9  mov     ecx, r14d
0x140083fcc  call    DeleteCacheEntry
0x140083fd1  mov     eax, ebx
0x140083fd3  mov     rcx, [rbp+390h+var_40]
  ... truncated ...
```
