# ScheduledTileManager::Add(NotificationPlatform *,ushort *,ushort const *,_WPN_SCHEDULED_TILE *,_GUID *)

- ea: `0x18008e7b0`
- end: `0x18008ee28`
- name: `?Add@ScheduledTileManager@@UEAAJPEAVNotificationPlatform@@PEAGPEBGPEAU_WPN_SCHEDULED_TILE@@PEAU_GUID@@@Z`
- size: `1656`
- prototype: `__int64 __fastcall(ScheduledTileManager *__hidden this, struct NotificationPlatform *, unsigned __int16 *, const unsigned __int16 *, struct _WPN_SCHEDULED_TILE *, struct _GUID *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001f180`
- `0x1800264a4`
- `0x18002ee38`
- `0x1800325c8`
- `0x1800330f0`
- `0x180061800`
- `0x1800622ac`
- `0x18006ae88`
- `0x18007883c`
- `0x180087a3c`
- `0x18008a97c`
- `0x18008e7b0`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x180107150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ec5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ec5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ec69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008ec69`

## string_xrefs

- `0x18008e832`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008e97f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008e9e9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008ea6b`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008eae7`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008eb50`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008ebaa`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008ec08`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008ec95`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008ed53`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008edc9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtilemanager.cpp`
- `0x18008e896`: `SetScheduledTileUpdate`

## pseudocode

```c
__int64 __fastcall ScheduledTileManager::Add(
        ScheduledTileManager *this,
        struct NotificationPlatform *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _WPN_SCHEDULED_TILE *a5,
        struct _GUID *a6)
{
  int v7; // r13d
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  ScheduledTileManager *v13; // rsi
  ScheduledTileManager *v14; // rcx
  __int64 v15; // r8
  int v16; // r8d
  int v17; // r9d
  __int64 v19; // r14
  union _ULARGE_INTEGER v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // r8
  int v23; // eax
  const unsigned __int16 *v24; // r8
  int v25; // eax
  int v26; // eax
  int v27; // eax
  void *v28; // rdi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  HANDLE ProcessHeap; // rax
  int v32; // eax
  ScheduledTileManager *v33; // rcx
  char *v34; // rax
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  int v43; // eax
  int v44; // eax
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  ScheduledTileManager *v47; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v48; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v50; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v51; // [rsp+70h] [rbp-90h] BYREF
  int v52; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v53[4]; // [rsp+84h] [rbp-7Ch] BYREF
  int v54; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v55[130]; // [rsp+D4h] [rbp-2Ch] BYREF
  char v56; // [rsp+1D8h] [rbp+D8h] BYREF
  union _ULARGE_INTEGER v57; // [rsp+2D8h] [rbp+1D8h]
  __int64 v58; // [rsp+2E0h] [rbp+1E0h]
  int v59; // [rsp+2E8h] [rbp+1E8h]
  unsigned __int16 v60[17]; // [rsp+2ECh] [rbp+1ECh] BYREF
  char v61[5120]; // [rsp+30Eh] [rbp+20Eh] BYREF
  unsigned __int16 v62[65]; // [rsp+170Eh] [rbp+160Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+17D8h] [rbp+16D8h]

  v47 = this;
  v7 = 0;
  v50 = 0;
  memset_0(&v52, 0, 0x1710u);
  lpMem[0] = 0;
  if ( !*(_QWORD *)a5 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x80070057LL,
      v45);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 25;
    goto LABEL_5;
  }
  if ( !*((_QWORD *)a5 + 1) )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x80070057LL,
      v45);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 26;
    goto LABEL_5;
  }
  v48 = (struct _FILETIME)*((_QWORD *)a5 + 3);
  if ( (unsigned int)WpnCheckTimeIsExpired(v48) )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)0x80070057LL,
      v45);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 27;
    goto LABEL_5;
  }
  v19 = 2;
  v20 = *(union _ULARGE_INTEGER *)((char *)a5 + 24);
  v52 = 2;
  v57 = v20;
  if ( *((_DWORD *)a5 + 8) )
  {
    v48 = *(struct _FILETIME *)((char *)a5 + 36);
    if ( (unsigned int)WpnCheckTimeIsExpired(v48) )
    {
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        (const char *)0x80070057LL,
        v45);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 28;
LABEL_5:
      v12 = 2147942487LL;
LABEL_6:
      WPP_SF_d(v10[2], v11, WPP_91456f608371345bae03279a5fee97df_Traceguids, v12);
LABEL_7:
      v13 = v47;
      goto LABEL_8;
    }
  }
  v21 = *((_DWORD *)a5 + 10);
  v22 = (const unsigned __int16 *)*((_QWORD *)a5 + 1);
  v58 = *((_QWORD *)a5 + 4);
  v59 = v21;
  v23 = StringCchCopyW(v60, 0x11u, v22);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x284,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v23,
      v45);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 29;
    goto LABEL_33;
  }
  v24 = (const unsigned __int16 *)*((_QWORD *)a5 + 2);
  if ( v24 )
  {
    v25 = StringCchCopyW(v62, 0x41u, v24);
    v9 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x28B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        (const char *)(unsigned int)v25,
        v45);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 30;
      goto LABEL_33;
    }
  }
  v26 = StringCchCopyW(v55, 0x82u, a4);
  v9 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v26,
      v45);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 31;
