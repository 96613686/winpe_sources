# InitializeTapiLine(ulong,ulong,linedevcaps_tag *,ulong,ulong,ushort const *,ushort const *,ushort const *,int,ulong)

- ea: `0x14004b0e0`
- end: `0x14004b6c7`
- name: `?InitializeTapiLine@@YAKKKPEAUlinedevcaps_tag@@KKPEBG11HK@Z`
- size: `1511`
- prototype: `__int64 __fastcall(DWORD dwDeviceID, int, struct linedevcaps_tag *, int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x1400492fc`

## callees

- `0x140002c43`
- `0x1400033ec`
- `0x140004a30`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x14000c5ac`
- `0x14004a638`
- `0x14004a690`
- `0x14004b0e0`
- `0x14004b6d0`
- `0x14004c07c`
- `0x14004e5c4`
- `0x140065d14`
- `0x140065dbc`
- `0x140067168`
- `0x140076484`
- `0x14007fd10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004b44c`
- `KERNEL32!GetLastError` at `0x14004b44c`
- `TAPI32!lineOpenW` at `0x14004b2e4`
- `TAPI32!lineOpenW` at `0x14004b32f`
- `TAPI32!lineOpenW` at `0x14004b2e4`
- `TAPI32!lineOpenW` at `0x14004b32f`
- `TAPI32!lineSetStatusMessages` at `0x14004b3a9`
- `TAPI32!lineSetStatusMessages` at `0x14004b3a9`

## pseudocode

```c
__int64 __fastcall InitializeTapiLine(
        DWORD dwDeviceID,
        int a2,
        struct linedevcaps_tag *a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        int a9,
        unsigned int a10)
{
  unsigned __int16 *v11; // rbp
  void *v13; // rax
  DWORD_PTR dwCallbackInstance; // rbx
  DWORD LastError; // edi
  __int64 v16; // rax
  __int64 v17; // rdi
  WCHAR *v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // rax
  int v21; // r15d
  struct _DEVICE_PROVIDER *DeviceProvider; // r13
  LONG v23; // eax
  DWORD v24; // r14d
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  DWORD_PTR *v29; // rax
  int v30; // eax
  CMapDeviceId *v31; // rcx
  unsigned int v32; // r10d
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  HLINE v36; // ecx
  bool v37; // cf
  struct linedevstatus_tag *LineDevStatus; // rax
  HLINE hLine; // [rsp+50h] [rbp-48h] BYREF
  LPCWSTR lpString2; // [rsp+58h] [rbp-40h]

  hLine = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  v13 = (void *)pMemAlloc(0xC0u);
  dwCallbackInstance = (DWORD_PTR)v13;
  if ( !v13 )
  {
    lpString2 = 0;
LABEL_7:
    LastError = 8;
    goto LABEL_48;
  }
  memset_0(v13, 0, 0xC0u);
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)((char *)&a3->dwTotalSize + 2 * v16 + a3->dwProviderInfoOffset) );
  v17 = (unsigned int)(v16 + 1);
  v18 = (WCHAR *)pMemAlloc(2 * v17);
  lpString2 = v18;
  if ( !v18 )
    goto LABEL_7;
  v19 = StringCchCopyW(v18, (unsigned int)v17, (const unsigned __int16 *)((char *)a3 + a3->dwProviderInfoOffset));
  if ( v19 < 0 )
  {
    LastError = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        (unsigned int)v19);
    }
    goto LABEL_48;
  }
  v20 = FixupDeviceName((const unsigned __int16 *)((char *)a3 + a3->dwLineNameOffset));
  v11 = v20;
  if ( !v20 )
    goto LABEL_7;
  if ( !a3->dwPermanentLineID )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v20);
    }
    LastError = 1200;
    goto LABEL_48;
  }
  v21 = IsDeviceModem(a3);
  DeviceProvider = FindDeviceProvider(lpString2, 1);
  if ( !DeviceProvider )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v11);
    }
    LastError = 1204;
    goto LABEL_48;
  }
  if ( v21 )
  {
    if ( !lineOpenW(g_hLineApp, dwDeviceID, &hLine, 0x20000u, 0, dwCallbackInstance, 6u, 0x12u, 0) )
      goto LABEL_38;
    v23 = lineOpenW(g_hLineApp, dwDeviceID, &hLine, 0x20000u, 0, dwCallbackInstance, 6u, 0x10u, 0);
  }
  else
  {
    v23 = lineOpenW(g_hLineApp, dwDeviceID, &hLine, 0x20000u, 0, dwCallbackInstance, 6u, 0x20u, 0);
  }
  LastError = v23;
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        (unsigned int)&WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        (_DWORD)v11,
        v23);
    }
    goto LABEL_48;
  }
