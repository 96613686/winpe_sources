# FindCacheEntryByTapiPermanentLineID

- ea: `0x1400815a0`
- end: `0x140081a41`
- name: `FindCacheEntryByTapiPermanentLineID`
- size: `1185`
- prototype: `__int64 __usercall@<rax>(DWORD cbData@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004c1a4`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x14006998c`
- `0x140073d5c`
- `0x140074cb4`
- `0x140074f18`
- `0x1400815a0`
- `0x140081f4c`
- `0x140083acc`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140081762`
- `ADVAPI32!RegCloseKey` at `0x140081827`
- `ADVAPI32!RegCloseKey` at `0x140081a03`
- `ADVAPI32!RegCloseKey` at `0x140081762`
- `ADVAPI32!RegCloseKey` at `0x140081827`
- `ADVAPI32!RegCloseKey` at `0x140081a03`
- `KERNEL32!SetLastError` at `0x140081699`
- `KERNEL32!SetLastError` at `0x140081699`

## string_xrefs

- `0x140081633`: `Software\Microsoft\Fax\Devices Cache`
- `0x140081781`: `Software\Microsoft\Fax\Devices Cache`

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
0x1400815a0  mov     [rsp-8+arg_8], rbx
0x1400815a5  push    rbp
0x1400815a6  push    rsi
0x1400815a7  push    rdi
0x1400815a8  push    r12
0x1400815aa  push    r13
0x1400815ac  push    r14
0x1400815ae  push    r15
0x1400815b0  lea     rbp, [rsp-160h]
0x1400815b8  sub     rsp, 260h
0x1400815bf  mov     rax, cs:__security_cookie
0x1400815c6  xor     rax, rsp
0x1400815c9  mov     [rbp+190h+var_40], rax
0x1400815d0  mov     rax, [rbp+190h+arg_20]
0x1400815d7  xor     esi, esi
0x1400815d9  mov     [rsp+290h+var_258], rax
0x1400815de  mov     r12, r9
0x1400815e1  mov     dword ptr [rsp+290h+Data], esi
0x1400815e5  mov     rdi, r8
0x1400815e8  mov     r14, rdx
0x1400815eb  mov     r13d, ecx
0x1400815ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400815f5  lea     r15, WPP_GLOBAL_Control
0x1400815fc  cmp     rcx, r15
0x1400815ff  jz      short loc_140081622
0x140081601  test    byte ptr [rcx+1Ch], 2
0x140081605  jz      short loc_140081622
0x140081607  cmp     byte ptr [rcx+19h], 5
0x14008160b  jb      short loc_140081622
0x14008160d  mov     rcx, [rcx+10h]
0x140081611  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081618  mov     edx, 9Dh
0x14008161d  call    WPP_SF_
0x140081622  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140081629  mov     edx, 104h; unsigned __int64
0x14008162e  mov     [rsp+290h+var_268], rax
0x140081633  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14008163a  lea     r8, aS08lxS; "%s\\%08lx\\%s"
0x140081641  mov     dword ptr [rsp+290h+cbData], r13d; cbData
0x140081646  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x14008164b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140081650  mov     ebx, eax
0x140081652  test    eax, eax
0x140081654  jns     short loc_1400816AC
0x140081656  mov     rcx, cs:WPP_GLOBAL_Control
0x14008165d  cmp     rcx, r15
0x140081660  jz      short loc_140081686
0x140081662  test    byte ptr [rcx+1Ch], 2
0x140081666  jz      short loc_140081686
0x140081668  cmp     byte ptr [rcx+19h], 2
0x14008166c  jb      short loc_140081686
0x14008166e  mov     rcx, [rcx+10h]
0x140081672  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081679  mov     edx, 9Eh
0x14008167e  mov     r9d, eax
0x140081681  call    WPP_SF_d
0x140081686  mov     eax, ebx
0x140081688  and     eax, 1FFF0000h
0x14008168d  cmp     eax, 70000h
0x140081692  jnz     short loc_140081697
0x140081694  movzx   ebx, bx
0x140081697  mov     ecx, ebx; dwErrCode
0x140081699  call    cs:__imp_SetLastError
0x1400816a0  nop     dword ptr [rax+rax+00h]
0x1400816a5  xor     eax, eax
0x1400816a7  jmp     loc_140081A16
0x1400816ac  mov     r9d, 20019h
0x1400816b2  lea     rdx, [rsp+290h+var_250]
0x1400816b7  xor     r8d, r8d
0x1400816ba  mov     rcx, 0FFFFFFFF80000002h
0x1400816c1  call    OpenRegistryKey
0x1400816c6  mov     r15, rax
0x1400816c9  test    rax, rax
0x1400816cc  jz      short loc_1400816A5
0x1400816ce  xor     r9d, r9d; unsigned __int16 *
0x1400816d1  lea     r8, aDeviceName; "Device Name"
0x1400816d8  mov     rcx, rax; hKey
0x1400816db  lea     edx, [r9+1]; dwType
0x1400816df  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1400816e4  mov     rbx, rax
0x1400816e7  test    rax, rax
0x1400816ea  jz      short loc_140081758
0x1400816ec  mov     r9, rax
0x1400816ef  sub     r9, r14
0x1400816f2  movzx   r8d, word ptr [r14]
0x1400816f6  movzx   edx, word ptr [r14+r9]
0x1400816fb  sub     r8d, edx
0x1400816fe  jnz     short loc_140081708
0x140081700  add     r14, 2
0x140081704  test    edx, edx
0x140081706  jnz     short loc_1400816F2
0x140081708  test    r8d, r8d
0x14008170b  jnz     short loc_140081758
0x14008170d  lea     rdx, [rsp+290h+Data]
0x140081712  mov     rcx, r12
0x140081715  call    GetNewServiceDeviceID
0x14008171a  test    eax, eax
0x14008171c  jz      short loc_140081754
0x14008171e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081725  lea     r12, WPP_GLOBAL_Control
0x14008172c  cmp     rcx, r12
0x14008172f  jz      short loc_14008175F
0x140081731  test    byte ptr [rcx+1Ch], 2
0x140081735  jz      short loc_14008175F
0x140081737  cmp     byte ptr [rcx+19h], 2
0x14008173b  jb      short loc_14008175F
0x14008173d  mov     rcx, [rcx+10h]
0x140081741  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140081748  mov     edx, 9Fh
0x14008174d  call    WPP_SF_
0x140081752  jmp     short loc_14008175F
0x140081754  mov     esi, dword ptr [rsp+290h+Data]
0x140081758  lea     r12, WPP_GLOBAL_Control
0x14008175f  mov     rcx, r15; hKey
0x140081762  call    cs:__imp_RegCloseKey
0x140081769  nop     dword ptr [rax+rax+00h]
0x14008176e  mov     rcx, rbx; lpMem
0x140081771  call    pMemFree
0x140081776  xor     r15d, r15d
0x140081779  test    esi, esi
0x14008177b  jz      loc_140081A14
0x140081781  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x140081788  mov     dword ptr [rsp+290h+cbData], r13d
0x14008178d  lea     r8, aS08lx; "%s\\%08lx"
0x140081794  mov     edx, 104h; unsigned __int64
0x140081799  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x14008179e  mov     r14d, r15d
0x1400817a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400817a6  test    eax, eax
0x1400817a8  jns     short loc_1400817DC
0x1400817aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400817b1  cmp     rcx, r12
0x1400817b4  jz      short loc_140081833
0x1400817b6  test    byte ptr [rcx+1Ch], 2
0x1400817ba  jz      short loc_140081833
0x1400817bc  cmp     byte ptr [rcx+19h], 2
0x1400817c0  jb      short loc_140081833
0x1400817c2  mov     rcx, [rcx+10h]
0x1400817c6  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400817cd  mov     edx, 0A0h
0x1400817d2  mov     r9d, eax
0x1400817d5  call    WPP_SF_d
0x1400817da  jmp     short loc_140081833
0x1400817dc  mov     r9d, 20019h
0x1400817e2  lea     rdx, [rsp+290h+var_250]
0x1400817e7  xor     r8d, r8d
0x1400817ea  mov     rcx, 0FFFFFFFF80000002h
0x1400817f1  call    OpenRegistryKey
0x1400817f6  mov     rbx, rax
0x1400817f9  test    rax, rax
0x1400817fc  jz      short loc_140081833
0x1400817fe  xor     r9d, r9d
0x140081801  mov     dword ptr [rsp+290h+Data], r15d
0x140081806  lea     r8, [rsp+290h+Data]; lpData
0x14008180b  mov     rcx, rax; hKey
0x14008180e  lea     rdx, aManualanswer; "ManualAnswer"
0x140081815  call    GetRegistryDwordDefault
0x14008181a  neg     eax
0x14008181c  mov     rcx, rbx; hKey
0x14008181f  sbb     r14d, r14d
0x140081822  and     r14d, dword ptr [rsp+290h+Data]
0x140081827  call    cs:__imp_RegCloseKey
0x14008182e  nop     dword ptr [rax+rax+00h]
0x140081833  mov     rax, [rsp+290h+var_258]
0x140081838  mov     edx, r13d
0x14008183b  mov     ecx, esi
0x14008183d  mov     [rax], r14d
0x140081840  call    RestoreDeviceRegFromDeviceCache
0x140081845  test    eax, eax
0x140081847  jnz     loc_140081A11
0x14008184d  lea     rax, aF10a5326026147; "{F10A5326-0261-4715-B367-2970427BBD99}"
0x140081854  mov     edx, 104h; unsigned __int64
0x140081859  mov     [rsp+290h+var_268], rax
0x14008185e  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Fax\\Devices"
0x140081865  lea     r8, aS010luS; "%s\\%010lu\\%s"
0x14008186c  mov     dword ptr [rsp+290h+cbData], esi; cbData
0x140081870  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x140081875  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008187a  test    eax, eax
0x14008187c  jns     short loc_1400818BF
0x14008187e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081885  cmp     rcx, r12
0x140081888  jz      loc_140081A14
0x14008188e  test    byte ptr [rcx+1Ch], 2
0x140081892  jz      loc_140081A14
0x140081898  cmp     byte ptr [rcx+19h], 2
0x14008189c  jb      loc_140081A14
0x1400818a2  mov     rcx, [rcx+10h]
0x1400818a6  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1400818ad  mov     edx, 0A1h
0x1400818b2  mov     r9d, eax
0x1400818b5  call    WPP_SF_d
0x1400818ba  jmp     loc_140081A14
0x1400818bf  mov     r9d, 20019h
0x1400818c5  lea     rdx, [rsp+290h+var_250]
0x1400818ca  xor     r8d, r8d
0x1400818cd  mov     rcx, 0FFFFFFFF80000002h
0x1400818d4  call    OpenRegistryKey
0x1400818d9  mov     rbx, rax
0x1400818dc  test    rax, rax
0x1400818df  jnz     short loc_140081924
0x1400818e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400818e8  cmp     rcx, r12
0x1400818eb  jz      loc_140081A14
0x1400818f1  test    byte ptr [rcx+1Ch], 2
0x1400818f5  jz      loc_140081A14
0x1400818fb  cmp     byte ptr [rcx+19h], 2
0x1400818ff  jb      loc_140081A14
0x140081905  mov     rcx, [rcx+10h]
0x140081909  lea     r9, [rsp+290h+var_250]
0x14008190e  mov     edx, 0A2h
0x140081913  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14008191a  call    WPP_SF_S
0x14008191f  jmp     loc_140081A14
0x140081924  mov     r12d, 1
0x14008192a  lea     r9, SubsystemName; "Fax"
0x140081931  mov     edx, r12d; dwType
0x140081934  lea     r8, aCsid; "CSID"
0x14008193b  mov     rcx, rbx; hKey
0x14008193e  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x140081943  mov     r14, rax
0x140081946  test    rax, rax
0x140081949  jz      short loc_140081956
0x14008194b  mov     rcx, [rdi]; lpMem
0x14008194e  call    pMemFree
0x140081953  mov     [rdi], r14
0x140081956  lea     r9, SubsystemName; "Fax"
0x14008195d  mov     edx, r12d; dwType
0x140081960  lea     r8, aTsid; "TSID"
0x140081967  mov     rcx, rbx; hKey
0x14008196a  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14008196f  mov     r14, rax
0x140081972  test    rax, rax
0x140081975  jz      short loc_140081984
0x140081977  mov     rcx, [rdi+8]; lpMem
0x14008197b  call    pMemFree
0x140081980  mov     [rdi+8], r14
0x140081984  lea     r9, Class; unsigned __int16 *
0x14008198b  mov     edx, r12d; dwType
0x14008198e  lea     r8, szDataDescr; "Description"
0x140081995  mov     rcx, rbx; hKey
0x140081998  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14008199d  mov     r14, rax
0x1400819a0  test    rax, rax
0x1400819a3  jz      short loc_1400819B2
0x1400819a5  mov     rcx, [rdi+10h]; lpMem
0x1400819a9  call    pMemFree
0x1400819ae  mov     [rdi+10h], r14
0x1400819b2  xor     r9d, r9d
0x1400819b5  mov     dword ptr [rsp+290h+Data], r15d
0x1400819ba  lea     r8, [rsp+290h+Data]; lpData
0x1400819bf  mov     rcx, rbx; hKey
0x1400819c2  lea     rdx, aFlags; "Flags"
0x1400819c9  call    GetRegistryDwordDefault
0x1400819ce  neg     eax
0x1400819d0  lea     r8, [rsp+290h+Data]; lpData
0x1400819d5  lea     rdx, aRings; "Rings"
0x1400819dc  sbb     ecx, ecx
0x1400819de  xor     r9d, r9d
0x1400819e1  and     ecx, dword ptr [rsp+290h+Data]
0x1400819e5  mov     [rdi+1Ch], ecx
0x1400819e8  mov     rcx, rbx; hKey
0x1400819eb  mov     dword ptr [rsp+290h+Data], r15d
0x1400819f0  call    GetRegistryDwordDefault
0x1400819f5  neg     eax
0x1400819f7  sbb     ecx, ecx
0x1400819f9  and     ecx, dword ptr [rsp+290h+Data]
0x1400819fd  mov     [rdi+18h], ecx
0x140081a00  mov     rcx, rbx; hKey
0x140081a03  call    cs:__imp_RegCloseKey
0x140081a0a  nop     dword ptr [rax+rax+00h]
0x140081a0f  jmp     short loc_140081A14
0x140081a11  mov     esi, r15d
0x140081a14  mov     eax, esi
0x140081a16  mov     rcx, [rbp+190h+var_40]
0x140081a1d  xor     rcx, rsp; StackCookie
0x140081a20  call    __security_check_cookie
0x140081a25  mov     rbx, [rsp+290h+arg_8]
0x140081a2d  add     rsp, 260h
0x140081a34  pop     r15
0x140081a36  pop     r14
0x140081a38  pop     r13
0x140081a3a  pop     r12
0x140081a3c  pop     rdi
0x140081a3d  pop     rsi
0x140081a3e  pop     rbp
0x140081a3f  retn
```
