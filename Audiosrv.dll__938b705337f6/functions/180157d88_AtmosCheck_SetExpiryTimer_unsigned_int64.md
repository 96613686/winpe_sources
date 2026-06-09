# AtmosCheck::SetExpiryTimer(unsigned __int64)

- ea: `0x180157d88`
- end: `0x180157f08`
- name: `?SetExpiryTimer@AtmosCheck@@AEAAX_K@Z`
- size: `384`
- prototype: `void __fastcall(PVOID pv, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800989a4`

## callees

- `0x18004f3a0`
- `0x1800565d0`
- `0x1800cf8c0`
- `0x180157d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180157dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180157dd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157e7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157e01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180157def`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180157def`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157e60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157e60`

## pseudocode

```c
void __fastcall AtmosCheck::SetExpiryTimer(char *pv, struct _FILETIME a2)
{
  __int64 v2; // r15
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  DWORD dwLowDateTime; // r14d
  unsigned __int64 v6; // rsi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // ecx
  __int64 v12; // [rsp+30h] [rbp-39h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-31h] BYREF
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  __int64 *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  v2 = *((_QWORD *)pv + 29);
  v3 = (struct _RTL_CRITICAL_SECTION *)(pv + 56);
  dwLowDateTime = a2.dwLowDateTime;
  v6 = HIDWORD(*(unsigned __int64 *)&a2);
  pftDueTime = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 56));
  ThreadpoolTimer = (struct _TP_TIMER *)*((_QWORD *)pv + 25);
  if ( ThreadpoolTimer
    || (ThreadpoolTimer = CreateThreadpoolTimer(AtmosCheck::StaticAtmosRefreshTimerCallback, pv, 0),
        (*((_QWORD *)pv + 25) = ThreadpoolTimer) != 0) )
  {
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x7530u);
    *((_DWORD *)pv + 58) = dwLowDateTime;
    *((_DWORD *)pv + 59) = v6;
    if ( v3 )
      LeaveCriticalSection(v3);
    if ( CallbackContext > 5u )
    {
      v12 = *((_QWORD *)pv + 29);
      v18 = &v12;
      v19 = 8;
      v16 = &v14;
      v17 = 8;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD))tlgWriteTransfer_EventWriteTransfer)(
        &CallbackContext,
        &unk_1801ACF0A,
        0,
        0,
        4,
        v15,
        v12,
        pftDueTime,
        v2);
    }
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( CallbackContext > 5u )
    {
      LODWORD(v12) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_1801ACE35,
        v9,
        v10,
        (__int64)&v12);
    }
    if ( v3 )
      LeaveCriticalSection(v3);
  }
}

```

## disassembly

