# AtmosCheck::ScheduleGracePeriodTimer(void)

- ea: `0x180157c20`
- end: `0x180157d80`
- name: `?ScheduleGracePeriodTimer@AtmosCheck@@AEAAXXZ`
- size: `352`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180155ebc`
- `0x180155fec`

## callees

- `0x1800565d0`
- `0x18006851c`
- `0x180156818`
- `0x180157c20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180157c36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180157c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157d6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157ca5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180157c93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180157c93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157d49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157d49`

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
            (unsigned int)&unk_1801AD064,
            v9,
            v10,
            (__int64)&v12);
        }
        pftDueTime = (struct _FILETIME)(-10000LL * SpatialAudioLicenseGracePeriodInMs);
        SetThreadpoolTimer(*((PTP_TIMER *)pv + 26), &pftDueTime, 0, 0);
        if ( CallbackContext > 5u )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v11,
            &unk_1801AD378);
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
            (unsigned int)&unk_1801AD4A3,
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
0x180157c20  mov     [rsp+arg_10], rbx
0x180157c25  push    rbp
0x180157c26  push    rsi
0x180157c27  push    rdi
0x180157c28  sub     rsp, 30h
0x180157c2c  lea     rdi, [rcx+38h]
0x180157c30  mov     rbx, rcx
0x180157c33  mov     rcx, rdi; lpCriticalSection
0x180157c36  call    cs:__imp_EnterCriticalSection
0x180157c3c  cmp     byte ptr [rbx+0D9h], 0
0x180157c43  jnz     short loc_180157C51
0x180157c45  mov     byte ptr [rbx+0D8h], 1
0x180157c4c  jmp     loc_180157D65
0x180157c51  cmp     byte ptr [rbx+0D8h], 0
0x180157c58  jnz     loc_180157D65
0x180157c5e  cmp     qword ptr [rbx+0D0h], 0
0x180157c66  jnz     loc_180157D65
0x180157c6c  cmp     byte ptr [rbx+109h], 0
0x180157c73  jz      loc_180157D65
0x180157c79  cmp     byte ptr [rbx+108h], 0
0x180157c80  jz      loc_180157D65
0x180157c86  xor     r8d, r8d; pcbe
0x180157c89  lea     rcx, ?StaticGracePeriodExpiredFired@AtmosCheck@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180157c90  mov     rdx, rbx; pv
0x180157c93  call    cs:__imp_CreateThreadpoolTimer
0x180157c99  mov     [rbx+0D0h], rax
0x180157ca0  test    rax, rax
0x180157ca3  jnz     short loc_180157CE9
0x180157ca5  call    cs:__imp_GetLastError
0x180157cab  mov     ecx, eax
0x180157cad  test    eax, eax
0x180157caf  jle     short loc_180157CBA
0x180157cb1  movzx   ecx, ax
0x180157cb4  or      ecx, 80070000h
0x180157cba  mov     eax, cs:CallbackContext
0x180157cc0  mov     esi, 5
0x180157cc5  cmp     eax, esi
0x180157cc7  jbe     loc_180157D65
0x180157ccd  lea     rax, [rsp+48h+arg_0]
0x180157cd2  mov     [rsp+48h+arg_0], ecx
0x180157cd6  lea     rdx, unk_1801AD4A3
0x180157cdd  mov     [rsp+48h+var_28], rax
0x180157ce2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180157ce7  jmp     short loc_180157D65
0x180157ce9  call    ?GetSpatialAudioLicenseGracePeriodInMs@AtmosCheck@@CAHXZ; AtmosCheck::GetSpatialAudioLicenseGracePeriodInMs(void)
0x180157cee  mov     ecx, cs:CallbackContext
0x180157cf4  test    eax, eax
0x180157cf6  mov     esi, 5
0x180157cfb  mov     ebp, eax
0x180157cfd  cmovz   ebp, esi
0x180157d00  cmp     ecx, esi
0x180157d02  jbe     short loc_180157D1E
0x180157d04  lea     rax, [rsp+48h+arg_0]
0x180157d09  mov     [rsp+48h+arg_0], ebp
0x180157d0d  lea     rdx, unk_1801AD064
0x180157d14  mov     [rsp+48h+var_28], rax
0x180157d19  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180157d1e  movsxd  rax, ebp
0x180157d21  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180157d26  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180157d2d  xor     r9d, r9d; msWindowLength
0x180157d30  xor     r8d, r8d; msPeriod
0x180157d33  mov     rcx, rax
0x180157d36  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180157d3a  shr     rcx, 20h
0x180157d3e  mov     [rsp+48h+pftDueTime.dwHighDateTime], ecx
0x180157d42  mov     rcx, [rbx+0D0h]; pti
0x180157d49  call    cs:__imp_SetThreadpoolTimer
0x180157d4f  mov     eax, cs:CallbackContext
0x180157d55  cmp     eax, esi
0x180157d57  jbe     short loc_180157D65
0x180157d59  lea     rdx, unk_1801AD378
0x180157d60  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180157d65  test    rdi, rdi
0x180157d68  jz      short loc_180157D73
0x180157d6a  mov     rcx, rdi; lpCriticalSection
0x180157d6d  call    cs:__imp_LeaveCriticalSection
0x180157d73  mov     rbx, [rsp+48h+arg_10]
0x180157d78  add     rsp, 30h
0x180157d7c  pop     rdi
0x180157d7d  pop     rsi
0x180157d7e  pop     rbp
0x180157d7f  retn
```
