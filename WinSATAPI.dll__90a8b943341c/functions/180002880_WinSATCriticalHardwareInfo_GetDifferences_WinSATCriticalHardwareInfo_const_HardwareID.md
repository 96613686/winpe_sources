# WinSATCriticalHardwareInfo::GetDifferences(WinSATCriticalHardwareInfo const &,HardwareID)

- ea: `0x180002880`
- end: `0x180002f64`
- name: `?GetDifferences@WinSATCriticalHardwareInfo@@QEBA?AW4HardwareID@@AEBU1@W42@@Z`
- size: `1764`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002690`

## callees

- `0x180002880`
- `0x18000d710`
- `0x18000f0e8`
- `0x18002bfac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002b6b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002b6b`
- `KERNEL32!lstrcmpW` at `0x180002d9f`
- `KERNEL32!lstrcmpW` at `0x180002ea9`
- `KERNEL32!lstrcmpW` at `0x180002d9f`
- `KERNEL32!lstrcmpW` at `0x180002ea9`

## string_xrefs

- `0x1800028df`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002939`: `base\winsat\common\loadrecentresults.cpp`
- `0x1800029c5`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002a2a`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002a5b`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002a8e`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002bef`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002c4e`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002cdf`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002d4f`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002d80`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002dc4`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002dff`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002e40`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002e78`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002ed1`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002f18`: `base\winsat\common\loadrecentresults.cpp`
- `0x180002f3a`: `base\winsat\common\loadrecentresults.cpp`

## pseudocode