LABEL_38:
  *(_DWORD *)(dwCallbackInstance + 32) = hLine;
  v24 = a3->dwLineStates & 0x1000E02;
  LastError = lineSetStatusMessages(hLine, v24, 0x3Cu);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, v25, v24, 60, LastError);
    }
    if ( LastError == -2147483605 )
      *(_DWORD *)(dwCallbackInstance + 32) = 0;
    LastError = 0;
  }
  *(_DWORD *)(dwCallbackInstance + 16) = 1162758476;
  *(_DWORD *)(dwCallbackInstance + 20) = dwDeviceID;
  *(_DWORD *)(dwCallbackInstance + 28) = a3->dwPermanentLineID;
  *(_QWORD *)(dwCallbackInstance + 40) = DeviceProvider;
  *(_DWORD *)(dwCallbackInstance + 104) = v21;
  *(_DWORD *)(dwCallbackInstance + 72) = 537919488;
  *(_QWORD *)(dwCallbackInstance + 80) = 0;
  *(_QWORD *)(dwCallbackInstance + 176) = 0;
  v26 = StringDup(v11);
  *(_QWORD *)(dwCallbackInstance + 56) = v26;
  if ( !v26 )
    goto LABEL_47;
  if ( a6 )
  {
    v33 = StringDup(a6);
    *(_QWORD *)(dwCallbackInstance + 88) = v33;
    if ( !v33 )
    {
LABEL_47:
      LastError = GetLastError();
      goto LABEL_48;
    }
  }
  else
  {
    *(_QWORD *)(dwCallbackInstance + 88) = 0;
  }
  if ( a7 )
  {
    v34 = StringDup(a7);
    *(_QWORD *)(dwCallbackInstance + 96) = v34;
    if ( !v34 )
      goto LABEL_47;
  }
  else
  {
    *(_QWORD *)(dwCallbackInstance + 96) = 0;
  }
  if ( a8 )
  {
    v35 = StringDup(a8);
    *(_QWORD *)(dwCallbackInstance + 64) = v35;
    if ( !v35 )
      goto LABEL_47;
  }
  else
  {
    *(_QWORD *)(dwCallbackInstance + 64) = 0;
  }
  v36 = *(_DWORD *)(dwCallbackInstance + 32);
  v37 = (a3->dwLineStates & 2) != 0;
  *(_DWORD *)(dwCallbackInstance + 112) = 0;
  *(_DWORD *)(dwCallbackInstance + 108) = v37 ? a4 : 0;
  *(_DWORD *)(dwCallbackInstance + 76) = a5;
  *(_DWORD *)(dwCallbackInstance + 164) = a3->dwLineStates;
  *(_DWORD *)(dwCallbackInstance + 24) = a2;
  *(_DWORD *)(dwCallbackInstance + 184) = a10;
  if ( v36 )
  {
    LineDevStatus = MyLineGetLineDevStatus(v36);
    if ( LineDevStatus )
    {
      if ( LineDevStatus->dwNumOpens && LineDevStatus->dwNumActiveCalls )
        *(_DWORD *)(dwCallbackInstance + 156) = 1;
      pMemFree(LineDevStatus);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v11);
    }
    *(_DWORD *)(dwCallbackInstance + 76) |= 0x20000000u;
  }
