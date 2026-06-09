# TelemetryLogger::SessionManagerBrokerMakeAvailable::StopActivity(void)

- ea: `0x180069540`
- end: `0x1800697c4`
- name: `?StopActivity@SessionManagerBrokerMakeAvailable@TelemetryLogger@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerMakeAvailable *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180069540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006959a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006972c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006959a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006972c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069764`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069764`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerMakeAvailable::StopActivity(
        TelemetryLogger::SessionManagerBrokerMakeAvailable *this)
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
        (__int64)&unk_18009D5E8,
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
        (__int64)byte_18009D4FB,
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
0x180069540  push    rbp
0x180069542  push    rbx
0x180069543  push    rdi
0x180069544  lea     rbp, [rsp-47h]
0x180069549  sub     rsp, 100h
0x180069550  mov     rdi, [rcx+110h]
0x180069557  mov     rbx, rcx
0x18006955a  mov     eax, [rdi+48h]
0x18006955d  test    eax, eax
0x18006955f  jns     loc_18006970D
0x180069565  add     rdi, 50h ; 'P'
0x180069569  cmp     eax, [rdi+8]
0x18006956c  jnz     loc_18006970D
0x180069572  test    rdi, rdi
0x180069575  jz      loc_18006970D
0x18006957b  lea     rdx, [rbp+57h+SRWLock]
0x18006957f  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069584  mov     rax, [rbx+110h]
0x18006958b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006958f  mov     dword ptr [rax], 2
0x180069595  test    rcx, rcx
0x180069598  jz      short loc_1800695A0
0x18006959a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800695a0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800695a5  mov     r9, [rax+8]
0x1800695a9  mov     eax, [r9]
0x1800695ac  cmp     eax, 5
0x1800695af  jbe     loc_1800697B2
0x1800695b5  mov     rdx, [r9+18h]
0x1800695b9  mov     rcx, 400000000000h
0x1800695c3  mov     rax, [r9+10h]
0x1800695c7  test    rcx, rax
0x1800695ca  jz      loc_1800697B2
0x1800695d0  mov     rax, rdx
0x1800695d3  and     rax, rcx
0x1800695d6  cmp     rax, rdx
0x1800695d9  jnz     loc_1800697B2
0x1800695df  mov     rax, [rdi+78h]
0x1800695e3  lea     rdx, unk_18009D5E8
0x1800695ea  mov     r8, [rbx+110h]
0x1800695f1  mov     rcx, r9
0x1800695f4  mov     [rbp+57h+var_68], rax
0x1800695f8  add     r8, 8
0x1800695fc  mov     rax, [rdi+70h]
0x180069600  mov     [rbp+57h+var_60], rax
0x180069604  mov     eax, [rdi+68h]
0x180069607  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006960a  mov     rax, [rdi+60h]
0x18006960e  mov     [rbp+57h+var_58], rax
0x180069612  mov     rax, [rdi+58h]
0x180069616  mov     [rbp+57h+var_50], rax
0x18006961a  mov     eax, [rdi+50h]
0x18006961d  mov     [rbp+57h+arg_8], eax
0x180069620  mov     rax, [rdi+48h]
0x180069624  mov     [rbp+57h+var_48], rax
0x180069628  mov     eax, [rdi+20h]
0x18006962b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006962e  mov     rax, [rdi+18h]
0x180069632  mov     [rbp+57h+var_40], rax
0x180069636  mov     eax, [rdi]
0x180069638  mov     [rbp+57h+arg_18], eax
0x18006963b  mov     rax, [rdi+80h]
0x180069642  mov     [rbp+57h+var_38], rax
0x180069646  mov     eax, [rdi+40h]
0x180069649  mov     [rbp+57h+var_70], eax
0x18006964c  mov     rax, [rdi+38h]
0x180069650  mov     [rbp+57h+var_30], rax
0x180069654  mov     eax, [rdi+8]
0x180069657  mov     [rbp+57h+var_6C], eax
0x18006965a  mov     eax, 1000000h
0x18006965f  mov     [rbp+57h+var_28], rax
0x180069663  mov     [rbp+57h+var_20], rax
0x180069667  lea     rax, [rbp+57h+var_68]
0x18006966b  mov     [rsp+110h+var_78], rax
0x180069673  lea     rax, [rbp+57h+var_60]
0x180069677  mov     [rsp+110h+var_80], rax
0x18006967f  lea     rax, [rbp+57h+SRWLock]
0x180069683  mov     [rsp+110h+var_88], rax
0x18006968b  lea     rax, [rbp+57h+var_58]
0x18006968f  mov     [rsp+110h+var_90], rax
0x180069697  lea     rax, [rbp+57h+var_50]
0x18006969b  mov     [rsp+110h+var_98], rax
0x1800696a0  lea     rax, [rbp+57h+arg_8]
0x1800696a4  mov     [rsp+110h+var_A0], rax
0x1800696a9  lea     rax, [rbp+57h+var_48]
0x1800696ad  mov     [rsp+110h+var_A8], rax
0x1800696b2  lea     rax, [rbp+57h+arg_10]
0x1800696b6  mov     [rsp+110h+var_B0], rax
0x1800696bb  lea     rax, [rbp+57h+var_40]
0x1800696bf  mov     [rsp+110h+var_B8], rax
0x1800696c4  lea     rax, [rbp+57h+arg_18]
0x1800696c8  mov     [rsp+110h+var_C0], rax
0x1800696cd  lea     rax, [rbp+57h+var_38]
0x1800696d1  mov     [rsp+110h+var_C8], rax
0x1800696d6  lea     rax, [rbp+57h+var_70]
0x1800696da  mov     [rsp+110h+var_D0], rax
0x1800696df  lea     rax, [rbp+57h+var_30]
0x1800696e3  mov     [rsp+110h+var_D8], rax
0x1800696e8  lea     rax, [rbp+57h+var_6C]
0x1800696ec  mov     [rsp+110h+var_E0], rax
0x1800696f1  lea     rax, [rbp+57h+var_28]
0x1800696f5  mov     [rsp+110h+var_E8], rax
0x1800696fa  lea     rax, [rbp+57h+var_20]
0x1800696fe  mov     [rsp+110h+var_F0], rax
0x180069703  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180069708  jmp     loc_1800697B2
0x18006970d  lea     rdx, [rbp+57h+SRWLock]
0x180069711  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069716  mov     rax, [rbx+110h]
0x18006971d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180069721  mov     dword ptr [rax], 2
0x180069727  test    rcx, rcx
0x18006972a  jz      short loc_180069732
0x18006972c  call    cs:__imp_ReleaseSRWLockExclusive
0x180069732  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180069737  mov     rdi, [rax+8]
0x18006973b  mov     eax, [rdi]
0x18006973d  cmp     eax, 5
0x180069740  jbe     short loc_1800697B2
0x180069742  mov     rdx, [rdi+18h]
0x180069746  mov     rcx, 400000000000h
0x180069750  mov     rax, [rdi+10h]
0x180069754  test    rcx, rax
0x180069757  jz      short loc_1800697B2
0x180069759  mov     rax, rdx
0x18006975c  and     rax, rcx
0x18006975f  cmp     rax, rdx
0x180069762  jnz     short loc_1800697B2
0x180069764  call    cs:__imp_GetCurrentThreadId
0x18006976a  mov     r8, [rbx+110h]
0x180069771  lea     rdx, byte_18009D4FB
0x180069778  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006977b  mov     rcx, rdi
0x18006977e  mov     eax, [r8+48h]
0x180069782  add     r8, 8
0x180069786  mov     [rbp+57h+arg_8], eax
0x180069789  mov     eax, 1000000h
0x18006978e  mov     [rbp+57h+arg_10], rax
0x180069792  lea     rax, [rbp+57h+SRWLock]
0x180069796  mov     [rsp+110h+var_E0], rax
0x18006979b  lea     rax, [rbp+57h+arg_8]
0x18006979f  mov     [rsp+110h+var_E8], rax
0x1800697a4  lea     rax, [rbp+57h+arg_10]
0x1800697a8  mov     [rsp+110h+var_F0], rax
0x1800697ad  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800697b2  mov     rcx, rbx
0x1800697b5  add     rsp, 100h
0x1800697bc  pop     rdi
0x1800697bd  pop     rbx
0x1800697be  pop     rbp
0x1800697bf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
