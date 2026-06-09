# ReadDeviceList

- ea: `0x180070f30`
- end: `0x180072922`
- name: `ReadDeviceList`
- size: `6642`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180072d4c`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bfb0`
- `0x18005cc20`
- `0x18006d670`
- `0x180070f30`
- `0x18007868c`
- `0x180078750`
- `0x180078d1c`
- `0x18007956c`
- `0x18007ffdc`
- `0x18008ef4c`
- `0x18008fec8`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800714bd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071516`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071859`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180072240`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800714bd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071516`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071859`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180072240`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800714ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800714fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007188c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800718b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800718e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007190a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071934`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007195e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071988`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719d8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719fe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800714ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800714fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007188c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800718b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800718e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007190a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071934`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007195e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071988`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719d8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800719fe`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800710d1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071295`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007142b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071655`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071685`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800716e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007184e`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800710d1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071295`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007142b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071655`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180071685`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800716e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007184e`

## string_xrefs

- `0x180071252`: `EnableCompression`
- `0x180071391`: `Compression`
- `0x180071372`: `Protocol`
- `0x1800713e9`: `MdmProtocol`

## pseudocode

```c
__int64 __fastcall ReadDeviceList(int a1, __int64 a2, int a3, __int64 a4, __int64 a5, int a6, _DWORD *a7)
{
  int v7; // ebx
  __int64 (__fastcall *v9)(CHAR *); // r14
  __int64 v10; // rsi
  int v11; // r9d
  int v12; // edx
  int v13; // r15d
  int v14; // r12d
  _QWORD *v15; // rcx
  __int64 v16; // r11
  __int64 v17; // r11
  int v18; // edx
  int v19; // r9d
  _BYTE *v20; // r11
  const char *v21; // rax
  int i; // ecx
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  unsigned int PhoneList; // eax
  unsigned int String; // ebx
  unsigned int Long; // eax
  unsigned int Flag; // eax
  unsigned int v30; // eax
  _DWORD *v31; // r14
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  int v36; // edx
  int v37; // r9d
  int v38; // edx
  int v39; // r8d
  int v40; // r9d
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  _DWORD *v48; // r9
  unsigned int v49; // eax
  unsigned int v50; // eax
  WCHAR *v51; // rbx
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  _WORD *v55; // rax
  int v56; // edx
  int v57; // r8d
  int v58; // r9d
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  struct _LIST_ENTRY *v63; // rcx
  __int64 v64; // rdx
  CHAR *v65; // r15
  __int64 v66; // rax
  const WCHAR *v67; // r14
  int v68; // ebx
  int v69; // r8d
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  WCHAR *v75; // rcx
  struct _LIST_ENTRY *v76; // rcx
  __int64 v77; // rdx
  struct _LIST_ENTRY *v78; // rcx
  __int64 v79; // rdx
  struct _LIST_ENTRY *v80; // rcx
  __int64 v81; // rdx
  int v83; // [rsp+44h] [rbp-BCh] BYREF
  int v84; // [rsp+48h] [rbp-B8h]
  int v85; // [rsp+4Ch] [rbp-B4h]
  int v86; // [rsp+50h] [rbp-B0h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall *v88)(CHAR *); // [rsp+60h] [rbp-A0h]
  CHAR String2[1552]; // [rsp+70h] [rbp-90h] BYREF

  v7 = a3;
  v9 = (__int64 (__fastcall *)(CHAR *))a2;
  v88 = (__int64 (__fastcall *)(CHAR *))a2;
  v10 = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 347, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  memset_0(String2, 0, 0x602u);
  LOBYTE(v11) = 3;
  LOBYTE(v12) = 2;
  if ( (unsigned int)rasFindLine(v10, v12, 1, v11, 1) && (unsigned int)v10 <= 0x1F3 )
  {
    v13 = 0;
    v85 = 0;
    v84 = 0;
    v14 = 0;
    while ( 2 )
    {
      v15 = (_QWORD *)gpRasfiles[v10];
      if ( v15 )
      {
        v16 = v15[1];
        if ( v16 != *v15 )
        {
          v17 = *(_QWORD *)(v16 + 16);
          if ( v17 )
          {
            if ( (unsigned int)IsMediaLine(v17, 0) )
            {
LABEL_383:
              LOBYTE(v19) = 4;
              LOBYTE(v18) = 63;
              rasFindLine(v10, v18, 1, v19, 2);
              break;
            }
            v21 = "DEVICE=";
            for ( i = 0; i < 7; ++i )
            {
              if ( *v20 != *v21 )
                goto LABEL_383;
              if ( !*v20 )
                break;
              ++v20;
              ++v21;
            }
            if ( !(unsigned int)RasfileGetKeyValueFields((unsigned int)v10, 0, 0, String2) )
            {
              v80 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
              {
                return 625;
              }
              v81 = 348;
              goto LABEL_389;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 349, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String2);
            }
            if ( CompareStringA(0x7Fu, 1u, "isdn", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = v9(String2);
              *(_DWORD *)(a5 + 40) = 6;
              PhoneList = ReadPhoneList(v10, v23, v24, v25, (__int64)v9, v7, a5 + 168);
              String = PhoneList;
              if ( PhoneList )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    350,
                    &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                    PhoneList);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 351;
                goto LABEL_187;
              }
              Long = ReadLong((unsigned int)v10, 2, "LastSelectedPhone", a5 + 176);
              String = Long;
              if ( Long )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 352, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, Long);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 353;
                goto LABEL_187;
              }
              Flag = ReadFlag((unsigned int)v10, 2, "PromoteAlternates", a5 + 180);
              String = Flag;
              if ( Flag )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 354, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, Flag);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 355;
                goto LABEL_187;
              }
              v30 = ReadFlag((unsigned int)v10, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v30;
              if ( v30 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 356, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v30);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 357;
                goto LABEL_187;
              }
              v31 = (_DWORD *)(a5 + 132);
              String = ReadLong((unsigned int)v10, 2, "LineType", a5 + 132);
              if ( String )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 358, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 359;
                goto LABEL_187;
              }
              if ( *v31 > 2u )
                *v31 = 0;
              v32 = ReadFlag((unsigned int)v10, 2, "Fallback", a5 + 136);
              String = v32;
              if ( v32 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 360, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v32);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 361;
                goto LABEL_187;
              }
              *(_DWORD *)(a5 + 128) = 1;
              v33 = ReadFlag((unsigned int)v10, 2, "Proprietary", a5 + 128);
              String = v33;
              if ( v33 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 362, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v33);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 363;
                goto LABEL_187;
              }
              v83 = -1;
              v34 = ReadLong((unsigned int)v10, 2, "ChannelAggregation", &v83);
              String = v34;
              if ( v34 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 364, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v34);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 365;
                goto LABEL_187;
              }
              if ( v83 == -1 )
                *(_DWORD *)(a5 + 128) = 0;
              else
                *(_DWORD *)(a5 + 144) = v83;
              v35 = ReadFlag((unsigned int)v10, 2, "EnableCompression", a5 + 140);
              String = v35;
              if ( !v35 )
              {
                v9 = v88;
LABEL_112:
                v7 = a3;
LABEL_113:
                LOBYTE(v37) = 3;
                LOBYTE(v36) = 2;
                if ( (unsigned int)rasFindLine(v10, v36, 1, v37, 1) )
                  continue;
                break;
              }
              v63 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 366, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v35);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(v63[1].Blink) < 0
                  && BYTE1(v63[1].Blink) >= 6u )
                {
                  v64 = 367;
                  goto LABEL_187;
                }
              }
              return String;
            }
            if ( CompareStringA(0x7Fu, 1u, "modem", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = v9(String2);
              *(_DWORD *)(a5 + 40) = 3;
              v41 = ReadPhoneList(v10, v38, v39, v40, (__int64)v9, v7, a5 + 168);
              String = v41;
              if ( v41 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 368, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v41);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 369;
                goto LABEL_187;
              }
              v42 = ReadLong((unsigned int)v10, 2, "LastSelectedPhone", a5 + 176);
              String = v42;
              if ( v42 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 370, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v42);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 371;
                goto LABEL_187;
              }
              v43 = ReadFlag((unsigned int)v10, 2, "PromoteAlternates", a5 + 180);
              String = v43;
              if ( v43 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 372, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v43);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 373;
                goto LABEL_187;
              }
              v44 = ReadFlag((unsigned int)v10, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v44;
              if ( v44 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 374, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v44);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 375;
                goto LABEL_187;
              }
              v45 = ReadFlag((unsigned int)v10, 2, "HwFlowControl", a5 + 108);
              String = v45;
              if ( v45 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 376, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v45);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 377;
                goto LABEL_187;
              }
              v46 = ReadFlag((unsigned int)v10, 2, "Protocol", a5 + 112);
              String = v46;
              if ( v46 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 378, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v46);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 379;
                goto LABEL_187;
              }
              v47 = ReadFlag((unsigned int)v10, 2, "Compression", a5 + 116);
              String = v47;
              if ( v47 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 380, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v47);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 381;
                goto LABEL_187;
              }
              v48 = (_DWORD *)(a5 + 120);
              if ( a7 )
              {
                *v48 = *a7 == 0;
              }
              else
              {
                v49 = ReadFlag((unsigned int)v10, 2, "Speaker", v48);
                String = v49;
                if ( v49 )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 382, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v49);
                    v63 = WPP_GLOBAL_Control;
                  }
                  if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v63[1].Blink) >= 0
                    || BYTE1(v63[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v64 = 383;
                  goto LABEL_187;
                }
              }
              v50 = ReadLong((unsigned int)v10, 2, "MdmProtocol", a5 + 124);
              String = v50;
              if ( !v50 )
              {
                v14 = 1;
                goto LABEL_112;
              }
              v63 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 384, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v50);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(v63[1].Blink) < 0
                  && BYTE1(v63[1].Blink) >= 6u )
                {
                  v64 = 385;
                  goto LABEL_187;
                }
              }
              return String;
            }
            if ( CompareStringA(0x7Fu, 1u, "switch", -1, String2, -1) == 2 )
            {
              lpString2 = 0;
              String = ReadString(v10, (_DWORD)v9, 2, (unsigned int)"Type", (__int64)&lpString2);
              if ( String )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 386, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 387;
                goto LABEL_187;
              }
              v51 = (WCHAR *)lpString2;
              if ( lpString2 )
              {
                if ( !v13 && !v14 )
                {
                  v13 = 1;
                  if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, lpString2, -1) == 2 )
                  {
                    *(_DWORD *)(a5 + 88) = 1;
                    GlobalFree(v51);
                  }
                  else
                  {
                    *(_DWORD *)(a5 + 92) = 1;
                    *(_QWORD *)(a5 + 96) = v51;
                  }
                  goto LABEL_58;
                }
                if ( v84 )
                {
                  v75 = (WCHAR *)lpString2;
                  *(_DWORD *)(a4 + 536) = 1;
                  GlobalFree(v75);
                  v76 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                    || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
                  {
                    return 0;
                  }
                  v77 = 388;
                  goto LABEL_395;
                }
                if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, lpString2, -1) == 2 )
                {
                  *(_DWORD *)(a4 + 212) = 1;
                  GlobalFree(v51);
                }
                else
                {
                  *(_DWORD *)(a4 + 216) = 1;
                  *(_QWORD *)(a4 + 224) = v51;
                }
              }
              else
              {
                v86 = 0;
                v83 = 0;
                lpString2 = 0;
                v52 = ReadFlag((unsigned int)v10, 2, "Terminal", &v86);
                String = v52;
                if ( v52 )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 389, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v52);
                    v63 = WPP_GLOBAL_Control;
                  }
                  if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v63[1].Blink) >= 0
                    || BYTE1(v63[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v64 = 390;
                  goto LABEL_187;
                }
                v53 = ReadFlag((unsigned int)v10, 2, "Script", &v83);
                String = v53;
                if ( v53 )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 391, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v53);
                    v63 = WPP_GLOBAL_Control;
                  }
                  if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v63[1].Blink) >= 0
                    || BYTE1(v63[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v64 = 392;
                  goto LABEL_187;
                }
                v54 = ReadLong((unsigned int)v10, 2, "CustomScript", a4 + 232);
                String = v54;
                if ( v54 )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 393, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v54);
                    v63 = WPP_GLOBAL_Control;
                  }
                  if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v63[1].Blink) >= 0
                    || BYTE1(v63[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v64 = 394;
                  goto LABEL_187;
                }
                String = ReadString(v10, (_DWORD)v9, 2, (unsigned int)"Name", (__int64)&lpString2);
                if ( String )
                {
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 395, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                    v63 = WPP_GLOBAL_Control;
                  }
                  if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v63[1].Blink) >= 0
                    || BYTE1(v63[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v64 = 396;
                  goto LABEL_187;
                }
                if ( !v13 && !v14 )
                {
                  v13 = 1;
                  *(_DWORD *)(a5 + 88) = v86;
                  *(_DWORD *)(a5 + 92) = v83;
                  *(_QWORD *)(a5 + 96) = lpString2;
LABEL_58:
                  v85 = 1;
                  goto LABEL_112;
                }
                if ( v84 )
                {
                  *(_DWORD *)(a4 + 536) = 1;
                  v76 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                    || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
                  {
                    return 0;
                  }
                  v77 = 397;
                  goto LABEL_395;
                }
                *(_DWORD *)(a4 + 212) = v86;
                *(_DWORD *)(a4 + 216) = v83;
                *(_QWORD *)(a4 + 224) = lpString2;
              }
              v84 = 1;
              goto LABEL_112;
            }
            if ( CompareStringA(0x7Fu, 1u, "pad", -1, String2, -1) == 2 )
              goto LABEL_113;
            if ( CompareStringA(0x7Fu, 1u, "null", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = v9(String2);
              *(_DWORD *)(a5 + 40) = 1;
              goto LABEL_113;
            }
            v55 = *(_WORD **)(a5 + 16);
            if ( v55 && !*v55 && CompareStringA(0x7Fu, 1u, "ATM", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = v9(String2);
              *(_DWORD *)(a5 + 40) = 13;
              v59 = ReadPhoneList(v10, v56, v57, v58, (__int64)v9, v7, a5 + 168);
              String = v59;
              if ( v59 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 398, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v59);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 399;
                goto LABEL_187;
              }
              v60 = ReadLong((unsigned int)v10, 2, "LastSelectedPhone", a5 + 176);
              String = v60;
              if ( v60 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 400, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v60);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 401;
                goto LABEL_187;
              }
              v61 = ReadFlag((unsigned int)v10, 2, "PromoteAlternates", a5 + 180);
              String = v61;
              if ( v61 )
              {
                v63 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 402, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v61);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v63[1].Blink) >= 0
                  || BYTE1(v63[1].Blink) < 6u )
                {
                  return String;
                }
                v64 = 403;
                goto LABEL_187;
              }
              v62 = ReadFlag((unsigned int)v10, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v62;
              if ( !v62 )
                goto LABEL_112;
              v63 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 404, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v62);
                  v63 = WPP_GLOBAL_Control;
                }
                if ( v63 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && SBYTE4(v63[1].Blink) < 0
                  && BYTE1(v63[1].Blink) >= 6u )
                {
                  v64 = 405;
LABEL_187:
                  WPP_SF_d(v63[1].Flink, v64, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                }
              }
              return String;
            }
            v65 = (CHAR *)StrDupAFromTInternal(*(LPCWCH *)(a5 + 24));
            if ( v65 )
            {
              v66 = v9(String2);
              *(_QWORD *)(a5 + 32) = v66;
              v67 = (const WCHAR *)v66;
              if ( v66 )
              {
                v68 = CompareStringA(0x7Fu, 1u, String2, -1, v65, -1);
                GlobalFree(v65);
                if ( v68 == 2
                  || CompareStringW(0x7Fu, 1u, L"SERIAL", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"vpn", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"GENERIC", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"ATM", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"SONET", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"SW56", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"IRDA", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, v67, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"PPPoE", -1, v67, -1) == 2 )
                {
                  if ( !*(_DWORD *)(a5 + 40) )
                    *(_DWORD *)(a5 + 40) = PbdevicetypeFromPszTypeA(String2);
                  v9 = v88;
                  v70 = ReadPhoneList(v10, v36, v69, v37, (__int64)v88, a3, a5 + 168);
                  String = v70;
                  if ( v70 )
                  {
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 409, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v70);
                      v63 = WPP_GLOBAL_Control;
                    }
                    if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v63[1].Blink) >= 0
                      || BYTE1(v63[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v64 = 410;
                    goto LABEL_187;
                  }
                  v71 = ReadLong((unsigned int)v10, 2, "LastSelectedPhone", a5 + 176);
                  String = v71;
                  if ( v71 )
                  {
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 411, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v71);
                      v63 = WPP_GLOBAL_Control;
                    }
                    if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v63[1].Blink) >= 0
                      || BYTE1(v63[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v64 = 412;
                    goto LABEL_187;
                  }
                  v72 = ReadFlag((unsigned int)v10, 2, "PromoteAlternates", a5 + 180);
                  String = v72;
                  if ( v72 )
                  {
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 413, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v72);
                      v63 = WPP_GLOBAL_Control;
                    }
                    if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v63[1].Blink) >= 0
                      || BYTE1(v63[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v64 = 414;
                    goto LABEL_187;
                  }
                  v73 = ReadFlag((unsigned int)v10, 2, "TryNextAlternateOnFail", a5 + 184);
                  String = v73;
                  if ( v73 )
                  {
                    v63 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 415, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v73);
                      v63 = WPP_GLOBAL_Control;
                    }
                    if ( v63 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v63[1].Blink) >= 0
                      || BYTE1(v63[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v64 = 416;
                    goto LABEL_187;
                  }
                }
                else
                {
                  v9 = v88;
                  *(_DWORD *)(a4 + 536) = 1;
                }
                v13 = v85;
                goto LABEL_112;
              }
              v78 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
              {
                return 8;
              }
              v79 = 408;
            }
            else
            {
              v78 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                return 8;
              if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 406, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 8);
                v78 = WPP_GLOBAL_Control;
              }
              if ( v78 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(v78[1].Blink) >= 0
                || BYTE1(v78[1].Blink) < 6u )
              {
                return 8;
              }
              v79 = 407;
            }
            WPP_SF_d(v78[1].Flink, v79, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 8);
            return 8;
          }
        }
      }
      break;
    }
  }
  if ( !*(_DWORD *)(a5 + 40) )
  {
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 625;
    }
    v81 = 417;