LABEL_48:
  pMemFree(v11);
  pMemFree((LPVOID)lpString2);
  if ( LastError )
  {
    FreeTapiLine((struct _LINE_INFO *)dwCallbackInstance);
    return LastError;
  }
  v29 = (DWORD_PTR *)qword_1400A1748;
  ++g_dwDeviceCount;
  *(_QWORD *)dwCallbackInstance = &g_TapiLinesListHead;
  *(_QWORD *)(dwCallbackInstance + 8) = v29;
  *v29 = dwCallbackInstance;
  qword_1400A1748 = dwCallbackInstance;
  if ( a9 )
    goto LABEL_65;
  if ( g_dwManualAnswerDeviceId )
    goto LABEL_58;
  if ( *(_DWORD *)(dwCallbackInstance + 184) != 10 )
    goto LABEL_58;
  if ( (*(_BYTE *)(dwCallbackInstance + 76) & 1) != 0 )
    goto LABEL_58;
  g_dwManualAnswerDeviceId = *(_DWORD *)(dwCallbackInstance + 24);
  v30 = WriteManualAnswerDeviceId(&g_TapiLinesListHead, v27, v28);
  if ( !v30 )
    goto LABEL_58;
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_h(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
      (unsigned __int16)v30);
LABEL_58:
    v31 = WPP_GLOBAL_Control;
  }
  v32 = g_dwDeviceEnabledCount;
  if ( g_dwDeviceEnabledCount >= g_dwDeviceEnabledLimit )
  {
    if ( v31 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 4) != 0 && *((_BYTE *)v31 + 25) >= 3u )
      WPP_SF_dd(
        *((_QWORD *)v31 + 2),
        103,
        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        g_dwDeviceEnabledLimit,
        g_dwDeviceEnabledCount);
    ResetDeviceFlags((struct _LINE_INFO *)dwCallbackInstance);
LABEL_65:
    v32 = g_dwDeviceEnabledCount;
  }
  if ( (*(_BYTE *)(dwCallbackInstance + 76) & 3) != 0
    || *(_DWORD *)(dwCallbackInstance + 24) == g_dwManualAnswerDeviceId )
  {
    g_dwDeviceEnabledCount = v32 + 1;
  }
  return LastError;
}