LABEL_33:
    v12 = v9;
    goto LABEL_6;
  }
  v27 = WpnUtf16ToUtf8(*(LPCWCH *)a5, (char **)lpMem);
  v28 = lpMem[0];
  v9 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v27,
      v45);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_48;
    v30 = 32;
    goto LABEL_47;
  }
  v32 = StringCchCopyA(v61, 0x1400u, (const char *)lpMem[0]);
  v9 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
      (const char *)(unsigned int)v32,
      v45);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_48;
    v30 = 33;
    goto LABEL_47;
  }
  if ( a3 )
  {
    v34 = &v56;
    do
    {
      v35 = *(_OWORD *)a3;
      v36 = *((_OWORD *)a3 + 1);
      a3 += 64;
      *(_OWORD *)v34 = v35;
      v37 = *((_OWORD *)a3 - 6);
      *((_OWORD *)v34 + 1) = v36;
      v38 = *((_OWORD *)a3 - 5);
      *((_OWORD *)v34 + 2) = v37;
      v39 = *((_OWORD *)a3 - 4);
      *((_OWORD *)v34 + 3) = v38;
      v40 = *((_OWORD *)a3 - 3);
      *((_OWORD *)v34 + 4) = v39;
      v41 = *((_OWORD *)a3 - 2);
      *((_OWORD *)v34 + 5) = v40;
      v42 = *((_OWORD *)a3 - 1);
      *((_OWORD *)v34 + 6) = v41;
      *((_OWORD *)v34 + 7) = v42;
      v34 += 128;
      --v19;
    }
    while ( v19 );
    v54 = 1;
  }
  v43 = ScheduledTileManager::SetupTimer(v33, v57, (struct ScheduledTileManager::_PERSISTED_TILE *)&v52, &v50);
  v9 = v43;
  if ( v43 >= 0 )
  {
    v13 = v47;
    v7 = 1;
    v44 = TimerBrokerHelper::AddToList(
            *((TimerBrokerHelper **)v47 + 15),
            (struct _WPN_TIMER_PERSISTENCE *)v53,
            &v50,
            v57.QuadPart,
            1);
    v9 = v44;
    if ( v44 >= 0 )
    {
      *a6 = (struct _GUID)v53[0];
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
        (const char *)(unsigned int)v44,
        v46);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_91456f608371345bae03279a5fee97df_Traceguids, v9);
    }
    goto LABEL_49;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2AC,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtilemanager.cpp",
    (const char *)(unsigned int)v43,
    v45);
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v30 = 34;
LABEL_47:
    WPP_SF_d(v29[2], v30, WPP_91456f608371345bae03279a5fee97df_Traceguids, v9);
  }
LABEL_48:
  v13 = v47;
LABEL_49:
  if ( v28 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v28);
  }
LABEL_8:
  if ( WpnTelemetryAggregator::AddEventCount(
         *(WpnTelemetryAggregator **)(*((_QWORD *)v13 + 16) + 344LL),
         L"SetScheduledTileUpdate",
         a4,
         L"Tile")
    && (unsigned int)dword_18015C038 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL, v15) )
  {
    lpMem[0] = (LPVOID)v57.QuadPart;
    v48 = (struct _FILETIME)v53;
    v51 = a4;
    LODWORD(v47) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
      (_DWORD)v14,
      (unsigned int)byte_180138EBD,
      v16,
      v17,
      (__int64)&v47,
      (__int64)&v51,
      (__int64)&v48,
      (__int64)lpMem);
  }
  if ( (v9 & 0x80000000) != 0 && v7 )
    ScheduledTileManager::CleanupTimer(v14, &v50, (struct _WPN_TIMER_PERSISTENCE *)v53);
  return v9;
}

