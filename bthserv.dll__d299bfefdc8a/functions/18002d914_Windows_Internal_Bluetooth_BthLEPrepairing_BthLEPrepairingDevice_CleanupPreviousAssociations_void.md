# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(void)

- ea: `0x18002d914`
- end: `0x18002defe`
- name: `?CleanupPreviousAssociations@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ`
- size: `1514`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c830`

## callees

- `0x180001790`
- `0x180001b9c`
- `0x180010cac`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x1800114c8`
- `0x18001d95c`
- `0x18002c15c`
- `0x18002c534`
- `0x18002d914`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dbac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dbac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dbd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dbce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dbce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dea7`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002dc70`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002de89`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002dc70`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002de89`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18002dc37`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x18002dc37`

## string_xrefs

- `0x18002ded3`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002deec`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this)
{
  char v2; // di
  _BYTE *v3; // rcx
  char v4; // dl
  _UNKNOWN **v5; // rax
  char v6; // dl
  __int64 v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rax
  HANDLE EventW; // rsi
  const char *v11; // r9
  HANDLE v12; // r15
  DWORD LastError; // ebx
  int v14; // eax
  __int64 *j; // r8
  __int64 v16; // rsi
  DWORD v17; // ebx
  __int64 *v18; // rbx
  _BYTE *v19; // rcx
  _UNKNOWN **v20; // rdx
  _QWORD *v21; // rax
  char v22; // r10
  char v23; // r10
  int v24; // r8d
  int v25; // edx
  bool v26; // cf
  char v27; // al
  __int64 *i; // rax
  int v29; // [rsp+20h] [rbp-E0h]
  _DWORD *v30; // [rsp+28h] [rbp-D8h]
  char v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v34[2]; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v37[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-48h] BYREF
  int v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+CCh] [rbp-34h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  __int128 v42; // [rsp+D8h] [rbp-28h]
  int v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+ECh] [rbp-14h]
  int v45; // [rsp+F0h] [rbp-10h]
  char *v46; // [rsp+F8h] [rbp-8h]
  _DWORD v47[3]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v48; // [rsp+10Ch] [rbp+Ch]
  _BYTE v49[28]; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v50; // [rsp+138h] [rbp+38h]
  __int128 v51; // [rsp+140h] [rbp+40h]
  int v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+154h] [rbp+54h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  int v55; // [rsp+160h] [rbp+60h]
  int v56; // [rsp+164h] [rbp+64h]
  char *v57; // [rsp+168h] [rbp+68h]
  int v58; // [rsp+170h] [rbp+70h]
  __int128 v59; // [rsp+178h] [rbp+78h]
  int v60; // [rsp+188h] [rbp+88h]
  int v61; // [rsp+18Ch] [rbp+8Ch]
  __int64 v62; // [rsp+190h] [rbp+90h]
  int v63; // [rsp+198h] [rbp+98h]
  int v64; // [rsp+19Ch] [rbp+9Ch]
  const struct _GUID *v65; // [rsp+1A0h] [rbp+A0h]
  int v66; // [rsp+1A8h] [rbp+A8h]
  __int128 v67; // [rsp+1B0h] [rbp+B0h]
  int v68; // [rsp+1C0h] [rbp+C0h]
  int v69; // [rsp+1C4h] [rbp+C4h]
  __int64 v70; // [rsp+1C8h] [rbp+C8h]
  int v71; // [rsp+1D0h] [rbp+D0h]
  int v72; // [rsp+1D4h] [rbp+D4h]
  __int64 v73; // [rsp+1D8h] [rbp+D8h]
  int v74; // [rsp+1E0h] [rbp+E0h]
  int v75; // [rsp+1E8h] [rbp+E8h]
  __int128 v76; // [rsp+1ECh] [rbp+ECh]
  _BYTE v77[28]; // [rsp+1FCh] [rbp+FCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v4 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    v4 = 0;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v3 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v3 == (_BYTE *)&WPP_GLOBAL_Control || (v6 = 1, v3[25] < 4u) )
    v6 = 0;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sS(*((_QWORD *)v3 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v3 + 5));
  v7 = -1;
  v31 = -1;
  v47[0] = 0x100000;
  v47[2] = 0;
  v48 = 0;
  memset(v49, 0, sizeof(v49));
  v50 = 2;
  v51 = DEVPKEY_Aep_IsAssociated;
  v52 = 16;
  v53 = 0;
  v54 = 0;
  v55 = 17;
  v56 = 1;
  v57 = &v31;
  v58 = 2;
  v59 = DEVPKEY_Aep_ProtocolId;
  v60 = 5;
  v61 = 0;
  v62 = 0;
  v63 = 13;
  v64 = 16;
  v65 = &DAF_ProtocolId_BluetoothLE;
  v66 = 65538;
  v67 = DEVPKEY_Aep_AepId;
  v68 = 8;
  v69 = 0;
  v70 = 0;
  v71 = 18;
  v8 = *((_QWORD *)this + 8);
  do
    ++v7;
  while ( *(_WORD *)(v8 + 2 * v7 + 2) );
  v72 = 2 * v7;
  v73 = v8;
  v74 = 0x200000;
  v75 = 0;
  v76 = 0;
  memset(v77, 0, sizeof(v77));
  v42 = DEVPKEY_DasParam_AepStoreOnly;
  v43 = 4;
  v44 = 17;
  v45 = 1;
  v46 = &v31;
  v38 = DEVPKEY_BluetoothLE_PrepairingDeviceId;
  v39 = 7;
  v40 = 0;
  v41 = 0;
  v34[1] = this;
  hObject = 0;
  v36 = 0;
  v9 = operator new(0x40u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)&v36 = v9;
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v12);
    SetLastError(LastError);
  }
  hObject = EventW;
  if ( !EventW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      v11);
  v32 = 0;
  v30 = v47;
  v29 = 5;
  v14 = DevCreateObjectQueryEx(5, 0, 1, &v38);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)(unsigned int)v14,
      5);
  WaitForSingleObject(hObject, 0x2710u);
  v16 = v32;
  if ( v32 )
  {
    v17 = GetLastError();
    DevCloseObjectQuery(v16);
    SetLastError(v17);
  }
  v32 = 0;
  v18 = *(__int64 **)v36;
  v19 = WPP_GLOBAL_Control;
  v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  while ( !*((_BYTE *)v18 + 25) )
  {
    v21 = v18 + 4;
    if ( (unsigned __int64)v18[7] > 7 )
      v21 = (_QWORD *)*v21;
    v34[0] = v21;
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || (v22 = 1, v19[25] < 5u) )
      v22 = 0;
    if ( v22 || v20 != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(j) = v20 != &WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v19 + 2), v22, (_DWORD)j, *((_QWORD *)v19 + 5));
      v19 = WPP_GLOBAL_Control;
      v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || (v23 = 1, v19[25] < 4u) )
      v23 = 0;
    LOBYTE(j) = v20 != &WPP_RECORDER_INITIALIZED;
    if ( v23 || v20 != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sS(*((_QWORD *)v19 + 2), v23, (_BYTE)j, *((_QWORD *)v19 + 5));
    v37[0] = &v33;
    v37[1] = v34;
    v37[2] = this;
    v24 = wil::ResultFromException__lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5___(v37, v20, j);
    v33 = v24;
    v25 = 0;
    v19 = WPP_GLOBAL_Control;
    if ( v24 )
      v26 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
    else
      v26 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v27 = 1, LOBYTE(v25) = !v26, !v25) )
      v27 = 0;
    v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    if ( v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v20) = v27;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v20,
        v24,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v29,
        (_DWORD)v30,
        63,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
      v19 = WPP_GLOBAL_Control;
      v20 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    j = (__int64 *)v18[2];
    if ( *((_BYTE *)j + 25) )
    {
      for ( i = (__int64 *)v18[1]; !*((_BYTE *)i + 25) && v18 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v18 = i;
      v18 = i;
    }
    else
    {
      v18 = (__int64 *)v18[2];
      for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v18 = j;
    }
  }
  if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || v19[25] < 5u )
    v2 = 0;
  if ( v2 || v20 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v19 + 2), v2, v20 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v19 + 5));
  if ( v32 )
    DevCloseObjectQuery(v32);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v36);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18002d914  push    rbp