```

## disassembly

```asm
0x14004b0e0  mov     rax, rsp
0x14004b0e3  mov     [rax+8], rbx
0x14004b0e7  mov     [rax+20h], r9d
0x14004b0eb  mov     [rax+10h], edx
0x14004b0ee  push    rbp
0x14004b0ef  push    rsi
0x14004b0f0  push    rdi
0x14004b0f1  push    r12
0x14004b0f3  push    r13
0x14004b0f5  push    r14
0x14004b0f7  push    r15
0x14004b0f9  sub     rsp, 60h
0x14004b0fd  xor     r14d, r14d
0x14004b100  mov     rsi, r8
0x14004b103  mov     [rax-48h], r14d
0x14004b107  mov     ebp, r14d
0x14004b10a  mov     r12d, ecx
0x14004b10d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b114  lea     r15, WPP_GLOBAL_Control
0x14004b11b  cmp     rcx, r15
0x14004b11e  jz      short loc_14004B140
0x14004b120  test    byte ptr [rcx+1Ch], 4
0x14004b124  jz      short loc_14004B140
0x14004b126  cmp     byte ptr [rcx+19h], 5
0x14004b12a  jb      short loc_14004B140
0x14004b12c  mov     rcx, [rcx+10h]
0x14004b130  lea     edx, [r14+5Fh]
0x14004b134  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b13b  call    WPP_SF_
0x14004b140  mov     edi, 0C0h
0x14004b145  mov     ecx, edi; dwBytes
0x14004b147  call    pMemAlloc
0x14004b14c  mov     rbx, rax
0x14004b14f  test    rax, rax
0x14004b152  jnz     short loc_14004B163
0x14004b154  mov     [rsp+98h+lpString2], r14
0x14004b159  mov     edi, 8
0x14004b15e  jmp     loc_14004B45B
0x14004b163  mov     r8, rdi; Size
0x14004b166  xor     edx, edx; Val
0x14004b168  mov     rcx, rbx; void *
0x14004b16b  call    memset_0
0x14004b170  mov     ecx, [rsi+10h]
0x14004b173  add     rcx, rsi
0x14004b176  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004b17a  inc     rax
0x14004b17d  cmp     [rcx+rax*2], r14w
0x14004b182  jnz     short loc_14004B17A
0x14004b184  inc     eax
0x14004b186  mov     edi, eax
0x14004b188  lea     rcx, [rax+rax]; dwBytes
0x14004b18c  call    pMemAlloc
0x14004b191  mov     [rsp+98h+lpString2], rax
0x14004b196  test    rax, rax
0x14004b199  jz      short loc_14004B159
0x14004b19b  mov     r8d, [rsi+10h]
0x14004b19f  mov     edx, edi; unsigned __int64
0x14004b1a1  add     r8, rsi; unsigned __int16 *
0x14004b1a4  mov     rcx, rax; unsigned __int16 *
0x14004b1a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004b1ac  test    eax, eax
0x14004b1ae  jns     short loc_14004B1F4
0x14004b1b0  mov     edi, r14d
0x14004b1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b1ba  cmp     rcx, r15
0x14004b1bd  jz      loc_14004B45B
0x14004b1c3  test    byte ptr [rcx+1Ch], 4
0x14004b1c7  jz      loc_14004B45B
0x14004b1cd  cmp     byte ptr [rcx+19h], 2
0x14004b1d1  jb      loc_14004B45B
0x14004b1d7  mov     rcx, [rcx+10h]
0x14004b1db  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b1e2  mov     edx, 60h ; '`'
0x14004b1e7  mov     r9d, eax
0x14004b1ea  call    WPP_SF_d
0x14004b1ef  jmp     loc_14004B45B
0x14004b1f4  mov     ecx, [rsi+24h]
0x14004b1f7  add     rcx, rsi; unsigned __int16 *
0x14004b1fa  call    ?FixupDeviceName@@YAPEAGPEBG@Z; FixupDeviceName(ushort const *)
0x14004b1ff  mov     rbp, rax
0x14004b202  test    rax, rax
0x14004b205  jz      loc_14004B159
0x14004b20b  cmp     [rsi+1Ch], r14d
0x14004b20f  jnz     short loc_14004B24B
0x14004b211  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b218  cmp     rcx, r15
0x14004b21b  jz      short loc_14004B241
0x14004b21d  test    byte ptr [rcx+1Ch], 4
0x14004b221  jz      short loc_14004B241
0x14004b223  cmp     byte ptr [rcx+19h], 2
0x14004b227  jb      short loc_14004B241
0x14004b229  mov     rcx, [rcx+10h]
0x14004b22d  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b234  mov     edx, 61h ; 'a'
0x14004b239  mov     r9, rax
0x14004b23c  call    WPP_SF_S
0x14004b241  mov     edi, 4B0h
0x14004b246  jmp     loc_14004B45B
0x14004b24b  mov     rcx, rsi
0x14004b24e  call    IsDeviceModem
0x14004b253  mov     rcx, [rsp+98h+lpString2]; lpString2
0x14004b258  mov     edx, 1; int
0x14004b25d  mov     r15d, eax
0x14004b260  call    ?FindDeviceProvider@@YAPEAU_DEVICE_PROVIDER@@PEBGH@Z; FindDeviceProvider(ushort const *,int)
0x14004b265  mov     r13, rax
0x14004b268  test    rax, rax
0x14004b26b  jnz     short loc_14004B2AC
0x14004b26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b274  lea     r15, WPP_GLOBAL_Control
0x14004b27b  cmp     rcx, r15
0x14004b27e  jz      short loc_14004B2A2
0x14004b280  test    byte ptr [rcx+1Ch], 4
0x14004b284  jz      short loc_14004B2A2
0x14004b286  cmp     byte ptr [rcx+19h], 2
0x14004b28a  jb      short loc_14004B2A2
0x14004b28c  mov     rcx, [rcx+10h]
0x14004b290  lea     edx, [rax+62h]
0x14004b293  mov     r9, rbp
0x14004b296  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b29d  call    WPP_SF_S
0x14004b2a2  mov     edi, 4B4h
0x14004b2a7  jmp     loc_14004B45B
0x14004b2ac  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004b2b2  mov     r9d, 20000h; dwAPIVersion
0x14004b2b8  mov     [rsp+98h+lpCallParams], r14; lpCallParams
0x14004b2bd  lea     r8, [rsp+98h+hLine]; lphLine
0x14004b2c2  mov     edx, r12d; dwDeviceID
0x14004b2c5  test    r15d, r15d
0x14004b2c8  jz      short loc_14004B315
0x14004b2ca  mov     [rsp+98h+dwMediaModes], 12h; dwMediaModes
0x14004b2d2  mov     [rsp+98h+dwPrivileges], 6; dwPrivileges
0x14004b2da  mov     [rsp+98h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004b2df  mov     [rsp+98h+dwExtVersion], r14d; dwExtVersion
0x14004b2e4  call    cs:__imp_lineOpenW
0x14004b2ea  test    eax, eax
0x14004b2ec  jz      loc_14004B387
0x14004b2f2  mov     ecx, cs:?g_hLineApp@@3KA; ulong g_hLineApp
0x14004b2f8  lea     r8, [rsp+98h+hLine]
0x14004b2fd  mov     [rsp+98h+lpCallParams], r14
0x14004b302  mov     r9d, 20000h
0x14004b308  mov     [rsp+98h+dwMediaModes], 10h
0x14004b310  mov     edx, r12d
0x14004b313  jmp     short loc_14004B31D
0x14004b315  mov     [rsp+98h+dwMediaModes], 20h ; ' '; dwMediaModes
0x14004b31d  mov     [rsp+98h+dwPrivileges], 6; dwPrivileges
0x14004b325  mov     [rsp+98h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004b32a  mov     [rsp+98h+dwExtVersion], r14d; dwExtVersion
0x14004b32f  call    cs:__imp_lineOpenW
0x14004b335  mov     edi, eax
0x14004b337  test    eax, eax
0x14004b339  jz      short loc_14004B387
0x14004b33b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b342  lea     r15, WPP_GLOBAL_Control
0x14004b349  cmp     rcx, r15
0x14004b34c  jz      loc_14004B45B
0x14004b352  test    byte ptr [rcx+1Ch], 4
0x14004b356  jz      loc_14004B45B
0x14004b35c  cmp     byte ptr [rcx+19h], 2
0x14004b360  jb      loc_14004B45B
0x14004b366  mov     rcx, [rcx+10h]
0x14004b36a  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b371  mov     edx, 63h ; 'c'
0x14004b376  mov     [rsp+98h+dwExtVersion], eax
0x14004b37a  mov     r9, rbp
0x14004b37d  call    WPP_SF_Sd
0x14004b382  jmp     loc_14004B45B
0x14004b387  mov     eax, [rsp+98h+hLine]
0x14004b38b  mov     r8d, 3Ch ; '<'; dwAddressStates
0x14004b391  mov     [rbx+20h], eax
0x14004b394  mov     r14d, [rsi+80h]
0x14004b39b  mov     ecx, [rsp+98h+hLine]; hLine
0x14004b39f  and     r14d, 1000E02h
0x14004b3a6  mov     edx, r14d; dwLineStates
0x14004b3a9  call    cs:__imp_lineSetStatusMessages
0x14004b3af  mov     edi, eax
0x14004b3b1  test    eax, eax
0x14004b3b3  jz      short loc_14004B405
0x14004b3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b3bc  lea     rax, WPP_GLOBAL_Control
0x14004b3c3  cmp     rcx, rax
0x14004b3c6  jz      short loc_14004B3F1
0x14004b3c8  test    byte ptr [rcx+1Ch], 4
0x14004b3cc  jz      short loc_14004B3F1
0x14004b3ce  cmp     byte ptr [rcx+19h], 2
0x14004b3d2  jb      short loc_14004B3F1
0x14004b3d4  mov     rcx, [rcx+10h]
0x14004b3d8  mov     edx, 64h ; 'd'
0x14004b3dd  mov     dword ptr [rsp+98h+dwCallbackInstance], edi
0x14004b3e1  mov     r9d, r14d
0x14004b3e4  mov     [rsp+98h+dwExtVersion], 3Ch ; '<'
0x14004b3ec  call    WPP_SF_DDD
0x14004b3f1  xor     r14d, r14d
0x14004b3f4  cmp     edi, 8000002Bh
0x14004b3fa  jnz     short loc_14004B400
0x14004b3fc  mov     [rbx+20h], r14d
0x14004b400  mov     edi, r14d
0x14004b403  jmp     short loc_14004B408
0x14004b405  xor     r14d, r14d
0x14004b408  mov     dword ptr [rbx+10h], 454E494Ch
0x14004b40f  mov     rcx, rbp; unsigned __int16 *
0x14004b412  mov     [rbx+14h], r12d
0x14004b416  mov     eax, [rsi+1Ch]
0x14004b419  mov     [rbx+1Ch], eax
0x14004b41c  mov     [rbx+28h], r13
0x14004b420  mov     [rbx+68h], r15d
0x14004b424  mov     dword ptr [rbx+48h], 20100000h
0x14004b42b  mov     qword ptr [rbx+50h], 0
0x14004b433  mov     [rbx+0B0h], r14
0x14004b43a  call    StringDup
0x14004b43f  mov     [rbx+38h], rax
0x14004b443  test    rax, rax
0x14004b446  jnz     loc_14004B579
0x14004b44c  call    cs:__imp_GetLastError
0x14004b452  mov     edi, eax
0x14004b454  lea     r15, WPP_GLOBAL_Control
0x14004b45b  mov     rcx, rbp; lpMem
0x14004b45e  call    pMemFree
0x14004b463  mov     rcx, [rsp+98h+lpString2]; lpMem
0x14004b468  call    pMemFree
0x14004b46d  test    edi, edi
0x14004b46f  jnz     loc_14004B6A5
0x14004b475  mov     rax, cs:qword_1400A1748
0x14004b47c  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14004b483  inc     cs:?g_dwDeviceCount@@3KA; ulong g_dwDeviceCount
0x14004b489  mov     [rbx], rcx
0x14004b48c  mov     [rbx+8], rax
0x14004b490  mov     [rax], rbx
0x14004b493  mov     cs:qword_1400A1748, rbx
0x14004b49a  cmp     [rsp+98h+arg_40], r14d
0x14004b4a2  jnz     loc_14004B54E
0x14004b4a8  cmp     cs:?g_dwManualAnswerDeviceId@@3KA, r14d; ulong g_dwManualAnswerDeviceId
0x14004b4af  jnz     short loc_14004B501
0x14004b4b1  cmp     dword ptr [rbx+0B8h], 0Ah
0x14004b4b8  jnz     short loc_14004B501
0x14004b4ba  test    byte ptr [rbx+4Ch], 1
0x14004b4be  jnz     short loc_14004B501
0x14004b4c0  mov     eax, [rbx+18h]
0x14004b4c3  mov     cs:?g_dwManualAnswerDeviceId@@3KA, eax; ulong g_dwManualAnswerDeviceId
0x14004b4c9  call    WriteManualAnswerDeviceId
0x14004b4ce  test    eax, eax
0x14004b4d0  jz      short loc_14004B501
0x14004b4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b4d9  cmp     rcx, r15
0x14004b4dc  jz      short loc_14004B508
0x14004b4de  test    byte ptr [rcx+1Ch], 4
0x14004b4e2  jz      short loc_14004B508
0x14004b4e4  cmp     byte ptr [rcx+19h], 2
0x14004b4e8  jb      short loc_14004B508
0x14004b4ea  mov     rcx, [rcx+10h]
0x14004b4ee  lea     edx, [rdi+66h]
0x14004b4f1  movzx   r9d, ax
0x14004b4f5  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b4fc  call    WPP_SF_h
0x14004b501  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b508  mov     r10d, cs:?g_dwDeviceEnabledCount@@3KA; ulong g_dwDeviceEnabledCount
0x14004b50f  mov     r9d, cs:?g_dwDeviceEnabledLimit@@3KA; ulong g_dwDeviceEnabledLimit
0x14004b516  cmp     r10d, r9d
0x14004b519  jb      short loc_14004B555
0x14004b51b  cmp     rcx, r15
0x14004b51e  jz      short loc_14004B546
0x14004b520  test    byte ptr [rcx+1Ch], 4
0x14004b524  jz      short loc_14004B546
0x14004b526  cmp     byte ptr [rcx+19h], 3
0x14004b52a  jb      short loc_14004B546
0x14004b52c  mov     rcx, [rcx+10h]
0x14004b530  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004b537  mov     edx, 67h ; 'g'
0x14004b53c  mov     [rsp+98h+dwExtVersion], r10d
0x14004b541  call    WPP_SF_dd
0x14004b546  mov     rcx, rbx; struct _LINE_INFO *
0x14004b549  call    ?ResetDeviceFlags@@YAXPEAU_LINE_INFO@@@Z; ResetDeviceFlags(_LINE_INFO *)
0x14004b54e  mov     r10d, cs:?g_dwDeviceEnabledCount@@3KA; ulong g_dwDeviceEnabledCount
0x14004b555  test    byte ptr [rbx+4Ch], 3
0x14004b559  jnz     short loc_14004B56A
0x14004b55b  mov     eax, cs:?g_dwManualAnswerDeviceId@@3KA; ulong g_dwManualAnswerDeviceId
0x14004b561  cmp     [rbx+18h], eax
0x14004b564  jnz     loc_14004B6AD
0x14004b56a  inc     r10d
0x14004b56d  mov     cs:?g_dwDeviceEnabledCount@@3KA, r10d; ulong g_dwDeviceEnabledCount
0x14004b574  jmp     loc_14004B6AD
0x14004b579  mov     rcx, [rsp+98h+arg_28]; unsigned __int16 *
0x14004b581  test    rcx, rcx
0x14004b584  jz      short loc_14004B599
0x14004b586  call    StringDup
0x14004b58b  mov     [rbx+58h], rax
0x14004b58f  test    rax, rax
0x14004b592  jnz     short loc_14004B59D
0x14004b594  jmp     loc_14004B44C
0x14004b599  mov     [rbx+58h], r14
0x14004b59d  mov     rcx, [rsp+98h+arg_30]; unsigned __int16 *
0x14004b5a5  test    rcx, rcx
0x14004b5a8  jz      short loc_14004B5BD
0x14004b5aa  call    StringDup
0x14004b5af  mov     [rbx+60h], rax
0x14004b5b3  test    rax, rax
0x14004b5b6  jnz     short loc_14004B5C1
0x14004b5b8  jmp     loc_14004B44C
0x14004b5bd  mov     [rbx+60h], r14
0x14004b5c1  mov     rcx, [rsp+98h+arg_38]; unsigned __int16 *
0x14004b5c9  test    rcx, rcx
  ... truncated ...
```