```c
__int64 __fastcall WinSATCriticalHardwareInfo::GetDifferences(__int64 a1, __int64 a2, __int16 a3)
{
  __int16 v4; // bx
  signed int v5; // edi
  unsigned int v7; // r14d
  __int64 v8; // r8
  __int64 v9; // r13
  __int64 v10; // r8
  signed int v11; // r14d
  __int64 v12; // r15
  int v13; // r9d
  int v14; // r9d
  __int64 v15; // r9
  unsigned __int64 v16; // r12
  __int64 i; // rdx
  __int64 v18; // rcx
  _DWORD *v19; // r8
  __int64 v20; // rcx
  unsigned __int64 *v21; // rax
  unsigned __int64 v22; // rcx
  const WCHAR *lpString2; // r9
  unsigned __int64 *v24; // rax
  unsigned __int64 cchCount2; // rdx
  const WCHAR *v26; // r8
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // r15
  signed int v30; // ebx
  __int64 v31; // r8
  __int64 v32; // r15
  __int64 v33; // r9
  int v34; // r9d
  __int64 v35; // r9
  __int64 v37; // [rsp+30h] [rbp-78h]
  __int64 v38; // [rsp+38h] [rbp-70h]
  __int64 v39; // [rsp+40h] [rbp-68h]
  _DWORD *v40; // [rsp+50h] [rbp-58h]
  __int64 v41; // [rsp+58h] [rbp-50h]
  unsigned __int64 v42; // [rsp+60h] [rbp-48h]
  unsigned __int64 v43; // [rsp+68h] [rbp-40h]
  _DWORD *v45; // [rsp+C8h] [rbp+20h]

  v4 = a3;
  v5 = 0;
  v7 = 0;
  if ( (a3 & 1) != 0 && !(unsigned __int8)EqualsBiosList<WinsatSystemBoardInfo>(a1 + 8, a2 + 8) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      755,
      "We could not find a match for WinsatSystemBoardInfo");
    v8 = *(_QWORD *)(a1 + 8);
    if ( (int)(-1431655765 * ((*(_QWORD *)(a1 + 16) - v8) >> 3)) > 0 )
    {
      v9 = 0;
      do
      {
        LODWORD(v37) = *(_DWORD *)(v8 + v9 + 16);
        Log_Text_F(
          "base\\winsat\\common\\loadrecentresults.cpp",
          757,
          "SystemBoardInfo_1[%d]: Manufacturer:%ws, Product:%ws, Type:%lu",
          v7,
          *(_QWORD *)(*(_QWORD *)(v8 + v9) + 24LL),
          *(_QWORD *)(*(_QWORD *)(v8 + v9 + 8) + 24LL),
          v37);
        v8 = *(_QWORD *)(a1 + 8);
        v9 += 24;
        ++v7;
      }
      while ( (int)v7 < (int)(-1431655765 * ((*(_QWORD *)(a1 + 16) - v8) >> 3)) );
      v4 = a3;
    }
    v10 = *(_QWORD *)(a2 + 8);
    v11 = 0;
    if ( (int)(-1431655765 * ((*(_QWORD *)(a2 + 16) - v10) >> 3)) > 0 )
    {
      v12 = 0;
      do
      {
        LODWORD(v37) = *(_DWORD *)(v12 + v10 + 16);
        Log_Text_F(
          "base\\winsat\\common\\loadrecentresults.cpp",
          760,
          "SystemBoardInfo_2[%d]: Manufacturer:%ws, Product:%ws, Type:%lu",
          (unsigned int)v11,
          *(_QWORD *)(*(_QWORD *)(v12 + v10) + 24LL),
          *(_QWORD *)(*(_QWORD *)(v12 + v10 + 8) + 24LL),
          v37);
        v10 = *(_QWORD *)(a2 + 8);
        v12 += 24;
        ++v11;
      }
      while ( v11 < (int)(-1431655765 * ((*(_QWORD *)(a2 + 16) - v10) >> 3)) );
    }
    v7 = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v13 = *(_DWORD *)(a1 + 32);
    if ( v13 != *(_DWORD *)(a2 + 32) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        768,
        "We could not find a match for CpuManufacturer CPU1:%lu, CPU2:%lu",
        v13,
        *(_DWORD *)(a2 + 32));
      v7 |= 2u;
    }
  }
  if ( (v4 & 4) != 0 )
  {
    v14 = *(_DWORD *)(a1 + 36);
    if ( v14 != *(_DWORD *)(a2 + 36) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        775,
        "We could not find a match for HARDWAREID_CPU_SIG CPUSig1:%lu, CPUSig2:%lu",
        v14,
        *(_DWORD *)(a2 + 36));
      v7 |= 4u;
    }
  }
  if ( (v4 & 8) != 0 )
  {
    v15 = *(_QWORD *)(a1 + 40);
    if ( v15 != *(_QWORD *)(a2 + 40) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        782,
        "We could not find a match for HARDWAREID_MEM_SIZE Size1:%lu Size2:%lu",
        v15,
        *(_QWORD *)(a2 + 40));
      v7 |= 8u;
    }
  }
  if ( (v4 & 0x10) != 0 )
  {
    if ( *(_QWORD *)(a1 + 64) - *(_QWORD *)(a1 + 56) == *(_QWORD *)(a2 + 64) - *(_QWORD *)(a2 + 56) )
    {
      v16 = 0;
      for ( i = 0; ; i = v41 + 40 )
      {
        v18 = *(_QWORD *)(a1 + 56);
        v41 = i;
        if ( v16 >= 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 64) - v18) >> 3) )
          break;
        v19 = (_DWORD *)(i + v18);
        v20 = i + *(_QWORD *)(a2 + 56);
        v40 = v19;
        v45 = (_DWORD *)v20;
        if ( *v19 != *(_DWORD *)v20 )
          goto LABEL_39;
        v21 = *(unsigned __int64 **)(v20 + 8);
        v22 = *v21;
        lpString2 = (const WCHAR *)v21[3];
        v24 = (unsigned __int64 *)*((_QWORD *)v19 + 1);
        v42 = v22;
        cchCount2 = *v24;
        v43 = *v24;
        if ( *v24 )
        {
          if ( !v22 )
            goto LABEL_39;
          v26 = (const WCHAR *)v24[3];
          v27 = cchCount2 >= v22
              ? CompareStringW(0x400u, 0x1001u, v26, v22, lpString2, v22)
              : CompareStringW(0x400u, 0x1001u, v26, cchCount2, lpString2, cchCount2);
          if ( v27 != 2 || v43 != v42 )
            goto LABEL_39;
          v19 = v40;
        }
        else if ( v22 )
        {
          goto LABEL_39;
        }
        if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(
                                 v19 + 4,
                                 v45 + 4)
          || v40[6] != v45[6]
          || v40[7] != v45[7]
          || v40[8] != v45[8] )
        {
          goto LABEL_39;
        }
        ++v16;
      }
    }
    else
    {
LABEL_39:
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        789,
        "We could not find a match for HARDWAREID_MEM_DIMMS");
      v28 = *(_QWORD *)(a1 + 56);
      if ( (int)(-858993459 * ((*(_QWORD *)(a1 + 64) - v28) >> 3)) > 0 )
      {
        v29 = 0;
        v30 = 0;
        do
        {
          LODWORD(v39) = *(_DWORD *)(v29 + v28 + 32);
          LODWORD(v38) = *(_DWORD *)(v29 + v28 + 28);
          LODWORD(v37) = *(_DWORD *)(v29 + v28 + 24);
          Log_Text_F(
            "base\\winsat\\common\\loadrecentresults.cpp",
            791,
            "SystemBoardInfo_1[%d]: Manufacturer:%ws, Part_Number:%ws, Form_Factor:%lu Type:%lu Type_Detail:%lu\n",
            (unsigned int)v30,
            *(_QWORD *)(*(_QWORD *)(v29 + v28 + 8) + 24LL),
            *(_QWORD *)(*(_QWORD *)(v29 + v28 + 16) + 24LL),
            v37,
            v38,
            v39);
          v28 = *(_QWORD *)(a1 + 56);
          v29 += 40;
          ++v30;
        }
        while ( v30 < (int)(-858993459 * ((*(_QWORD *)(a1 + 64) - v28) >> 3)) );
        v4 = a3;
      }
      v31 = *(_QWORD *)(a2 + 56);
      if ( (int)(-858993459 * ((*(_QWORD *)(a2 + 64) - v31) >> 3)) > 0 )
      {
        v32 = 0;
        do
        {
          LODWORD(v39) = *(_DWORD *)(v32 + v31 + 32);
          LODWORD(v38) = *(_DWORD *)(v32 + v31 + 28);
          LODWORD(v37) = *(_DWORD *)(v32 + v31 + 24);
          Log_Text_F(
            "base\\winsat\\common\\loadrecentresults.cpp",
            794,
            "SystemBoardInfo_1[%d]: Manufacturer:%ws, Part_Number:%ws, Form_Factor:%lu Type:%lu Type_Detail:%lu\n",
            (unsigned int)v5,
            *(_QWORD *)(*(_QWORD *)(v32 + v31 + 8) + 24LL),
            *(_QWORD *)(*(_QWORD *)(v32 + v31 + 16) + 24LL),
            v37,
            v38,
            v39);
          v31 = *(_QWORD *)(a2 + 56);
          v32 += 40;
          ++v5;
        }
        while ( v5 < (int)(-858993459 * ((*(_QWORD *)(a2 + 64) - v31) >> 3)) );
      }
      v7 |= 0x10u;
    }
  }
  if ( (v4 & 0x20) != 0 )
  {
    v33 = *(_QWORD *)(a1 + 88);
    if ( v33 != *(_QWORD *)(a2 + 88) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        803,
        "We could not find a match for HARDWAREID_DISK_SIZE Size1:%u Size2:%u",
        v33,
        *(_QWORD *)(a2 + 88));
      v7 |= 0x20u;
    }
  }
  if ( (v4 & 0x40) != 0 )
  {
    v34 = *(_DWORD *)(a1 + 84);
    if ( v34 != *(_DWORD *)(a2 + 84) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        810,
        "We could not find a match for HARDWAREID_DISK_NUMBER DiskNum1:%lu DiskNum2:%lu",
        v34,
        *(_DWORD *)(a2 + 84));
      v7 |= 0x40u;
    }
  }
  if ( (v4 & 0x80u) != 0 && lstrcmpW((LPCWSTR)(a1 + 96), (LPCWSTR)(a2 + 96)) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      817,
      "We could not find a match for AdapterPnpIdStr String1:%ws String2:%ws\n",
      a1 + 96,
      a2 + 96);
    v7 |= 0x80u;
  }
  if ( (v4 & 0x100) != 0 )
  {
    v35 = *(_QWORD *)(a1 + 232);
    if ( v35 != *(_QWORD *)(a2 + 232) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        824,
        "We could not find a match for DriverVersion Version1:%lu Version2:%lu",
        v35,
        *(_QWORD *)(a2 + 232));
      v7 |= 0x100u;
    }
  }
  if ( (v4 & 0x200) != 0
    && (*(_BYTE *)(a1 + 225) != *(_BYTE *)(a2 + 225) || *(_BYTE *)(a1 + 224) != *(_BYTE *)(a2 + 224)) )
  {
    Log_Text_F("base\\winsat\\common\\loadrecentresults.cpp", 831, "We could not find a match for fHasWDDMDriver");
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      832,
      "fHasWDDMDriver1:%d fHasWDDMDriver2:%d, IsWDDMDriver1:%d, IsWDDMDriver2:%d",
      *(unsigned __int8 *)(a1 + 225),
      *(unsigned __int8 *)(a2 + 225),
      *(unsigned __int8 *)(a1 + 224),
      *(unsigned __int8 *)(a2 + 224));
    v7 |= 0x200u;
  }
  if ( (v4 & 0x400) != 0 && lstrcmpW((LPCWSTR)(a1 + 240), (LPCWSTR)(a2 + 240)) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      839,
      "We could not find a match for WinsatVersionStr Version1:%ws Version2:%ws\n",
      a1 + 240,
      a2 + 240);
    v7 |= 0x400u;
  }
  if ( (v4 & 0x800) != 0 && *(_BYTE *)(a1 + 368) != *(_BYTE *)(a2 + 368) )
  {
    Log_Text_F("base\\winsat\\common\\loadrecentresults.cpp", 846, "We could not find a match for Is64Bit");
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      847,
      "Is64Bit1:%d Is64Bit2:%d",
      *(unsigned __int8 *)(a1 + 368),
      *(unsigned __int8 *)(a2 + 368));
    v7 |= 0x800u;
  }
  return v7;
}

```