0x18002d916  push    rbx
0x18002d917  push    rsi
0x18002d918  push    rdi
0x18002d919  push    r12
0x18002d91b  push    r13
0x18002d91d  push    r14
0x18002d91f  push    r15
0x18002d921  lea     rbp, [rsp-138h]
0x18002d929  sub     rsp, 238h
0x18002d930  mov     rax, cs:__security_cookie
0x18002d937  xor     rax, rsp
0x18002d93a  mov     [rbp+170h+var_50], rax
0x18002d941  mov     r14, rcx
0x18002d944  lea     r13, WPP_GLOBAL_Control
0x18002d94b  xor     r12d, r12d
0x18002d94e  lea     edi, [r12+1]
0x18002d953  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d95a  cmp     rcx, r13
0x18002d95d  jz      short loc_18002D968
0x18002d95f  cmp     byte ptr [rcx+19h], 5
0x18002d963  mov     dl, dil
0x18002d966  jnb     short loc_18002D96B
0x18002d968  mov     dl, r12b
0x18002d96b  lea     r9, WPP_RECORDER_INITIALIZED
0x18002d972  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002d979  cmp     rax, r9
0x18002d97c  setnz   r8b
0x18002d980  lea     r10, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d987  test    dl, dl
0x18002d989  jnz     short loc_18002D990
0x18002d98b  test    r8b, r8b
0x18002d98e  jz      short loc_18002D9CA
0x18002d990  mov     [rsp+270h+var_228], r14
0x18002d995  mov     [rsp+270h+var_238], r10
0x18002d99a  mov     word ptr [rsp+270h+var_240], 2Ch ; ','
0x18002d9a1  mov     r9, [rcx+28h]
0x18002d9a5  mov     rcx, [rcx+10h]
0x18002d9a9  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002d9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9b5  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002d9bc  lea     r9, WPP_RECORDER_INITIALIZED
0x18002d9c3  lea     r10, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d9ca  cmp     rcx, r13
0x18002d9cd  jz      short loc_18002D9D8
0x18002d9cf  cmp     byte ptr [rcx+19h], 4
0x18002d9d3  mov     dl, dil
0x18002d9d6  jnb     short loc_18002D9DB
0x18002d9d8  mov     dl, r12b
0x18002d9db  cmp     rax, r9
0x18002d9de  setnz   r8b
0x18002d9e2  test    dl, dl
0x18002d9e4  jnz     short loc_18002D9EB
0x18002d9e6  test    r8b, r8b
0x18002d9e9  jz      short loc_18002DA0D
0x18002d9eb  mov     rax, [r14+40h]
0x18002d9ef  mov     [rsp+270h+var_228], rax
0x18002d9f4  mov     [rsp+270h+var_238], r10
0x18002d9f9  mov     word ptr [rsp+270h+var_240], 2Dh ; '-'
0x18002da00  mov     r9, [rcx+28h]
0x18002da04  mov     rcx, [rcx+10h]
0x18002da08  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002da0d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002da11  mov     [rsp+270h+var_210], cl
0x18002da15  mov     [rbp+170h+var_170], 100000h
0x18002da1c  mov     [rbp+170h+var_168], r12d
0x18002da20  xorps   xmm0, xmm0
0x18002da23  movups  [rbp+170h+var_164], xmm0
0x18002da27  movups  xmmword ptr [rbp+170h+var_154], xmm0
0x18002da2b  movups  xmmword ptr [rbp+170h+var_154+0Ch], xmm0
0x18002da2f  lea     edx, [rcx+3]
0x18002da32  mov     [rbp+170h+var_138], edx
0x18002da35  movups  xmm0, cs:DEVPKEY_Aep_IsAssociated
0x18002da3c  movaps  [rbp+170h+var_130], xmm0
0x18002da40  mov     eax, cs:dword_18003C238
0x18002da46  mov     [rbp+170h+var_120], eax
0x18002da49  mov     [rbp+170h+var_11C], r12d
0x18002da4d  mov     [rbp+170h+var_118], r12
0x18002da51  lea     r8d, [rcx+12h]
0x18002da55  mov     [rbp+170h+var_110], r8d
0x18002da59  mov     [rbp+170h+var_10C], edi
0x18002da5c  lea     rax, [rsp+270h+var_210]
0x18002da61  mov     [rbp+170h+var_108], rax
0x18002da65  mov     [rbp+170h+var_100], edx
0x18002da68  movups  xmm0, cs:DEVPKEY_Aep_ProtocolId
0x18002da6f  movups  [rbp+170h+var_F8], xmm0
0x18002da73  mov     eax, cs:dword_18003C220
0x18002da79  mov     [rbp+170h+var_E8], eax
0x18002da7f  mov     [rbp+170h+var_E4], r12d
0x18002da86  mov     [rbp+170h+var_E0], r12
0x18002da8d  mov     [rbp+170h+var_D8], 0Dh
0x18002da97  mov     [rbp+170h+var_D4], 10h
0x18002daa1  lea     rax, DAF_ProtocolId_BluetoothLE
0x18002daa8  mov     [rbp+170h+var_D0], rax
0x18002daaf  mov     [rbp+170h+var_C8], 10002h
0x18002dab9  movups  xmm0, cs:DEVPKEY_Aep_AepId
0x18002dac0  movaps  [rbp+170h+var_C0], xmm0
0x18002dac7  mov     eax, cs:dword_18003C2F0
0x18002dacd  mov     [rbp+170h+var_B0], eax
0x18002dad3  mov     [rbp+170h+var_AC], r12d
0x18002dada  mov     [rbp+170h+var_A8], r12
0x18002dae1  mov     [rbp+170h+var_A0], 12h
0x18002daeb  mov     rdx, [r14+40h]
0x18002daef  inc     rcx
0x18002daf2  cmp     [rdx+rcx*2+2], r12w
0x18002daf8  jnz     short loc_18002DAEF
0x18002dafa  lea     eax, [rcx+rcx]
0x18002dafd  mov     [rbp+170h+var_9C], eax
0x18002db03  mov     [rbp+170h+var_98], rdx
0x18002db0a  mov     [rbp+170h+var_90], 200000h
0x18002db14  mov     [rbp+170h+var_88], r12d
0x18002db1b  xorps   xmm0, xmm0
0x18002db1e  movups  [rbp+170h+var_84], xmm0
0x18002db25  movups  xmmword ptr [rbp+170h+var_74], xmm0
0x18002db2c  movups  xmmword ptr [rbp+170h+var_74+0Ch], xmm0
0x18002db33  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x18002db3a  movups  [rbp+170h+var_198], xmm0
0x18002db3e  mov     eax, cs:dword_18003C1E8
0x18002db44  mov     [rbp+170h+var_188], eax
0x18002db47  mov     [rbp+170h+var_184], r8d
0x18002db4b  mov     [rbp+170h+var_180], edi
0x18002db4e  lea     rax, [rsp+270h+var_210]
0x18002db53  mov     [rbp+170h+var_178], rax
0x18002db57  movups  xmm0, cs:DEVPKEY_BluetoothLE_PrepairingDeviceId
0x18002db5e  movups  [rbp+170h+var_1B8], xmm0
0x18002db62  mov     eax, cs:dword_18003CF40
0x18002db68  mov     [rbp+170h+var_1A8], eax
0x18002db6b  mov     [rbp+170h+var_1A4], r12d
0x18002db6f  mov     [rbp+170h+var_1A0], r12
0x18002db73  mov     [rbp+170h+var_1F0], r14
0x18002db77  mov     [rbp+170h+hObject], r12
0x18002db7b  xorps   xmm0, xmm0
0x18002db7e  movdqu  [rbp+170h+var_1E0], xmm0
0x18002db83  mov     ecx, 40h ; '@'; Size
0x18002db88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002db8d  mov     [rax], rax
0x18002db90  mov     [rax+8], rax
0x18002db94  mov     [rax+10h], rax
0x18002db98  mov     word ptr [rax+18h], 101h
0x18002db9e  mov     qword ptr [rbp+170h+var_1E0], rax
0x18002dba2  xor     r9d, r9d; lpName
0x18002dba5  xor     r8d, r8d; bInitialState
0x18002dba8  xor     edx, edx; bManualReset
0x18002dbaa  xor     ecx, ecx; lpEventAttributes
0x18002dbac  call    cs:__imp_CreateEventW
0x18002dbb2  mov     rsi, rax
0x18002dbb5  mov     r15, [rbp+170h+hObject]
0x18002dbb9  lea     rdx, [r15-1]
0x18002dbbd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002dbc1  ja      short loc_18002DBDC
0x18002dbc3  call    cs:__imp_GetLastError
0x18002dbc9  mov     ebx, eax
0x18002dbcb  mov     rcx, r15; hObject
0x18002dbce  call    cs:__imp_CloseHandle
0x18002dbd4  mov     ecx, ebx; dwErrCode
0x18002dbd6  call    cs:__imp_SetLastError
0x18002dbdc  mov     [rbp+170h+hObject], rsi
0x18002dbe0  test    rsi, rsi
0x18002dbe3  jz      loc_18002DEE5
0x18002dbe9  mov     [rsp+270h+var_208], r12
0x18002dbee  lea     rax, [rsp+270h+var_208]
0x18002dbf3  mov     [rsp+270h+var_220], rax
0x18002dbf8  lea     rax, [rbp+170h+var_1F0]
0x18002dbfc  mov     [rsp+270h+var_228], rax
0x18002dc01  lea     rax, ?s_PairedDeviceQueryCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002dc08  mov     [rsp+270h+var_230], rax
0x18002dc0d  lea     rax, [rbp+170h+var_198]
0x18002dc11  mov     [rsp+270h+var_238], rax
0x18002dc16  mov     [rsp+270h+var_240], edi
0x18002dc1a  lea     rax, [rbp+170h+var_170]
0x18002dc1e  mov     [rsp+270h+var_248], rax
0x18002dc23  mov     [rsp+270h+var_250], 5; int
0x18002dc2b  lea     r9, [rbp+170h+var_1B8]
0x18002dc2f  mov     r8d, edi
0x18002dc32  xor     edx, edx
0x18002dc34  lea     ecx, [rdx+5]
0x18002dc37  call    cs:__imp_DevCreateObjectQueryEx
0x18002dc3d  mov     rcx, [rbp+178h]; this
0x18002dc44  test    eax, eax
0x18002dc46  js      loc_18002DED0
0x18002dc4c  mov     edx, 2710h; dwMilliseconds
0x18002dc51  mov     rcx, [rbp+170h+hObject]; hHandle
0x18002dc55  call    cs:__imp_WaitForSingleObject
0x18002dc5b  mov     rsi, [rsp+270h+var_208]
0x18002dc60  test    rsi, rsi
0x18002dc63  jz      short loc_18002DC7E
0x18002dc65  call    cs:__imp_GetLastError
0x18002dc6b  mov     ebx, eax
0x18002dc6d  mov     rcx, rsi
0x18002dc70  call    cs:__imp_DevCloseObjectQuery
0x18002dc76  mov     ecx, ebx; dwErrCode
0x18002dc78  call    cs:__imp_SetLastError
0x18002dc7e  mov     [rsp+270h+var_208], r12
0x18002dc83  mov     rbx, qword ptr [rbp+170h+var_1E0]
0x18002dc87  mov     rbx, [rbx]
0x18002dc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc91  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002dc98  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002dc9f  lea     r15, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002dca6  cmp     [rbx+19h], r12b
0x18002dcaa  jnz     loc_18002DE3E
0x18002dcb0  lea     rax, [rbx+20h]
0x18002dcb4  cmp     qword ptr [rbx+38h], 7
0x18002dcb9  jbe     short loc_18002DCBE
0x18002dcbb  mov     rax, [rax]
0x18002dcbe  mov     [rsp+270h+var_1F8], rax
0x18002dcc3  cmp     rcx, r13
0x18002dcc6  jz      short loc_18002DCD1
0x18002dcc8  cmp     byte ptr [rcx+19h], 5
0x18002dccc  mov     r10b, dil
0x18002dccf  jnb     short loc_18002DCD4
0x18002dcd1  mov     r10b, r12b
0x18002dcd4  cmp     rdx, rsi
0x18002dcd7  setnz   r8b
0x18002dcdb  test    r10b, r10b
0x18002dcde  jnz     short loc_18002DCE5
0x18002dce0  test    r8b, r8b
0x18002dce3  jz      short loc_18002DD14
0x18002dce5  mov     [rsp+270h+var_238], r15
0x18002dcea  mov     word ptr [rsp+270h+var_240], 39h ; '9'
0x18002dcf1  mov     r9, [rcx+28h]
0x18002dcf5  mov     dl, r10b
0x18002dcf8  mov     rcx, [rcx+10h]
0x18002dcfc  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002dd01  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd08  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002dd0f  mov     rax, [rsp+270h+var_1F8]
0x18002dd14  cmp     rcx, r13
0x18002dd17  jz      short loc_18002DD22
0x18002dd19  cmp     byte ptr [rcx+19h], 4
0x18002dd1d  mov     r10b, dil
0x18002dd20  jnb     short loc_18002DD25
0x18002dd22  mov     r10b, r12b
0x18002dd25  cmp     rdx, rsi
0x18002dd28  setnz   r8b
0x18002dd2c  test    r10b, r10b
0x18002dd2f  jnz     short loc_18002DD36
0x18002dd31  test    r8b, r8b
0x18002dd34  jz      short loc_18002DD57
0x18002dd36  mov     [rsp+270h+var_228], rax
0x18002dd3b  mov     [rsp+270h+var_238], r15
0x18002dd40  mov     word ptr [rsp+270h+var_240], 3Ah ; ':'
0x18002dd47  mov     r9, [rcx+28h]
0x18002dd4b  mov     dl, r10b
0x18002dd4e  mov     rcx, [rcx+10h]
0x18002dd52  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18002dd57  lea     rax, [rsp+270h+var_200]
0x18002dd5c  mov     [rbp+170h+var_1D0], rax
0x18002dd60  lea     rax, [rsp+270h+var_1F8]
0x18002dd65  mov     [rbp+170h+var_1C8], rax
0x18002dd69  mov     [rbp+170h+var_1C0], r14
0x18002dd6d  lea     rcx, [rbp+170h+var_1D0]
0x18002dd71  call    wil__ResultFromException__lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5___
0x18002dd76  mov     r8d, eax
0x18002dd79  mov     [rsp+270h+var_200], eax
0x18002dd7d  mov     edx, r12d
0x18002dd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd87  test    eax, eax
0x18002dd89  jnz     short loc_18002DD91
0x18002dd8b  cmp     byte ptr [rcx+19h], 5
0x18002dd8f  jmp     short loc_18002DD95
0x18002dd91  cmp     byte ptr [rcx+19h], 2
0x18002dd95  setnb   dl
0x18002dd98  cmp     rcx, r13
0x18002dd9b  jz      short loc_18002DDA4
0x18002dd9d  test    edx, edx
0x18002dd9f  mov     al, dil
0x18002dda2  jnz     short loc_18002DDA7
0x18002dda4  mov     al, r12b
0x18002dda7  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002ddae  cmp     rdx, rsi
0x18002ddb1  setnz   r10b
0x18002ddb5  test    al, al
0x18002ddb7  jnz     short loc_18002DDBE
0x18002ddb9  test    r10b, r10b
0x18002ddbc  jz      short loc_18002DDEF
0x18002ddbe  mov     dword ptr [rsp+270h+var_228], r8d
0x18002ddc3  mov     [rsp+270h+var_238], r15
0x18002ddc8  mov     word ptr [rsp+270h+var_240], 3Fh ; '?'
0x18002ddcf  mov     r9, [rcx+28h]
0x18002ddd3  mov     r8b, r10b
0x18002ddd6  mov     dl, al
0x18002ddd8  mov     rcx, [rcx+10h]
0x18002dddc  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002dde1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dde8  mov     rdx, cs:WPP_RECORDER_INITIALIZED
0x18002ddef  mov     r8, [rbx+10h]
0x18002ddf3  cmp     [r8+19h], r12b
0x18002ddf7  jz      short loc_18002DE1A
0x18002ddf9  mov     rax, [rbx+8]
0x18002ddfd  jmp     short loc_18002DE0C
0x18002ddff  cmp     rbx, [rax+10h]
0x18002de03  jnz     short loc_18002DE12
0x18002de05  mov     rbx, rax
0x18002de08  mov     rax, [rax+8]
0x18002de0c  cmp     [rax+19h], r12b
0x18002de10  jz      short loc_18002DDFF
0x18002de12  mov     rbx, rax
0x18002de15  jmp     loc_18002DCA6
0x18002de1a  mov     rbx, r8
  ... truncated ...
```
