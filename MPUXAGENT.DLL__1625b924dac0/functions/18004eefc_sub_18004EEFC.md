# sub_18004EEFC

- ea: `0x18004eefc`
- end: `0x1800502f4`
- name: `sub_18004EEFC`
- size: `5112`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, const WCHAR *, const WCHAR *, const WCHAR *)`
- caller_count: `8`
- callee_count: `28`
- tags: `registry_config`

## callers

- `0x18004ed20`
- `0x18004ed50`
- `0x18004ed80`
- `0x18004ed90`
- `0x18004edc0`
- `0x18004ee10`
- `0x18004ee60`
- `0x18004eeb0`

## callees

- `0x1800025ec`
- `0x180002898`
- `0x180004d20`
- `0x18000726c`
- `0x180007274`
- `0x1800095a0`
- `0x18000969c`
- `0x180032da0`
- `0x180034c4c`
- `0x18003626c`
- `0x180036850`
- `0x18003d4f8`
- `0x180043004`
- `0x18004345c`
- `0x180043688`
- `0x18004c2f0`
- `0x18004d4ac`
- `0x18004eefc`
- `0x180055f44`
- `0x180057f94`
- `0x1800589c4`
- `0x1800592bc`
- `0x1800619dc`
- `0x1800639f0`
- `0x180064a70`
- `0x1800653e8`
- `0x1800675c4`
- `0x180068420`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18004ef55`
- `KERNEL32!DebugBreak` at `0x18004ef55`

## string_xrefs

- `0x18004ef45`: `MpDlp_DebugOnMpUxCreate`
- `0x180050258`: `Left-over characters in stream after parsing a JSON value`

## pseudocode

