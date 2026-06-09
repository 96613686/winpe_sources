# _lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()

- ea: `0x18002ce84`
- end: `0x18002d366`
- name: `_lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18002c17c`

## callees

- `0x180001b60`
- `0x180002834`
- `0x1800034a0`
- `0x180010cac`
- `0x180011194`
- `0x18002ce84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ceaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cf9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cff3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ceaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cf9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ced9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ced9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d020`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cf60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cf60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cf36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cf36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002cf74`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002cf74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002cf6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002cf6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ced1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ced1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cfc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d018`

## string_xrefs

- `0x18002d152`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002d201`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002d2a9`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002d351`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
unsigned int *__fastcall lambda_7f6a21a309c31e551c5f24e42f403fef_::operator()(unsigned int **a1)
{
  unsigned int *v1; // rax
  unsigned int *v3; // rsi
  HANDLE EventW; // rax
  char *v5; // rbp
  HANDLE v6; // r14
  DWORD LastError; // ebx
  __int64 v8; // rcx
  unsigned int *v9; // r14
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rbp
  char v12; // si
  PTP_TIMER v13; // r15
  DWORD v14; // ebx
  unsigned int *v15; // rbp
  HANDLE v16; // rax
  char *v17; // r14
  HANDLE v18; // r15
  DWORD v19; // ebx
  unsigned int *v20; // rbp
  HANDLE v21; // rax
  char *v22; // r14
  HANDLE v23; // r15
  DWORD v24; // ebx
  unsigned int *v25; // rbx
  _OWORD *v26; // rax
  const struct std::nothrow_t *v27; // rdx
  void *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rdx
  unsigned int *result; // rax
  signed int v32; // eax
  int v33; // edx
  int v34; // r8d
  unsigned int v35; // ecx
  unsigned int v36; // eax
  signed int v37; // eax
  int v38; // edx
  int v39; // r8d
  unsigned int v40; // ecx
  bool v41; // si
  unsigned int v42; // eax
  signed int v43; // eax
  int v44; // edx
  int v45; // r8d
  unsigned int v46; // ecx
  unsigned int v47; // eax
  signed int v48; // eax
  int v49; // edx
  int v50; // r8d
  unsigned int v51; // ecx
  unsigned int v52; // eax
  int v53; // [rsp+20h] [rbp-68h]
  int v54; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = *a1;
  *(_OWORD *)(v1 + 22) = 0;
  *(_OWORD *)(v1 + 26) = 0;
  v3 = *a1;
  EventW = CreateEventW(0, 0, 0, 0);
  v5 = (char *)*((_QWORD *)v3 + 15);
  v6 = EventW;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)v3 + 15) = v6;
  v8 = *((_QWORD *)*a1 + 15);
  if ( !v8 )
  {
    v37 = GetLastError();
    v40 = v37;
    if ( v37 > 0 )
      v40 = (unsigned __int16)v37 | 0x80070000;
    *a1[1] = v40;
    v41 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v41 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v38) = v41;
      LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v38,
        v39,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v53,
        v54,
        13,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v42 = wil::verify_hresult<long>(*a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v42,
      v53);
  }
  *((_QWORD *)*a1 + 14) = v8;
  *((_BYTE *)*a1 + 16) = *(_BYTE *)a1[2];
  *(_QWORD *)((char *)*a1 + 17) = **(_QWORD **)a1[3];
  *(_OWORD *)((char *)*a1 + 25) = *(_OWORD *)*(_QWORD *)a1[4];
  v9 = *a1;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      (PTP_TIMER_CALLBACK)Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_OnIgnoreTimer,
                      *a1,
                      0);
  v11 = (struct _TP_TIMER *)*((_QWORD *)v9 + 9);
  v12 = 1;
  v13 = ThreadpoolTimer;
  if ( v11 )
  {
    v14 = GetLastError();
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
    SetLastError(v14);
  }
  *((_QWORD *)v9 + 9) = v13;
  v15 = *a1;
  if ( !*((_QWORD *)*a1 + 9) )
  {
    v43 = GetLastError();
    v46 = v43;
    if ( v43 > 0 )
      v46 = (unsigned __int16)v43 | 0x80070000;
    *a1[1] = v46;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v12 = 0;
    if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v44) = v12;
      LOBYTE(v45) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v44,
        v45,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v53,
        v54,
        14,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v47 = wil::verify_hresult<long>(*a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v47,
      v53);
  }
  v16 = CreateEventW(0, 1, 0, 0);
  v17 = (char *)*((_QWORD *)v15 + 256);
  v18 = v16;
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v19 = GetLastError();
    CloseHandle(v17);
    SetLastError(v19);
  }
  *((_QWORD *)v15 + 256) = v18;
  v20 = *a1;
  if ( !*((_QWORD *)*a1 + 256) )
  {
    v48 = GetLastError();
    v51 = v48;
    if ( v48 > 0 )
      v51 = (unsigned __int16)v48 | 0x80070000;
    *a1[1] = v51;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v12 = 0;
    if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v49) = v12;
      LOBYTE(v50) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v49,
        v50,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v53,
        v54,
        15,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v52 = wil::verify_hresult<long>(*a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v52,
      v53);
  }
  v21 = CreateEventW(0, 1, 0, 0);
  v22 = (char *)*((_QWORD *)v20 + 257);
  v23 = v21;
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v24 = GetLastError();
    CloseHandle(v22);
    SetLastError(v24);
  }
  *((_QWORD *)v20 + 257) = v23;
  v25 = *a1;
  if ( !*((_QWORD *)*a1 + 257) )
  {
    v32 = GetLastError();
    v35 = v32;
    if ( v32 > 0 )
      v35 = (unsigned __int16)v32 | 0x80070000;
    *a1[1] = v35;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v12 = 0;
    if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v33) = v12;
      LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v33,
        v34,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v53,
        v54,
        16,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v36 = wil::verify_hresult<long>(*a1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v36,
      v53);
  }
  v26 = operator new[](0x2Du);
  *v26 = 0;
  v26[1] = 0;
  *(_OWORD *)((char *)v26 + 29) = 0;
  v28 = (void *)*((_QWORD *)v25 + 16);
  *((_QWORD *)v25 + 16) = v26;
  if ( v28 )
    operator delete(v28, v27);
  v29 = 0;
  v30 = *((_QWORD *)*a1 + 16);
  do
    *(_BYTE *)(v30 + v29++ + 24) = *((_BYTE *)*a1 + 16);
  while ( v29 != 2 );
  *(_DWORD *)(v30 + 26) = 16779836;
  *(_DWORD *)(v30 + 33) = 4;
  *(_WORD *)(v30 + 30) = 767;
  *(_BYTE *)(v30 + 32) = 12;
  result = *a1;
  *(_QWORD *)(v30 + 37) = *(_QWORD *)((char *)*a1 + 17);
  return result;
}

```