```asm
0x180157d88  mov     [rsp-8+arg_10], rbx
0x180157d8d  push    rbp
0x180157d8e  push    rsi
0x180157d8f  push    rdi
0x180157d90  push    r14
0x180157d92  push    r15
0x180157d94  lea     rbp, [rsp-37h]
0x180157d99  sub     rsp, 0A0h
0x180157da0  mov     rax, cs:__security_cookie
0x180157da7  xor     rax, rsp
0x180157daa  mov     [rbp+57h+var_30], rax
0x180157dae  mov     r15, [rcx+0E8h]
0x180157db5  lea     rbx, [rcx+38h]
0x180157db9  mov     rsi, rdx
0x180157dbc  mov     r14, rdx
0x180157dbf  mov     rdi, rcx
0x180157dc2  shr     rsi, 20h
0x180157dc6  mov     rcx, rbx; lpCriticalSection
0x180157dc9  mov     [rbp+57h+pftDueTime.dwHighDateTime], esi
0x180157dcc  mov     [rbp+57h+pftDueTime.dwLowDateTime], r14d
0x180157dd0  call    cs:__imp_EnterCriticalSection
0x180157dd6  mov     rax, [rdi+0C8h]
0x180157ddd  test    rax, rax
0x180157de0  jnz     short loc_180157E50
0x180157de2  xor     r8d, r8d; pcbe
0x180157de5  lea     rcx, ?StaticAtmosRefreshTimerCallback@AtmosCheck@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180157dec  mov     rdx, rdi; pv
0x180157def  call    cs:__imp_CreateThreadpoolTimer
0x180157df5  mov     [rdi+0C8h], rax
0x180157dfc  test    rax, rax
0x180157dff  jnz     short loc_180157E50
0x180157e01  call    cs:__imp_GetLastError
0x180157e07  mov     ecx, eax
0x180157e09  test    eax, eax
0x180157e0b  jle     short loc_180157E16
0x180157e0d  movzx   ecx, ax
0x180157e10  or      ecx, 80070000h
0x180157e16  mov     eax, cs:CallbackContext
0x180157e1c  cmp     eax, 5
0x180157e1f  jbe     short loc_180157E39
0x180157e21  lea     rax, [rbp+57h+var_90]
0x180157e25  mov     dword ptr [rbp+57h+var_90], ecx
0x180157e28  lea     rdx, unk_1801ACE35
0x180157e2f  mov     [rsp+0C0h+var_A0], rax
0x180157e34  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180157e39  test    rbx, rbx
0x180157e3c  jz      loc_180157EE5
0x180157e42  mov     rcx, rbx; lpCriticalSection
0x180157e45  call    cs:__imp_LeaveCriticalSection
0x180157e4b  jmp     loc_180157EE5
0x180157e50  mov     r9d, 7530h; msWindowLength
0x180157e56  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180157e5a  xor     r8d, r8d; msPeriod
0x180157e5d  mov     rcx, rax; pti
0x180157e60  call    cs:__imp_SetThreadpoolTimer
0x180157e66  mov     [rdi+0E8h], r14d
0x180157e6d  mov     [rdi+0ECh], esi
0x180157e73  test    rbx, rbx
0x180157e76  jz      short loc_180157E81
0x180157e78  mov     rcx, rbx; lpCriticalSection
0x180157e7b  call    cs:__imp_LeaveCriticalSection
0x180157e81  mov     eax, cs:CallbackContext
0x180157e87  cmp     eax, 5
0x180157e8a  jbe     short loc_180157EE5
0x180157e8c  mov     rax, [rdi+0E8h]
0x180157e93  lea     rdx, unk_1801ACF0A
0x180157e9a  mov     [rbp+57h+var_90], rax
0x180157e9e  lea     rcx, CallbackContext
0x180157ea5  lea     rax, [rbp+57h+var_90]
0x180157ea9  mov     [rbp+57h+var_80], r15
0x180157ead  mov     [rbp+57h+var_40], rax
0x180157eb1  xor     r9d, r9d
0x180157eb4  lea     rax, [rbp+57h+var_80]
0x180157eb8  mov     [rbp+57h+var_38], 8
0x180157ec0  mov     [rbp+57h+var_50], rax
0x180157ec4  xor     r8d, r8d
0x180157ec7  lea     rax, [rbp+57h+var_70]
0x180157ecb  mov     [rbp+57h+var_48], 8
0x180157ed3  mov     [rsp+0C0h+var_98], rax
0x180157ed8  mov     dword ptr [rsp+0C0h+var_A0], 4
0x180157ee0  call    _tlgWriteTransfer_EventWriteTransfer
0x180157ee5  mov     rcx, [rbp+57h+var_30]
0x180157ee9  xor     rcx, rsp; StackCookie
0x180157eec  call    __security_check_cookie
0x180157ef1  mov     rbx, [rsp+0C0h+arg_10]
0x180157ef9  add     rsp, 0A0h
0x180157f00  pop     r15
0x180157f02  pop     r14
0x180157f04  pop     rdi
0x180157f05  pop     rsi
0x180157f06  pop     rbp
0x180157f07  retn
```
