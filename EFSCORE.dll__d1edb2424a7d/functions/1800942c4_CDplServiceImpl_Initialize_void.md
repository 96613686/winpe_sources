# CDplServiceImpl::Initialize(void)

- ea: `0x1800942c4`
- end: `0x180094687`
- name: `?Initialize@CDplServiceImpl@@AEAAJXZ`
- size: `963`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800912c4`

## callees

- `0x180001a7c`
- `0x180001e5c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800841b0`
- `0x1800942c4`
- `0x180094690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094467`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009460f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009460f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800945fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800945fd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800945b3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800945b3`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180094357`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180094357`
- `ntdll!RtlNtStatusToDosError` at `0x1800945c1`
- `ntdll!RtlNtStatusToDosError` at `0x1800945c1`
- `ntdll!RtlIsMultiSessionSku` at `0x1800944d7`
- `ntdll!RtlIsMultiSessionSku` at `0x1800944d7`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::Initialize(char *pv)
{
  int v2; // ebx
  int v3; // ecx
  HANDLE EventW; // rax
  int v5; // ecx
  signed int LastError; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // eax
  int v11; // esi
  signed int v12; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v14; // eax
  char v16; // [rsp+20h] [rbp-58h]
  __int128 v17; // [rsp+40h] [rbp-38h] BYREF
  int v18; // [rsp+80h] [rbp+8h] BYREF
  __int64 v19; // [rsp+88h] [rbp+10h] BYREF

  v17 = 0;
  fnEfsLogTrace1Strings((_DWORD)pv, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 201);
  if ( (*((_QWORD *)pv + 9) == 0) != (*((_QWORD *)pv + 10) == 0) )
  {
    v2 = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 37, 205);
    goto LABEL_31;
  }
  *((_QWORD *)&v17 + 1) = pv;
  *(_QWORD *)&v17 = CDplServiceImpl::PowerNotificationCallback;
  v2 = PowerRegisterSuspendResumeNotification(2, &v17, pv + 152);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)L"Registering for power events",
    v2,
    37,
    219);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v18 = 0;
    v19 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180114250,
      (__int64)byte_180102E03,
      0,
      0,
      (__int64)&v19,
      (__int64)&v18);
  }
  fnEfsLogTrace1Strings(v3, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 229);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              37,
              229) >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)pv + 20) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v16 = -22;
      goto LABEL_30;
    }
    fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 236);
    fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 196);
    *((_DWORD *)pv + 42) = 0;
    if ( (unsigned __int8)RtlIsMultiSessionSku() && !(unsigned int)EdpCredSvcIsDesktopAndDplDisallowed() )
      *((_DWORD *)pv + 42) = 1;
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_LEAVE_EVENT, (unsigned int)&sourceString, 37, 230);
    v2 = 0;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                0,
                37,
                236) >= 0 )
    {
      fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 238);
      v2 = DpmCache::Initialize((DpmCache *)(pv + 176));
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v2,
                  37,
                  238) >= 0 )
      {
        if ( *((_QWORD *)pv + 30)
          || (v10 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)pv + 30, L"SHA256", 0, 0), v11 = v10, v10 >= 0) )
        {
          ThreadpoolTimer = CreateThreadpoolTimer(CDplServiceImpl::FileKeysLockTimerCallbackStatic, pv, 0);
          *((_QWORD *)pv + 31) = ThreadpoolTimer;
          if ( ThreadpoolTimer )
            goto LABEL_31;
          v14 = GetLastError();
          v2 = v14;
          if ( v14 > 0 )
            v2 = (unsigned __int16)v14 | 0x80070000;
          v16 = 3;
        }
        else
        {
          v12 = RtlNtStatusToDosError(v10);
          v2 = v12;
          if ( !v12 || v12 == 317 )
          {
            v2 = v11 | 0x10000000;
          }
          else if ( v12 > 0 )
          {
            v2 = (unsigned __int16)v12 | 0x80070000;
          }
          v16 = -8;
        }