## disassembly

```asm
0x18002ce84  push    rbx
0x18002ce86  push    rbp
0x18002ce87  push    rsi
0x18002ce88  push    rdi
0x18002ce89  push    r14
0x18002ce8b  push    r15
0x18002ce8d  sub     rsp, 58h
0x18002ce91  mov     rax, [rcx]
0x18002ce94  xorps   xmm0, xmm0
0x18002ce97  mov     rdi, rcx
0x18002ce9a  xor     r9d, r9d; lpName
0x18002ce9d  xor     r8d, r8d; bInitialState
0x18002cea0  xor     edx, edx; bManualReset
0x18002cea2  movups  xmmword ptr [rax+58h], xmm0
0x18002cea6  movups  xmmword ptr [rax+68h], xmm0
0x18002ceaa  mov     rsi, [rcx]
0x18002cead  xor     ecx, ecx; lpEventAttributes
0x18002ceaf  call    cs:__imp_CreateEventW
0x18002ceb5  mov     rbp, [rsi+78h]
0x18002ceb9  mov     r14, rax
0x18002cebc  lea     rdx, [rbp-1]
0x18002cec0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002cec4  ja      short loc_18002CEDF
0x18002cec6  call    cs:__imp_GetLastError
0x18002cecc  mov     rcx, rbp; hObject
0x18002cecf  mov     ebx, eax
0x18002ced1  call    cs:__imp_CloseHandle
0x18002ced7  mov     ecx, ebx; dwErrCode
0x18002ced9  call    cs:__imp_SetLastError
0x18002cedf  mov     [rsi+78h], r14
0x18002cee3  mov     rax, [rdi]
0x18002cee6  mov     rcx, [rax+78h]
0x18002ceea  test    rcx, rcx
0x18002ceed  jz      loc_18002D167
0x18002cef3  mov     [rax+70h], rcx
0x18002cef7  xor     r8d, r8d; pcbe
0x18002cefa  mov     rax, [rdi+10h]
0x18002cefe  mov     rcx, [rdi]
0x18002cf01  mov     al, [rax]
0x18002cf03  mov     [rcx+10h], al
0x18002cf06  mov     rax, [rdi+18h]
0x18002cf0a  mov     rcx, [rdi]
0x18002cf0d  mov     rax, [rax]
0x18002cf10  mov     rax, [rax]
0x18002cf13  mov     [rcx+11h], rax
0x18002cf17  mov     rax, [rdi+20h]
0x18002cf1b  mov     rcx, [rax]
0x18002cf1e  mov     rax, [rdi]
0x18002cf21  movups  xmm0, xmmword ptr [rcx]
0x18002cf24  lea     rcx, ?s_OnIgnoreTimer@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002cf2b  movdqu  xmmword ptr [rax+19h], xmm0
0x18002cf30  mov     r14, [rdi]
0x18002cf33  mov     rdx, r14; pv
0x18002cf36  call    cs:__imp_CreateThreadpoolTimer
0x18002cf3c  mov     rbp, [r14+48h]
0x18002cf40  mov     esi, 1
0x18002cf45  mov     r15, rax
0x18002cf48  test    rbp, rbp
0x18002cf4b  jz      short loc_18002CF82
0x18002cf4d  call    cs:__imp_GetLastError
0x18002cf53  xor     r9d, r9d; msWindowLength
0x18002cf56  xor     r8d, r8d; msPeriod
0x18002cf59  xor     edx, edx; pftDueTime
0x18002cf5b  mov     rcx, rbp; pti
0x18002cf5e  mov     ebx, eax
0x18002cf60  call    cs:__imp_SetThreadpoolTimer
0x18002cf66  mov     edx, esi; fCancelPendingCallbacks
0x18002cf68  mov     rcx, rbp; pti
0x18002cf6b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002cf71  mov     rcx, rbp; pti
0x18002cf74  call    cs:__imp_CloseThreadpoolTimer
0x18002cf7a  mov     ecx, ebx; dwErrCode
0x18002cf7c  call    cs:__imp_SetLastError
0x18002cf82  mov     [r14+48h], r15
0x18002cf86  mov     rbp, [rdi]
0x18002cf89  cmp     qword ptr [rbp+48h], 0
0x18002cf8e  jz      loc_18002D216
0x18002cf94  xor     r9d, r9d; lpName
0x18002cf97  xor     r8d, r8d; bInitialState
0x18002cf9a  mov     edx, esi; bManualReset
0x18002cf9c  xor     ecx, ecx; lpEventAttributes
0x18002cf9e  call    cs:__imp_CreateEventW
0x18002cfa4  mov     r14, [rbp+800h]
0x18002cfab  mov     r15, rax
0x18002cfae  lea     rdx, [r14-1]
0x18002cfb2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002cfb6  ja      short loc_18002CFD1
0x18002cfb8  call    cs:__imp_GetLastError
0x18002cfbe  mov     rcx, r14; hObject
0x18002cfc1  mov     ebx, eax
0x18002cfc3  call    cs:__imp_CloseHandle
0x18002cfc9  mov     ecx, ebx; dwErrCode
0x18002cfcb  call    cs:__imp_SetLastError
0x18002cfd1  mov     [rbp+800h], r15
0x18002cfd8  mov     rbp, [rdi]
0x18002cfdb  cmp     qword ptr [rbp+800h], 0
0x18002cfe3  jz      loc_18002D2BE
0x18002cfe9  xor     r9d, r9d; lpName
0x18002cfec  xor     r8d, r8d; bInitialState
0x18002cfef  mov     edx, esi; bManualReset
0x18002cff1  xor     ecx, ecx; lpEventAttributes
0x18002cff3  call    cs:__imp_CreateEventW
0x18002cff9  mov     r14, [rbp+808h]
0x18002d000  mov     r15, rax
0x18002d003  lea     rdx, [r14-1]
0x18002d007  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d00b  ja      short loc_18002D026
0x18002d00d  call    cs:__imp_GetLastError
0x18002d013  mov     rcx, r14; hObject
0x18002d016  mov     ebx, eax
0x18002d018  call    cs:__imp_CloseHandle
0x18002d01e  mov     ecx, ebx; dwErrCode
0x18002d020  call    cs:__imp_SetLastError
0x18002d026  mov     [rbp+808h], r15
0x18002d02d  mov     rbx, [rdi]
0x18002d030  cmp     qword ptr [rbx+808h], 0
0x18002d038  jz      loc_18002D0BF
0x18002d03e  mov     ecx, 2Dh ; '-'; unsigned __int64
0x18002d043  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d048  xorps   xmm0, xmm0
0x18002d04b  movups  xmmword ptr [rax], xmm0
0x18002d04e  movups  xmmword ptr [rax+10h], xmm0
0x18002d052  movups  xmmword ptr [rax+1Dh], xmm0
0x18002d056  mov     rcx, [rbx+80h]; void *
0x18002d05d  mov     [rbx+80h], rax
0x18002d064  test    rcx, rcx
0x18002d067  jz      short loc_18002D06E
0x18002d069  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d06e  mov     rax, [rdi]
0x18002d071  xor     r8d, r8d
0x18002d074  mov     rdx, [rax+80h]
0x18002d07b  mov     rax, [rdi]
0x18002d07e  mov     cl, [rax+10h]
0x18002d081  mov     [rdx+r8+18h], cl
0x18002d086  add     r8, rsi
0x18002d089  cmp     r8, 2
0x18002d08d  jnz     short loc_18002D07B
0x18002d08f  mov     dword ptr [rdx+1Ah], 1000A3Ch
0x18002d096  mov     dword ptr [rdx+21h], 4
0x18002d09d  mov     word ptr [rdx+1Eh], 2FFh
0x18002d0a3  mov     byte ptr [rdx+20h], 0Ch
0x18002d0a7  mov     rax, [rdi]
0x18002d0aa  mov     rcx, [rax+11h]
0x18002d0ae  mov     [rdx+25h], rcx
0x18002d0b2  add     rsp, 58h
0x18002d0b6  pop     r15
0x18002d0b8  pop     r14
0x18002d0ba  pop     rdi
0x18002d0bb  pop     rsi
0x18002d0bc  pop     rbp
0x18002d0bd  pop     rbx
0x18002d0be  retn
0x18002d0bf  call    cs:__imp_GetLastError
0x18002d0c5  mov     ecx, eax
0x18002d0c7  test    eax, eax
0x18002d0c9  jle     short loc_18002D0D4
0x18002d0cb  movzx   ecx, ax
0x18002d0ce  or      ecx, 80070000h
0x18002d0d4  mov     rax, [rdi+8]
0x18002d0d8  mov     [rax], ecx
0x18002d0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0e1  lea     rax, WPP_GLOBAL_Control
0x18002d0e8  cmp     rcx, rax
0x18002d0eb  jz      short loc_18002D0F3
0x18002d0ed  cmp     byte ptr [rcx+19h], 2
0x18002d0f1  jnb     short loc_18002D0F6
0x18002d0f3  xor     sil, sil
0x18002d0f6  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d0fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d104  setnz   r8b
0x18002d108  test    sil, sil
0x18002d10b  jnz     short loc_18002D112
0x18002d10d  test    r8b, r8b
0x18002d110  jz      short loc_18002D13F
0x18002d112  mov     rax, [rdi+8]
0x18002d116  mov     dl, sil
0x18002d119  mov     r9, [rcx+28h]
0x18002d11d  mov     rcx, [rcx+10h]
0x18002d121  mov     eax, [rax]
0x18002d123  mov     [rsp+88h+var_40], eax
0x18002d127  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d12e  mov     [rsp+88h+var_50], rax
0x18002d133  mov     [rsp+88h+var_58], 10h
0x18002d13a  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d13f  mov     rcx, [rdi+8]
0x18002d143  mov     ecx, [rcx]
0x18002d145  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d14a  mov     rcx, [rsp+88h]; this
0x18002d152  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d159  mov     r9d, eax; char *
0x18002d15c  mov     edx, 6Bh ; 'k'; void *
0x18002d161  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d167  call    cs:__imp_GetLastError
0x18002d16d  mov     ecx, eax
0x18002d16f  test    eax, eax
0x18002d171  jle     short loc_18002D17C
0x18002d173  movzx   ecx, ax
0x18002d176  or      ecx, 80070000h
0x18002d17c  mov     rax, [rdi+8]
0x18002d180  mov     [rax], ecx
0x18002d182  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d189  lea     rax, WPP_GLOBAL_Control
0x18002d190  cmp     rcx, rax
0x18002d193  jz      short loc_18002D1A2
0x18002d195  cmp     byte ptr [rcx+19h], 2
0x18002d199  jb      short loc_18002D1A2
0x18002d19b  mov     esi, 1
0x18002d1a0  jmp     short loc_18002D1A5
0x18002d1a2  xor     sil, sil
0x18002d1a5  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d1ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d1b3  setnz   r8b
0x18002d1b7  test    sil, sil
0x18002d1ba  jnz     short loc_18002D1C1
0x18002d1bc  test    r8b, r8b
0x18002d1bf  jz      short loc_18002D1EE
0x18002d1c1  mov     rax, [rdi+8]
0x18002d1c5  mov     dl, sil
0x18002d1c8  mov     r9, [rcx+28h]
0x18002d1cc  mov     rcx, [rcx+10h]
0x18002d1d0  mov     eax, [rax]
0x18002d1d2  mov     [rsp+88h+var_40], eax
0x18002d1d6  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d1dd  mov     [rsp+88h+var_50], rax
0x18002d1e2  mov     [rsp+88h+var_58], 0Dh
0x18002d1e9  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d1ee  mov     rcx, [rdi+8]
0x18002d1f2  mov     ecx, [rcx]
0x18002d1f4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d1f9  mov     rcx, [rsp+88h]; this
0x18002d201  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d208  mov     r9d, eax; char *
0x18002d20b  mov     edx, 49h ; 'I'; void *
0x18002d210  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d216  call    cs:__imp_GetLastError
0x18002d21c  mov     ecx, eax
0x18002d21e  test    eax, eax
0x18002d220  jle     short loc_18002D22B
0x18002d222  movzx   ecx, ax
0x18002d225  or      ecx, 80070000h
0x18002d22b  mov     rax, [rdi+8]
0x18002d22f  mov     [rax], ecx
0x18002d231  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d238  lea     rax, WPP_GLOBAL_Control
0x18002d23f  cmp     rcx, rax
0x18002d242  jz      short loc_18002D24A
0x18002d244  cmp     byte ptr [rcx+19h], 2
0x18002d248  jnb     short loc_18002D24D
0x18002d24a  xor     sil, sil
0x18002d24d  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d254  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d25b  setnz   r8b
0x18002d25f  test    sil, sil
0x18002d262  jnz     short loc_18002D269
0x18002d264  test    r8b, r8b
0x18002d267  jz      short loc_18002D296
0x18002d269  mov     rax, [rdi+8]
0x18002d26d  mov     dl, sil
0x18002d270  mov     r9, [rcx+28h]
0x18002d274  mov     rcx, [rcx+10h]
0x18002d278  mov     eax, [rax]
0x18002d27a  mov     [rsp+88h+var_40], eax
0x18002d27e  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d285  mov     [rsp+88h+var_50], rax
0x18002d28a  mov     [rsp+88h+var_58], 0Eh
0x18002d291  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d296  mov     rcx, [rdi+8]
0x18002d29a  mov     ecx, [rcx]
0x18002d29c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d2a1  mov     rcx, [rsp+88h]; this
0x18002d2a9  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d2b0  mov     r9d, eax; char *
0x18002d2b3  mov     edx, 5Bh ; '['; void *
0x18002d2b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d2be  call    cs:__imp_GetLastError
0x18002d2c4  mov     ecx, eax
0x18002d2c6  test    eax, eax
0x18002d2c8  jle     short loc_18002D2D3
0x18002d2ca  movzx   ecx, ax
0x18002d2cd  or      ecx, 80070000h
0x18002d2d3  mov     rax, [rdi+8]
0x18002d2d7  mov     [rax], ecx
0x18002d2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2e0  lea     rax, WPP_GLOBAL_Control
0x18002d2e7  cmp     rcx, rax
0x18002d2ea  jz      short loc_18002D2F2
0x18002d2ec  cmp     byte ptr [rcx+19h], 2
0x18002d2f0  jnb     short loc_18002D2F5
0x18002d2f2  xor     sil, sil
0x18002d2f5  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d2fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d303  setnz   r8b
0x18002d307  test    sil, sil
0x18002d30a  jnz     short loc_18002D311
0x18002d30c  test    r8b, r8b
0x18002d30f  jz      short loc_18002D33E
0x18002d311  mov     rax, [rdi+8]
0x18002d315  mov     dl, sil
0x18002d318  mov     r9, [rcx+28h]
0x18002d31c  mov     rcx, [rcx+10h]
  ... truncated ...
```
