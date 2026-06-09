# DSService::ToggleShutdownTimer(int)

- ea: `0x180007ec4`
- end: `0x1800080be`
- name: `?ToggleShutdownTimer@DSService@@IEAAXH@Z`
- size: `506`
- prototype: `void __fastcall(PVOID pv, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180006730`
- `0x1800068e0`
- `0x180006e30`

## callees

- `0x180001178`
- `0x180001720`
- `0x180001d28`
- `0x180007ec4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ffb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007f3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ffb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000800a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000800a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008014`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008014`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f03`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007f03`

## string_xrefs

- `0x180007f5f`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x18000803a`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180007f75`: `DSService::ToggleShutdownTimer`
- `0x180008053`: `DSService::ToggleShutdownTimer`

## pseudocode

```c
void __fastcall DSService::ToggleShutdownTimer(unsigned int *pv, int a2)
{
  struct _TP_TIMER *v3; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const char *v18; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v19; // [rsp+70h] [rbp+27h] BYREF
  const char *v20; // [rsp+78h] [rbp+2Fh] BYREF
  _QWORD v21[4]; // [rsp+80h] [rbp+37h] BYREF
  int v22; // [rsp+C0h] [rbp+77h] BYREF
  struct _FILETIME pftDueTime; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( pv[15] != -1 )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)pv + 8);
    if ( a2 )
    {
      if ( !v3 )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(DSService::ShutdownTimerCallback, pv, 0);
        *((_QWORD *)pv + 8) = ThreadpoolTimer;
        if ( ThreadpoolTimer )
        {
          v5 = -10000LL * pv[15];
          pftDueTime.dwLowDateTime = -10000 * pv[15];
          pftDueTime.dwHighDateTime = HIDWORD(v5);
          SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
          if ( (unsigned int)dword_180039000 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v7, v6, v8) )
            {
              v18 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
              v19 = "DSService::ToggleShutdownTimer";
              v20 = "Creating shutdown timer";
              v21[0] = pv + 26;
              v22 = 0;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                v9,
                (__int64)byte_18002EFB1,
                v10,
                v11,
                v21,
                (__int64)&v22,
                &v20,
                &v19,
                &v18);
            }
          }
        }
      }
    }
    else if ( v3 )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)pv + 8), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)pv + 8));
      *((_QWORD *)pv + 8) = 0;
      if ( (unsigned int)dword_180039000 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v13, v12, v14) )
        {
          pftDueTime = (struct _FILETIME)"onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
          v22 = 0;
          v21[0] = "DSService::ToggleShutdownTimer";
          v20 = "Stopping and closing shutdown timer";
          v19 = (const char *)(pv + 26);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v15,
            (__int64)&unk_18002EF48,
            v16,
            v17,
            &v19,
            (__int64)&v22,
            &v20,
            v21,
            &pftDueTime);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180007ec4  push    rbp
