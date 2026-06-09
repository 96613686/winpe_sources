# CRegistration::DeliverNextMessage(void)

- ea: `0x18003429c`
- end: `0x18003477a`
- name: `?DeliverNextMessage@CRegistration@@AEAAJXZ`
- size: `1246`
- prototype: `__int64 __fastcall(CRegistration *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033aa0`
- `0x180034780`
- `0x180034a98`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800093d4`
- `0x18001d2ec`
- `0x18003429c`
- `0x180034b80`
- `0x180038344`
- `0x180051420`
- `0x180051628`
- `0x18006b128`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800342d3`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800342d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034379`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800345f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034379`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800345f4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003444f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003447d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800346a6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800346dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034712`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034740`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003444f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003447d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800346a6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800346dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034712`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180034740`

## string_xrefs

- `0x18003472f`: `AccessCount`
- `0x180034589`: `Registrationid: %S to be disabled (and scheduled to be deleted on restart) since it has not accessed messages for %d notifications, LastNotifiedMessageId: %llu`
- `0x180034538`: `Registrationid: %S notified for MessageId: %llu, NotifyCount: %d, LastAccessedMessageId, %llu, RegistrationName: %S, Filter: %S`
- `0x180034630`: `Registrationid: %S has not yet accessed LastNotifiedMessageId: %llu`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistration::DeliverNextMessage(void (__fastcall **this)(char *))
{
  char *v2; // r13
  unsigned __int64 *v3; // rdi
  unsigned int v4; // ecx
  unsigned int *v5; // r15
  const WCHAR *v6; // rsi
  const WCHAR *v7; // rdx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rax
  const wchar_t *v14; // r9
  unsigned __int64 v15; // r12
  unsigned int v16; // esi
  const wchar_t *v17; // r9
  unsigned int v18; // r8d
  char *v19; // r15
  char *v20; // rsi
  const WCHAR *v21; // rbx
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rdx
  const WCHAR *v24; // rdx
  int pvData; // [rsp+50h] [rbp-89h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-85h] BYREF
  __time64_t Time[3]; // [rsp+58h] [rbp-81h] BYREF
  __int128 v29; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int64 v30; // [rsp+80h] [rbp-59h] BYREF
  _BYTE v31[4]; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int16 v32[42]; // [rsp+8Ch] [rbp-4Dh] BYREF

  Time[0] = 0;
  _time64(Time);
  Time[1] = (__time64_t)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v2 = (char *)(this + 38);
  Time[2] = (__time64_t)(this + 38);
  (*(void (__fastcall **)(char *))this[38])((char *)this + 304);
  v3 = (unsigned __int64 *)(this + 33);
  if ( this[32] )
  {
    if ( !*((_DWORD *)this + 57) )
      goto LABEL_39;
    if ( *v3 != *(_QWORD *)(*(_QWORD *)this[31] + 32LL) )
      goto LABEL_8;
    pvData = 120;
    pcbData = 4;
    if ( RegGetValueW(g_SmsRouterKey, L"Registration", L"PeekAcknowledgeTimeoutSecs", 0x10u, 0, &pvData, &pcbData)
      || (v4 = pvData) == 0 )
    {
      v4 = 120;
    }
    if ( LODWORD(Time[0]) - *((_DWORD *)this + 70) <= v4 )
    {
LABEL_39:
      if ( (unsigned __int64)this[3] > 7 )
        this = (void (__fastcall **)(char *))*this;
      LogSmsRouterInfo(
        "CRegistration::DeliverNextMessage",
        0x4F2u,
        "Registrationid: %S has not yet accessed LastNotifiedMessageId: %llu",
        (const wchar_t *)this,
        *v3);
    }
    else
    {
LABEL_8:
      memset_0((char *)&v29 + 4, 0, 0x6Cu);
      v29 = xmmword_180077F58;
      v30 = *(_QWORD *)(*(_QWORD *)this[31] + 32LL);
      CSmsMessageStore::GetMessageType(
        (CSmsMessageStore *)this[44],
        v30,
        (enum Windows::Sms::Common::SmsMessageType *)v31);
      if ( (unsigned __int64)this[3] <= 7 )
        StringCchPrintfW(v32, 0x28u, (const unsigned __int16 *)this);
      else
        StringCchPrintfW(v32, 0x28u, (const unsigned __int16 *)*this);
      v5 = (unsigned int *)(this + 34);
      if ( *v3 == v30 )
      {
        ++*v5;
      }
      else
      {
        *v3 = v30;
        *v5 = 1;
      }
      v6 = (const WCHAR *)(this + 22);
      if ( (unsigned __int64)this[25] <= 7 )
        v7 = (const WCHAR *)(this + 22);
      else
        v7 = *(const WCHAR **)v6;
      RegSetKeyValueW(g_SmsRouterKey, v7, L"LastNotifiedMessageId", 0xBu, this + 33, 8u);
      if ( (unsigned __int64)this[25] > 7 )
        v6 = *(const WCHAR **)v6;
      RegSetKeyValueW(g_SmsRouterKey, v6, L"NotifyCount", 4u, this + 34, 4u);
      this[35] = (void (__fastcall *)(char *))Time[0];
      v11 = EaSignalEventImpl((unsigned int)this[26], v8, v9, v10, (__int64)&v29, (unsigned int)&v30);
      if ( v11 )
      {
        LogSmsRouterError(
          "CRegistration::DeliverNextMessage",
          0x4C7u,
          v11 | 0x10000000,
          "EaSignalEvent failed for registrationid: %S, msgid: %llu",
          v32,
          v30);
      }
      else
      {
        v12 = (const wchar_t *)(this + 18);
        if ( (unsigned __int64)this[21] > 7 )
          v12 = *(const wchar_t **)v12;
        v13 = (const wchar_t *)(this + 6);
        if ( (unsigned __int64)this[9] > 7 )
          v13 = *(const wchar_t **)v13;
        if ( (unsigned __int64)this[3] <= 7 )
          v14 = (const wchar_t *)this;
        else
          v14 = (const wchar_t *)*this;
        LogSmsRouterInfo(
          "CRegistration::DeliverNextMessage",
          0x4D1u,
          "Registrationid: %S notified for MessageId: %llu, NotifyCount: %d, LastAccessedMessageId, %llu, RegistrationNam"
          "e: %S, Filter: %S",
          v14,
          *v3,
          *v5,
          this[36],
          v13,
          v12);
      }
      v15 = v30;
      v16 = *v5;
      if ( v16 <= CRegistration::GetMaxNotifyCount() )
      {
        if ( *((_DWORD *)this + 59) != 3 )
          goto LABEL_54;
      }
      else
      {
        *v3 = -1;
        *((_DWORD *)this + 56) = 0;
        if ( (unsigned __int64)this[3] <= 7 )
          v17 = (const wchar_t *)this;
        else
          v17 = (const wchar_t *)*this;
        LogSmsRouterInfo(
          "CRegistration::DeliverNextMessage",
          0x4E3u,
          "Registrationid: %S to be disabled (and scheduled to be deleted on restart) since it has not accessed messages "
          "for %d notifications, LastNotifiedMessageId: %llu",
          v17,
          v16,
          -1);
      }
      pvData = 60;
      pcbData = 4;
      if ( RegGetValueW(g_SmsRouterKey, L"Registration", L"PeekAcknowledgeTimeoutSecs", 0x10u, 0, &pvData, &pcbData)
        || (v18 = pvData) == 0 )
      {
        v18 = 60;
      }
      CRegistration::StartAcknowledgeMessageTimer((CRegistration *)this, v15, v18);
    }
  }
  else
  {
    *v3 = -1;
    this[36] = (void (__fastcall *)(char *))-1LL;
    v19 = (char *)(this + 34);
    *((_DWORD *)this + 68) = 0;
    v20 = (char *)(this + 37);
    *((_DWORD *)this + 74) = 0;
    v21 = (const WCHAR *)(this + 22);
    if ( *((_QWORD *)v21 + 3) <= 7u )
      v22 = v21;
    else
      v22 = *(const WCHAR **)v21;
    RegSetKeyValueW(g_SmsRouterKey, v22, L"LastNotifiedMessageId", 0xBu, v3, 8u);
    if ( *((_QWORD *)v21 + 3) <= 7u )
      v23 = v21;
    else
      v23 = *(const WCHAR **)v21;
    RegSetKeyValueW(g_SmsRouterKey, v23, L"NotifyCount", 4u, v19, 4u);
    if ( *((_QWORD *)v21 + 3) <= 7u )
      v24 = v21;
    else
      v24 = *(const WCHAR **)v21;
    RegSetKeyValueW(g_SmsRouterKey, v24, L"LastNotifiedMessageId", 0xBu, v3, 8u);
    if ( *((_QWORD *)v21 + 3) > 7u )
      v21 = *(const WCHAR **)v21;
    RegSetKeyValueW(g_SmsRouterKey, v21, L"AccessCount", 4u, v20, 4u);
  }
LABEL_54:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x18003429c  push    rbp
0x18003429e  push    rbx
0x18003429f  push    rsi
0x1800342a0  push    rdi
0x1800342a1  push    r12
0x1800342a3  push    r13
0x1800342a5  push    r14
0x1800342a7  push    r15
0x1800342a9  lea     rbp, [rsp-1Fh]
0x1800342ae  sub     rsp, 0F8h
0x1800342b5  mov     rax, cs:__security_cookie
0x1800342bc  xor     rax, rsp
0x1800342bf  mov     [rbp+57h+var_50], rax
0x1800342c3  mov     rbx, rcx
0x1800342c6  xor     r12d, r12d
0x1800342c9  mov     [rsp+130h+Time], r12
0x1800342ce  lea     rcx, [rsp+130h+Time]; Time
0x1800342d3  call    cs:__imp__time64
0x1800342d9  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800342e0  mov     [rbp+57h+var_D0], rax
0x1800342e4  lea     r13, [rbx+130h]
0x1800342eb  mov     [rbp+57h+var_C8], r13
0x1800342ef  mov     rax, [r13+0]
0x1800342f3  mov     rcx, r13
0x1800342f6  mov     rax, [rax]
0x1800342f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342fe  nop
0x1800342ff  lea     rdi, [rbx+108h]
0x180034306  cmp     [rbx+100h], r12
0x18003430d  jbe     loc_18003464D
0x180034313  cmp     [rbx+0E4h], r12d
0x18003431a  jz      loc_18003461B
0x180034320  mov     rax, [rbx+0F8h]
0x180034327  mov     rcx, [rax]
0x18003432a  mov     rax, [rcx+20h]
0x18003432e  lea     r14d, [r12+4]
0x180034333  cmp     [rdi], rax
0x180034336  jnz     short loc_18003439F
0x180034338  lea     esi, [r12+78h]
0x18003433d  mov     [rsp+130h+var_E0], esi
0x180034341  mov     [rsp+130h+var_DC], r14d
0x180034346  lea     rax, [rsp+130h+var_DC]
0x18003434b  mov     [rsp+130h+pcbData], rax; pcbData
0x180034350  lea     rax, [rsp+130h+var_E0]
0x180034355  mov     [rsp+130h+pvData], rax; pvData
0x18003435a  mov     [rsp+130h+pdwType], r12; pdwType
0x18003435f  lea     r9d, [r12+10h]; dwFlags
0x180034364  lea     r8, aPeekacknowledg; "PeekAcknowledgeTimeoutSecs"
0x18003436b  lea     rdx, aRegistration; "Registration"
0x180034372  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x180034379  call    cs:__imp_RegGetValueW
0x18003437f  test    eax, eax
0x180034381  jnz     short loc_18003438B
0x180034383  mov     ecx, [rsp+130h+var_E0]
0x180034387  test    ecx, ecx
0x180034389  jnz     short loc_18003438D
0x18003438b  mov     ecx, esi
0x18003438d  mov     eax, dword ptr [rsp+130h+Time]
0x180034391  sub     eax, [rbx+118h]
0x180034397  cmp     eax, ecx
0x180034399  jbe     loc_18003461B
0x18003439f  xor     edx, edx; Val
0x1800343a1  lea     r8d, [rdx+6Ch]; Size
0x1800343a5  lea     rcx, [rbp+57h+var_BC]; void *
0x1800343a9  call    memset_0
0x1800343ae  movups  xmm0, cs:xmmword_180077F58
0x1800343b5  movdqu  xmmword ptr [rbp-69h], xmm0
0x1800343ba  mov     rax, [rbx+0F8h]
0x1800343c1  mov     rcx, [rax]
0x1800343c4  mov     rdx, [rcx+20h]; unsigned __int64
0x1800343c8  mov     [rbp+57h+var_B0], rdx
0x1800343cc  lea     r8, [rbp+57h+var_A8]; enum Windows::Sms::Common::SmsMessageType *
0x1800343d0  mov     rcx, [rbx+160h]; this
0x1800343d7  call    ?GetMessageType@CSmsMessageStore@@QEAAJ_KPEAW4SmsMessageType@Common@Sms@Windows@@@Z; CSmsMessageStore::GetMessageType(unsigned __int64,Windows::Sms::Common::SmsMessageType *)
0x1800343dc  cmp     qword ptr [rbx+18h], 7
0x1800343e1  jbe     short loc_1800343E8
0x1800343e3  mov     r8, [rbx]
0x1800343e6  jmp     short loc_1800343EB
0x1800343e8  mov     r8, rbx; unsigned __int16 *
0x1800343eb  mov     edx, 28h ; '('; unsigned __int64
0x1800343f0  lea     rcx, [rbp+57h+var_A4]; unsigned __int16 *
0x1800343f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800343f9  lea     r15, [rbx+110h]
0x180034400  mov     rax, [rbp+57h+var_B0]
0x180034404  cmp     [rdi], rax
0x180034407  jnz     short loc_18003440E
0x180034409  inc     dword ptr [r15]
0x18003440c  jmp     short loc_180034418
0x18003440e  mov     [rdi], rax
0x180034411  mov     dword ptr [r15], 1
0x180034418  lea     rsi, [rbx+0B0h]
0x18003441f  cmp     qword ptr [rsi+18h], 7
0x180034424  jbe     short loc_18003442B
0x180034426  mov     rdx, [rsi]
0x180034429  jmp     short loc_18003442E
0x18003442b  mov     rdx, rsi; lpSubKey
0x18003442e  mov     dword ptr [rsp+130h+pvData], 8; cbData
0x180034436  mov     [rsp+130h+pdwType], rdi; lpData
0x18003443b  mov     r9d, 0Bh; dwType
0x180034441  lea     r8, aLastnotifiedme; "LastNotifiedMessageId"
0x180034448  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18003444f  call    cs:__imp_RegSetKeyValueW
0x180034455  cmp     qword ptr [rsi+18h], 7
0x18003445a  jbe     short loc_18003445F
0x18003445c  mov     rsi, [rsi]
0x18003445f  mov     dword ptr [rsp+130h+pvData], r14d; cbData
0x180034464  mov     [rsp+130h+pdwType], r15; lpData
0x180034469  mov     r9d, r14d; dwType
0x18003446c  lea     r8, aNotifycount; "NotifyCount"
0x180034473  mov     rdx, rsi; lpSubKey
0x180034476  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18003447d  call    cs:__imp_RegSetKeyValueW
0x180034483  mov     rax, [rsp+130h+Time]
0x180034488  mov     [rbx+118h], rax
0x18003448f  lea     rax, [rbp+57h+var_B0]
0x180034493  mov     [rsp+130h+pvData], rax
0x180034498  lea     rax, [rbp+57h+var_C0]
0x18003449c  mov     [rsp+130h+pdwType], rax
0x1800344a1  mov     rcx, [rbx+0D0h]
0x1800344a8  call    EaSignalEventImpl
0x1800344ad  test    eax, eax
0x1800344af  jz      short loc_1800344E4
0x1800344b1  bts     eax, 1Ch
0x1800344b5  mov     rcx, [rbp+57h+var_B0]
0x1800344b9  mov     [rsp+130h+pvData], rcx
0x1800344be  lea     rcx, [rbp+57h+var_A4]
0x1800344c2  mov     [rsp+130h+pdwType], rcx
0x1800344c7  lea     r9, aEasignaleventF; "EaSignalEvent failed for registrationid"...
0x1800344ce  mov     r8d, eax; int
0x1800344d1  mov     edx, 4C7h; unsigned int
0x1800344d6  lea     rcx, aCregistrationD_2; "CRegistration::DeliverNextMessage"
0x1800344dd  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800344e2  jmp     short loc_180034550
0x1800344e4  lea     rcx, [rbx+90h]
0x1800344eb  cmp     qword ptr [rcx+18h], 7
0x1800344f0  jbe     short loc_1800344F5
0x1800344f2  mov     rcx, [rcx]
0x1800344f5  lea     rax, [rbx+30h]
0x1800344f9  cmp     qword ptr [rax+18h], 7
0x1800344fe  jbe     short loc_180034503
0x180034500  mov     rax, [rax]
0x180034503  mov     rdx, [rbx+120h]
0x18003450a  mov     r8d, [r15]
0x18003450d  mov     r10, [rdi]
0x180034510  cmp     qword ptr [rbx+18h], 7
0x180034515  jbe     short loc_18003451C
0x180034517  mov     r9, [rbx]
0x18003451a  jmp     short loc_18003451F
0x18003451c  mov     r9, rbx
0x18003451f  mov     [rsp+130h+var_F0], rcx
0x180034524  mov     [rsp+130h+var_F8], rax
0x180034529  mov     [rsp+130h+pcbData], rdx
0x18003452e  mov     dword ptr [rsp+130h+pvData], r8d
0x180034533  mov     [rsp+130h+pdwType], r10
0x180034538  lea     r8, aRegistrationid_4; "Registrationid: %S notified for Message"...
0x18003453f  mov     edx, 4D1h; unsigned int
0x180034544  lea     rcx, aCregistrationD_2; "CRegistration::DeliverNextMessage"
0x18003454b  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180034550  mov     r12, [rbp+57h+var_B0]
0x180034554  mov     esi, [r15]
0x180034557  call    ?GetMaxNotifyCount@CRegistration@@SAKXZ; CRegistration::GetMaxNotifyCount(void)
0x18003455c  cmp     esi, eax
0x18003455e  jbe     short loc_1800345A3
0x180034560  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034564  mov     [rdi], rax
0x180034567  mov     dword ptr [rbx+0E0h], 0
0x180034571  cmp     qword ptr [rbx+18h], 7
0x180034576  jbe     short loc_18003457D
0x180034578  mov     r9, [rbx]
0x18003457b  jmp     short loc_180034580
0x18003457d  mov     r9, rbx
0x180034580  mov     [rsp+130h+pvData], rax
0x180034585  mov     dword ptr [rsp+130h+pdwType], esi
0x180034589  lea     r8, aRegistrationid; "Registrationid: %S to be disabled (and "...
0x180034590  mov     edx, 4E3h; unsigned int
0x180034595  lea     rcx, aCregistrationD_2; "CRegistration::DeliverNextMessage"
0x18003459c  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800345a1  jmp     short loc_1800345B0
0x1800345a3  cmp     dword ptr [rbx+0ECh], 3
0x1800345aa  jnz     loc_180034747
0x1800345b0  mov     edi, 3Ch ; '<'
0x1800345b5  mov     [rsp+130h+var_E0], edi
0x1800345b9  mov     [rsp+130h+var_DC], r14d
0x1800345be  lea     rax, [rsp+130h+var_DC]
0x1800345c3  mov     [rsp+130h+pcbData], rax; pcbData
0x1800345c8  lea     rax, [rsp+130h+var_E0]
0x1800345cd  mov     [rsp+130h+pvData], rax; pvData
0x1800345d2  mov     [rsp+130h+pdwType], 0; pdwType
0x1800345db  lea     r9d, [rdi-2Ch]; dwFlags
0x1800345df  lea     r8, aPeekacknowledg; "PeekAcknowledgeTimeoutSecs"
0x1800345e6  lea     rdx, aRegistration; "Registration"
0x1800345ed  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x1800345f4  call    cs:__imp_RegGetValueW
0x1800345fa  test    eax, eax
0x1800345fc  jnz     short loc_180034608
0x1800345fe  mov     r8d, [rsp+130h+var_E0]
0x180034603  test    r8d, r8d
0x180034606  jnz     short loc_18003460B
0x180034608  mov     r8d, edi; unsigned int
0x18003460b  mov     rdx, r12; unsigned __int64
0x18003460e  mov     rcx, rbx; this
0x180034611  call    ?StartAcknowledgeMessageTimer@CRegistration@@QEAAX_KK@Z; CRegistration::StartAcknowledgeMessageTimer(unsigned __int64,ulong)
0x180034616  jmp     loc_180034747
0x18003461b  mov     rax, [rdi]
0x18003461e  cmp     qword ptr [rbx+18h], 7
0x180034623  jbe     short loc_180034628
0x180034625  mov     rbx, [rbx]
0x180034628  mov     [rsp+130h+pdwType], rax
0x18003462d  mov     r9, rbx
0x180034630  lea     r8, aRegistrationid_1; "Registrationid: %S has not yet accessed"...
0x180034637  mov     edx, 4F2h; unsigned int
0x18003463c  lea     rcx, aCregistrationD_2; "CRegistration::DeliverNextMessage"
0x180034643  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180034648  jmp     loc_180034747
0x18003464d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034651  mov     [rdi], rax
0x180034654  mov     [rbx+120h], rax
0x18003465b  lea     r15, [rbx+110h]
0x180034662  mov     [r15], r12d
0x180034665  lea     rsi, [rbx+128h]
0x18003466c  mov     [rsi], r12d
0x18003466f  add     rbx, 0B0h
0x180034676  cmp     qword ptr [rbx+18h], 7
0x18003467b  jbe     short loc_180034682
0x18003467d  mov     rdx, [rbx]
0x180034680  jmp     short loc_180034685
0x180034682  mov     rdx, rbx; lpSubKey
0x180034685  mov     dword ptr [rsp+130h+pvData], 8; cbData
0x18003468d  mov     [rsp+130h+pdwType], rdi; lpData
0x180034692  mov     r9d, 0Bh; dwType
0x180034698  lea     r8, aLastnotifiedme; "LastNotifiedMessageId"
0x18003469f  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x1800346a6  call    cs:__imp_RegSetKeyValueW
0x1800346ac  cmp     qword ptr [rbx+18h], 7
0x1800346b1  jbe     short loc_1800346B8
0x1800346b3  mov     rdx, [rbx]
0x1800346b6  jmp     short loc_1800346BB
0x1800346b8  mov     rdx, rbx; lpSubKey
0x1800346bb  mov     r14d, 4
0x1800346c1  mov     dword ptr [rsp+130h+pvData], r14d; cbData
0x1800346c6  mov     [rsp+130h+pdwType], r15; lpData
0x1800346cb  mov     r9d, r14d; dwType
0x1800346ce  lea     r8, aNotifycount; "NotifyCount"
0x1800346d5  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x1800346dc  call    cs:__imp_RegSetKeyValueW
0x1800346e2  cmp     qword ptr [rbx+18h], 7
0x1800346e7  jbe     short loc_1800346EE
0x1800346e9  mov     rdx, [rbx]
0x1800346ec  jmp     short loc_1800346F1
0x1800346ee  mov     rdx, rbx; lpSubKey
0x1800346f1  mov     dword ptr [rsp+130h+pvData], 8; cbData
0x1800346f9  mov     [rsp+130h+pdwType], rdi; lpData
0x1800346fe  mov     r9d, 0Bh; dwType
0x180034704  lea     r8, aLastnotifiedme; "LastNotifiedMessageId"
0x18003470b  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180034712  call    cs:__imp_RegSetKeyValueW
0x180034718  cmp     qword ptr [rbx+18h], 7
0x18003471d  jbe     short loc_180034722
0x18003471f  mov     rbx, [rbx]
0x180034722  mov     dword ptr [rsp+130h+pvData], r14d; cbData
0x180034727  mov     [rsp+130h+pdwType], rsi; lpData
0x18003472c  mov     r9d, r14d; dwType
0x18003472f  lea     r8, aAccesscount; "AccessCount"
0x180034736  mov     rdx, rbx; lpSubKey
0x180034739  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x180034740  call    cs:__imp_RegSetKeyValueW
0x180034746  nop
0x180034747  mov     rax, [r13+0]
0x18003474b  mov     rcx, r13
0x18003474e  mov     rax, [rax+8]
0x180034752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034757  nop
0x180034758  xor     eax, eax
0x18003475a  mov     rcx, [rbp+57h+var_50]
0x18003475e  xor     rcx, rsp; StackCookie
0x180034761  call    __security_check_cookie
0x180034766  add     rsp, 0F8h
0x18003476d  pop     r15
0x18003476f  pop     r14
0x180034771  pop     r13
0x180034773  pop     r12
0x180034775  pop     rdi
0x180034776  pop     rsi
0x180034777  pop     rbx
0x180034778  pop     rbp
0x180034779  retn
```