LABEL_30:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v2, 37, v16);
      }
    }
  }
LABEL_31:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v2,
    37,
    8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800942c4  mov     [rsp+arg_10], rbx
0x1800942c9  push    rsi
0x1800942ca  push    rdi
0x1800942cb  push    r12
0x1800942cd  push    r14
0x1800942cf  push    r15
0x1800942d1  sub     rsp, 50h
0x1800942d5  xorps   xmm0, xmm0
0x1800942d8  mov     dword ptr [rsp+78h+var_58], 0C9h
0x1800942e0  mov     r14d, 25h ; '%'
0x1800942e6  lea     r15, sourceString
0x1800942ed  mov     r9d, r14d
0x1800942f0  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800942f7  mov     r8, r15
0x1800942fa  mov     rdi, rcx
0x1800942fd  movups  [rsp+78h+var_38], xmm0
0x180094302  call    fnEfsLogTrace1Strings
0x180094307  xor     edx, edx
0x180094309  cmp     [rdi+50h], rdx
0x18009430d  setz    dl
0x180094310  xor     eax, eax
0x180094312  cmp     [rdi+48h], rax
0x180094316  setz    al
0x180094319  cmp     eax, edx
0x18009431b  jz      short loc_180094335
0x18009431d  mov     ebx, 8000FFFFh
0x180094322  mov     dword ptr [rsp+78h+var_58], 0CDh
0x18009432a  mov     r8d, 8000FFFFh
0x180094330  jmp     loc_18009462C
0x180094335  lea     rax, ?PowerNotificationCallback@CDplServiceImpl@@CAKPEAXK0@Z; CDplServiceImpl::PowerNotificationCallback(void *,ulong,void *)
0x18009433c  mov     qword ptr [rsp+78h+var_38+8], rdi
0x180094341  lea     r8, [rdi+98h]
0x180094348  mov     qword ptr [rsp+78h+var_38], rax
0x18009434d  lea     rdx, [rsp+78h+var_38]
0x180094352  mov     ecx, 2
0x180094357  call    cs:__imp_PowerRegisterSuspendResumeNotification
0x18009435d  mov     rcx, cs:g_hPublisher
0x180094364  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18009436b  mov     [rsp+78h+var_48], 0DBh
0x180094373  lea     r9, aRegisteringFor; "Registering for power events"
0x18009437a  mov     r8, rdx
0x18009437d  mov     dword ptr [rsp+78h+var_50], r14d
0x180094382  mov     ebx, eax
0x180094384  mov     dword ptr [rsp+78h+var_58], eax
0x180094388  call    fnEfsLogTrace1String1Dword
0x18009438d  mov     eax, cs:dword_180114250
0x180094393  cmp     eax, 5
0x180094396  jbe     short loc_1800943FC
0x180094398  mov     rdx, 400000000000h
0x1800943a2  lea     rcx, dword_180114250
0x1800943a9  call    _tlgKeywordOn
0x1800943ae  test    al, al
0x1800943b0  jz      short loc_1800943FC
0x1800943b2  lea     rax, [rsp+78h+arg_0]
0x1800943ba  mov     [rsp+78h+arg_0], 0
0x1800943c5  mov     [rsp+78h+var_50], rax
0x1800943ca  lea     rdx, byte_180102E03
0x1800943d1  lea     rax, [rsp+78h+arg_8]
0x1800943d9  mov     [rsp+78h+arg_8], 1000000h
0x1800943e5  xor     r9d, r9d
0x1800943e8  mov     [rsp+78h+var_58], rax
0x1800943ed  xor     r8d, r8d
0x1800943f0  lea     rcx, dword_180114250
0x1800943f7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800943fc  mov     esi, 0E5h
0x180094401  lea     rdx, EFS_TRACE_START_EVENT
0x180094408  mov     r9d, r14d
0x18009440b  mov     dword ptr [rsp+78h+var_58], esi
0x18009440f  mov     r8, r15
0x180094412  call    fnEfsLogTrace1Strings
0x180094417  mov     r12d, 80070000h
0x18009441d  test    ebx, ebx
0x18009441f  jle     short loc_180094427
0x180094421  movzx   ebx, bx
0x180094424  or      ebx, r12d
0x180094427  mov     rcx, cs:g_hPublisher
0x18009442e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094435  mov     [rsp+78h+var_48], esi
0x180094439  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094440  mov     dword ptr [rsp+78h+var_50], r14d
0x180094445  mov     r9, r15
0x180094448  mov     dword ptr [rsp+78h+var_58], ebx
0x18009444c  call    fnEfsLogTrace1String1Dword
0x180094451  test    eax, eax
0x180094453  js      loc_180094642
0x180094459  xor     r9d, r9d; lpName
0x18009445c  xor     r8d, r8d; bInitialState
0x18009445f  xor     ecx, ecx; lpEventAttributes
0x180094461  lea     ebx, [r9+1]
0x180094465  mov     edx, ebx; bManualReset
0x180094467  call    cs:__imp_CreateEventW
0x18009446d  mov     [rdi+0A0h], rax
0x180094474  test    rax, rax
0x180094477  jnz     short loc_180094498
0x180094479  call    cs:__imp_GetLastError
0x18009447f  mov     ebx, eax
0x180094481  test    eax, eax
0x180094483  jle     short loc_18009448B
0x180094485  movzx   ebx, ax
0x180094488  or      ebx, r12d
0x18009448b  mov     dword ptr [rsp+78h+var_58], 0EAh
0x180094493  jmp     loc_180094629
0x180094498  mov     esi, 0ECh
0x18009449d  lea     rdx, EFS_TRACE_START_EVENT
0x1800944a4  mov     r9d, r14d
0x1800944a7  mov     dword ptr [rsp+78h+var_58], esi
0x1800944ab  mov     r8, r15
0x1800944ae  call    fnEfsLogTrace1Strings
0x1800944b3  mov     r9d, r14d
0x1800944b6  mov     dword ptr [rsp+78h+var_58], 20C4h
0x1800944be  mov     r8, r15
0x1800944c1  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800944c8  call    fnEfsLogTrace1Strings
0x1800944cd  mov     dword ptr [rdi+0A8h], 0
0x1800944d7  call    cs:__imp_RtlIsMultiSessionSku
0x1800944dd  test    al, al
0x1800944df  jz      short loc_1800944F0
0x1800944e1  call    ?EdpCredSvcIsDesktopAndDplDisallowed@@YAHXZ; EdpCredSvcIsDesktopAndDplDisallowed(void)
0x1800944e6  test    eax, eax
0x1800944e8  jnz     short loc_1800944F0
0x1800944ea  mov     [rdi+0A8h], ebx
0x1800944f0  mov     r9d, r14d
0x1800944f3  mov     dword ptr [rsp+78h+var_58], 20E6h
0x1800944fb  mov     r8, r15
0x1800944fe  lea     rdx, EFS_TRACE_LEAVE_EVENT
0x180094505  call    fnEfsLogTrace1Strings
0x18009450a  mov     rcx, cs:g_hPublisher
0x180094511  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094518  mov     [rsp+78h+var_48], esi
0x18009451c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094523  xor     ebx, ebx
0x180094525  mov     dword ptr [rsp+78h+var_50], r14d
0x18009452a  mov     r9, r15
0x18009452d  mov     dword ptr [rsp+78h+var_58], ebx
0x180094531  call    fnEfsLogTrace1String1Dword
0x180094536  test    eax, eax
0x180094538  js      loc_180094642
0x18009453e  mov     esi, 0EEh
0x180094543  lea     rdx, EFS_TRACE_START_EVENT
0x18009454a  mov     r9d, r14d
0x18009454d  mov     dword ptr [rsp+78h+var_58], esi
0x180094551  mov     r8, r15
0x180094554  call    fnEfsLogTrace1Strings
0x180094559  lea     rcx, [rdi+0B0h]; this
0x180094560  call    ?Initialize@DpmCache@@QEAAJXZ; DpmCache::Initialize(void)
0x180094565  mov     rcx, cs:g_hPublisher
0x18009456c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094573  mov     [rsp+78h+var_48], esi
0x180094577  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18009457e  mov     dword ptr [rsp+78h+var_50], r14d
0x180094583  mov     r9, r15
0x180094586  mov     dword ptr [rsp+78h+var_58], eax
0x18009458a  mov     ebx, eax
0x18009458c  call    fnEfsLogTrace1String1Dword
0x180094591  test    eax, eax
0x180094593  js      loc_180094642
0x180094599  lea     rcx, [rdi+0F0h]; phAlgorithm
0x1800945a0  cmp     qword ptr [rcx], 0
0x1800945a4  jnz     short loc_1800945F0
0x1800945a6  xor     r9d, r9d; dwFlags
0x1800945a9  lea     rdx, aSha256; "SHA256"
0x1800945b0  xor     r8d, r8d; pszImplementation
0x1800945b3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800945b9  mov     esi, eax
0x1800945bb  test    eax, eax
0x1800945bd  jns     short loc_1800945F0
0x1800945bf  mov     ecx, eax; Status
0x1800945c1  call    cs:__imp_RtlNtStatusToDosError
0x1800945c7  mov     ebx, eax
0x1800945c9  test    eax, eax
0x1800945cb  jz      short loc_1800945E0
0x1800945cd  cmp     eax, 13Dh
0x1800945d2  jz      short loc_1800945E0
0x1800945d4  test    eax, eax
0x1800945d6  jle     short loc_1800945E6
0x1800945d8  movzx   ebx, ax
0x1800945db  or      ebx, r12d
0x1800945de  jmp     short loc_1800945E6
0x1800945e0  mov     ebx, esi
0x1800945e2  bts     ebx, 1Ch
0x1800945e6  mov     dword ptr [rsp+78h+var_58], 0F8h
0x1800945ee  jmp     short loc_180094629
0x1800945f0  xor     r8d, r8d; pcbe
0x1800945f3  lea     rcx, ?FileKeysLockTimerCallbackStatic@CDplServiceImpl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800945fa  mov     rdx, rdi; pv
0x1800945fd  call    cs:__imp_CreateThreadpoolTimer
0x180094603  mov     [rdi+0F8h], rax
0x18009460a  test    rax, rax
0x18009460d  jnz     short loc_180094642
0x18009460f  call    cs:__imp_GetLastError
0x180094615  mov     ebx, eax
0x180094617  test    eax, eax
0x180094619  jle     short loc_180094621
0x18009461b  movzx   ebx, ax
0x18009461e  or      ebx, r12d
0x180094621  mov     dword ptr [rsp+78h+var_58], 103h
0x180094629  mov     r8d, ebx
0x18009462c  mov     rcx, cs:g_hPublisher
0x180094633  lea     rdx, EFS_TRACE_ERROR
0x18009463a  mov     r9d, r14d
0x18009463d  call    fnEfsLogTrace1
0x180094642  mov     rcx, cs:g_hPublisher
0x180094649  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180094650  mov     [rsp+78h+var_48], 108h
0x180094658  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x18009465f  mov     dword ptr [rsp+78h+var_50], r14d
0x180094664  mov     r9, r15
0x180094667  mov     dword ptr [rsp+78h+var_58], ebx
0x18009466b  call    fnEfsLogTrace1String1Dword
0x180094670  mov     eax, ebx
0x180094672  mov     rbx, [rsp+78h+arg_10]
0x18009467a  add     rsp, 50h
0x18009467e  pop     r15
0x180094680  pop     r14
0x180094682  pop     r12
0x180094684  pop     rdi
0x180094685  pop     rsi
0x180094686  retn
```