0x180007ec6  push    rbx
0x180007ec7  push    rdi
0x180007ec8  lea     rbp, [rsp-47h]
0x180007ecd  sub     rsp, 90h
0x180007ed4  cmp     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x180007ed8  mov     rdi, rcx
0x180007edb  jz      loc_1800080B3
0x180007ee1  mov     rcx, [rcx+40h]; pti
0x180007ee5  test    edx, edx
0x180007ee7  jz      loc_180007FEA
0x180007eed  test    rcx, rcx
0x180007ef0  jnz     loc_1800080B3
0x180007ef6  xor     r8d, r8d; pcbe
0x180007ef9  lea     rcx, ?ShutdownTimerCallback@DSService@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007f00  mov     rdx, rdi; pv
0x180007f03  call    cs:__imp_CreateThreadpoolTimer
0x180007f09  mov     [rdi+40h], rax
0x180007f0d  test    rax, rax
0x180007f10  jz      loc_1800080B3
0x180007f16  mov     ecx, [rdi+3Ch]
0x180007f19  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180007f1d  imul    rbx, rcx, 0FFFFFFFFFFFFD8F0h
0x180007f24  xor     r9d, r9d; msWindowLength
0x180007f27  xor     r8d, r8d; msPeriod
0x180007f2a  mov     rcx, rbx
0x180007f2d  mov     [rbp+57h+pftDueTime.dwLowDateTime], ebx
0x180007f30  shr     rcx, 20h
0x180007f34  mov     [rbp+57h+pftDueTime.dwHighDateTime], ecx
0x180007f3a  mov     rcx, rax; pti
0x180007f3d  call    cs:__imp_SetThreadpoolTimer
0x180007f43  mov     eax, cs:dword_180039000
0x180007f49  cmp     eax, 5
0x180007f4c  jbe     loc_1800080B3
0x180007f52  call    _tlgKeywordOn
0x180007f57  test    al, al
0x180007f59  jz      loc_1800080B3
0x180007f5f  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180007f66  mov     [rbp+57h+var_40], rbx
0x180007f6a  mov     [rbp+57h+var_38], rax
0x180007f6e  lea     rdx, byte_18002EFB1
0x180007f75  lea     rax, aDsserviceToggl; "DSService::ToggleShutdownTimer"
0x180007f7c  mov     [rbp+57h+arg_0], 261h
0x180007f83  mov     [rbp+57h+var_30], rax
0x180007f87  lea     rax, aCreatingShutdo; "Creating shutdown timer"
0x180007f8e  mov     [rbp+57h+var_28], rax
0x180007f92  lea     rax, [rdi+68h]
0x180007f96  mov     [rbp+57h+var_20], rax
0x180007f9a  lea     rax, [rbp+57h+var_40]
0x180007f9e  mov     [rsp+0A0h+var_50], rax
0x180007fa3  lea     rax, [rbp+57h+arg_0]
0x180007fa7  mov     [rsp+0A0h+var_58], rax
0x180007fac  lea     rax, [rbp+57h+var_38]
0x180007fb0  mov     [rsp+0A0h+var_60], rax
0x180007fb5  lea     rax, [rbp+57h+var_30]
0x180007fb9  mov     [rsp+0A0h+var_68], rax
0x180007fbe  lea     rax, [rbp+57h+var_28]
0x180007fc2  mov     [rsp+0A0h+var_70], rax
0x180007fc7  lea     rax, [rbp+57h+arg_10]
0x180007fcb  mov     [rsp+0A0h+var_78], rax
0x180007fd0  lea     rax, [rbp+57h+var_20]
0x180007fd4  mov     [rsp+0A0h+var_80], rax
0x180007fd9  mov     [rbp+57h+arg_10], 0
0x180007fe0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180007fe5  jmp     loc_1800080B3
0x180007fea  test    rcx, rcx
0x180007fed  jz      loc_1800080B3
0x180007ff3  xor     r9d, r9d; msWindowLength
0x180007ff6  xor     r8d, r8d; msPeriod
0x180007ff9  xor     edx, edx; pftDueTime
0x180007ffb  call    cs:__imp_SetThreadpoolTimer
0x180008001  mov     rcx, [rdi+40h]; pti
0x180008005  mov     edx, 1; fCancelPendingCallbacks
0x18000800a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008010  mov     rcx, [rdi+40h]; pti
0x180008014  call    cs:__imp_CloseThreadpoolTimer
0x18000801a  mov     qword ptr [rdi+40h], 0
0x180008022  mov     eax, cs:dword_180039000
0x180008028  cmp     eax, 5
0x18000802b  jbe     loc_1800080B3
0x180008031  call    _tlgKeywordOn
0x180008036  test    al, al
0x180008038  jz      short loc_1800080B3
0x18000803a  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180008041  mov     [rbp+57h+arg_0], 271h
0x180008048  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x18000804c  lea     rdx, unk_18002EF48
0x180008053  lea     rax, aDsserviceToggl; "DSService::ToggleShutdownTimer"
0x18000805a  mov     [rbp+57h+arg_10], 0
0x180008061  mov     [rbp+57h+var_20], rax
0x180008065  lea     rax, aStoppingAndClo; "Stopping and closing shutdown timer"
0x18000806c  mov     [rbp+57h+var_28], rax
0x180008070  lea     rax, [rdi+68h]
0x180008074  mov     [rbp+57h+var_30], rax
0x180008078  lea     rax, [rbp+57h+arg_0]
0x18000807c  mov     [rsp+0A0h+var_58], rax
0x180008081  lea     rax, [rbp+57h+pftDueTime]
0x180008085  mov     [rsp+0A0h+var_60], rax
0x18000808a  lea     rax, [rbp+57h+var_20]
0x18000808e  mov     [rsp+0A0h+var_68], rax
0x180008093  lea     rax, [rbp+57h+var_28]
0x180008097  mov     [rsp+0A0h+var_70], rax
0x18000809c  lea     rax, [rbp+57h+arg_10]
0x1800080a0  mov     [rsp+0A0h+var_78], rax
0x1800080a5  lea     rax, [rbp+57h+var_30]
0x1800080a9  mov     [rsp+0A0h+var_80], rax
0x1800080ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800080b3  add     rsp, 90h
0x1800080ba  pop     rdi
0x1800080bb  pop     rbx
0x1800080bc  pop     rbp
0x1800080bd  retn
```
