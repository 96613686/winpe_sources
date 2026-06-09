# TelemetryLogger::SessionManagerBrokerIsAvailable::StopActivity(void)

- ea: `0x180069020`
- end: `0x1800692a4`
- name: `?StopActivity@SessionManagerBrokerIsAvailable@TelemetryLogger@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerIsAvailable *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180069020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006907a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006920c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006907a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006920c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069244`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069244`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerIsAvailable::StopActivity(
        TelemetryLogger::SessionManagerBrokerIsAvailable *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v15; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v18; // [rsp+C0h] [rbp+7h] BYREF
  const wchar_t *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v20; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const wchar_t *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v16 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v6,
        (__int64)byte_18009D97D,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        &v22,
        (__int64)&v13,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        (__int64)&v26,
        &v18,
        &v17,
        (__int64)&SRWLock,
        &v16,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)byte_18009D91D,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180069020  push    rbp
0x180069022  push    rbx
0x180069023  push    rdi
0x180069024  lea     rbp, [rsp-47h]
0x180069029  sub     rsp, 100h
0x180069030  mov     rdi, [rcx+110h]
0x180069037  mov     rbx, rcx
0x18006903a  mov     eax, [rdi+48h]
0x18006903d  test    eax, eax
0x18006903f  jns     loc_1800691ED
0x180069045  add     rdi, 50h ; 'P'
0x180069049  cmp     eax, [rdi+8]
0x18006904c  jnz     loc_1800691ED
0x180069052  test    rdi, rdi
0x180069055  jz      loc_1800691ED
0x18006905b  lea     rdx, [rbp+57h+SRWLock]
0x18006905f  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069064  mov     rax, [rbx+110h]
0x18006906b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006906f  mov     dword ptr [rax], 2
0x180069075  test    rcx, rcx
0x180069078  jz      short loc_180069080
0x18006907a  call    cs:__imp_ReleaseSRWLockExclusive
0x180069080  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069085  mov     r9, [rax+8]
0x180069089  mov     eax, [r9]
0x18006908c  cmp     eax, 5
0x18006908f  jbe     loc_180069292
0x180069095  mov     rdx, [r9+18h]
0x180069099  mov     rcx, 400000000000h
0x1800690a3  mov     rax, [r9+10h]
0x1800690a7  test    rcx, rax
0x1800690aa  jz      loc_180069292
0x1800690b0  mov     rax, rdx
0x1800690b3  and     rax, rcx
0x1800690b6  cmp     rax, rdx
0x1800690b9  jnz     loc_180069292
0x1800690bf  mov     rax, [rdi+78h]
0x1800690c3  lea     rdx, byte_18009D97D
0x1800690ca  mov     r8, [rbx+110h]
0x1800690d1  mov     rcx, r9
0x1800690d4  mov     [rbp+57h+var_68], rax
0x1800690d8  add     r8, 8
0x1800690dc  mov     rax, [rdi+70h]
0x1800690e0  mov     [rbp+57h+var_60], rax
0x1800690e4  mov     eax, [rdi+68h]
0x1800690e7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800690ea  mov     rax, [rdi+60h]
0x1800690ee  mov     [rbp+57h+var_58], rax
0x1800690f2  mov     rax, [rdi+58h]
0x1800690f6  mov     [rbp+57h+var_50], rax
0x1800690fa  mov     eax, [rdi+50h]
0x1800690fd  mov     [rbp+57h+arg_8], eax
0x180069100  mov     rax, [rdi+48h]
0x180069104  mov     [rbp+57h+var_48], rax
0x180069108  mov     eax, [rdi+20h]
0x18006910b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006910e  mov     rax, [rdi+18h]
0x180069112  mov     [rbp+57h+var_40], rax
0x180069116  mov     eax, [rdi]
0x180069118  mov     [rbp+57h+arg_18], eax
0x18006911b  mov     rax, [rdi+80h]
0x180069122  mov     [rbp+57h+var_38], rax
0x180069126  mov     eax, [rdi+40h]
0x180069129  mov     [rbp+57h+var_70], eax
0x18006912c  mov     rax, [rdi+38h]
0x180069130  mov     [rbp+57h+var_30], rax
0x180069134  mov     eax, [rdi+8]
0x180069137  mov     [rbp+57h+var_6C], eax
0x18006913a  mov     eax, 1000000h
0x18006913f  mov     [rbp+57h+var_28], rax
0x180069143  mov     [rbp+57h+var_20], rax
0x180069147  lea     rax, [rbp+57h+var_68]
0x18006914b  mov     [rsp+110h+var_78], rax
0x180069153  lea     rax, [rbp+57h+var_60]
0x180069157  mov     [rsp+110h+var_80], rax
0x18006915f  lea     rax, [rbp+57h+SRWLock]
0x180069163  mov     [rsp+110h+var_88], rax
0x18006916b  lea     rax, [rbp+57h+var_58]
0x18006916f  mov     [rsp+110h+var_90], rax
0x180069177  lea     rax, [rbp+57h+var_50]
0x18006917b  mov     [rsp+110h+var_98], rax
0x180069180  lea     rax, [rbp+57h+arg_8]
0x180069184  mov     [rsp+110h+var_A0], rax
0x180069189  lea     rax, [rbp+57h+var_48]
0x18006918d  mov     [rsp+110h+var_A8], rax
0x180069192  lea     rax, [rbp+57h+arg_10]
0x180069196  mov     [rsp+110h+var_B0], rax
0x18006919b  lea     rax, [rbp+57h+var_40]
0x18006919f  mov     [rsp+110h+var_B8], rax
0x1800691a4  lea     rax, [rbp+57h+arg_18]
0x1800691a8  mov     [rsp+110h+var_C0], rax
0x1800691ad  lea     rax, [rbp+57h+var_38]
0x1800691b1  mov     [rsp+110h+var_C8], rax
0x1800691b6  lea     rax, [rbp+57h+var_70]
0x1800691ba  mov     [rsp+110h+var_D0], rax
0x1800691bf  lea     rax, [rbp+57h+var_30]
0x1800691c3  mov     [rsp+110h+var_D8], rax
0x1800691c8  lea     rax, [rbp+57h+var_6C]
0x1800691cc  mov     [rsp+110h+var_E0], rax
0x1800691d1  lea     rax, [rbp+57h+var_28]
0x1800691d5  mov     [rsp+110h+var_E8], rax
0x1800691da  lea     rax, [rbp+57h+var_20]
0x1800691de  mov     [rsp+110h+var_F0], rax
0x1800691e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800691e8  jmp     loc_180069292
0x1800691ed  lea     rdx, [rbp+57h+SRWLock]
0x1800691f1  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800691f6  mov     rax, [rbx+110h]
0x1800691fd  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180069201  mov     dword ptr [rax], 2
0x180069207  test    rcx, rcx
0x18006920a  jz      short loc_180069212
0x18006920c  call    cs:__imp_ReleaseSRWLockExclusive
0x180069212  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069217  mov     rdi, [rax+8]
0x18006921b  mov     eax, [rdi]
0x18006921d  cmp     eax, 5
0x180069220  jbe     short loc_180069292
0x180069222  mov     rdx, [rdi+18h]
0x180069226  mov     rcx, 400000000000h
0x180069230  mov     rax, [rdi+10h]
0x180069234  test    rcx, rax
0x180069237  jz      short loc_180069292
0x180069239  mov     rax, rdx
0x18006923c  and     rax, rcx
0x18006923f  cmp     rax, rdx
0x180069242  jnz     short loc_180069292
0x180069244  call    cs:__imp_GetCurrentThreadId
0x18006924a  mov     r8, [rbx+110h]
0x180069251  lea     rdx, byte_18009D91D
0x180069258  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006925b  mov     rcx, rdi
0x18006925e  mov     eax, [r8+48h]
0x180069262  add     r8, 8
0x180069266  mov     [rbp+57h+arg_8], eax
0x180069269  mov     eax, 1000000h
0x18006926e  mov     [rbp+57h+arg_10], rax
0x180069272  lea     rax, [rbp+57h+SRWLock]
0x180069276  mov     [rsp+110h+var_E0], rax
0x18006927b  lea     rax, [rbp+57h+arg_8]
0x18006927f  mov     [rsp+110h+var_E8], rax
0x180069284  lea     rax, [rbp+57h+arg_10]
0x180069288  mov     [rsp+110h+var_F0], rax
0x18006928d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069292  mov     rcx, rbx
0x180069295  add     rsp, 100h
0x18006929c  pop     rdi
0x18006929d  pop     rbx
0x18006929e  pop     rbp
0x18006929f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