LABEL_389:
    WPP_SF_d(v80[1].Flink, v81, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 625);
    return 625;
  }
  v76 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v77 = 418;
LABEL_395:
    WPP_SF_d(v76[1].Flink, v77, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180070f30  push    rbp
0x180070f32  push    rbx
0x180070f33  push    rsi
0x180070f34  push    rdi
0x180070f35  push    r12
0x180070f37  push    r13
0x180070f39  push    r14
0x180070f3b  push    r15
0x180070f3d  lea     rbp, [rsp-598h]
0x180070f45  sub     rsp, 698h
0x180070f4c  mov     rax, cs:__security_cookie
0x180070f53  xor     rax, rsp
0x180070f56  mov     [rbp+5D0h+var_50], rax
0x180070f5d  mov     rdi, [rbp+5D0h+arg_20]
0x180070f64  mov     ebx, r8d
0x180070f67  mov     [rsp+6D0h+var_690], ebx
0x180070f6b  mov     r13, r9
0x180070f6e  mov     r14, rdx
0x180070f71  mov     [rsp+6D0h+var_670], rdx
0x180070f76  movsxd  rsi, ecx
0x180070f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180070f80  lea     r15, WPP_GLOBAL_Control
0x180070f87  cmp     rcx, r15
0x180070f8a  jz      short loc_180070FAD
0x180070f8c  test    byte ptr [rcx+1Ch], 80h
0x180070f90  jz      short loc_180070FAD
0x180070f92  cmp     byte ptr [rcx+19h], 6
0x180070f96  jb      short loc_180070FAD
0x180070f98  mov     rcx, [rcx+10h]
0x180070f9c  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180070fa3  mov     edx, 15Bh
0x180070fa8  call    WPP_SF_
0x180070fad  xor     edx, edx; Val
0x180070faf  lea     rcx, [rsp+6D0h+String2]; void *
0x180070fb4  mov     r8d, 602h; Size
0x180070fba  call    memset_0
0x180070fbf  mov     r9b, 3
0x180070fc2  mov     byte ptr [rsp+6D0h+lpString2], 1
0x180070fc7  mov     r8d, 1
0x180070fcd  mov     dl, 2
0x180070fcf  mov     ecx, esi
0x180070fd1  call    rasFindLine
0x180070fd6  xor     edx, edx
0x180070fd8  test    eax, eax
0x180070fda  jz      loc_18007288E
0x180070fe0  cmp     esi, 1F3h
0x180070fe6  ja      loc_18007288E
0x180070fec  mov     r15d, edx
0x180070fef  mov     [rsp+6D0h+var_684], edx
0x180070ff3  mov     [rsp+6D0h+var_688], edx
0x180070ff7  mov     r12d, edx
0x180070ffa  lea     rcx, gpRasfiles
0x180071001  mov     rcx, [rcx+rsi*8]
0x180071005  test    rcx, rcx
0x180071008  jz      loc_180072887
0x18007100e  mov     r11, [rcx+8]
0x180071012  cmp     r11, [rcx]
0x180071015  jz      loc_180072887
0x18007101b  mov     r11, [r11+10h]
0x18007101f  test    r11, r11
0x180071022  jz      loc_180072887
0x180071028  mov     rcx, r11
0x18007102b  call    IsMediaLine
0x180071030  xor     r8d, r8d
0x180071033  test    eax, eax
0x180071035  jnz     loc_18007286E
0x18007103b  lea     rax, aDevice_0; "DEVICE="
0x180071042  mov     ecx, r8d
0x180071045  mov     dl, [r11]
0x180071048  cmp     dl, [rax]
0x18007104a  jnz     loc_18007286E
0x180071050  test    dl, dl
0x180071052  jz      short loc_180071061
0x180071054  inc     r11
0x180071057  inc     rax
0x18007105a  inc     ecx
0x18007105c  cmp     ecx, 7
0x18007105f  jl      short loc_180071045
0x180071061  lea     r9, [rsp+6D0h+String2]
0x180071066  xor     edx, edx
0x180071068  mov     ecx, esi
0x18007106a  call    RasfileGetKeyValueFields
0x18007106f  test    eax, eax
0x180071071  jz      loc_180072848
0x180071077  mov     rcx, cs:WPP_GLOBAL_Control
0x18007107e  lea     rax, WPP_GLOBAL_Control
0x180071085  cmp     rcx, rax
0x180071088  jz      short loc_1800710B0
0x18007108a  test    byte ptr [rcx+1Ch], 80h
0x18007108e  jz      short loc_1800710B0
0x180071090  cmp     byte ptr [rcx+19h], 5
0x180071094  jb      short loc_1800710B0
0x180071096  mov     rcx, [rcx+10h]
0x18007109a  lea     r9, [rsp+6D0h+String2]
0x18007109f  mov     edx, 15Dh
0x1800710a4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800710ab  call    WPP_SF_s
0x1800710b0  or      ecx, 0FFFFFFFFh
0x1800710b3  lea     rax, [rsp+6D0h+String2]
0x1800710b8  mov     [rsp+6D0h+cchCount2], ecx; cchCount2
0x1800710bc  lea     r8, aIsdn_0; "isdn"
0x1800710c3  mov     r9d, ecx; cchCount1
0x1800710c6  mov     [rsp+6D0h+lpString2], rax; lpString2
0x1800710cb  lea     edx, [rcx+2]; dwCmpFlags
0x1800710ce  lea     ecx, [rdx+7Eh]; Locale
0x1800710d1  call    cs:__imp_CompareStringA
0x1800710d7  cmp     eax, 2
0x1800710da  jnz     loc_180071274
0x1800710e0  lea     rcx, [rsp+6D0h+String2]
0x1800710e5  mov     rax, r14
0x1800710e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800710ed  mov     [rdi+20h], rax
0x1800710f1  mov     ecx, esi
0x1800710f3  lea     rax, [rdi+0A8h]
0x1800710fa  mov     dword ptr [rdi+28h], 6
0x180071101  mov     [rsp+6D0h+var_6A0], rax
0x180071106  mov     [rsp+6D0h+cchCount2], ebx
0x18007110a  mov     [rsp+6D0h+lpString2], r14
0x18007110f  call    ReadPhoneList
0x180071114  mov     ebx, eax
0x180071116  test    eax, eax
0x180071118  jnz     loc_180071E2A
0x18007111e  lea     r14d, [rax+2]
0x180071122  mov     ecx, esi
0x180071124  mov     edx, r14d
0x180071127  lea     r9, [rdi+0B0h]
0x18007112e  lea     r8, aLastselectedph; "LastSelectedPhone"
0x180071135  call    ReadLong
0x18007113a  mov     ebx, eax
0x18007113c  test    eax, eax
0x18007113e  jnz     loc_180071DD0
0x180071144  lea     r9, [rdi+0B4h]
0x18007114b  mov     edx, r14d
0x18007114e  lea     r8, aPromotealterna; "PromoteAlternates"
0x180071155  mov     ecx, esi
0x180071157  call    ReadFlag
0x18007115c  mov     ebx, eax
0x18007115e  test    eax, eax
0x180071160  jnz     loc_180071D67
0x180071166  lea     r9, [rdi+0B8h]
0x18007116d  mov     edx, r14d
0x180071170  lea     r8, aTrynextalterna; "TryNextAlternateOnFail"
0x180071177  mov     ecx, esi
0x180071179  call    ReadFlag
0x18007117e  mov     ebx, eax
0x180071180  test    eax, eax
0x180071182  jnz     loc_180071CFE
0x180071188  lea     r14, [rdi+84h]
0x18007118f  mov     ecx, esi
0x180071191  mov     r9, r14
0x180071194  lea     r8, aLinetype; "LineType"
0x18007119b  lea     edx, [rax+2]
0x18007119e  call    ReadLong
0x1800711a3  mov     ebx, eax
0x1800711a5  xor     eax, eax
0x1800711a7  test    ebx, ebx
0x1800711a9  jnz     loc_180071C95
0x1800711af  cmp     dword ptr [r14], 2
0x1800711b3  jbe     short loc_1800711B8
0x1800711b5  mov     [r14], eax
0x1800711b8  lea     r9, [rdi+88h]
0x1800711bf  mov     edx, 2
0x1800711c4  lea     r8, aFallback; "Fallback"
0x1800711cb  mov     ecx, esi
0x1800711cd  call    ReadFlag
0x1800711d2  mov     ebx, eax
0x1800711d4  test    eax, eax
0x1800711d6  jnz     loc_180071C2C
0x1800711dc  lea     r14, [rdi+80h]
0x1800711e3  mov     ecx, esi
0x1800711e5  mov     r9, r14
0x1800711e8  mov     dword ptr [r14], 1
0x1800711ef  lea     r8, aProprietary; "Proprietary"
0x1800711f6  lea     edx, [rax+2]
0x1800711f9  call    ReadFlag
0x1800711fe  mov     ebx, eax
0x180071200  test    eax, eax
0x180071202  jnz     loc_180071BC3
0x180071208  lea     r9, [rsp+6D0h+var_68C]
0x18007120d  mov     [rsp+6D0h+var_68C], 0FFFFFFFFh
0x180071215  lea     r8, aChannelaggrega; "ChannelAggregation"
0x18007121c  mov     ecx, esi
0x18007121e  lea     edx, [rax+2]
0x180071221  call    ReadLong
0x180071226  xor     ecx, ecx
0x180071228  mov     ebx, eax
0x18007122a  test    eax, eax
0x18007122c  jnz     loc_180071B5A
0x180071232  mov     eax, [rsp+6D0h+var_68C]
0x180071236  cmp     eax, 0FFFFFFFFh
0x180071239  jnz     short loc_180071240
0x18007123b  mov     [r14], ecx
0x18007123e  jmp     short loc_180071246
0x180071240  mov     [rdi+90h], eax
0x180071246  lea     r9, [rdi+8Ch]
0x18007124d  mov     edx, 2
0x180071252  lea     r8, aEnablecompress; "EnableCompression"
0x180071259  mov     ecx, esi
0x18007125b  call    ReadFlag
0x180071260  mov     ebx, eax
0x180071262  test    eax, eax
0x180071264  jnz     loc_180071AF1
0x18007126a  mov     r14, [rsp+6D0h+var_670]
0x18007126f  jmp     loc_180071AC7
0x180071274  or      ecx, 0FFFFFFFFh
0x180071277  lea     rax, [rsp+6D0h+String2]
0x18007127c  mov     [rsp+6D0h+cchCount2], ecx; cchCount2
0x180071280  lea     r8, aModem_0; "modem"
0x180071287  mov     r9d, ecx; cchCount1
0x18007128a  mov     [rsp+6D0h+lpString2], rax; lpString2
0x18007128f  lea     edx, [rcx+2]; dwCmpFlags
0x180071292  lea     ecx, [rdx+7Eh]; Locale
0x180071295  call    cs:__imp_CompareStringA
0x18007129b  cmp     eax, 2
0x18007129e  jnz     loc_18007140A
0x1800712a4  lea     rcx, [rsp+6D0h+String2]
0x1800712a9  mov     rax, r14
0x1800712ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712b1  mov     [rdi+20h], rax
0x1800712b5  mov     ecx, esi
0x1800712b7  lea     rax, [rdi+0A8h]
0x1800712be  mov     dword ptr [rdi+28h], 3
0x1800712c5  mov     [rsp+6D0h+var_6A0], rax
0x1800712ca  mov     [rsp+6D0h+cchCount2], ebx
0x1800712ce  mov     [rsp+6D0h+lpString2], r14
0x1800712d3  call    ReadPhoneList
0x1800712d8  mov     ebx, eax
0x1800712da  test    eax, eax
0x1800712dc  jnz     loc_1800721C9
0x1800712e2  lea     r12d, [rax+2]
0x1800712e6  mov     ecx, esi
0x1800712e8  mov     edx, r12d
0x1800712eb  lea     r9, [rdi+0B0h]
0x1800712f2  lea     r8, aLastselectedph; "LastSelectedPhone"
0x1800712f9  call    ReadLong
0x1800712fe  mov     ebx, eax
0x180071300  test    eax, eax
0x180071302  jnz     loc_180072160
0x180071308  lea     r9, [rdi+0B4h]
0x18007130f  mov     edx, r12d
0x180071312  lea     r8, aPromotealterna; "PromoteAlternates"
0x180071319  mov     ecx, esi
0x18007131b  call    ReadFlag
0x180071320  mov     ebx, eax
0x180071322  test    eax, eax
0x180071324  jnz     loc_1800720F7
0x18007132a  lea     r9, [rdi+0B8h]
0x180071331  mov     edx, r12d
0x180071334  lea     r8, aTrynextalterna; "TryNextAlternateOnFail"
0x18007133b  mov     ecx, esi
0x18007133d  call    ReadFlag
0x180071342  mov     ebx, eax
0x180071344  test    eax, eax
0x180071346  jnz     loc_18007208E
0x18007134c  lea     r9, [rdi+6Ch]
0x180071350  mov     edx, r12d
0x180071353  lea     r8, aHwflowcontrol; "HwFlowControl"
0x18007135a  mov     ecx, esi
0x18007135c  call    ReadFlag
0x180071361  mov     ebx, eax
0x180071363  test    eax, eax
0x180071365  jnz     loc_180072025
0x18007136b  lea     r9, [rdi+70h]
0x18007136f  mov     edx, r12d
0x180071372  lea     r8, aProtocol; "Protocol"
0x180071379  mov     ecx, esi
0x18007137b  call    ReadFlag
0x180071380  mov     ebx, eax
0x180071382  test    eax, eax
0x180071384  jnz     loc_180071FBC
0x18007138a  lea     r9, [rdi+74h]
0x18007138e  mov     edx, r12d
0x180071391  lea     r8, aCompression; "Compression"
0x180071398  mov     ecx, esi
0x18007139a  call    ReadFlag
0x18007139f  xor     edx, edx
0x1800713a1  mov     ebx, eax
0x1800713a3  test    eax, eax
0x1800713a5  jnz     loc_180071F53
0x1800713ab  mov     rcx, [rbp+5D0h+arg_30]
0x1800713b2  lea     r9, [rdi+78h]
0x1800713b6  test    rcx, rcx
0x1800713b9  jz      short loc_1800713C7
0x1800713bb  cmp     [rcx], edx
0x1800713bd  mov     eax, edx
0x1800713bf  setz    al
0x1800713c2  mov     [r9], eax
0x1800713c5  jmp     short loc_1800713E2
0x1800713c7  lea     r8, aSpeaker; "Speaker"
0x1800713ce  mov     edx, r12d
0x1800713d1  mov     ecx, esi
0x1800713d3  call    ReadFlag
0x1800713d8  mov     ebx, eax
0x1800713da  test    eax, eax
0x1800713dc  jnz     loc_180071EEE
0x1800713e2  lea     r9, [rdi+7Ch]
0x1800713e6  mov     edx, r12d
0x1800713e9  lea     r8, aMdmprotocol; "MdmProtocol"
0x1800713f0  mov     ecx, esi
0x1800713f2  call    ReadLong
  ... truncated ...
```