## disassembly

```asm
0x180002880  mov     rax, rsp
0x180002883  mov     [rax+18h], r8d
0x180002887  push    rbp
0x180002888  push    rsi
0x180002889  push    r14
0x18000288b  sub     rsp, 90h
0x180002892  mov     [rax+8], rbx
0x180002896  mov     rsi, rdx
0x180002899  mov     [rax-20h], rdi
0x18000289d  mov     ebx, r8d
0x1800028a0  xor     edi, edi
0x1800028a2  mov     [rax-28h], r12
0x1800028a6  mov     [rax-30h], r13
0x1800028aa  mov     rbp, rcx
0x1800028ad  mov     [rax-38h], r15
0x1800028b1  mov     r14d, edi
0x1800028b4  test    r8b, 1
0x1800028b8  jz      loc_180002A09
0x1800028be  add     rdx, 8
0x1800028c2  add     rcx, 8
0x1800028c6  call    ??$EqualsBiosList@UWinsatSystemBoardInfo@@@@YA_NAEBV?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@0@Z; EqualsBiosList<WinsatSystemBoardInfo>(std::vector<WinsatSystemBoardInfo> const &,std::vector<WinsatSystemBoardInfo> const &)
0x1800028cb  test    al, al
0x1800028cd  jnz     loc_180002A09
0x1800028d3  lea     r8, aWeCouldNotFind_9; "We could not find a match for WinsatSys"...
0x1800028da  mov     edx, 2F3h
0x1800028df  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x1800028e6  call    Log_Text_F
0x1800028eb  mov     r8, [rbp+8]
0x1800028ef  mov     r13, 0AAAAAAAAAAAAAAABh
0x1800028f9  mov     rax, [rbp+10h]
0x1800028fd  sub     rax, r8
0x180002900  sar     rax, 3
0x180002904  imul    rax, r13
0x180002908  test    eax, eax
0x18000290a  jle     short loc_180002988
0x18000290c  mov     r13d, edi
0x18000290f  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180002919  mov     rcx, [r8+r13+8]
0x18000291e  mov     r9d, r14d
0x180002921  mov     rdx, [r8+r13]
0x180002925  mov     eax, [r8+r13+10h]
0x18000292a  lea     r8, aSystemboardinf; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180002931  mov     dword ptr [rsp+0A8h+var_78], eax
0x180002935  mov     rax, [rcx+18h]
0x180002939  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002940  mov     qword ptr [rsp+0A8h+cchCount2], rax
0x180002945  mov     rax, [rdx+18h]
0x180002949  mov     edx, 2F5h
0x18000294e  mov     [rsp+0A8h+lpString2], rax
0x180002953  call    Log_Text_F
0x180002958  mov     r8, [rbp+8]
0x18000295c  lea     r13, [r13+18h]
0x180002960  mov     rax, [rbp+10h]
0x180002964  inc     r14d
0x180002967  sub     rax, r8
0x18000296a  sar     rax, 3
0x18000296e  imul    rax, rbx
0x180002972  cmp     r14d, eax
0x180002975  jl      short loc_180002919
0x180002977  mov     ebx, [rsp+0A8h+arg_10]
0x18000297e  mov     r13, 0AAAAAAAAAAAAAAABh
0x180002988  mov     r8, [rsi+8]
0x18000298c  mov     r14d, edi
0x18000298f  mov     rax, [rsi+10h]
0x180002993  sub     rax, r8
0x180002996  sar     rax, 3
0x18000299a  imul    rax, r13
0x18000299e  test    eax, eax
0x1800029a0  jle     short loc_180002A03
0x1800029a2  mov     r15, rdi
0x1800029a5  mov     rcx, [r15+r8+8]
0x1800029aa  mov     r9d, r14d
0x1800029ad  mov     rdx, [r15+r8]
0x1800029b1  mov     eax, [r15+r8+10h]
0x1800029b6  lea     r8, aSystemboardinf_1; "SystemBoardInfo_2[%d]: Manufacturer:%ws"...
0x1800029bd  mov     dword ptr [rsp+0A8h+var_78], eax
0x1800029c1  mov     rax, [rcx+18h]
0x1800029c5  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x1800029cc  mov     qword ptr [rsp+0A8h+cchCount2], rax
0x1800029d1  mov     rax, [rdx+18h]
0x1800029d5  mov     edx, 2F8h
0x1800029da  mov     [rsp+0A8h+lpString2], rax
0x1800029df  call    Log_Text_F
0x1800029e4  mov     r8, [rsi+8]
0x1800029e8  lea     r15, [r15+18h]
0x1800029ec  mov     rax, [rsi+10h]
0x1800029f0  inc     r14d
0x1800029f3  sub     rax, r8
0x1800029f6  sar     rax, 3
0x1800029fa  imul    rax, r13
0x1800029fe  cmp     r14d, eax
0x180002a01  jl      short loc_1800029A5
0x180002a03  mov     r14d, 1
0x180002a09  test    bl, 2
0x180002a0c  jz      short loc_180002A3A
0x180002a0e  mov     r9d, [rbp+20h]
0x180002a12  mov     eax, [rsi+20h]
0x180002a15  cmp     r9d, eax
0x180002a18  jz      short loc_180002A3A
0x180002a1a  lea     r8, aWeCouldNotFind_8; "We could not find a match for CpuManufa"...
0x180002a21  mov     dword ptr [rsp+0A8h+lpString2], eax
0x180002a25  mov     edx, 300h
0x180002a2a  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002a31  call    Log_Text_F
0x180002a36  or      r14d, 2
0x180002a3a  test    bl, 4
0x180002a3d  jz      short loc_180002A6B
0x180002a3f  mov     r9d, [rbp+24h]
0x180002a43  mov     eax, [rsi+24h]
0x180002a46  cmp     r9d, eax
0x180002a49  jz      short loc_180002A6B
0x180002a4b  lea     r8, aWeCouldNotFind_10; "We could not find a match for HARDWAREI"...
0x180002a52  mov     dword ptr [rsp+0A8h+lpString2], eax
0x180002a56  mov     edx, 307h
0x180002a5b  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002a62  call    Log_Text_F
0x180002a67  or      r14d, 4
0x180002a6b  test    bl, 8
0x180002a6e  jz      short loc_180002A9E
0x180002a70  mov     r9, [rbp+28h]
0x180002a74  mov     rax, [rsi+28h]
0x180002a78  cmp     r9, rax
0x180002a7b  jz      short loc_180002A9E
0x180002a7d  lea     r8, aWeCouldNotFind; "We could not find a match for HARDWAREI"...
0x180002a84  mov     [rsp+0A8h+lpString2], rax
0x180002a89  mov     edx, 30Eh
0x180002a8e  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002a95  call    Log_Text_F
0x180002a9a  or      r14d, 8
0x180002a9e  test    bl, 10h
0x180002aa1  jz      loc_180002D1F
0x180002aa7  mov     rcx, [rsi+40h]
0x180002aab  mov     r13, 0CCCCCCCCCCCCCCCDh
0x180002ab5  mov     rax, [rbp+40h]
0x180002ab9  sub     rcx, [rsi+38h]
0x180002abd  sub     rax, [rbp+38h]
0x180002ac1  cmp     rax, rcx
0x180002ac4  jnz     loc_180002BE3
0x180002aca  mov     r12, rdi
0x180002acd  mov     rdx, rdi
0x180002ad0  mov     rcx, [rbp+38h]
0x180002ad4  mov     rax, [rbp+40h]
0x180002ad8  sub     rax, rcx
0x180002adb  mov     [rsp+0A8h+var_50], rdx
0x180002ae0  sar     rax, 3
0x180002ae4  imul    rax, r13
0x180002ae8  cmp     r12, rax
0x180002aeb  jnb     loc_180002D1F
0x180002af1  lea     r8, [rdx+rcx]
0x180002af5  mov     rcx, [rsi+38h]
0x180002af9  add     rcx, rdx
0x180002afc  mov     [rsp+0A8h+var_58], r8
0x180002b01  mov     [rsp+0A8h+arg_18], rcx
0x180002b09  mov     eax, [rcx]
0x180002b0b  cmp     [r8], eax
0x180002b0e  jnz     loc_180002BE3
0x180002b14  mov     rax, [rcx+8]
0x180002b18  mov     rcx, [rax]
0x180002b1b  mov     r9, [rax+18h]
0x180002b1f  mov     rax, [r8+8]
0x180002b23  mov     [rsp+0A8h+var_48], rcx
0x180002b28  mov     rdx, [rax]
0x180002b2b  mov     [rsp+0A8h+var_40], rdx
0x180002b30  test    rdx, rdx
0x180002b33  jz      short loc_180002B8F
0x180002b35  test    rcx, rcx
0x180002b38  jz      loc_180002BE3
0x180002b3e  mov     r8, [rax+18h]; lpString1
0x180002b42  cmp     rdx, rcx
0x180002b45  jnb     short loc_180002B55
0x180002b47  mov     [rsp+0A8h+cchCount2], edx
0x180002b4b  mov     [rsp+0A8h+lpString2], r9
0x180002b50  mov     r9d, edx
0x180002b53  jmp     short loc_180002B61
0x180002b55  mov     [rsp+0A8h+cchCount2], ecx; cchCount2
0x180002b59  mov     [rsp+0A8h+lpString2], r9; lpString2
0x180002b5e  mov     r9d, ecx; cchCount1
0x180002b61  mov     edx, 1001h; dwCmpFlags
0x180002b66  mov     ecx, 400h; Locale
0x180002b6b  call    cs:__imp_CompareStringW
0x180002b72  nop     dword ptr [rax+rax+00h]
0x180002b77  add     eax, 0FFFFFFFEh
0x180002b7a  jnz     short loc_180002BE3
0x180002b7c  mov     rax, [rsp+0A8h+var_48]
0x180002b81  cmp     [rsp+0A8h+var_40], rax
0x180002b86  jnz     short loc_180002BE3
0x180002b88  mov     r8, [rsp+0A8h+var_58]
0x180002b8d  jmp     short loc_180002B94
0x180002b8f  test    rcx, rcx
0x180002b92  jnz     short loc_180002BE3
0x180002b94  mov     rdx, [rsp+0A8h+arg_18]
0x180002b9c  lea     rcx, [r8+10h]
0x180002ba0  add     rdx, 10h
0x180002ba4  call    ?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NAEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x180002ba9  test    al, al
0x180002bab  jz      short loc_180002BE3
0x180002bad  mov     rdx, [rsp+0A8h+arg_18]
0x180002bb5  mov     rcx, [rsp+0A8h+var_58]
0x180002bba  mov     eax, [rdx+18h]
0x180002bbd  cmp     [rcx+18h], eax
0x180002bc0  jnz     short loc_180002BE3
0x180002bc2  mov     eax, [rdx+1Ch]
0x180002bc5  cmp     [rcx+1Ch], eax
0x180002bc8  jnz     short loc_180002BE3
0x180002bca  mov     eax, [rdx+20h]
0x180002bcd  cmp     [rcx+20h], eax
0x180002bd0  jnz     short loc_180002BE3
0x180002bd2  mov     rdx, [rsp+0A8h+var_50]
0x180002bd7  inc     r12
0x180002bda  add     rdx, 28h ; '('
0x180002bde  jmp     loc_180002AD0
0x180002be3  lea     r8, aWeCouldNotFind_4; "We could not find a match for HARDWAREI"...
0x180002bea  mov     edx, 315h
0x180002bef  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002bf6  lea     r12, [rbp+38h]
0x180002bfa  call    Log_Text_F
0x180002bff  mov     r8, [rbp+38h]
0x180002c03  mov     rax, [rbp+40h]
0x180002c07  sub     rax, r8
0x180002c0a  sar     rax, 3
0x180002c0e  imul    rax, r13
0x180002c12  test    eax, eax
0x180002c14  jle     short loc_180002C92
0x180002c16  mov     r15, rdi
0x180002c19  mov     ebx, edi
0x180002c1b  mov     eax, [r15+r8+20h]
0x180002c20  mov     r9d, ebx
0x180002c23  mov     rcx, [r15+r8+10h]
0x180002c28  mov     rdx, [r15+r8+8]
0x180002c2d  mov     [rsp+0A8h+var_68], eax
0x180002c31  mov     eax, [r15+r8+1Ch]
0x180002c36  mov     dword ptr [rsp+0A8h+var_70], eax
0x180002c3a  mov     eax, [r15+r8+18h]
0x180002c3f  lea     r8, aSystemboardinf_0; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180002c46  mov     dword ptr [rsp+0A8h+var_78], eax
0x180002c4a  mov     rax, [rcx+18h]
0x180002c4e  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002c55  mov     qword ptr [rsp+0A8h+cchCount2], rax
0x180002c5a  mov     rax, [rdx+18h]
0x180002c5e  mov     edx, 317h
0x180002c63  mov     [rsp+0A8h+lpString2], rax
0x180002c68  call    Log_Text_F
0x180002c6d  mov     r8, [r12]
0x180002c71  lea     r15, [r15+28h]
0x180002c75  mov     rax, [r12+8]
0x180002c7a  inc     ebx
0x180002c7c  sub     rax, r8
0x180002c7f  sar     rax, 3
0x180002c83  imul    rax, r13
0x180002c87  cmp     ebx, eax
0x180002c89  jl      short loc_180002C1B
0x180002c8b  mov     ebx, [rsp+0A8h+arg_10]
0x180002c92  mov     r8, [rsi+38h]
0x180002c96  mov     rax, [rsi+40h]
0x180002c9a  sub     rax, r8
0x180002c9d  sar     rax, 3
0x180002ca1  imul    rax, r13
0x180002ca5  test    eax, eax
0x180002ca7  jle     short loc_180002D1B
0x180002ca9  mov     r15, rdi
0x180002cac  mov     eax, [r15+r8+20h]
0x180002cb1  mov     r9d, edi
0x180002cb4  mov     rcx, [r15+r8+10h]
0x180002cb9  mov     rdx, [r15+r8+8]
0x180002cbe  mov     [rsp+0A8h+var_68], eax
0x180002cc2  mov     eax, [r15+r8+1Ch]
0x180002cc7  mov     dword ptr [rsp+0A8h+var_70], eax
0x180002ccb  mov     eax, [r15+r8+18h]
0x180002cd0  lea     r8, aSystemboardinf_0; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180002cd7  mov     dword ptr [rsp+0A8h+var_78], eax
0x180002cdb  mov     rax, [rcx+18h]
0x180002cdf  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002ce6  mov     qword ptr [rsp+0A8h+cchCount2], rax
0x180002ceb  mov     rax, [rdx+18h]
0x180002cef  mov     edx, 31Ah
0x180002cf4  mov     [rsp+0A8h+lpString2], rax
0x180002cf9  call    Log_Text_F
0x180002cfe  mov     r8, [rsi+38h]
0x180002d02  lea     r15, [r15+28h]
0x180002d06  mov     rax, [rsi+40h]
0x180002d0a  inc     edi
0x180002d0c  sub     rax, r8
0x180002d0f  sar     rax, 3
0x180002d13  imul    rax, r13
0x180002d17  cmp     edi, eax
0x180002d19  jl      short loc_180002CAC
0x180002d1b  or      r14d, 10h
0x180002d1f  mov     r13, [rsp+0A8h+var_30]
0x180002d24  mov     r12, [rsp+0A8h+var_28]
0x180002d2c  test    bl, 20h
0x180002d2f  jz      short loc_180002D5F
0x180002d31  mov     r9, [rbp+58h]
0x180002d35  mov     rax, [rsi+58h]
0x180002d39  cmp     r9, rax
0x180002d3c  jz      short loc_180002D5F
0x180002d3e  lea     r8, aWeCouldNotFind_3; "We could not find a match for HARDWAREI"...
0x180002d45  mov     [rsp+0A8h+lpString2], rax
0x180002d4a  mov     edx, 323h
0x180002d4f  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180002d56  call    Log_Text_F
  ... truncated ...
```
