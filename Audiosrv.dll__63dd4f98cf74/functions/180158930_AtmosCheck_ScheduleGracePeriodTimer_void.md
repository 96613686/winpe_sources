# AtmosCheck::ScheduleGracePeriodTimer(void)

- ea: `0x180158930`
- end: `0x180158a90`
- name: `?ScheduleGracePeriodTimer@AtmosCheck@@AEAAXXZ`
- size: `352`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180156bcc`
- `0x180156cfc`

## callees

- `0x180056140`
- `0x18006808c`
- `0x180157528`
- `0x180158930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801589b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801589b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801589a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801589a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180158a59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180158a59`

## pseudocode

```c
void __fastcall AtmosCheck::ScheduleGracePeriodTimer(char *pv)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ecx
  int SpatialAudioLicenseGracePeriodInMs; // ebp
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  unsigned int v12; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(pv + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 56));
  if ( pv[217] )
  {
    if ( !pv[216] && !*((_QWORD *)pv + 26) && pv[265] && pv[264] )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(AtmosCheck::StaticGracePeriodExpiredFired, pv, 0);
      *((_QWORD *)pv + 26) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        SpatialAudioLicenseGracePeriodInMs = AtmosCheck::GetSpatialAudioLicenseGracePeriodInMs();
        if ( !SpatialAudioLicenseGracePeriodInMs )
          SpatialAudioLicenseGracePeriodInMs = 5;
        if ( CallbackContext > 5u )
        {
          v12 = SpatialAudioLicenseGracePeriodInMs;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            CallbackContext,
            (unsigned int)&byte_1801AE2A7,
            v9,
            v10,
            (__int64)&v12);
        }
        pftDueTime = (struct _FILETIME)(-10000LL * SpatialAudioLicenseGracePeriodInMs);
        SetThreadpoolTimer(*((PTP_TIMER *)pv + 26), &pftDueTime, 0, 0);
        if ( CallbackContext > 5u )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v11,
            byte_1801AE5BB);
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( CallbackContext > 5u )
        {
          v12 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)&word_1801AE6E6,
            v5,
            v6,
            (__int64)&v12);
        }
      }
    }
  }
  else
  {
    pv[216] = 1;
  }
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180158930  mov     [rsp+arg_10], rbx
0x180158935  push    rbp
0x180158936  push    rsi
0x180158937  push    rdi
0x180158938  sub     rsp, 30h
0x18015893c  lea     rdi, [rcx+38h]
0x180158940  mov     rbx, rcx
0x180158943  mov     rcx, rdi; lpCriticalSection
0x180158946  call    cs:__imp_EnterCriticalSection
0x18015894c  cmp     byte ptr [rbx+0D9h], 0
0x180158953  jnz     short loc_180158961
0x180158955  mov     byte ptr [rbx+0D8h], 1
0x18015895c  jmp     loc_180158A75
0x180158961  cmp     byte ptr [rbx+0D8h], 0
0x180158968  jnz     loc_180158A75
0x18015896e  cmp     qword ptr [rbx+0D0h], 0
0x180158976  jnz     loc_180158A75
0x18015897c  cmp     byte ptr [rbx+109h], 0
0x180158983  jz      loc_180158A75
0x180158989  cmp     byte ptr [rbx+108h], 0
0x180158990  jz      loc_180158A75
0x180158996  xor     r8d, r8d; pcbe
0x180158999  lea     rcx, ?StaticGracePeriodExpiredFired@AtmosCheck@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801589a0  mov     rdx, rbx; pv
0x1801589a3  call    cs:__imp_CreateThreadpoolTimer
0x1801589a9  mov     [rbx+0D0h], rax
0x1801589b0  test    rax, rax
0x1801589b3  jnz     short loc_1801589F9
0x1801589b5  call    cs:__imp_GetLastError
0x1801589bb  mov     ecx, eax
0x1801589bd  test    eax, eax
0x1801589bf  jle     short loc_1801589CA
0x1801589c1  movzx   ecx, ax
0x1801589c4  or      ecx, 80070000h
0x1801589ca  mov     eax, cs:CallbackContext
0x1801589d0  mov     esi, 5
0x1801589d5  cmp     eax, esi
0x1801589d7  jbe     loc_180158A75
0x1801589dd  lea     rax, [rsp+48h+arg_0]
0x1801589e2  mov     [rsp+48h+arg_0], ecx
0x1801589e6  lea     rdx, word_1801AE6E6
0x1801589ed  mov     [rsp+48h+var_28], rax
0x1801589f2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801589f7  jmp     short loc_180158A75
0x1801589f9  call    ?GetSpatialAudioLicenseGracePeriodInMs@AtmosCheck@@CAHXZ; AtmosCheck::GetSpatialAudioLicenseGracePeriodInMs(void)
0x1801589fe  mov     ecx, cs:CallbackContext
0x180158a04  test    eax, eax
0x180158a06  mov     esi, 5
0x180158a0b  mov     ebp, eax
0x180158a0d  cmovz   ebp, esi
0x180158a10  cmp     ecx, esi
0x180158a12  jbe     short loc_180158A2E
0x180158a14  lea     rax, [rsp+48h+arg_0]
0x180158a19  mov     [rsp+48h+arg_0], ebp
0x180158a1d  lea     rdx, byte_1801AE2A7
0x180158a24  mov     [rsp+48h+var_28], rax
0x180158a29  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180158a2e  movsxd  rax, ebp
0x180158a31  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180158a36  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180158a3d  xor     r9d, r9d; msWindowLength
0x180158a40  xor     r8d, r8d; msPeriod
0x180158a43  mov     rcx, rax
0x180158a46  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180158a4a  shr     rcx, 20h
0x180158a4e  mov     [rsp+48h+pftDueTime.dwHighDateTime], ecx
0x180158a52  mov     rcx, [rbx+0D0h]; pti
0x180158a59  call    cs:__imp_SetThreadpoolTimer
0x180158a5f  mov     eax, cs:CallbackContext
0x180158a65  cmp     eax, esi
0x180158a67  jbe     short loc_180158A75
0x180158a69  lea     rdx, byte_1801AE5BB
0x180158a70  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180158a75  test    rdi, rdi
0x180158a78  jz      short loc_180158A83
0x180158a7a  mov     rcx, rdi; lpCriticalSection
0x180158a7d  call    cs:__imp_LeaveCriticalSection
0x180158a83  mov     rbx, [rsp+48h+arg_10]
0x180158a88  add     rsp, 30h
0x180158a8c  pop     rdi
0x180158a8d  pop     rsi
0x180158a8e  pop     rbp
0x180158a8f  retn
```
