# RestoreDeviceRegFromDeviceCache

- ea: `0x14007e844`
- end: `0x14007ed53`
- name: `RestoreDeviceRegFromDeviceCache`
- size: `1295`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007c450`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x14006fb00`
- `0x14006fc98`
- `0x1400708c4`
- `0x1400709fc`
- `0x14007b150`
- `0x14007e844`
- `0x14007fbd8`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007ec79`
- `ADVAPI32!RegCloseKey` at `0x14007ecce`
- `ADVAPI32!RegCloseKey` at `0x14007ec79`
- `ADVAPI32!RegCloseKey` at `0x14007ecce`
- `KERNEL32!GetLastError` at `0x14007ea6d`
- `KERNEL32!GetLastError` at `0x14007eadd`
- `KERNEL32!GetLastError` at `0x14007ec4f`
- `KERNEL32!GetLastError` at `0x14007ea6d`
- `KERNEL32!GetLastError` at `0x14007eadd`
- `KERNEL32!GetLastError` at `0x14007ec4f`

## string_xrefs

- `0x14007e8c8`: `Software\Microsoft\Fax\Devices Cache`
- `0x14007eb42`: `Software\Microsoft\Fax\Devices Cache`

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
0x14007e844  mov     [rsp-8+arg_10], rbx
0x14007e849  push    rbp
0x14007e84a  push    rsi
0x14007e84b  push    rdi
0x14007e84c  push    r12
0x14007e84e  push    r13
0x14007e850  push    r14
0x14007e852  push    r15
0x14007e854  lea     rbp, [rsp-360h]
0x14007e85c  sub     rsp, 460h
0x14007e863  mov     rax, cs:__security_cookie
0x14007e86a  xor     rax, rsp
0x14007e86d  mov     [rbp+390h+var_40], rax
0x14007e874  mov     r14d, edx
0x14007e877  mov     r15d, ecx
0x14007e87a  xor     r12d, r12d
0x14007e87d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e884  lea     rsi, WPP_GLOBAL_Control
0x14007e88b  lea     rdi, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007e892  mov     r13b, 2
0x14007e895  cmp     rcx, rsi
0x14007e898  jz      short loc_14007E8B7
0x14007e89a  test    [rcx+1Ch], r13b
0x14007e89e  jz      short loc_14007E8B7
0x14007e8a0  cmp     byte ptr [rcx+19h], 5
0x14007e8a4  jb      short loc_14007E8B7
0x14007e8a6  mov     rcx, [rcx+10h]
0x14007e8aa  mov     edx, 90h
0x14007e8af  mov     r8, rdi
0x14007e8b2  call    WPP_SF_
0x14007e8b7  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007e8be  mov     edx, 104h; unsigned __int64
0x14007e8c3  mov     [rsp+490h+var_468], rax
0x14007e8c8  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007e8cf  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x14007e8d6  mov     dword ptr [rsp+490h+var_470], r14d
0x14007e8db  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x14007e8e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007e8e5  mov     ebx, eax
0x14007e8e7  test    eax, eax
0x14007e8e9  jns     short loc_14007E931
0x14007e8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e8f2  cmp     rcx, rsi
0x14007e8f5  jz      short loc_14007E917
0x14007e8f7  test    [rcx+1Ch], r13b
0x14007e8fb  jz      short loc_14007E917
0x14007e8fd  cmp     [rcx+19h], r13b
0x14007e901  jb      short loc_14007E917
0x14007e903  mov     edx, 91h
0x14007e908  mov     rcx, [rcx+10h]
0x14007e90c  mov     r9d, ebx
0x14007e90f  mov     r8, rdi
0x14007e912  call    WPP_SF_d
0x14007e917  mov     eax, ebx
0x14007e919  and     eax, 1FFF0000h
0x14007e91e  cmp     eax, 70000h
0x14007e923  jnz     loc_14007ECDB
0x14007e929  movzx   ebx, bx
0x14007e92c  jmp     loc_14007ECDB
0x14007e931  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007e938  mov     edx, 104h; unsigned __int64
0x14007e93d  mov     [rsp+490h+var_468], rax
0x14007e942  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007e949  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x14007e950  mov     dword ptr [rsp+490h+var_470], r15d
0x14007e955  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x14007e95c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007e961  mov     ebx, eax
0x14007e963  test    eax, eax
0x14007e965  jns     short loc_14007E986
0x14007e967  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e96e  cmp     rcx, rsi
0x14007e971  jz      short loc_14007E917
0x14007e973  test    [rcx+1Ch], r13b
0x14007e977  jz      short loc_14007E917
0x14007e979  cmp     [rcx+19h], r13b
0x14007e97d  jb      short loc_14007E917
0x14007e97f  mov     edx, 92h
0x14007e984  jmp     short loc_14007E908
0x14007e986  lea     r8, [rsp+490h+var_460]; unsigned __int16 *
0x14007e98b  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x14007e992  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x14007e997  mov     ebx, eax
0x14007e999  test    eax, eax
0x14007e99b  jz      short loc_14007E9D0
0x14007e99d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e9a4  cmp     rcx, rsi
0x14007e9a7  jz      loc_14007ED1F
0x14007e9ad  test    [rcx+1Ch], r13b
0x14007e9b1  jz      loc_14007ED1F
0x14007e9b7  cmp     [rcx+19h], r13b
0x14007e9bb  jb      loc_14007ED1F
0x14007e9c1  mov     edx, 93h
0x14007e9c6  mov     dword ptr [rsp+490h+var_470], r14d
0x14007e9cb  jmp     loc_14007ED13
0x14007e9d0  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007e9d7  mov     dword ptr [rsp+490h+var_470], r15d
0x14007e9dc  lea     r8, aS010lu; "%s\\%010lu"
0x14007e9e3  mov     edx, 104h; unsigned __int64
0x14007e9e8  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x14007e9ed  mov     r12d, 1
0x14007e9f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007e9f8  mov     edi, eax
0x14007e9fa  test    eax, eax
0x14007e9fc  jns     short loc_14007EA4B
0x14007e9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea05  cmp     rcx, rsi
0x14007ea08  jz      short loc_14007EA2E
0x14007ea0a  test    [rcx+1Ch], r13b
0x14007ea0e  jz      short loc_14007EA2E
0x14007ea10  cmp     [rcx+19h], r13b
0x14007ea14  jb      short loc_14007EA2E
0x14007ea16  mov     rcx, [rcx+10h]
0x14007ea1a  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007ea21  mov     edx, 94h
0x14007ea26  mov     r9d, eax
0x14007ea29  call    WPP_SF_d
0x14007ea2e  mov     eax, edi
0x14007ea30  and     eax, 1FFF0000h
0x14007ea35  cmp     eax, 70000h
0x14007ea3a  jnz     short loc_14007EA44
0x14007ea3c  movzx   ebx, di
0x14007ea3f  jmp     loc_14007ECDB
0x14007ea44  mov     ebx, edi
0x14007ea46  jmp     loc_14007ECDB
0x14007ea4b  mov     r9d, 20006h
0x14007ea51  lea     rdx, [rsp+490h+var_460]
0x14007ea56  xor     r8d, r8d
0x14007ea59  mov     rcx, 0FFFFFFFF80000002h
0x14007ea60  call    OpenRegistryKey
0x14007ea65  mov     rsi, rax
0x14007ea68  test    rax, rax
0x14007ea6b  jnz     short loc_14007EAC7
0x14007ea6d  call    cs:__imp_GetLastError
0x14007ea73  mov     ebx, eax
0x14007ea75  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea7c  lea     rsi, WPP_GLOBAL_Control
0x14007ea83  cmp     rcx, rsi
0x14007ea86  jz      loc_14007ECDB
0x14007ea8c  test    [rcx+1Ch], r13b
0x14007ea90  jz      loc_14007ECDB
0x14007ea96  cmp     [rcx+19h], r13b
0x14007ea9a  jb      loc_14007ECDB
0x14007eaa0  mov     rcx, [rcx+10h]
0x14007eaa4  lea     rax, [rsp+490h+var_460]
0x14007eaa9  mov     edx, 95h
0x14007eaae  mov     [rsp+490h+var_470], rax
0x14007eab3  mov     r9d, ebx
0x14007eab6  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007eabd  call    WPP_SF_DS
0x14007eac2  jmp     loc_14007ECDB
0x14007eac7  mov     r8d, r15d
0x14007eaca  lea     rdx, aPermanentLinei; "Permanent Lineid"
0x14007ead1  mov     rcx, rsi
0x14007ead4  call    SetRegistryDword
0x14007ead9  test    eax, eax
0x14007eadb  jnz     short loc_14007EB31
0x14007eadd  call    cs:__imp_GetLastError
0x14007eae3  mov     ebx, eax
0x14007eae5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eaec  lea     rdx, WPP_GLOBAL_Control
0x14007eaf3  cmp     rcx, rdx
0x14007eaf6  jz      loc_14007ECCB
0x14007eafc  test    [rcx+1Ch], r13b
0x14007eb00  jz      loc_14007ECCB
0x14007eb06  cmp     [rcx+19h], r13b
0x14007eb0a  jb      loc_14007ECCB
0x14007eb10  mov     rcx, [rcx+10h]
0x14007eb14  lea     r9, aPermanentLinei; "Permanent Lineid"
0x14007eb1b  mov     edx, 96h
0x14007eb20  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007eb27  call    WPP_SF_S
0x14007eb2c  jmp     loc_14007ECCB
0x14007eb31  lea     rax, aTapiData; "TAPI Data"
0x14007eb38  mov     edx, 104h; unsigned __int64
0x14007eb3d  mov     [rsp+490h+var_468], rax
0x14007eb42  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007eb49  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x14007eb50  mov     dword ptr [rsp+490h+var_470], r14d
0x14007eb55  lea     rcx, [rsp+490h+var_460]; unsigned __int16 *
0x14007eb5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007eb5f  mov     edi, eax
0x14007eb61  test    eax, eax
0x14007eb63  jns     short loc_14007EBB9
0x14007eb65  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb6c  lea     rdx, WPP_GLOBAL_Control
0x14007eb73  cmp     rcx, rdx
0x14007eb76  jz      short loc_14007EB9C
0x14007eb78  test    [rcx+1Ch], r13b
0x14007eb7c  jz      short loc_14007EB9C
0x14007eb7e  cmp     [rcx+19h], r13b
0x14007eb82  jb      short loc_14007EB9C
0x14007eb84  mov     edx, 97h
0x14007eb89  mov     rcx, [rcx+10h]
0x14007eb8d  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007eb94  mov     r9d, edi
0x14007eb97  call    WPP_SF_d
0x14007eb9c  mov     eax, edi
0x14007eb9e  and     eax, 1FFF0000h
0x14007eba3  cmp     eax, 70000h
0x14007eba8  jnz     short loc_14007EBB2
0x14007ebaa  movzx   ebx, di
0x14007ebad  jmp     loc_14007ECCB
0x14007ebb2  mov     ebx, edi
0x14007ebb4  jmp     loc_14007ECCB
0x14007ebb9  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Fax\\TAPIDevices"
0x14007ebc0  mov     dword ptr [rsp+490h+var_470], r14d
0x14007ebc5  lea     r8, aS08lx; "%s\\%08lx"
0x14007ebcc  mov     edx, 104h; unsigned __int64
0x14007ebd1  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x14007ebd8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007ebdd  mov     edi, eax
0x14007ebdf  test    eax, eax
0x14007ebe1  jns     short loc_14007EC09
0x14007ebe3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ebea  lea     rdx, WPP_GLOBAL_Control
0x14007ebf1  cmp     rcx, rdx
0x14007ebf4  jz      short loc_14007EB9C
0x14007ebf6  test    [rcx+1Ch], r13b
0x14007ebfa  jz      short loc_14007EB9C
0x14007ebfc  cmp     [rcx+19h], r13b
0x14007ec00  jb      short loc_14007EB9C
0x14007ec02  mov     edx, 98h
0x14007ec07  jmp     short loc_14007EB89
0x14007ec09  mov     r9d, 20019h
0x14007ec0f  lea     rdx, [rsp+490h+var_460]
0x14007ec14  xor     r8d, r8d
0x14007ec17  mov     rcx, 0FFFFFFFF80000002h
0x14007ec1e  call    OpenRegistryKey
0x14007ec23  test    rax, rax
0x14007ec26  jnz     short loc_14007EC76
0x14007ec28  mov     rax, cs:WPP_GLOBAL_Control
0x14007ec2f  lea     rdx, WPP_GLOBAL_Control
0x14007ec36  cmp     rax, rdx
0x14007ec39  jz      loc_14007ECCB
0x14007ec3f  test    [rax+1Ch], r13b
0x14007ec43  jz      loc_14007ECCB
0x14007ec49  cmp     byte ptr [rax+19h], 3
0x14007ec4d  jb      short loc_14007ECCB
0x14007ec4f  call    cs:__imp_GetLastError
0x14007ec55  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec5c  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007ec63  mov     edx, 99h
0x14007ec68  mov     r9d, eax
0x14007ec6b  mov     rcx, [rcx+10h]
0x14007ec6f  call    WPP_SF_d
0x14007ec74  jmp     short loc_14007ECCB
0x14007ec76  mov     rcx, rax; hKey
0x14007ec79  call    cs:__imp_RegCloseKey
0x14007ec7f  lea     r8, [rsp+490h+var_460]; unsigned __int16 *
0x14007ec84  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x14007ec8b  call    ?FaxCopyRegSubkeys@@YAKPEBGPEAUHKEY__@@0@Z; FaxCopyRegSubkeys(ushort const *,HKEY__ *,ushort const *)
0x14007ec90  mov     ebx, eax
0x14007ec92  test    eax, eax
0x14007ec94  jz      short loc_14007ECCB
0x14007ec96  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec9d  lea     rdx, WPP_GLOBAL_Control
0x14007eca4  cmp     rcx, rdx
0x14007eca7  jz      short loc_14007ECCB
0x14007eca9  test    [rcx+1Ch], r13b
0x14007ecad  jz      short loc_14007ECCB
0x14007ecaf  cmp     byte ptr [rcx+19h], 3
0x14007ecb3  jb      short loc_14007ECCB
0x14007ecb5  mov     rcx, [rcx+10h]
0x14007ecb9  mov     edx, 9Ah
0x14007ecbe  mov     r9d, eax
0x14007ecc1  mov     dword ptr [rsp+490h+var_470], r14d
0x14007ecc6  call    WPP_SF_lL
0x14007eccb  mov     rcx, rsi; hKey
0x14007ecce  call    cs:__imp_RegCloseKey
0x14007ecd4  lea     rsi, WPP_GLOBAL_Control
0x14007ecdb  test    ebx, ebx
0x14007ecdd  jz      short loc_14007ED1F
0x14007ecdf  cmp     r12d, 1
0x14007ece3  jnz     short loc_14007ED1F
0x14007ece5  mov     ecx, r15d
0x14007ece8  call    DeleteDeviceEntry
0x14007eced  test    eax, eax
0x14007ecef  jz      short loc_14007ED1F
0x14007ecf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ecf8  cmp     rcx, rsi
0x14007ecfb  jz      short loc_14007ED1F
0x14007ecfd  test    [rcx+1Ch], r13b
0x14007ed01  jz      short loc_14007ED1F
0x14007ed03  cmp     [rcx+19h], r13b
0x14007ed07  jb      short loc_14007ED1F
0x14007ed09  mov     edx, 9Bh
0x14007ed0e  mov     dword ptr [rsp+490h+var_470], r15d
0x14007ed13  mov     rcx, [rcx+10h]
0x14007ed17  mov     r9d, eax
0x14007ed1a  call    WPP_SF_lL
0x14007ed1f  mov     ecx, r14d
0x14007ed22  call    DeleteCacheEntry
0x14007ed27  mov     eax, ebx
0x14007ed29  mov     rcx, [rbp+390h+var_40]
0x14007ed30  xor     rcx, rsp; StackCookie
0x14007ed33  call    __security_check_cookie
0x14007ed38  mov     rbx, [rsp+490h+arg_10]
0x14007ed40  add     rsp, 460h
0x14007ed47  pop     r15
  ... truncated ...
```
