# InitializeTapiLine(ulong,ulong,linedevcaps_tag *,ulong,ulong,ushort const *,ushort const *,ushort const *,int,ulong)

- ea: `0x14004e0a4`
- end: `0x14004e6a4`
- name: `?InitializeTapiLine@@YAKKKPEAUlinedevcaps_tag@@KKPEBG11HK@Z`
- size: `1536`
- prototype: `__int64 __fastcall(DWORD dwDeviceID, int, struct linedevcaps_tag *, int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x14004c1a4`

## callees

- `0x140002c73`
- `0x140003450`
- `0x140004b70`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x14000cc48`
- `0x14004d560`
- `0x14004d5c4`
- `0x14004e0a4`
- `0x14004e6ac`
- `0x14004f0d0`
- `0x140051804`
- `0x1400698ec`
- `0x14006998c`
- `0x14006af2c`
- `0x14007b10c`
- `0x1400850a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004e422`
- `KERNEL32!GetLastError` at `0x14004e422`
- `TAPI32!lineOpenW` at `0x14004e2a8`
- `TAPI32!lineOpenW` at `0x14004e2f9`
- `TAPI32!lineOpenW` at `0x14004e2a8`
- `TAPI32!lineOpenW` at `0x14004e2f9`
- `TAPI32!lineSetStatusMessages` at `0x14004e379`
- `TAPI32!lineSetStatusMessages` at `0x14004e379`

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
  unsigned __int16 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  DWORD_PTR *v29; // rax
  int v30; // eax
  CMapDeviceId *v31; // rcx
  unsigned int v32; // r10d
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rax
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
  v29 = (DWORD_PTR *)qword_1400A7740;
  ++g_dwDeviceCount;
  *(_QWORD *)dwCallbackInstance = &g_TapiLinesListHead;
  *(_QWORD *)(dwCallbackInstance + 8) = v29;
  *v29 = dwCallbackInstance;
  qword_1400A7740 = dwCallbackInstance;
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
      WPP_SF_dd(*((_QWORD *)v31 + 2), 103, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
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
0x14004e0a4  mov     rax, rsp
0x14004e0a7  mov     [rax+8], rbx
0x14004e0ab  mov     [rax+20h], r9d
0x14004e0af  mov     [rax+10h], edx
0x14004e0b2  push    rbp
0x14004e0b3  push    rsi
0x14004e0b4  push    rdi
0x14004e0b5  push    r12
0x14004e0b7  push    r13
0x14004e0b9  push    r14
0x14004e0bb  push    r15
0x14004e0bd  sub     rsp, 60h
0x14004e0c1  xor     r14d, r14d
0x14004e0c4  mov     rsi, r8
0x14004e0c7  mov     [rax-48h], r14d
0x14004e0cb  mov     ebp, r14d
0x14004e0ce  mov     r12d, ecx
0x14004e0d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e0d8  lea     r15, WPP_GLOBAL_Control
0x14004e0df  cmp     rcx, r15
0x14004e0e2  jz      short loc_14004E104
0x14004e0e4  test    byte ptr [rcx+1Ch], 4
0x14004e0e8  jz      short loc_14004E104
0x14004e0ea  cmp     byte ptr [rcx+19h], 5
0x14004e0ee  jb      short loc_14004E104
0x14004e0f0  mov     rcx, [rcx+10h]
0x14004e0f4  lea     edx, [r14+5Fh]
0x14004e0f8  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e0ff  call    WPP_SF_
0x14004e104  mov     edi, 0C0h
0x14004e109  mov     ecx, edi; dwBytes
0x14004e10b  call    pMemAlloc
0x14004e110  mov     rbx, rax
0x14004e113  test    rax, rax
0x14004e116  jnz     short loc_14004E127
0x14004e118  mov     [rsp+98h+lpString2], r14
0x14004e11d  mov     edi, 8
0x14004e122  jmp     loc_14004E437
0x14004e127  mov     r8, rdi; Size
0x14004e12a  xor     edx, edx; Val
0x14004e12c  mov     rcx, rbx; void *
0x14004e12f  call    memset_0
0x14004e134  mov     ecx, [rsi+10h]
0x14004e137  add     rcx, rsi
0x14004e13a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004e13e  inc     rax
0x14004e141  cmp     [rcx+rax*2], r14w
0x14004e146  jnz     short loc_14004E13E
0x14004e148  inc     eax
0x14004e14a  mov     edi, eax
0x14004e14c  lea     rcx, [rax+rax]; dwBytes
0x14004e150  call    pMemAlloc
0x14004e155  mov     [rsp+98h+lpString2], rax
0x14004e15a  test    rax, rax
0x14004e15d  jz      short loc_14004E11D
0x14004e15f  mov     r8d, [rsi+10h]
0x14004e163  mov     edx, edi; unsigned __int64
0x14004e165  add     r8, rsi; unsigned __int16 *
0x14004e168  mov     rcx, rax; unsigned __int16 *
0x14004e16b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004e170  test    eax, eax
0x14004e172  jns     short loc_14004E1B8
0x14004e174  mov     edi, r14d
0x14004e177  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e17e  cmp     rcx, r15
0x14004e181  jz      loc_14004E437
0x14004e187  test    byte ptr [rcx+1Ch], 4
0x14004e18b  jz      loc_14004E437
0x14004e191  cmp     byte ptr [rcx+19h], 2
0x14004e195  jb      loc_14004E437
0x14004e19b  mov     rcx, [rcx+10h]
0x14004e19f  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e1a6  mov     edx, 60h ; '`'
0x14004e1ab  mov     r9d, eax
0x14004e1ae  call    WPP_SF_d
0x14004e1b3  jmp     loc_14004E437
0x14004e1b8  mov     ecx, [rsi+24h]
0x14004e1bb  add     rcx, rsi; unsigned __int16 *
0x14004e1be  call    ?FixupDeviceName@@YAPEAGPEBG@Z; FixupDeviceName(ushort const *)
0x14004e1c3  mov     rbp, rax
0x14004e1c6  test    rax, rax
0x14004e1c9  jz      loc_14004E11D
0x14004e1cf  cmp     [rsi+1Ch], r14d
0x14004e1d3  jnz     short loc_14004E20F
0x14004e1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e1dc  cmp     rcx, r15
0x14004e1df  jz      short loc_14004E205
0x14004e1e1  test    byte ptr [rcx+1Ch], 4
0x14004e1e5  jz      short loc_14004E205
0x14004e1e7  cmp     byte ptr [rcx+19h], 2
0x14004e1eb  jb      short loc_14004E205
0x14004e1ed  mov     rcx, [rcx+10h]
0x14004e1f1  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e1f8  mov     edx, 61h ; 'a'
0x14004e1fd  mov     r9, rax
0x14004e200  call    WPP_SF_S
0x14004e205  mov     edi, 4B0h
0x14004e20a  jmp     loc_14004E437
0x14004e20f  mov     rcx, rsi
0x14004e212  call    IsDeviceModem
0x14004e217  mov     rcx, [rsp+98h+lpString2]; lpString2
0x14004e21c  mov     edx, 1; int
0x14004e221  mov     r15d, eax
0x14004e224  call    ?FindDeviceProvider@@YAPEAU_DEVICE_PROVIDER@@PEBGH@Z; FindDeviceProvider(ushort const *,int)
0x14004e229  mov     r13, rax
0x14004e22c  test    rax, rax
0x14004e22f  jnz     short loc_14004E270
0x14004e231  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e238  lea     r15, WPP_GLOBAL_Control
0x14004e23f  cmp     rcx, r15
0x14004e242  jz      short loc_14004E266
0x14004e244  test    byte ptr [rcx+1Ch], 4
0x14004e248  jz      short loc_14004E266
0x14004e24a  cmp     byte ptr [rcx+19h], 2
0x14004e24e  jb      short loc_14004E266
0x14004e250  mov     rcx, [rcx+10h]
0x14004e254  lea     edx, [rax+62h]
0x14004e257  mov     r9, rbp
0x14004e25a  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e261  call    WPP_SF_S
0x14004e266  mov     edi, 4B4h
0x14004e26b  jmp     loc_14004E437
0x14004e270  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004e276  mov     r9d, 20000h; dwAPIVersion
0x14004e27c  mov     [rsp+98h+lpCallParams], r14; lpCallParams
0x14004e281  lea     r8, [rsp+98h+hLine]; lphLine
0x14004e286  mov     edx, r12d; dwDeviceID
0x14004e289  test    r15d, r15d
0x14004e28c  jz      short loc_14004E2DF
0x14004e28e  mov     [rsp+98h+dwMediaModes], 12h; dwMediaModes
0x14004e296  mov     [rsp+98h+dwPrivileges], 6; dwPrivileges
0x14004e29e  mov     [rsp+98h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004e2a3  mov     [rsp+98h+dwExtVersion], r14d; dwExtVersion
0x14004e2a8  call    cs:__imp_lineOpenW
0x14004e2af  nop     dword ptr [rax+rax+00h]
0x14004e2b4  test    eax, eax
0x14004e2b6  jz      loc_14004E357
0x14004e2bc  mov     ecx, cs:?g_hLineApp@@3KA; ulong g_hLineApp
0x14004e2c2  lea     r8, [rsp+98h+hLine]
0x14004e2c7  mov     [rsp+98h+lpCallParams], r14
0x14004e2cc  mov     r9d, 20000h
0x14004e2d2  mov     [rsp+98h+dwMediaModes], 10h
0x14004e2da  mov     edx, r12d
0x14004e2dd  jmp     short loc_14004E2E7
0x14004e2df  mov     [rsp+98h+dwMediaModes], 20h ; ' '; dwMediaModes
0x14004e2e7  mov     [rsp+98h+dwPrivileges], 6; dwPrivileges
0x14004e2ef  mov     [rsp+98h+dwCallbackInstance], rbx; dwCallbackInstance
0x14004e2f4  mov     [rsp+98h+dwExtVersion], r14d; dwExtVersion
0x14004e2f9  call    cs:__imp_lineOpenW
0x14004e300  nop     dword ptr [rax+rax+00h]
0x14004e305  mov     edi, eax
0x14004e307  test    eax, eax
0x14004e309  jz      short loc_14004E357
0x14004e30b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e312  lea     r15, WPP_GLOBAL_Control
0x14004e319  cmp     rcx, r15
0x14004e31c  jz      loc_14004E437
0x14004e322  test    byte ptr [rcx+1Ch], 4
0x14004e326  jz      loc_14004E437
0x14004e32c  cmp     byte ptr [rcx+19h], 2
0x14004e330  jb      loc_14004E437
0x14004e336  mov     rcx, [rcx+10h]
0x14004e33a  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e341  mov     edx, 63h ; 'c'
0x14004e346  mov     [rsp+98h+dwExtVersion], eax
0x14004e34a  mov     r9, rbp
0x14004e34d  call    WPP_SF_Sd
0x14004e352  jmp     loc_14004E437
0x14004e357  mov     eax, [rsp+98h+hLine]
0x14004e35b  mov     r8d, 3Ch ; '<'; dwAddressStates
0x14004e361  mov     [rbx+20h], eax
0x14004e364  mov     r14d, [rsi+80h]
0x14004e36b  mov     ecx, [rsp+98h+hLine]; hLine
0x14004e36f  and     r14d, 1000E02h
0x14004e376  mov     edx, r14d; dwLineStates
0x14004e379  call    cs:__imp_lineSetStatusMessages
0x14004e380  nop     dword ptr [rax+rax+00h]
0x14004e385  mov     edi, eax
0x14004e387  test    eax, eax
0x14004e389  jz      short loc_14004E3DB
0x14004e38b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e392  lea     rax, WPP_GLOBAL_Control
0x14004e399  cmp     rcx, rax
0x14004e39c  jz      short loc_14004E3C7
0x14004e39e  test    byte ptr [rcx+1Ch], 4
0x14004e3a2  jz      short loc_14004E3C7
0x14004e3a4  cmp     byte ptr [rcx+19h], 2
0x14004e3a8  jb      short loc_14004E3C7
0x14004e3aa  mov     rcx, [rcx+10h]
0x14004e3ae  mov     edx, 64h ; 'd'
0x14004e3b3  mov     dword ptr [rsp+98h+dwCallbackInstance], edi
0x14004e3b7  mov     r9d, r14d
0x14004e3ba  mov     [rsp+98h+dwExtVersion], 3Ch ; '<'
0x14004e3c2  call    WPP_SF_DDD
0x14004e3c7  xor     r14d, r14d
0x14004e3ca  cmp     edi, 8000002Bh
0x14004e3d0  jnz     short loc_14004E3D6
0x14004e3d2  mov     [rbx+20h], r14d
0x14004e3d6  mov     edi, r14d
0x14004e3d9  jmp     short loc_14004E3DE
0x14004e3db  xor     r14d, r14d
0x14004e3de  mov     dword ptr [rbx+10h], 454E494Ch
0x14004e3e5  mov     rcx, rbp; unsigned __int16 *
0x14004e3e8  mov     [rbx+14h], r12d
0x14004e3ec  mov     eax, [rsi+1Ch]
0x14004e3ef  mov     [rbx+1Ch], eax
0x14004e3f2  mov     [rbx+28h], r13
0x14004e3f6  mov     [rbx+68h], r15d
0x14004e3fa  mov     dword ptr [rbx+48h], 20100000h
0x14004e401  mov     qword ptr [rbx+50h], 0
0x14004e409  mov     [rbx+0B0h], r14
0x14004e410  call    StringDup
0x14004e415  mov     [rbx+38h], rax
0x14004e419  test    rax, rax
0x14004e41c  jnz     loc_14004E555
0x14004e422  call    cs:__imp_GetLastError
0x14004e429  nop     dword ptr [rax+rax+00h]
0x14004e42e  mov     edi, eax
0x14004e430  lea     r15, WPP_GLOBAL_Control
0x14004e437  mov     rcx, rbp; lpMem
0x14004e43a  call    pMemFree
0x14004e43f  mov     rcx, [rsp+98h+lpString2]; lpMem
0x14004e444  call    pMemFree
0x14004e449  test    edi, edi
0x14004e44b  jnz     loc_14004E681
0x14004e451  mov     rax, cs:qword_1400A7740
0x14004e458  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14004e45f  inc     cs:?g_dwDeviceCount@@3KA; ulong g_dwDeviceCount
0x14004e465  mov     [rbx], rcx
0x14004e468  mov     [rbx+8], rax
0x14004e46c  mov     [rax], rbx
0x14004e46f  mov     cs:qword_1400A7740, rbx
0x14004e476  cmp     [rsp+98h+arg_40], r14d
0x14004e47e  jnz     loc_14004E52A
0x14004e484  cmp     cs:?g_dwManualAnswerDeviceId@@3KA, r14d; ulong g_dwManualAnswerDeviceId
0x14004e48b  jnz     short loc_14004E4DD
0x14004e48d  cmp     dword ptr [rbx+0B8h], 0Ah
0x14004e494  jnz     short loc_14004E4DD
0x14004e496  test    byte ptr [rbx+4Ch], 1
0x14004e49a  jnz     short loc_14004E4DD
0x14004e49c  mov     eax, [rbx+18h]
0x14004e49f  mov     cs:?g_dwManualAnswerDeviceId@@3KA, eax; ulong g_dwManualAnswerDeviceId
0x14004e4a5  call    WriteManualAnswerDeviceId
0x14004e4aa  test    eax, eax
0x14004e4ac  jz      short loc_14004E4DD
0x14004e4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e4b5  cmp     rcx, r15
0x14004e4b8  jz      short loc_14004E4E4
0x14004e4ba  test    byte ptr [rcx+1Ch], 4
0x14004e4be  jz      short loc_14004E4E4
0x14004e4c0  cmp     byte ptr [rcx+19h], 2
0x14004e4c4  jb      short loc_14004E4E4
0x14004e4c6  mov     rcx, [rcx+10h]
0x14004e4ca  lea     edx, [rdi+66h]
0x14004e4cd  movzx   r9d, ax
0x14004e4d1  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e4d8  call    WPP_SF_h
0x14004e4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e4e4  mov     r10d, cs:?g_dwDeviceEnabledCount@@3KA; ulong g_dwDeviceEnabledCount
0x14004e4eb  mov     r9d, cs:?g_dwDeviceEnabledLimit@@3KA; ulong g_dwDeviceEnabledLimit
0x14004e4f2  cmp     r10d, r9d
0x14004e4f5  jb      short loc_14004E531
0x14004e4f7  cmp     rcx, r15
0x14004e4fa  jz      short loc_14004E522
0x14004e4fc  test    byte ptr [rcx+1Ch], 4
0x14004e500  jz      short loc_14004E522
0x14004e502  cmp     byte ptr [rcx+19h], 3
0x14004e506  jb      short loc_14004E522
0x14004e508  mov     rcx, [rcx+10h]
0x14004e50c  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004e513  mov     edx, 67h ; 'g'
0x14004e518  mov     [rsp+98h+dwExtVersion], r10d
0x14004e51d  call    WPP_SF_dd
0x14004e522  mov     rcx, rbx; struct _LINE_INFO *
0x14004e525  call    ?ResetDeviceFlags@@YAXPEAU_LINE_INFO@@@Z; ResetDeviceFlags(_LINE_INFO *)
0x14004e52a  mov     r10d, cs:?g_dwDeviceEnabledCount@@3KA; ulong g_dwDeviceEnabledCount
0x14004e531  test    byte ptr [rbx+4Ch], 3
0x14004e535  jnz     short loc_14004E546
0x14004e537  mov     eax, cs:?g_dwManualAnswerDeviceId@@3KA; ulong g_dwManualAnswerDeviceId
0x14004e53d  cmp     [rbx+18h], eax
0x14004e540  jnz     loc_14004E689
0x14004e546  inc     r10d
0x14004e549  mov     cs:?g_dwDeviceEnabledCount@@3KA, r10d; ulong g_dwDeviceEnabledCount
0x14004e550  jmp     loc_14004E689
0x14004e555  mov     rcx, [rsp+98h+arg_28]; unsigned __int16 *
0x14004e55d  test    rcx, rcx
0x14004e560  jz      short loc_14004E575
0x14004e562  call    StringDup
0x14004e567  mov     [rbx+58h], rax
0x14004e56b  test    rax, rax
0x14004e56e  jnz     short loc_14004E579
0x14004e570  jmp     loc_14004E422
0x14004e575  mov     [rbx+58h], r14
0x14004e579  mov     rcx, [rsp+98h+arg_30]; unsigned __int16 *
0x14004e581  test    rcx, rcx
0x14004e584  jz      short loc_14004E599
0x14004e586  call    StringDup
0x14004e58b  mov     [rbx+60h], rax
0x14004e58f  test    rax, rax
0x14004e592  jnz     short loc_14004E59D
  ... truncated ...
```