```c
__int64 __fastcall sub_18004EEFC(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        const WCHAR *a4,
        const WCHAR *a5,
        const WCHAR *a6)
{
  __int64 v9; // r12
  int v10; // eax
  _UNKNOWN **v11; // rcx
  unsigned __int64 v12; // r8
  __int128 *v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  const WCHAR *v19; // rax
  const WCHAR *v20; // rax
  int v21; // r13d
  struct _RTL_CRITICAL_SECTION *v22; // r12
  struct _RTL_CRITICAL_SECTION *v23; // r12
  int v24; // r15d
  char v25; // al
  int *v26; // rcx
  _WORD *v27; // rdx
  int v28; // eax
  unsigned int v29; // r15d
  _UNKNOWN **v30; // rcx
  struct _RTL_CRITICAL_SECTION *v31; // r12
  int v32; // r13d
  struct _RTL_CRITICAL_SECTION *v33; // r12
  struct _RTL_CRITICAL_SECTION *v34; // r15
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  _BYTE v39[4]; // [rsp+B0h] [rbp-468h] BYREF
  int v40; // [rsp+B4h] [rbp-464h] BYREF
  unsigned int v41; // [rsp+B8h] [rbp-460h] BYREF
  int v42; // [rsp+C0h] [rbp-458h] BYREF
  int v43; // [rsp+C4h] [rbp-454h] BYREF
  int v44; // [rsp+C8h] [rbp-450h] BYREF
  int v45; // [rsp+CCh] [rbp-44Ch] BYREF
  __int64 v46; // [rsp+D0h] [rbp-448h] BYREF
  unsigned int v47; // [rsp+D8h] [rbp-440h] BYREF
  unsigned int v48; // [rsp+DCh] [rbp-43Ch] BYREF
  __int64 v49; // [rsp+E0h] [rbp-438h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-430h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-428h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-420h] BYREF
  __int64 v53; // [rsp+100h] [rbp-418h] BYREF
  __int64 v54; // [rsp+108h] [rbp-410h] BYREF
  __int64 v55; // [rsp+110h] [rbp-408h] BYREF
  __int64 v56; // [rsp+118h] [rbp-400h] BYREF
  __int64 v57; // [rsp+120h] [rbp-3F8h] BYREF
  __int64 v58; // [rsp+128h] [rbp-3F0h] BYREF
  __int64 v59; // [rsp+130h] [rbp-3E8h] BYREF
  __int64 v60; // [rsp+138h] [rbp-3E0h] BYREF
  __int64 v61; // [rsp+140h] [rbp-3D8h] BYREF
  __int64 v62; // [rsp+148h] [rbp-3D0h] BYREF
  __int64 v63; // [rsp+150h] [rbp-3C8h] BYREF
  __int64 v64; // [rsp+158h] [rbp-3C0h] BYREF
  __int64 v65; // [rsp+160h] [rbp-3B8h] BYREF
  __int64 v66; // [rsp+168h] [rbp-3B0h] BYREF
  __int128 v67; // [rsp+170h] [rbp-3A8h] BYREF
  __int128 v68; // [rsp+180h] [rbp-398h]
  _BYTE v69[32]; // [rsp+198h] [rbp-380h] BYREF
  _BYTE v70[32]; // [rsp+1B8h] [rbp-360h] BYREF
  __int64 v71; // [rsp+1D8h] [rbp-340h] BYREF
  LPVOID v72; // [rsp+1E0h] [rbp-338h] BYREF
  char v73; // [rsp+1E8h] [rbp-330h]
  LPVOID v74; // [rsp+1F0h] [rbp-328h]
  char v75; // [rsp+1F8h] [rbp-320h]
  LPVOID v76[2]; // [rsp+200h] [rbp-318h]
  LPVOID v77[2]; // [rsp+210h] [rbp-308h]
  LPVOID v78[2]; // [rsp+220h] [rbp-2F8h]
  LPVOID lpMem; // [rsp+230h] [rbp-2E8h] BYREF
  int v80; // [rsp+238h] [rbp-2E0h]
  unsigned int v81; // [rsp+23Ch] [rbp-2DCh]
  __int16 v82; // [rsp+240h] [rbp-2D8h]
  char v83; // [rsp+242h] [rbp-2D6h]
  __int64 v84[3]; // [rsp+250h] [rbp-2C8h] BYREF
  _QWORD v85[7]; // [rsp+268h] [rbp-2B0h] BYREF
  _BYTE v86[136]; // [rsp+2A0h] [rbp-278h] BYREF
  signed __int64 v87; // [rsp+328h] [rbp-1F0h] BYREF
  int v88; // [rsp+330h] [rbp-1E8h] BYREF
  __int128 v89; // [rsp+338h] [rbp-1E0h] BYREF
  __int64 v90; // [rsp+348h] [rbp-1D0h]
  __int64 v91; // [rsp+350h] [rbp-1C8h]
  int v92; // [rsp+378h] [rbp-1A0h] BYREF
  __int64 (__fastcall ***v93)(); // [rsp+380h] [rbp-198h]
  _WORD v94[136]; // [rsp+3C0h] [rbp-158h] BYREF

  v9 = a1;
  v58 = a1;
  v41 = a2;
  v40 = 0;
  if ( (unsigned int)sub_1800592BC(L"MpDlp_DebugOnMpUxCreate") )
    DebugBreak();
  v71 = 0;
  sub_1800619DC(&v71);
  if ( !a3 )
    goto LABEL_19;
  if ( a2 == 15000 )
  {
    v10 = sub_180043004(&v71, a3);
    if ( v10 >= 0 )
    {
LABEL_19:
      v11 = (_UNKNOWN **)off_180096D60;
      goto LABEL_20;
    }
    v11 = (_UNKNOWN **)off_180096D60;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 2) != 0 )
    {
      sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0xFu, &MessageGuid, v10);
      goto LABEL_19;
    }
  }
  else
  {
    v67 = 0;
    v68 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a3 + 2 * v12) );
    sub_180034C4C((__int64 *)&v67, a3, v12);
    v85[1] = 1;
    v85[2] = 1;
    v85[3] = 0;
    v85[0] = &web::json::details::JSON_StringParser<wchar_t>::`vftable';
    v13 = &v67;
    if ( *((_QWORD *)&v68 + 1) > 7u )
      v13 = (__int128 *)v67;
    v85[4] = v13;
    v85[5] = v13;
    v85[6] = (char *)v13 + 2 * v68;
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 7;
    LOWORD(v89) = 0;
    v92 = 0;
    v93 = &off_180096E10;
    sub_180064A70(v85, &v88);
    if ( v92 )
    {
      v37 = sub_1800589C4(&v92, v70);
      v38 = sub_1800675C4(v69, v37);
      sub_1800639F0(&v88, v38);
    }
    v50 = 0;
    v14 = (__int64 *)sub_1800653E8(v85, &v49, &v88);
    v15 = *v14;
    *v14 = 0;
    v50 = v15;
    v40 = 6;
    if ( v92 )
    {
      v35 = sub_1800589C4(&v92, v69);
      v36 = sub_1800675C4(v70, v35);
      sub_1800639F0(&v88, v36);
    }
    if ( v88 )
    {
      sub_18003626C(v69, L"Left-over characters in stream after parsing a JSON value");
      sub_1800639F0(&v88, v69);
    }
    sub_180057F94(&v89);
    v16 = v71;
    v71 = v15;
    if ( v16 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 192LL))(v16, 1);
    sub_180057F94(&v67);
    v11 = (_UNKNOWN **)off_180096D60;
  }
