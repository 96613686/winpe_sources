# FindCacheEntryByTapiPermanentLineID

- ea: `0x14007c450`
- end: `0x14007c8d8`
- name: `FindCacheEntryByTapiPermanentLineID`
- size: `1160`
- prototype: `__int64 __usercall@<rax>(DWORD cbData@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400492fc`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140065dbc`
- `0x14006f808`
- `0x140070684`
- `0x1400708c4`
- `0x14007c450`
- `0x14007cdc4`
- `0x14007e844`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007c60c`
- `ADVAPI32!RegCloseKey` at `0x14007c6cb`
- `ADVAPI32!RegCloseKey` at `0x14007c8a1`
- `ADVAPI32!RegCloseKey` at `0x14007c60c`
- `ADVAPI32!RegCloseKey` at `0x14007c6cb`
- `ADVAPI32!RegCloseKey` at `0x14007c8a1`
- `KERNEL32!SetLastError` at `0x14007c549`
- `KERNEL32!SetLastError` at `0x14007c549`

## string_xrefs

- `0x14007c4e3`: `Software\Microsoft\Fax\Devices Cache`
- `0x14007c625`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall FindCacheEntryByTapiPermanentLineID(DWORD cbData, BYTE *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  DWORD v5; // esi
  int v10; // eax
  DWORD v11; // ebx
  HKEY v13; // rax
  HKEY v14; // r15
  BYTE *RegistryStringValue; // rax
  BYTE *v16; // rbx
  signed __int64 v17; // r9
  int v18; // edx
  int v19; // r8d
  int v20; // r14d
  int v21; // eax
  HKEY v22; // rax
  HKEY v23; // rbx
  int RegistryDwordDefault; // eax
  int v25; // eax
  HKEY v26; // rax
  HKEY v27; // rbx
  BYTE *v28; // r14
  BYTE *v29; // r14
  BYTE *v30; // r14
  int v31; // eax
  int v32; // eax
  DWORD cbDataa; // [rsp+20h] [rbp-E0h]
  __int64 cbDatab; // [rsp+20h] [rbp-E0h]
  DWORD cbDatac; // [rsp+20h] [rbp-E0h]
  DWORD cbDatad; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v38; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v39[264]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = 0;
  v38 = a5;
  *(_DWORD *)Data = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v10 = StringCchPrintfW(
          v39,
          0x104u,
          L"%s\\%08lx\\%s",
          L"Software\\Microsoft\\Fax\\Devices Cache",
          cbData,
          L"{F10A5326-0261-4715-B367-2970427BBD99}");
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        158,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v10);
    }
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    SetLastError(v11);
    return 0;
  }
  v13 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v39, 0, 0x20019u);
  v14 = v13;
  if ( !v13 )
    return 0;
  RegistryStringValue = GetRegistryStringValue(v13, 1u, L"Device Name", 0, cbDataa);
  v16 = RegistryStringValue;
  if ( RegistryStringValue )
  {
    v17 = RegistryStringValue - a2;
    do
    {
      v18 = *(unsigned __int16 *)&a2[v17];
      v19 = *(unsigned __int16 *)a2 - v18;
      if ( v19 )
        break;
      a2 += 2;
    }
    while ( v18 );
    if ( !v19 )
    {
      if ( (unsigned int)GetNewServiceDeviceID(a4, Data) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
        }
      }
      else
      {
        v5 = *(_DWORD *)Data;
      }
    }
  }
  RegCloseKey(v14);
  pMemFree(v16);
  if ( v5 )
  {
    LODWORD(cbDatab) = cbData;
    v20 = 0;
    v21 = StringCchPrintfW(v39, 0x104u, L"%s\\%08lx", L"Software\\Microsoft\\Fax\\Devices Cache", cbDatab);
    if ( v21 >= 0 )
    {
      v22 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v39, 0, 0x20019u);
      v23 = v22;
      if ( v22 )
      {
        *(_DWORD *)Data = 0;
        RegistryDwordDefault = GetRegistryDwordDefault(v22, L"ManualAnswer", Data, 0);
        v20 = RegistryDwordDefault != 0 ? *(_DWORD *)Data : 0;
        RegCloseKey(v23);
      }
    }
    else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v21);
    }
    *v38 = v20;
    if ( (unsigned int)RestoreDeviceRegFromDeviceCache(v5, cbData) )
    {
      return 0;
    }
    else
    {
      v25 = StringCchPrintfW(v39, 0x104u, L"%s\\%010lu\\%s", L"Software\\Microsoft\\Fax\\Devices");
      if ( v25 >= 0 )
      {
        v26 = OpenRegistryKey(HKEY_LOCAL_MACHINE, v39, 0, 0x20019u);
        v27 = v26;
        if ( v26 )
        {
          v28 = GetRegistryStringValue(v26, 1u, L"CSID", L"Fax", v5);
          if ( v28 )
          {
            pMemFree(*(LPVOID *)a3);
            *(_QWORD *)a3 = v28;
          }
          v29 = GetRegistryStringValue(v27, 1u, L"TSID", L"Fax", cbDatac);
          if ( v29 )
          {
            pMemFree(*(LPVOID *)(a3 + 8));
            *(_QWORD *)(a3 + 8) = v29;
          }
          v30 = GetRegistryStringValue(v27, 1u, L"Description", &Class, cbDatad);
          if ( v30 )
          {
            pMemFree(*(LPVOID *)(a3 + 16));
            *(_QWORD *)(a3 + 16) = v30;
          }
          *(_DWORD *)Data = 0;
          v31 = GetRegistryDwordDefault(v27, L"Flags", Data, 0);
          *(_DWORD *)(a3 + 28) = v31 != 0 ? *(_DWORD *)Data : 0;
          *(_DWORD *)Data = 0;
          v32 = GetRegistryDwordDefault(v27, L"Rings", Data, 0);
          *(_DWORD *)(a3 + 24) = v32 != 0 ? *(_DWORD *)Data : 0;
          RegCloseKey(v27);
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v39);
        }
      }
      else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
          (unsigned int)v25);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14007c450  mov     [rsp-8+arg_8], rbx
