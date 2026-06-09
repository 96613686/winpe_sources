# AtmosCheck::SetExpiryTimer(unsigned __int64)

- ea: `0x180158a98`
- end: `0x180158c18`
- name: `?SetExpiryTimer@AtmosCheck@@AEAAX_K@Z`
- size: `384`
- prototype: `void __fastcall(PVOID pv, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180098a54`

## callees

- `0x18004ef10`
- `0x180056140`
- `0x1800cd8d0`
- `0x180158a98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ae0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158b55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158b8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158b55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180158aff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180158aff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180158b70`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180158b70`

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
        byte_1801AE14D,
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
        (unsigned int)&dword_1801AE024,
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
0x180158a98  mov     [rsp-8+arg_10], rbx
0x180158a9d  push    rbp
0x180158a9e  push    rsi
0x180158a9f  push    rdi
0x180158aa0  push    r14
0x180158aa2  push    r15
0x180158aa4  lea     rbp, [rsp-37h]
0x180158aa9  sub     rsp, 0A0h
0x180158ab0  mov     rax, cs:__security_cookie
0x180158ab7  xor     rax, rsp
0x180158aba  mov     [rbp+57h+var_30], rax
0x180158abe  mov     r15, [rcx+0E8h]
0x180158ac5  lea     rbx, [rcx+38h]
0x180158ac9  mov     rsi, rdx
0x180158acc  mov     r14, rdx
0x180158acf  mov     rdi, rcx
0x180158ad2  shr     rsi, 20h
0x180158ad6  mov     rcx, rbx; lpCriticalSection
0x180158ad9  mov     [rbp+57h+pftDueTime.dwHighDateTime], esi
0x180158adc  mov     [rbp+57h+pftDueTime.dwLowDateTime], r14d
0x180158ae0  call    cs:__imp_EnterCriticalSection
0x180158ae6  mov     rax, [rdi+0C8h]
0x180158aed  test    rax, rax
0x180158af0  jnz     short loc_180158B60
0x180158af2  xor     r8d, r8d; pcbe
0x180158af5  lea     rcx, ?StaticAtmosRefreshTimerCallback@AtmosCheck@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180158afc  mov     rdx, rdi; pv
0x180158aff  call    cs:__imp_CreateThreadpoolTimer
0x180158b05  mov     [rdi+0C8h], rax
0x180158b0c  test    rax, rax
0x180158b0f  jnz     short loc_180158B60
0x180158b11  call    cs:__imp_GetLastError
0x180158b17  mov     ecx, eax
0x180158b19  test    eax, eax
0x180158b1b  jle     short loc_180158B26
0x180158b1d  movzx   ecx, ax
0x180158b20  or      ecx, 80070000h
0x180158b26  mov     eax, cs:CallbackContext
0x180158b2c  cmp     eax, 5
0x180158b2f  jbe     short loc_180158B49
0x180158b31  lea     rax, [rbp+57h+var_90]
0x180158b35  mov     dword ptr [rbp+57h+var_90], ecx
0x180158b38  lea     rdx, dword_1801AE024
0x180158b3f  mov     [rsp+0C0h+var_A0], rax
0x180158b44  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180158b49  test    rbx, rbx
0x180158b4c  jz      loc_180158BF5
0x180158b52  mov     rcx, rbx; lpCriticalSection
0x180158b55  call    cs:__imp_LeaveCriticalSection
0x180158b5b  jmp     loc_180158BF5
0x180158b60  mov     r9d, 7530h; msWindowLength
0x180158b66  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180158b6a  xor     r8d, r8d; msPeriod
0x180158b6d  mov     rcx, rax; pti
0x180158b70  call    cs:__imp_SetThreadpoolTimer
0x180158b76  mov     [rdi+0E8h], r14d
0x180158b7d  mov     [rdi+0ECh], esi
0x180158b83  test    rbx, rbx
0x180158b86  jz      short loc_180158B91
0x180158b88  mov     rcx, rbx; lpCriticalSection
0x180158b8b  call    cs:__imp_LeaveCriticalSection
0x180158b91  mov     eax, cs:CallbackContext
0x180158b97  cmp     eax, 5
0x180158b9a  jbe     short loc_180158BF5
0x180158b9c  mov     rax, [rdi+0E8h]
0x180158ba3  lea     rdx, byte_1801AE14D
0x180158baa  mov     [rbp+57h+var_90], rax
0x180158bae  lea     rcx, CallbackContext
0x180158bb5  lea     rax, [rbp+57h+var_90]
0x180158bb9  mov     [rbp+57h+var_80], r15
0x180158bbd  mov     [rbp+57h+var_40], rax
0x180158bc1  xor     r9d, r9d
0x180158bc4  lea     rax, [rbp+57h+var_80]
0x180158bc8  mov     [rbp+57h+var_38], 8
0x180158bd0  mov     [rbp+57h+var_50], rax
0x180158bd4  xor     r8d, r8d
0x180158bd7  lea     rax, [rbp+57h+var_70]
0x180158bdb  mov     [rbp+57h+var_48], 8
0x180158be3  mov     [rsp+0C0h+var_98], rax
0x180158be8  mov     dword ptr [rsp+0C0h+var_A0], 4
0x180158bf0  call    _tlgWriteTransfer_EventWriteTransfer
0x180158bf5  mov     rcx, [rbp+57h+var_30]
0x180158bf9  xor     rcx, rsp; StackCookie
0x180158bfc  call    __security_check_cookie
0x180158c01  mov     rbx, [rsp+0C0h+arg_10]
0x180158c09  add     rsp, 0A0h
0x180158c10  pop     r15
0x180158c12  pop     r14
0x180158c14  pop     rdi
0x180158c15  pop     rsi
0x180158c16  pop     rbp
0x180158c17  retn
```