LABEL_20:
  if ( v11 != &off_180096D60 && (*((_BYTE *)v11 + 28) & 4) != 0 )
    sub_180032DA0((TRACEHANDLE)v11[2], 0x11u, &MessageGuid, a2);
  if ( (unsigned __int8)sub_18004345C(v11, L"S-1-5-80-1643833996-2250221834-4030382726-1771290504-1710830024")
    || (unsigned __int8)sub_18004345C(v17, L"S-1-5-80-1913148863-3492339771-4165695881-2087618961-4109116736") )
  {
    sub_180036850((__int64)v86);
    if ( !a4 )
      a4 = &word_18007D770;
    v84[0] = (__int64)a4;
    v19 = a5;
    if ( !a5 )
      v19 = &word_18007D770;
    v84[1] = (__int64)v19;
    v20 = a6;
    if ( !a6 )
      v20 = &word_18007D770;
    v84[2] = (__int64)v20;
    v39[0] = 0;
    v21 = sub_18004D4AC(&word_18007D770, a2, v39);
    if ( v21 < 0 )
    {
      v22 = lpCriticalSection;
      if ( lpCriticalSection )
      {
        EnterCriticalSection(lpCriticalSection);
        if ( (unsigned int)dword_180096000 > 5
          && (*(_QWORD *)algn_180096010 & 0x400000000000LL) != 0
          && (*(_QWORD *)&algn_180096010[8] & 0x400000000000LL) == *(_QWORD *)&algn_180096010[8] )
        {
          v41 = v21;
          v40 = a2;
          sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), &v88);
          v49 = (__int64)&v88;
          v42 = *(_DWORD *)(qword_180099048 + 72);
          v43 = *(_DWORD *)(qword_180099048 + 68);
          v44 = *(_DWORD *)(qword_180099048 + 64);
          v45 = *(unsigned __int8 *)(qword_180099048 + 60);
          LODWORD(v46) = *(unsigned __int8 *)(qword_180099048 + 59);
          HIDWORD(v46) = *(unsigned __int8 *)(qword_180099048 + 58);
          v47 = *(unsigned __int8 *)(qword_180099048 + 57);
          v48 = *(unsigned __int8 *)(qword_180099048 + 56);
          v50 = *(_QWORD *)(qword_180099048 + 48);
          v55 = *(_QWORD *)(qword_180099048 + 40);
          v54 = *(_QWORD *)(qword_180099048 + 32);
          v53 = *(_QWORD *)(qword_180099048 + 24);
          v52 = *(_QWORD *)(qword_180099048 + 16);
          v51 = *(_QWORD *)(qword_180099048 + 8);
          v57 = 0x2000000;
          sub_180002898(
            (int)&dword_180096000,
            (int)&unk_18008DA18,
            (__int64)&v57,
            (__int64)&v51,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)&v54,
            (__int64)&v55,
            (__int64)&v50,
            (__int64)&v48,
            (__int64)&v47,
            (__int64)&v46 + 4,
            (__int64)&v46,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v49,
            (__int64)&v40,
            (__int64)&v41);
        }
        LeaveCriticalSection(v22);
      }
      sub_18004C2F0(v86);
      v9 = v58;
    }
    if ( v39[0] )
    {
      v23 = lpCriticalSection;
      if ( lpCriticalSection )
      {
        EnterCriticalSection(lpCriticalSection);
        if ( (unsigned int)dword_180096000 > 5
          && (*(_QWORD *)algn_180096010 & 0x400000000000LL) != 0
          && (*(_QWORD *)&algn_180096010[8] & 0x400000000000LL) == *(_QWORD *)&algn_180096010[8] )
        {
          v48 = a2;
          sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), &v88);
          v49 = (__int64)&v88;
          v47 = *(_DWORD *)(qword_180099048 + 72);
          v46 = *(_QWORD *)(qword_180099048 + 64);
          v45 = *(unsigned __int8 *)(qword_180099048 + 60);
          v44 = *(unsigned __int8 *)(qword_180099048 + 59);
          v43 = *(unsigned __int8 *)(qword_180099048 + 58);
          v42 = *(unsigned __int8 *)(qword_180099048 + 57);
          v41 = *(unsigned __int8 *)(qword_180099048 + 56);
          v50 = *(_QWORD *)(qword_180099048 + 48);
          v55 = *(_QWORD *)(qword_180099048 + 40);
          v54 = *(_QWORD *)(qword_180099048 + 32);
          v53 = *(_QWORD *)(qword_180099048 + 24);
          v52 = *(_QWORD *)(qword_180099048 + 16);
          v51 = *(_QWORD *)(qword_180099048 + 8);
          v65 = 0x2000000;
          sub_1800025EC(
            (int)&dword_180096000,
            (int)&dword_18008D90C,
            (__int64)&v65,
            (__int64)&v51,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)&v54,
            (__int64)&v55,
            (__int64)&v50,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v43,
            (__int64)&v44,
            (__int64)&v45,
            (__int64)&v46,
            (__int64)&v46 + 4,
            (__int64)&v47,
            (__int64)&v49,
            (__int64)&v48);
        }
        LeaveCriticalSection(v23);
      }
      if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
        sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x13u, &MessageGuid, -2147023636);
      if ( v71 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 192LL))(v71, 1);
      return 2147943660LL;
    }
    else
    {
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      *(_OWORD *)v76 = 0;
      *(_OWORD *)v77 = 0;
      *(_OWORD *)v78 = 0;
      lpMem = 0;
      v80 = 0;
      v82 = 0;
      v83 = 1;
      v81 = a2;
      v24 = 0;
      sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), &v88);
      v25 = v88;
      if ( (_BYTE)v88 )
      {
        v26 = &v88;
        v27 = v94;
        do
        {
          *v27 = v25;
          ++v24;
          ++v27;
          v26 = (int *)((char *)v26 + 1);
          v25 = *(_BYTE *)v26;
        }
        while ( *(_BYTE *)v26 );
      }
      v94[v24] = 0;
      if ( lpMem )
        sub_18000969C(lpMem);
      sub_180004D20((__int64)&lpMem, (__int64)v94);
      v28 = sub_18003D4F8(v9, (unsigned int)v86, a2, (unsigned int)v84, (__int64)&v71, (__int64)&v72);
      v29 = v28;
      if ( v28 >= 0 )
      {
        v32 = sub_180043688(v9, (__int64)&v72, v84, (const wchar_t *)&v71);
        if ( v32 >= 0 )
        {
          v34 = lpCriticalSection;
          if ( lpCriticalSection )
          {
            EnterCriticalSection(lpCriticalSection);
            if ( (unsigned int)dword_180096000 > 5
              && (*(_QWORD *)algn_180096010 & 0x400000000000LL) != 0
              && (*(_QWORD *)&algn_180096010[8] & 0x400000000000LL) == *(_QWORD *)&algn_180096010[8] )
            {
              v47 = a2;
              sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), &v88);
              v56 = (__int64)&v88;
              v46 = *(_QWORD *)(qword_180099048 + 68);
              v45 = *(_DWORD *)(qword_180099048 + 64);
              v44 = *(unsigned __int8 *)(qword_180099048 + 60);
              v43 = *(unsigned __int8 *)(qword_180099048 + 59);
              v42 = *(unsigned __int8 *)(qword_180099048 + 58);
              v41 = *(unsigned __int8 *)(qword_180099048 + 57);
              v40 = *(unsigned __int8 *)(qword_180099048 + 56);
              v64 = *(_QWORD *)(qword_180099048 + 48);
              v63 = *(_QWORD *)(qword_180099048 + 40);
              v62 = *(_QWORD *)(qword_180099048 + 32);
              v61 = *(_QWORD *)(qword_180099048 + 24);
              v60 = *(_QWORD *)(qword_180099048 + 16);
              v59 = *(_QWORD *)(qword_180099048 + 8);
              v65 = 0x2000000;
              sub_1800025EC(
                (int)&dword_180096000,
                (int)&dword_18008D5F4,
                (__int64)&v65,
                (__int64)&v59,
                (__int64)&v60,
                (__int64)&v61,
                (__int64)&v62,
                (__int64)&v63,
                (__int64)&v64,
                (__int64)&v40,
                (__int64)&v41,
                (__int64)&v42,
                (__int64)&v43,
                (__int64)&v44,
                (__int64)&v45,
                (__int64)&v46,
                (__int64)&v46 + 4,
                (__int64)&v56,
                (__int64)&v47);
            }
            LeaveCriticalSection(v34);
          }
        }
        else
        {
          v33 = lpCriticalSection;
          if ( lpCriticalSection )
          {
            EnterCriticalSection(lpCriticalSection);
            if ( (unsigned int)dword_180096000 > 5
              && (*(_QWORD *)algn_180096010 & 0x400000000000LL) != 0
              && (*(_QWORD *)&algn_180096010[8] & 0x400000000000LL) == *(_QWORD *)&algn_180096010[8] )
            {
              LODWORD(v49) = v32;
              LODWORD(v50) = a2;
              sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), v94);
              v56 = (__int64)v94;
              LODWORD(v55) = *(_DWORD *)(qword_180099048 + 72);
              LODWORD(v54) = *(_DWORD *)(qword_180099048 + 68);
              LODWORD(v53) = *(_DWORD *)(qword_180099048 + 64);
              LODWORD(v52) = *(unsigned __int8 *)(qword_180099048 + 60);
              LODWORD(v51) = *(unsigned __int8 *)(qword_180099048 + 59);
              LODWORD(v57) = *(unsigned __int8 *)(qword_180099048 + 58);
              LODWORD(v58) = *(unsigned __int8 *)(qword_180099048 + 57);
              v48 = *(unsigned __int8 *)(qword_180099048 + 56);
              v64 = *(_QWORD *)(qword_180099048 + 48);
              v63 = *(_QWORD *)(qword_180099048 + 40);
              v62 = *(_QWORD *)(qword_180099048 + 32);
              v61 = *(_QWORD *)(qword_180099048 + 24);
              v60 = *(_QWORD *)(qword_180099048 + 16);
              v59 = *(_QWORD *)(qword_180099048 + 8);
              v66 = 0x2000000;
              sub_180002898(
                (int)&dword_180096000,
                (int)&byte_18008D6F9,
                (__int64)&v66,
                (__int64)&v59,
                (__int64)&v60,
                (__int64)&v61,
                (__int64)&v62,
                (__int64)&v63,
                (__int64)&v64,
                (__int64)&v48,
                (__int64)&v58,
                (__int64)&v57,
                (__int64)&v51,
                (__int64)&v52,
                (__int64)&v53,
                (__int64)&v54,
                (__int64)&v55,
                (__int64)&v56,
                (__int64)&v50,
                (__int64)&v49);
            }
            LeaveCriticalSection(v33);
          }
          if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
            sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x15u, &MessageGuid, v32);
        }
        if ( lpMem )
          sub_18000969C(lpMem);
        if ( v78[1] )
          sub_18000969C(v78[1]);
        if ( v78[0] )
          sub_18000969C(v78[0]);
        if ( v77[1] )
          sub_18000969C(v77[1]);
        if ( v77[0] )
          sub_18000969C(v77[0]);
        if ( v76[1] )
          sub_18000969C(v76[1]);
        if ( v76[0] )
          sub_18000969C(v76[0]);
        if ( v74 )
          sub_18000969C(v74);
        if ( v72 )
          sub_18000969C(v72);
        if ( v71 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 192LL))(v71, 1);
        return (unsigned int)v32;
      }
      else
      {
        v30 = (_UNKNOWN **)off_180096D60;
        if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
        {
          sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x1B5u, &MessageGuid, v28);
          v30 = (_UNKNOWN **)off_180096D60;
        }
        v31 = lpCriticalSection;
        if ( lpCriticalSection )
        {
          EnterCriticalSection(lpCriticalSection);
          if ( (unsigned int)dword_180096000 > 5
            && (*(_QWORD *)algn_180096010 & 0x400000000000LL) != 0
            && (*(_QWORD *)&algn_180096010[8] & 0x400000000000LL) == *(_QWORD *)&algn_180096010[8] )
          {
            v40 = v29;
            LODWORD(v58) = a2;
            sub_180055F44(v86, _InterlockedExchangeAdd64(&v87, 0), v94);
            v66 = (__int64)v94;
            LODWORD(v57) = *(_DWORD *)(qword_180099048 + 72);
            LODWORD(v51) = *(_DWORD *)(qword_180099048 + 68);
            LODWORD(v52) = *(_DWORD *)(qword_180099048 + 64);
            LODWORD(v53) = *(unsigned __int8 *)(qword_180099048 + 60);
            LODWORD(v54) = *(unsigned __int8 *)(qword_180099048 + 59);
            LODWORD(v55) = *(unsigned __int8 *)(qword_180099048 + 58);
            LODWORD(v50) = *(unsigned __int8 *)(qword_180099048 + 57);
            LODWORD(v49) = *(unsigned __int8 *)(qword_180099048 + 56);
            v59 = *(_QWORD *)(qword_180099048 + 48);
            v60 = *(_QWORD *)(qword_180099048 + 40);
            v61 = *(_QWORD *)(qword_180099048 + 32);
            v62 = *(_QWORD *)(qword_180099048 + 24);
            v63 = *(_QWORD *)(qword_180099048 + 16);
            v64 = *(_QWORD *)(qword_180099048 + 8);
            v56 = 0x2000000;
            sub_180002898(
              (int)&dword_180096000,
              (int)&word_18008D802,
              (__int64)&v56,
              (__int64)&v64,
              (__int64)&v63,
              (__int64)&v62,
              (__int64)&v61,
              (__int64)&v60,
              (__int64)&v59,
              (__int64)&v49,
              (__int64)&v50,
              (__int64)&v55,
              (__int64)&v54,
              (__int64)&v53,
              (__int64)&v52,
              (__int64)&v51,
              (__int64)&v57,
              (__int64)&v66,
              (__int64)&v58,
              (__int64)&v40);
          }
          LeaveCriticalSection(v31);
          v30 = (_UNKNOWN **)off_180096D60;
        }
        if ( v30 != &off_180096D60 && (*((_BYTE *)v30 + 28) & 1) != 0 )
          sub_180032DA0((TRACEHANDLE)v30[2], 0x14u, &MessageGuid, v29);
        if ( lpMem )
          sub_18000969C(lpMem);
        if ( v78[1] )
          sub_18000969C(v78[1]);
        if ( v78[0] )
          sub_18000969C(v78[0]);
        if ( v77[1] )
          sub_18000969C(v77[1]);
        if ( v77[0] )
          sub_18000969C(v77[0]);
        if ( v76[1] )
          sub_18000969C(v76[1]);
        if ( v76[0] )
          sub_18000969C(v76[0]);
        if ( v74 )
          sub_18000969C(v74);
        if ( v72 )
          sub_18000969C(v72);
        if ( v71 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 192LL))(v71, 1);
        return v29;
      }
    }
  }
  else
  {
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
      sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x12u, &MessageGuid, -2147024891);
    if ( v71 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 192LL))(v71, 1);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x18004eefc  push    rbx