0x14007c455  push    rbp
0x14007c456  push    rsi
0x14007c457  push    rdi
0x14007c458  push    r12
0x14007c45a  push    r13
0x14007c45c  push    r14
0x14007c45e  push    r15
0x14007c460  lea     rbp, [rsp-160h]
0x14007c468  sub     rsp, 260h
0x14007c46f  mov     rax, cs:__security_cookie
0x14007c476  xor     rax, rsp
0x14007c479  mov     [rbp+190h+var_40], rax
0x14007c480  mov     rax, [rbp+190h+arg_20]
0x14007c487  xor     esi, esi
0x14007c489  mov     [rsp+290h+var_258], rax
0x14007c48e  mov     r12, r9
0x14007c491  mov     dword ptr [rsp+290h+Data], esi
0x14007c495  mov     rdi, r8
0x14007c498  mov     r14, rdx
0x14007c49b  mov     r13d, ecx
0x14007c49e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c4a5  lea     r15, WPP_GLOBAL_Control
0x14007c4ac  cmp     rcx, r15
0x14007c4af  jz      short loc_14007C4D2
0x14007c4b1  test    byte ptr [rcx+1Ch], 2
0x14007c4b5  jz      short loc_14007C4D2
0x14007c4b7  cmp     byte ptr [rcx+19h], 5
0x14007c4bb  jb      short loc_14007C4D2
0x14007c4bd  mov     rcx, [rcx+10h]
0x14007c4c1  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c4c8  mov     edx, 9Dh
0x14007c4cd  call    WPP_SF_
0x14007c4d2  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007c4d9  mov     edx, 104h; unsigned __int64
0x14007c4de  mov     [rsp+290h+var_268], rax
0x14007c4e3  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007c4ea  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x14007c4f1  mov     dword ptr [rsp+290h+cbData], r13d; cbData
0x14007c4f6  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x14007c4fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007c500  mov     ebx, eax
0x14007c502  test    eax, eax
0x14007c504  jns     short loc_14007C556
0x14007c506  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c50d  cmp     rcx, r15
0x14007c510  jz      short loc_14007C536
0x14007c512  test    byte ptr [rcx+1Ch], 2
0x14007c516  jz      short loc_14007C536
0x14007c518  cmp     byte ptr [rcx+19h], 2
0x14007c51c  jb      short loc_14007C536
0x14007c51e  mov     rcx, [rcx+10h]
0x14007c522  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c529  mov     edx, 9Eh
0x14007c52e  mov     r9d, eax
0x14007c531  call    WPP_SF_d
0x14007c536  mov     eax, ebx
0x14007c538  and     eax, 1FFF0000h
0x14007c53d  cmp     eax, 70000h
0x14007c542  jnz     short loc_14007C547
0x14007c544  movzx   ebx, bx
0x14007c547  mov     ecx, ebx; dwErrCode
0x14007c549  call    cs:__imp_SetLastError
0x14007c54f  xor     eax, eax
0x14007c551  jmp     loc_14007C8AE
0x14007c556  mov     r9d, 20019h
0x14007c55c  lea     rdx, [rsp+290h+var_250]
0x14007c561  xor     r8d, r8d
0x14007c564  mov     rcx, 0FFFFFFFF80000002h
0x14007c56b  call    OpenRegistryKey
0x14007c570  mov     r15, rax
0x14007c573  test    rax, rax
0x14007c576  jz      short loc_14007C54F
0x14007c578  xor     r9d, r9d; unsigned __int16 *
0x14007c57b  lea     r8, aDeviceName; "Device Name"
0x14007c582  mov     rcx, rax; hKey
0x14007c585  lea     edx, [r9+1]; dwType
0x14007c589  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007c58e  mov     rbx, rax
0x14007c591  test    rax, rax
0x14007c594  jz      short loc_14007C602
0x14007c596  mov     r9, rax
0x14007c599  sub     r9, r14
0x14007c59c  movzx   r8d, word ptr [r14]
0x14007c5a0  movzx   edx, word ptr [r14+r9]
0x14007c5a5  sub     r8d, edx
0x14007c5a8  jnz     short loc_14007C5B2
0x14007c5aa  add     r14, 2
0x14007c5ae  test    edx, edx
0x14007c5b0  jnz     short loc_14007C59C
0x14007c5b2  test    r8d, r8d
0x14007c5b5  jnz     short loc_14007C602
0x14007c5b7  lea     rdx, [rsp+290h+Data]
0x14007c5bc  mov     rcx, r12
0x14007c5bf  call    GetNewServiceDeviceID
0x14007c5c4  test    eax, eax
0x14007c5c6  jz      short loc_14007C5FE
0x14007c5c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c5cf  lea     r12, WPP_GLOBAL_Control
0x14007c5d6  cmp     rcx, r12
0x14007c5d9  jz      short loc_14007C609
0x14007c5db  test    byte ptr [rcx+1Ch], 2
0x14007c5df  jz      short loc_14007C609
0x14007c5e1  cmp     byte ptr [rcx+19h], 2
0x14007c5e5  jb      short loc_14007C609
0x14007c5e7  mov     rcx, [rcx+10h]
0x14007c5eb  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c5f2  mov     edx, 9Fh
0x14007c5f7  call    WPP_SF_
0x14007c5fc  jmp     short loc_14007C609
0x14007c5fe  mov     esi, dword ptr [rsp+290h+Data]
0x14007c602  lea     r12, WPP_GLOBAL_Control
0x14007c609  mov     rcx, r15; hKey
0x14007c60c  call    cs:__imp_RegCloseKey
0x14007c612  mov     rcx, rbx; lpMem
0x14007c615  call    pMemFree
0x14007c61a  xor     r15d, r15d
0x14007c61d  test    esi, esi
0x14007c61f  jz      loc_14007C8AC
0x14007c625  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14007c62c  mov     dword ptr [rsp+290h+cbData], r13d
0x14007c631  lea     r8, aS08lx; "%s\\%08lx"
0x14007c638  mov     edx, 104h; unsigned __int64
0x14007c63d  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x14007c642  mov     r14d, r15d
0x14007c645  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007c64a  test    eax, eax
0x14007c64c  jns     short loc_14007C680
0x14007c64e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c655  cmp     rcx, r12
0x14007c658  jz      short loc_14007C6D1
0x14007c65a  test    byte ptr [rcx+1Ch], 2
0x14007c65e  jz      short loc_14007C6D1
0x14007c660  cmp     byte ptr [rcx+19h], 2
0x14007c664  jb      short loc_14007C6D1
0x14007c666  mov     rcx, [rcx+10h]
0x14007c66a  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c671  mov     edx, 0A0h
0x14007c676  mov     r9d, eax
0x14007c679  call    WPP_SF_d
0x14007c67e  jmp     short loc_14007C6D1
0x14007c680  mov     r9d, 20019h
0x14007c686  lea     rdx, [rsp+290h+var_250]
0x14007c68b  xor     r8d, r8d
0x14007c68e  mov     rcx, 0FFFFFFFF80000002h
0x14007c695  call    OpenRegistryKey
0x14007c69a  mov     rbx, rax
0x14007c69d  test    rax, rax
0x14007c6a0  jz      short loc_14007C6D1
0x14007c6a2  xor     r9d, r9d
0x14007c6a5  mov     dword ptr [rsp+290h+Data], r15d
0x14007c6aa  lea     r8, [rsp+290h+Data]; lpData
0x14007c6af  mov     rcx, rax; hKey
0x14007c6b2  lea     rdx, aManualanswer; "ManualAnswer"
0x14007c6b9  call    GetRegistryDwordDefault
0x14007c6be  neg     eax
0x14007c6c0  mov     rcx, rbx; hKey
0x14007c6c3  sbb     r14d, r14d
0x14007c6c6  and     r14d, dword ptr [rsp+290h+Data]
0x14007c6cb  call    cs:__imp_RegCloseKey
0x14007c6d1  mov     rax, [rsp+290h+var_258]
0x14007c6d6  mov     edx, r13d
0x14007c6d9  mov     ecx, esi
0x14007c6db  mov     [rax], r14d
0x14007c6de  call    RestoreDeviceRegFromDeviceCache
0x14007c6e3  test    eax, eax
0x14007c6e5  jnz     loc_14007C8A9
0x14007c6eb  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x14007c6f2  mov     edx, 104h; unsigned __int64
0x14007c6f7  mov     [rsp+290h+var_268], rax
0x14007c6fc  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x14007c703  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x14007c70a  mov     dword ptr [rsp+290h+cbData], esi; cbData
0x14007c70e  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x14007c713  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007c718  test    eax, eax
0x14007c71a  jns     short loc_14007C75D
0x14007c71c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c723  cmp     rcx, r12
0x14007c726  jz      loc_14007C8AC
0x14007c72c  test    byte ptr [rcx+1Ch], 2
0x14007c730  jz      loc_14007C8AC
0x14007c736  cmp     byte ptr [rcx+19h], 2
0x14007c73a  jb      loc_14007C8AC
0x14007c740  mov     rcx, [rcx+10h]
0x14007c744  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c74b  mov     edx, 0A1h
0x14007c750  mov     r9d, eax
0x14007c753  call    WPP_SF_d
0x14007c758  jmp     loc_14007C8AC
0x14007c75d  mov     r9d, 20019h
0x14007c763  lea     rdx, [rsp+290h+var_250]
0x14007c768  xor     r8d, r8d
0x14007c76b  mov     rcx, 0FFFFFFFF80000002h
0x14007c772  call    OpenRegistryKey
0x14007c777  mov     rbx, rax
0x14007c77a  test    rax, rax
0x14007c77d  jnz     short loc_14007C7C2
0x14007c77f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c786  cmp     rcx, r12
0x14007c789  jz      loc_14007C8AC
0x14007c78f  test    byte ptr [rcx+1Ch], 2
0x14007c793  jz      loc_14007C8AC
0x14007c799  cmp     byte ptr [rcx+19h], 2
0x14007c79d  jb      loc_14007C8AC
0x14007c7a3  mov     rcx, [rcx+10h]
0x14007c7a7  lea     r9, [rsp+290h+var_250]
0x14007c7ac  mov     edx, 0A2h
0x14007c7b1  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c7b8  call    WPP_SF_S
0x14007c7bd  jmp     loc_14007C8AC
0x14007c7c2  mov     r12d, 1
0x14007c7c8  lea     r9, SubsystemName; "Fax"
0x14007c7cf  mov     edx, r12d; dwType
0x14007c7d2  lea     r8, aCsid; "CSID"
0x14007c7d9  mov     rcx, rbx; hKey
0x14007c7dc  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007c7e1  mov     r14, rax
0x14007c7e4  test    rax, rax
0x14007c7e7  jz      short loc_14007C7F4
0x14007c7e9  mov     rcx, [rdi]; lpMem
0x14007c7ec  call    pMemFree
0x14007c7f1  mov     [rdi], r14
0x14007c7f4  lea     r9, SubsystemName; "Fax"
0x14007c7fb  mov     edx, r12d; dwType
0x14007c7fe  lea     r8, aTsid; "TSID"
0x14007c805  mov     rcx, rbx; hKey
0x14007c808  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007c80d  mov     r14, rax
0x14007c810  test    rax, rax
0x14007c813  jz      short loc_14007C822
0x14007c815  mov     rcx, [rdi+8]; lpMem
0x14007c819  call    pMemFree
0x14007c81e  mov     [rdi+8], r14
0x14007c822  lea     r9, Class; unsigned __int16 *
0x14007c829  mov     edx, r12d; dwType
0x14007c82c  lea     r8, szDataDescr; "Description"
0x14007c833  mov     rcx, rbx; hKey
0x14007c836  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007c83b  mov     r14, rax
0x14007c83e  test    rax, rax
0x14007c841  jz      short loc_14007C850
0x14007c843  mov     rcx, [rdi+10h]; lpMem
0x14007c847  call    pMemFree
0x14007c84c  mov     [rdi+10h], r14
0x14007c850  xor     r9d, r9d
0x14007c853  mov     dword ptr [rsp+290h+Data], r15d
0x14007c858  lea     r8, [rsp+290h+Data]; lpData
0x14007c85d  mov     rcx, rbx; hKey
0x14007c860  lea     rdx, aFlags; "Flags"
0x14007c867  call    GetRegistryDwordDefault
0x14007c86c  neg     eax
0x14007c86e  lea     r8, [rsp+290h+Data]; lpData
0x14007c873  lea     rdx, aRings; "Rings"
0x14007c87a  sbb     ecx, ecx
0x14007c87c  xor     r9d, r9d
0x14007c87f  and     ecx, dword ptr [rsp+290h+Data]
0x14007c883  mov     [rdi+1Ch], ecx
0x14007c886  mov     rcx, rbx; hKey
0x14007c889  mov     dword ptr [rsp+290h+Data], r15d
0x14007c88e  call    GetRegistryDwordDefault
0x14007c893  neg     eax
0x14007c895  sbb     ecx, ecx
0x14007c897  and     ecx, dword ptr [rsp+290h+Data]
0x14007c89b  mov     [rdi+18h], ecx
0x14007c89e  mov     rcx, rbx; hKey
0x14007c8a1  call    cs:__imp_RegCloseKey
0x14007c8a7  jmp     short loc_14007C8AC
0x14007c8a9  mov     esi, r15d
0x14007c8ac  mov     eax, esi
0x14007c8ae  mov     rcx, [rbp+190h+var_40]
0x14007c8b5  xor     rcx, rsp; StackCookie
0x14007c8b8  call    __security_check_cookie
0x14007c8bd  mov     rbx, [rsp+290h+arg_8]
0x14007c8c5  add     rsp, 260h
0x14007c8cc  pop     r15
0x14007c8ce  pop     r14
0x14007c8d0  pop     r13
0x14007c8d2  pop     r12
0x14007c8d4  pop     rdi
0x14007c8d5  pop     rsi
0x14007c8d6  pop     rbp
0x14007c8d7  retn
```