```

## disassembly

```asm
0x18008e7b0  mov     [rsp-8+arg_8], rbx
0x18008e7b5  push    rbp
0x18008e7b6  push    rsi
0x18008e7b7  push    rdi
0x18008e7b8  push    r12
0x18008e7ba  push    r13
0x18008e7bc  push    r14
0x18008e7be  push    r15
0x18008e7c0  lea     rbp, [rsp-16A0h]
0x18008e7c8  mov     eax, 17A0h
0x18008e7cd  call    _alloca_probe
0x18008e7d2  sub     rsp, rax
0x18008e7d5  mov     rax, cs:__security_cookie
0x18008e7dc  xor     rax, rsp
0x18008e7df  mov     [rbp+16D0h+var_40], rax
0x18008e7e6  mov     rdi, [rbp+16D0h+arg_20]
0x18008e7ed  mov     rsi, r8
0x18008e7f0  mov     r15, [rbp+16D0h+arg_28]
0x18008e7f7  xorps   xmm0, xmm0
0x18008e7fa  mov     [rsp+17D0h+var_1790], rcx
0x18008e7ff  xor     ebx, ebx
0x18008e801  mov     r8d, 1710h; Size
0x18008e807  lea     rcx, [rbp+16D0h+var_1750]; void *
0x18008e80b  xor     edx, edx; Val
0x18008e80d  mov     r13d, ebx
0x18008e810  movups  xmmword ptr [rsp+17D0h+var_1770.Data1], xmm0
0x18008e815  mov     r12, r9
0x18008e818  call    memset_0
0x18008e81d  mov     [rsp+17D0h+lpMem], rbx
0x18008e822  cmp     [rdi], rbx
0x18008e825  jnz     loc_18008E972
0x18008e82b  mov     rcx, [rbp+16D8h]; this
0x18008e832  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e839  mov     r9d, 80070057h; char *
0x18008e83f  mov     edx, 261h; void *
0x18008e844  mov     ebx, r9d
0x18008e847  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e853  lea     rax, WPP_GLOBAL_Control
0x18008e85a  cmp     rcx, rax
0x18008e85d  jz      short loc_18008E880
0x18008e85f  test    byte ptr [rcx+1Ch], 80h
0x18008e863  jz      short loc_18008E880
0x18008e865  mov     edx, 19h
0x18008e86a  mov     r9d, 80070057h
0x18008e870  mov     rcx, [rcx+10h]
0x18008e874  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x18008e87b  call    WPP_SF_d
0x18008e880  mov     rsi, [rsp+17D0h+var_1790]
0x18008e885  mov     rcx, [rsi+80h]
0x18008e88c  lea     r9, aTile_1; "Tile"
0x18008e893  mov     r8, r12; unsigned __int16 *
0x18008e896  lea     rdx, aSetscheduledti; "SetScheduledTileUpdate"
0x18008e89d  mov     rcx, [rcx+158h]; this
0x18008e8a4  call    ?AddEventCount@WpnTelemetryAggregator@@QEAA_NPEBG00@Z; WpnTelemetryAggregator::AddEventCount(ushort const *,ushort const *,ushort const *)
0x18008e8a9  test    al, al
0x18008e8ab  jz      short loc_18008E924
0x18008e8ad  mov     eax, cs:dword_18015C038
0x18008e8b3  cmp     eax, 5
0x18008e8b6  jbe     short loc_18008E924
0x18008e8b8  mov     rdx, 400000000000h
0x18008e8c2  lea     rcx, dword_18015C038
0x18008e8c9  call    _tlgKeywordOn
0x18008e8ce  test    al, al
0x18008e8d0  jz      short loc_18008E924
0x18008e8d2  mov     rax, qword ptr [rbp+16D0h+var_14F8]
0x18008e8d9  lea     rdx, byte_180138EBD
0x18008e8e0  mov     [rsp+17D0h+lpMem], rax
0x18008e8e5  lea     rax, [rbp+16D0h+var_174C]
0x18008e8e9  mov     qword ptr [rsp+17D0h+var_1788.dwLowDateTime], rax
0x18008e8ee  lea     rax, [rsp+17D0h+lpMem]
0x18008e8f3  mov     [rsp+17D0h+var_1798], rax
0x18008e8f8  lea     rax, [rsp+17D0h+var_1788]
0x18008e8fd  mov     [rsp+17D0h+var_17A0], rax
0x18008e902  lea     rax, [rsp+17D0h+var_1760]
0x18008e907  mov     [rsp+17D0h+var_17A8], rax
0x18008e90c  lea     rax, [rsp+17D0h+var_1790]
0x18008e911  mov     qword ptr [rsp+17D0h+var_17B0], rax
0x18008e916  mov     [rsp+17D0h+var_1760], r12
0x18008e91b  mov     dword ptr [rsp+17D0h+var_1790], ebx
0x18008e91f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x18008e924  test    ebx, ebx
0x18008e926  jns     short loc_18008E946
0x18008e928  test    r13d, r13d
0x18008e92b  jz      short loc_18008E946
0x18008e92d  movaps  xmm0, xmmword ptr [rsp+17D0h+var_1770.Data1]
0x18008e932  lea     r8, [rbp+16D0h+var_174C]; struct _WPN_TIMER_PERSISTENCE *
0x18008e936  lea     rdx, [rsp+17D0h+var_1770]; struct _GUID
0x18008e93b  movdqa  xmmword ptr [rsp+17D0h+var_1770.Data1], xmm0
0x18008e941  call    ?CleanupTimer@ScheduledTileManager@@AEAAXU_GUID@@PEAU_WPN_TIMER_PERSISTENCE@@@Z; ScheduledTileManager::CleanupTimer(_GUID,_WPN_TIMER_PERSISTENCE *)
0x18008e946  mov     eax, ebx
0x18008e948  mov     rcx, [rbp+16D0h+var_40]
0x18008e94f  xor     rcx, rsp; StackCookie
0x18008e952  call    __security_check_cookie
0x18008e957  mov     rbx, [rsp+17D0h+arg_8]
0x18008e95f  add     rsp, 17A0h
0x18008e966  pop     r15
0x18008e968  pop     r14
0x18008e96a  pop     r13
0x18008e96c  pop     r12
0x18008e96e  pop     rdi
0x18008e96f  pop     rsi
0x18008e970  pop     rbp
0x18008e971  retn
0x18008e972  cmp     [rdi+8], rbx
0x18008e976  jnz     short loc_18008E9C4
0x18008e978  mov     rcx, [rbp+16D8h]; this
0x18008e97f  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e986  mov     r9d, 80070057h; char *
0x18008e98c  mov     edx, 262h; void *
0x18008e991  mov     ebx, r9d
0x18008e994  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e999  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9a0  lea     rax, WPP_GLOBAL_Control
0x18008e9a7  cmp     rcx, rax
0x18008e9aa  jz      loc_18008E880
0x18008e9b0  test    byte ptr [rcx+1Ch], 80h
0x18008e9b4  jz      loc_18008E880
0x18008e9ba  mov     edx, 1Ah
0x18008e9bf  jmp     loc_18008E86A
0x18008e9c4  mov     rax, [rdi+18h]
0x18008e9c8  mov     [rsp+17D0h+var_1788.dwLowDateTime], eax
0x18008e9cc  shr     rax, 20h
0x18008e9d0  mov     [rsp+17D0h+var_1788.dwHighDateTime], eax
0x18008e9d4  mov     rcx, qword ptr [rsp+17D0h+var_1788.dwLowDateTime]; struct _FILETIME
0x18008e9d9  call    ?WpnCheckTimeIsExpired@@YAHU_FILETIME@@@Z; WpnCheckTimeIsExpired(_FILETIME)
0x18008e9de  test    eax, eax
0x18008e9e0  jz      short loc_18008EA2E
0x18008e9e2  mov     rcx, [rbp+16D8h]; this
0x18008e9e9  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e9f0  mov     r9d, 80070057h; char *
0x18008e9f6  mov     edx, 26Eh; void *
0x18008e9fb  mov     ebx, r9d
0x18008e9fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ea03  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea0a  lea     rax, WPP_GLOBAL_Control
0x18008ea11  cmp     rcx, rax
0x18008ea14  jz      loc_18008E880
0x18008ea1a  test    byte ptr [rcx+1Ch], 80h
0x18008ea1e  jz      loc_18008E880
0x18008ea24  mov     edx, 1Bh
0x18008ea29  jmp     loc_18008E86A
0x18008ea2e  mov     r14d, 2
0x18008ea34  mov     rax, [rdi+18h]
0x18008ea38  mov     [rbp+16D0h+var_1750], r14d
0x18008ea3c  mov     qword ptr [rbp+16D0h+var_14F8], rax
0x18008ea43  cmp     [rdi+20h], ebx
0x18008ea46  jz      short loc_18008EAAF
0x18008ea48  mov     eax, [rdi+24h]
0x18008ea4b  mov     [rsp+17D0h+var_1788.dwLowDateTime], eax
0x18008ea4f  mov     eax, [rdi+28h]
0x18008ea52  mov     [rsp+17D0h+var_1788.dwHighDateTime], eax
0x18008ea56  mov     rcx, qword ptr [rsp+17D0h+var_1788.dwLowDateTime]; struct _FILETIME
0x18008ea5b  call    ?WpnCheckTimeIsExpired@@YAHU_FILETIME@@@Z; WpnCheckTimeIsExpired(_FILETIME)
0x18008ea60  test    eax, eax
0x18008ea62  jz      short loc_18008EAAF
0x18008ea64  mov     rcx, [rbp+16D8h]; this
0x18008ea6b  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008ea72  mov     r9d, 80070057h; char *
0x18008ea78  mov     edx, 27Ah; void *
0x18008ea7d  mov     ebx, r9d
0x18008ea80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ea85  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea8c  lea     rax, WPP_GLOBAL_Control
0x18008ea93  cmp     rcx, rax
0x18008ea96  jz      loc_18008E880
0x18008ea9c  test    byte ptr [rcx+1Ch], 80h
0x18008eaa0  jz      loc_18008E880
0x18008eaa6  lea     edx, [r14+1Ah]
0x18008eaaa  jmp     loc_18008E86A
0x18008eaaf  movsd   xmm0, qword ptr [rdi+20h]
0x18008eab4  lea     rcx, [rbp+16D0h+var_14E4]; unsigned __int16 *
0x18008eabb  mov     eax, [rdi+28h]
0x18008eabe  mov     edx, 11h; unsigned __int64
0x18008eac3  mov     r8, [rdi+8]; unsigned __int16 *
0x18008eac7  movsd   [rbp+16D0h+var_14F0], xmm0
0x18008eacf  mov     [rbp+16D0h+var_14E8], eax
0x18008ead5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008eada  mov     ebx, eax
0x18008eadc  test    eax, eax
0x18008eade  jns     short loc_18008EB29
0x18008eae0  mov     rcx, [rbp+16D8h]; this
0x18008eae7  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008eaee  mov     r9d, eax; char *
0x18008eaf1  mov     edx, 284h; void *
0x18008eaf6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008eafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb02  lea     rax, WPP_GLOBAL_Control
0x18008eb09  cmp     rcx, rax
0x18008eb0c  jz      loc_18008E880
0x18008eb12  test    byte ptr [rcx+1Ch], 80h
0x18008eb16  jz      loc_18008E880
0x18008eb1c  mov     edx, 1Dh
0x18008eb21  mov     r9d, ebx
0x18008eb24  jmp     loc_18008E870
0x18008eb29  mov     r8, [rdi+10h]; unsigned __int16 *
0x18008eb2d  test    r8, r8
0x18008eb30  jz      short loc_18008EB8C
0x18008eb32  mov     edx, 41h ; 'A'; unsigned __int64
0x18008eb37  lea     rcx, [rbp+16D0h+var_C2]; unsigned __int16 *
0x18008eb3e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008eb43  mov     ebx, eax
0x18008eb45  test    eax, eax
0x18008eb47  jns     short loc_18008EB8C
0x18008eb49  mov     rcx, [rbp+16D8h]; this
0x18008eb50  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008eb57  mov     r9d, eax; char *
0x18008eb5a  mov     edx, 28Bh; void *
0x18008eb5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008eb64  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb6b  lea     rax, WPP_GLOBAL_Control
0x18008eb72  cmp     rcx, rax
0x18008eb75  jz      loc_18008E880
0x18008eb7b  test    byte ptr [rcx+1Ch], 80h
0x18008eb7f  jz      loc_18008E880
0x18008eb85  mov     edx, 1Eh
0x18008eb8a  jmp     short loc_18008EB21
0x18008eb8c  mov     r8, r12; unsigned __int16 *
0x18008eb8f  lea     rcx, [rbp+16D0h+var_16FC]; unsigned __int16 *
0x18008eb93  mov     edx, 82h; unsigned __int64
0x18008eb98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008eb9d  mov     ebx, eax
0x18008eb9f  test    eax, eax
0x18008eba1  jns     short loc_18008EBE9
0x18008eba3  mov     rcx, [rbp+16D8h]; this
0x18008ebaa  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008ebb1  mov     r9d, eax; char *
0x18008ebb4  mov     edx, 292h; void *
0x18008ebb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ebbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ebc5  lea     rax, WPP_GLOBAL_Control
0x18008ebcc  cmp     rcx, rax
0x18008ebcf  jz      loc_18008E880
0x18008ebd5  test    byte ptr [rcx+1Ch], 80h
0x18008ebd9  jz      loc_18008E880
0x18008ebdf  mov     edx, 1Fh
0x18008ebe4  jmp     loc_18008EB21
0x18008ebe9  mov     rcx, [rdi]; lpWideCharStr
0x18008ebec  lea     rdx, [rsp+17D0h+lpMem]; char **
0x18008ebf1  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x18008ebf6  mov     rdi, [rsp+17D0h+lpMem]
0x18008ebfb  mov     ebx, eax
0x18008ebfd  test    eax, eax
0x18008ebff  jns     short loc_18008EC74
0x18008ec01  mov     rcx, [rbp+16D8h]; this
0x18008ec08  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008ec0f  mov     r9d, eax; char *
0x18008ec12  mov     edx, 295h; void *
0x18008ec17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ec1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ec23  lea     rax, WPP_GLOBAL_Control
0x18008ec2a  cmp     rcx, rax
0x18008ec2d  jz      short loc_18008EC4D
0x18008ec2f  test    byte ptr [rcx+1Ch], 80h
0x18008ec33  jz      short loc_18008EC4D
0x18008ec35  mov     edx, 20h ; ' '
0x18008ec3a  mov     rcx, [rcx+10h]
0x18008ec3e  lea     r8, WPP_91456f608371345bae03279a5fee97df_Traceguids
0x18008ec45  mov     r9d, ebx
0x18008ec48  call    WPP_SF_d
0x18008ec4d  mov     rsi, [rsp+17D0h+var_1790]
0x18008ec52  test    rdi, rdi
0x18008ec55  jz      loc_18008E885
0x18008ec5b  call    cs:__imp_GetProcessHeap
0x18008ec61  mov     r8, rdi; lpMem
0x18008ec64  xor     edx, edx; dwFlags
0x18008ec66  mov     rcx, rax; hHeap
0x18008ec69  call    cs:__imp_HeapFree
0x18008ec6f  jmp     loc_18008E885
0x18008ec74  mov     r8, rdi; char *
0x18008ec77  lea     rcx, [rbp+16D0h+var_14C2]; char *
0x18008ec7e  mov     edx, 1400h; unsigned __int64
0x18008ec83  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18008ec88  mov     ebx, eax
0x18008ec8a  test    eax, eax
0x18008ec8c  jns     short loc_18008ECCC
0x18008ec8e  mov     rcx, [rbp+16D8h]; this
0x18008ec95  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008ec9c  mov     r9d, eax; char *
0x18008ec9f  mov     edx, 29Bh; void *
0x18008eca4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008eca9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ecb0  lea     rax, WPP_GLOBAL_Control
0x18008ecb7  cmp     rcx, rax
0x18008ecba  jz      short loc_18008EC4D
0x18008ecbc  test    byte ptr [rcx+1Ch], 80h
0x18008ecc0  jz      short loc_18008EC4D
0x18008ecc2  mov     edx, 21h ; '!'
0x18008ecc7  jmp     loc_18008EC3A
0x18008eccc  test    rsi, rsi
0x18008eccf  jz      short loc_18008ED31
0x18008ecd1  lea     rax, [rbp+16D0h+var_15F8]
0x18008ecd8  movups  xmm0, xmmword ptr [rsi]
0x18008ecdb  movups  xmm1, xmmword ptr [rsi+10h]
0x18008ecdf  lea     rsi, [rsi+80h]
0x18008ece6  movups  xmmword ptr [rax], xmm0
0x18008ece9  movups  xmm0, xmmword ptr [rsi-60h]
0x18008eced  movups  xmmword ptr [rax+10h], xmm1
0x18008ecf1  movups  xmm1, xmmword ptr [rsi-50h]
0x18008ecf5  movups  xmmword ptr [rax+20h], xmm0
  ... truncated ...
```