0x18004eefe  push    rsi
0x18004eeff  push    rdi
0x18004ef00  push    r12
0x18004ef02  push    r13
0x18004ef04  push    r14
0x18004ef06  push    r15
0x18004ef08  sub     rsp, 4E0h
0x18004ef0f  mov     rax, cs:__security_cookie
0x18004ef16  xor     rax, rsp
0x18004ef19  mov     [rsp+518h+var_48], rax
0x18004ef21  mov     r15, r9
0x18004ef24  mov     rdi, r8
0x18004ef27  mov     r14d, edx
0x18004ef2a  mov     r12, rcx
0x18004ef2d  mov     [rsp+518h+var_3F0], rcx
0x18004ef35  mov     dword ptr [rsp+518h+var_464+4], edx
0x18004ef3c  xor     ebx, ebx
0x18004ef3e  mov     dword ptr [rsp+518h+var_464], ebx
0x18004ef45  lea     rcx, aMpdlpDebugonmp_0; "MpDlp_DebugOnMpUxCreate"
0x18004ef4c  call    sub_1800592BC
0x18004ef51  test    eax, eax
0x18004ef53  jz      short loc_18004EF5B
0x18004ef55  call    cs:DebugBreak
0x18004ef5b  mov     [rsp+518h+var_340], rbx
0x18004ef63  lea     rcx, [rsp+518h+var_340]
0x18004ef6b  call    sub_1800619DC
0x18004ef70  nop
0x18004ef71  test    rdi, rdi
0x18004ef74  jz      loc_18004F1BC
0x18004ef7a  cmp     r14d, 3A98h
0x18004ef81  jnz     short loc_18004EFD9
0x18004ef83  mov     rdx, rdi
0x18004ef86  lea     rcx, [rsp+518h+var_340]
0x18004ef8e  call    sub_180043004
0x18004ef93  test    eax, eax
0x18004ef95  jns     loc_18004F1BC
0x18004ef9b  lea     rsi, off_180096D60
0x18004efa2  mov     rcx, cs:off_180096D60
0x18004efa9  cmp     rcx, rsi
0x18004efac  jz      loc_18004F1CA
0x18004efb2  test    byte ptr [rcx+1Ch], 2
0x18004efb6  jz      loc_18004F1CA
0x18004efbc  mov     edx, 0Fh
0x18004efc1  mov     r9d, eax
0x18004efc4  lea     r8, MessageGuid
0x18004efcb  mov     rcx, [rcx+10h]
0x18004efcf  call    sub_180032DA0
0x18004efd4  jmp     loc_18004F1C3
0x18004efd9  xorps   xmm0, xmm0
0x18004efdc  movups  [rsp+518h+var_3A8], xmm0
0x18004efe4  xorps   xmm1, xmm1
0x18004efe7  movdqu  [rsp+518h+var_398], xmm1
0x18004eff0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004eff4  inc     r8
0x18004eff7  cmp     [rdi+r8*2], bx
0x18004effc  jnz     short loc_18004EFF4
0x18004effe  mov     rdx, rdi
0x18004f001  lea     rcx, [rsp+518h+var_3A8]
0x18004f009  call    sub_180034C4C
0x18004f00e  nop
0x18004f00f  mov     [rsp+518h+var_2A8], 1
0x18004f01b  mov     [rsp+518h+var_2A0], 1
0x18004f027  mov     [rsp+518h+var_298], rbx
0x18004f02f  lea     rax, ??_7?$JSON_StringParser@_W@details@json@web@@6B@; const web::json::details::JSON_StringParser<wchar_t>::`vftable'
0x18004f036  mov     [rsp+518h+var_2B0], rax
0x18004f03e  lea     rcx, [rsp+518h+var_3A8]
0x18004f046  cmp     qword ptr [rsp+518h+var_398+8], 7
0x18004f04f  cmova   rcx, qword ptr [rsp+518h+var_3A8]
0x18004f058  mov     [rsp+518h+var_290], rcx
0x18004f060  mov     [rsp+518h+var_288], rcx
0x18004f068  mov     rax, qword ptr [rsp+518h+var_398]
0x18004f070  lea     rcx, [rcx+rax*2]
0x18004f074  mov     [rsp+518h+var_280], rcx
0x18004f07c  mov     [rsp+518h+var_1E8], ebx
0x18004f083  xorps   xmm0, xmm0
0x18004f086  movups  [rsp+518h+var_1E0], xmm0
0x18004f08e  mov     [rsp+518h+var_1D0], rbx
0x18004f096  mov     [rsp+518h+var_1C8], 7
0x18004f0a2  mov     word ptr [rsp+518h+var_1E0], bx
0x18004f0aa  mov     [rsp+518h+var_1A0], ebx
0x18004f0b1  lea     rax, off_180096E10
0x18004f0b8  mov     [rsp+518h+var_198], rax
0x18004f0c0  lea     rdx, [rsp+518h+var_1E8]
0x18004f0c8  lea     rcx, [rsp+518h+var_2B0]
0x18004f0d0  call    sub_180064A70
0x18004f0d5  cmp     [rsp+518h+var_1A0], ebx
0x18004f0dc  jnz     loc_1800502BB
0x18004f0e2  mov     [rsp+518h+var_430], rbx
0x18004f0ea  lea     r8, [rsp+518h+var_1E8]
0x18004f0f2  lea     rdx, [rsp+518h+var_438]
0x18004f0fa  lea     rcx, [rsp+518h+var_2B0]
0x18004f102  call    sub_1800653E8
0x18004f107  mov     rdi, [rax]
0x18004f10a  mov     [rax], rbx
0x18004f10d  mov     [rsp+518h+var_430], rdi
0x18004f115  mov     dword ptr [rsp+518h+var_464], 6
0x18004f120  cmp     [rsp+518h+var_1A0], ebx
0x18004f127  jnz     loc_180050283
0x18004f12d  cmp     [rsp+518h+var_1E8], ebx
0x18004f134  jnz     loc_180050258
0x18004f13a  lea     rcx, [rsp+518h+var_1E0]
0x18004f142  call    sub_180057F94
0x18004f147  nop
0x18004f148  mov     rcx, [rsp+518h+var_340]
0x18004f150  mov     [rsp+518h+var_340], rdi
0x18004f158  test    rcx, rcx
0x18004f15b  jz      short loc_18004F173
0x18004f15d  mov     rax, [rcx]
0x18004f160  mov     edx, 1
0x18004f165  mov     rax, [rax+0C0h]
0x18004f16c  call    cs:__guard_dispatch_icall_fptr
0x18004f172  nop
0x18004f173  lea     rcx, [rsp+518h+var_3A8]
0x18004f17b  call    sub_180057F94
0x18004f180  lea     rsi, off_180096D60
0x18004f187  mov     rcx, cs:off_180096D60
0x18004f18e  jmp     short loc_18004F1CA
0x18004f190  mov     rcx, [rsp+518h+var_340]
0x18004f198  test    rcx, rcx
0x18004f19b  jz      short loc_18004F1B2
0x18004f19d  mov     rax, [rcx]
0x18004f1a0  mov     edx, 1
0x18004f1a5  mov     rax, [rax+0C0h]
0x18004f1ac  call    cs:__guard_dispatch_icall_fptr
0x18004f1b2  mov     eax, 80070057h
0x18004f1b7  jmp     loc_180050235
0x18004f1bc  lea     rsi, off_180096D60
0x18004f1c3  mov     rcx, cs:off_180096D60
0x18004f1ca  cmp     rcx, rsi
0x18004f1cd  jz      short loc_18004F1ED
0x18004f1cf  test    byte ptr [rcx+1Ch], 4
0x18004f1d3  jz      short loc_18004F1ED
0x18004f1d5  mov     edx, 11h
0x18004f1da  mov     r9d, r14d
0x18004f1dd  lea     r8, MessageGuid
0x18004f1e4  mov     rcx, [rcx+10h]
0x18004f1e8  call    sub_180032DA0
0x18004f1ed  lea     rdx, aS1580164383399; "S-1-5-80-1643833996-2250221834-40303827"...
0x18004f1f4  call    sub_18004345C
0x18004f1f9  test    al, al
0x18004f1fb  jnz     short loc_18004F267
0x18004f1fd  lea     rdx, aS1580191314886; "S-1-5-80-1913148863-3492339771-41656958"...
0x18004f204  call    sub_18004345C
0x18004f209  test    al, al
0x18004f20b  jnz     short loc_18004F267
0x18004f20d  mov     rcx, cs:off_180096D60
0x18004f214  cmp     rcx, rsi
0x18004f217  jz      short loc_18004F23B
0x18004f219  test    byte ptr [rcx+1Ch], 1
0x18004f21d  jz      short loc_18004F23B
0x18004f21f  mov     edx, 12h
0x18004f224  mov     r9d, 80070005h
0x18004f22a  lea     r8, MessageGuid
0x18004f231  mov     rcx, [rcx+10h]
0x18004f235  call    sub_180032DA0
0x18004f23a  nop
0x18004f23b  mov     rcx, [rsp+518h+var_340]
0x18004f243  test    rcx, rcx
0x18004f246  jz      short loc_18004F25D
0x18004f248  mov     rdx, [rcx]
0x18004f24b  mov     rax, [rdx+0C0h]
0x18004f252  mov     edx, 1
0x18004f257  call    cs:__guard_dispatch_icall_fptr
0x18004f25d  mov     eax, 80070005h
0x18004f262  jmp     loc_180050235
0x18004f267  lea     rcx, [rsp+518h+var_278]
0x18004f26f  call    sub_180036850
0x18004f274  lea     rcx, word_18007D770
0x18004f27b  test    r15, r15
0x18004f27e  cmovz   r15, rcx
0x18004f282  mov     [rsp+518h+var_2C8], r15
0x18004f28a  mov     rax, [rsp+518h+arg_20]
0x18004f292  test    rax, rax
0x18004f295  cmovz   rax, rcx
0x18004f299  mov     [rsp+518h+var_2C0], rax
0x18004f2a1  mov     rax, [rsp+518h+arg_28]
0x18004f2a9  test    rax, rax
0x18004f2ac  cmovz   rax, rcx
0x18004f2b0  mov     [rsp+518h+var_2B8], rax
0x18004f2b8  mov     [rsp+518h+var_468], bl
0x18004f2bf  lea     r8, [rsp+518h+var_468]
0x18004f2c7  mov     edx, r14d
0x18004f2ca  call    sub_18004D4AC
0x18004f2cf  mov     r13d, eax
0x18004f2d2  test    eax, eax
0x18004f2d4  jns     loc_18004F550
0x18004f2da  mov     r12, cs:lpCriticalSection
0x18004f2e1  test    r12, r12
0x18004f2e4  jz      loc_18004F52F
0x18004f2ea  mov     rcx, r12; lpCriticalSection
0x18004f2ed  call    EnterCriticalSection
0x18004f2f2  mov     r15, cs:off_18006EFF8
0x18004f2f9  mov     rdi, 400000000000h
0x18004f303  cmp     dword ptr [r15], 5
0x18004f307  jbe     loc_18004F525
0x18004f30d  test    [r15+10h], rdi
0x18004f311  jz      loc_18004F525
0x18004f317  mov     rax, [r15+18h]
0x18004f31b  and     rax, rdi
0x18004f31e  cmp     rax, [r15+18h]
0x18004f322  jnz     loc_18004F525
0x18004f328  mov     dword ptr [rsp+518h+var_464+4], r13d
0x18004f330  mov     dword ptr [rsp+518h+var_464], r14d
0x18004f338  mov     rdx, rbx
0x18004f33b  lock xadd [rsp+518h+var_1F0], rdx
0x18004f345  lea     r8, [rsp+518h+var_1E8]
0x18004f34d  lea     rcx, [rsp+518h+var_278]
0x18004f355  call    sub_180055F44
0x18004f35a  lea     rax, [rsp+518h+var_1E8]
0x18004f362  mov     [rsp+518h+var_438], rax
0x18004f36a  mov     rcx, cs:qword_180099048
0x18004f371  mov     eax, [rcx+48h]
0x18004f374  mov     dword ptr [rsp+518h+var_458], eax
0x18004f37b  mov     eax, [rcx+44h]
0x18004f37e  mov     dword ptr [rsp+518h+var_458+4], eax
0x18004f385  mov     eax, [rcx+40h]
0x18004f388  mov     dword ptr [rsp+518h+var_450], eax
0x18004f38f  movzx   eax, byte ptr [rcx+3Ch]
0x18004f393  mov     dword ptr [rsp+518h+var_450+4], eax
0x18004f39a  movzx   eax, byte ptr [rcx+3Bh]
0x18004f39e  mov     dword ptr [rsp+518h+var_448], eax
0x18004f3a5  movzx   eax, byte ptr [rcx+3Ah]
0x18004f3a9  mov     dword ptr [rsp+518h+var_448+4], eax
0x18004f3b0  movzx   eax, byte ptr [rcx+39h]
0x18004f3b4  mov     dword ptr [rsp+518h+var_440], eax
0x18004f3bb  movzx   eax, byte ptr [rcx+38h]
0x18004f3bf  mov     dword ptr [rsp+518h+var_440+4], eax
0x18004f3c6  mov     rax, [rcx+30h]
0x18004f3ca  mov     [rsp+518h+var_430], rax
0x18004f3d2  mov     rax, [rcx+28h]
0x18004f3d6  mov     [rsp+518h+var_408], rax
0x18004f3de  mov     rax, [rcx+20h]
0x18004f3e2  mov     [rsp+518h+var_410], rax
0x18004f3ea  mov     rax, [rcx+18h]
0x18004f3ee  mov     [rsp+518h+var_418], rax
0x18004f3f6  mov     rax, [rcx+10h]
0x18004f3fa  mov     [rsp+518h+var_420], rax
0x18004f402  mov     rax, [rcx+8]
0x18004f406  mov     [rsp+518h+var_428], rax
0x18004f40e  mov     [rsp+518h+var_3F8], 2000000h
0x18004f41a  lea     rax, [rsp+518h+var_464+4]
0x18004f422  mov     [rsp+518h+var_470], rax; __int64
0x18004f42a  lea     rax, [rsp+518h+var_464]
0x18004f432  mov     [rsp+518h+var_478], rax; __int64
0x18004f43a  lea     rax, [rsp+518h+var_438]
0x18004f442  mov     [rsp+518h+var_480], rax; __int64
0x18004f44a  lea     rax, [rsp+518h+var_458]
0x18004f452  mov     [rsp+518h+var_488], rax; __int64
0x18004f45a  lea     rax, [rsp+518h+var_458+4]
0x18004f462  mov     [rsp+518h+var_490], rax; __int64
0x18004f46a  lea     rax, [rsp+518h+var_450]
0x18004f472  mov     [rsp+518h+var_498], rax; __int64
0x18004f47a  lea     rax, [rsp+518h+var_450+4]
0x18004f482  mov     [rsp+518h+var_4A0], rax; __int64
0x18004f487  lea     rax, [rsp+518h+var_448]
0x18004f48f  mov     [rsp+518h+var_4A8], rax; __int64
0x18004f494  lea     rax, [rsp+518h+var_448+4]
0x18004f49c  mov     [rsp+518h+var_4B0], rax; __int64
0x18004f4a1  lea     rax, [rsp+518h+var_440]
0x18004f4a9  mov     [rsp+518h+var_4B8], rax; __int64
0x18004f4ae  lea     rax, [rsp+518h+var_440+4]
0x18004f4b6  mov     [rsp+518h+var_4C0], rax; __int64
0x18004f4bb  lea     rax, [rsp+518h+var_430]
0x18004f4c3  mov     [rsp+518h+var_4C8], rax; __int64
0x18004f4c8  lea     rax, [rsp+518h+var_408]
0x18004f4d0  mov     [rsp+518h+var_4D0], rax; __int64
0x18004f4d5  lea     rax, [rsp+518h+var_410]
0x18004f4dd  mov     [rsp+518h+var_4D8], rax; __int64
0x18004f4e2  lea     rax, [rsp+518h+var_418]
0x18004f4ea  mov     [rsp+518h+var_4E0], rax; __int64
0x18004f4ef  lea     rax, [rsp+518h+var_420]
0x18004f4f7  mov     [rsp+518h+var_4E8], rax; __int64
0x18004f4fc  lea     rax, [rsp+518h+var_428]
0x18004f504  mov     [rsp+518h+var_4F0], rax; __int64
0x18004f509  lea     rax, [rsp+518h+var_3F8]
0x18004f511  mov     [rsp+518h+var_4F8], rax; __int64
0x18004f516  lea     rdx, unk_18008DA18; int
0x18004f51d  mov     rcx, r15; int
0x18004f520  call    sub_180002898
0x18004f525  mov     rcx, r12; lpCriticalSection
0x18004f528  call    LeaveCriticalSection
0x18004f52d  jmp     short loc_18004F539
0x18004f52f  mov     rdi, 400000000000h
0x18004f539  lea     rcx, [rsp+518h+var_278]
0x18004f541  call    sub_18004C2F0
0x18004f546  mov     r12, [rsp+518h+var_3F0]
0x18004f54e  jmp     short loc_18004F55A
0x18004f550  mov     rdi, 400000000000h
0x18004f55a  cmp     [rsp+518h+var_468], bl
0x18004f561  jz      loc_18004F7F2
0x18004f567  mov     r12, cs:lpCriticalSection
0x18004f56e  test    r12, r12
0x18004f571  jz      loc_18004F798
0x18004f577  mov     rcx, r12; lpCriticalSection
0x18004f57a  call    EnterCriticalSection
0x18004f57f  mov     r15, cs:off_18006EFF8
0x18004f586  cmp     dword ptr [r15], 5
0x18004f58a  jbe     loc_18004F790
0x18004f590  test    [r15+10h], rdi
  ... truncated ...
```
