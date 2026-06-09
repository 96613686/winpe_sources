# WaasMedic::TelemetryProvider::OneSettingsActivity::StopActivity(void)

- ea: `0x180024fc0`
- end: `0x180025244`
- name: `?StopActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::OneSettingsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x180024fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002501a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800251ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002501a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800251ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800251e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800251e4`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::OneSettingsActivity::StopActivity(
        WaasMedic::TelemetryProvider::OneSettingsActivity *this)
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
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&unk_1800929EF,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
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
        (unsigned int)&unk_180092B65,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180024fc0  push    rbp
0x180024fc2  push    rbx
0x180024fc3  push    rdi
0x180024fc4  lea     rbp, [rsp-47h]
0x180024fc9  sub     rsp, 100h
0x180024fd0  mov     rdi, [rcx+110h]
0x180024fd7  mov     rbx, rcx
0x180024fda  mov     eax, [rdi+48h]
0x180024fdd  test    eax, eax
0x180024fdf  jns     loc_18002518D
0x180024fe5  add     rdi, 50h ; 'P'
0x180024fe9  cmp     eax, [rdi+8]
0x180024fec  jnz     loc_18002518D
0x180024ff2  test    rdi, rdi
0x180024ff5  jz      loc_18002518D
0x180024ffb  lea     rdx, [rbp+57h+SRWLock]
0x180024fff  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025004  mov     rax, [rbx+110h]
0x18002500b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002500f  mov     dword ptr [rax], 2
0x180025015  test    rcx, rcx
0x180025018  jz      short loc_180025020
0x18002501a  call    cs:__imp_ReleaseSRWLockExclusive
0x180025020  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180025025  mov     r9, [rax+8]
0x180025029  mov     eax, [r9]
0x18002502c  cmp     eax, 5
0x18002502f  jbe     loc_180025232
0x180025035  mov     rdx, [r9+18h]
0x180025039  mov     rcx, 400000000000h
0x180025043  mov     rax, [r9+10h]
0x180025047  test    rcx, rax
0x18002504a  jz      loc_180025232
0x180025050  mov     rax, rdx
0x180025053  and     rax, rcx
0x180025056  cmp     rax, rdx
0x180025059  jnz     loc_180025232
0x18002505f  mov     rax, [rdi+78h]
0x180025063  lea     rdx, unk_1800929EF
0x18002506a  mov     r8, [rbx+110h]
0x180025071  mov     rcx, r9
0x180025074  mov     [rbp+57h+var_68], rax
0x180025078  add     r8, 8
0x18002507c  mov     rax, [rdi+70h]
0x180025080  mov     [rbp+57h+var_60], rax
0x180025084  mov     eax, [rdi+68h]
0x180025087  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002508a  mov     rax, [rdi+60h]
0x18002508e  mov     [rbp+57h+var_58], rax
0x180025092  mov     rax, [rdi+58h]
0x180025096  mov     [rbp+57h+var_50], rax
0x18002509a  mov     eax, [rdi+50h]
0x18002509d  mov     [rbp+57h+arg_8], eax
0x1800250a0  mov     rax, [rdi+48h]
0x1800250a4  mov     [rbp+57h+var_48], rax
0x1800250a8  mov     eax, [rdi+20h]
0x1800250ab  mov     dword ptr [rbp+57h+arg_10], eax
0x1800250ae  mov     rax, [rdi+18h]
0x1800250b2  mov     [rbp+57h+var_40], rax
0x1800250b6  mov     eax, [rdi]
0x1800250b8  mov     [rbp+57h+arg_18], eax
0x1800250bb  mov     rax, [rdi+80h]
0x1800250c2  mov     [rbp+57h+var_38], rax
0x1800250c6  mov     eax, [rdi+40h]
0x1800250c9  mov     [rbp+57h+var_70], eax
0x1800250cc  mov     rax, [rdi+38h]
0x1800250d0  mov     [rbp+57h+var_30], rax
0x1800250d4  mov     eax, [rdi+8]
0x1800250d7  mov     [rbp+57h+var_6C], eax
0x1800250da  mov     eax, 1000000h
0x1800250df  mov     [rbp+57h+var_28], rax
0x1800250e3  mov     [rbp+57h+var_20], rax
0x1800250e7  lea     rax, [rbp+57h+var_68]
0x1800250eb  mov     [rsp+110h+var_78], rax
0x1800250f3  lea     rax, [rbp+57h+var_60]
0x1800250f7  mov     [rsp+110h+var_80], rax
0x1800250ff  lea     rax, [rbp+57h+SRWLock]
0x180025103  mov     [rsp+110h+var_88], rax
0x18002510b  lea     rax, [rbp+57h+var_58]
0x18002510f  mov     [rsp+110h+var_90], rax
0x180025117  lea     rax, [rbp+57h+var_50]
0x18002511b  mov     [rsp+110h+var_98], rax
0x180025120  lea     rax, [rbp+57h+arg_8]
0x180025124  mov     [rsp+110h+var_A0], rax
0x180025129  lea     rax, [rbp+57h+var_48]
0x18002512d  mov     [rsp+110h+var_A8], rax
0x180025132  lea     rax, [rbp+57h+arg_10]
0x180025136  mov     [rsp+110h+var_B0], rax
0x18002513b  lea     rax, [rbp+57h+var_40]
0x18002513f  mov     [rsp+110h+var_B8], rax
0x180025144  lea     rax, [rbp+57h+arg_18]
0x180025148  mov     [rsp+110h+var_C0], rax
0x18002514d  lea     rax, [rbp+57h+var_38]
0x180025151  mov     [rsp+110h+var_C8], rax
0x180025156  lea     rax, [rbp+57h+var_70]
0x18002515a  mov     [rsp+110h+var_D0], rax
0x18002515f  lea     rax, [rbp+57h+var_30]
0x180025163  mov     [rsp+110h+var_D8], rax
0x180025168  lea     rax, [rbp+57h+var_6C]
0x18002516c  mov     [rsp+110h+var_E0], rax
0x180025171  lea     rax, [rbp+57h+var_28]
0x180025175  mov     [rsp+110h+var_E8], rax
0x18002517a  lea     rax, [rbp+57h+var_20]
0x18002517e  mov     [rsp+110h+var_F0], rax
0x180025183  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180025188  jmp     loc_180025232
0x18002518d  lea     rdx, [rbp+57h+SRWLock]
0x180025191  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025196  mov     rax, [rbx+110h]
0x18002519d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800251a1  mov     dword ptr [rax], 2
0x1800251a7  test    rcx, rcx
0x1800251aa  jz      short loc_1800251B2
0x1800251ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800251b2  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x1800251b7  mov     rdi, [rax+8]
0x1800251bb  mov     eax, [rdi]
0x1800251bd  cmp     eax, 5
0x1800251c0  jbe     short loc_180025232
0x1800251c2  mov     rdx, [rdi+18h]
0x1800251c6  mov     rcx, 400000000000h
0x1800251d0  mov     rax, [rdi+10h]
0x1800251d4  test    rcx, rax
0x1800251d7  jz      short loc_180025232
0x1800251d9  mov     rax, rdx
0x1800251dc  and     rax, rcx
0x1800251df  cmp     rax, rdx
0x1800251e2  jnz     short loc_180025232
0x1800251e4  call    cs:__imp_GetCurrentThreadId
0x1800251ea  mov     r8, [rbx+110h]
0x1800251f1  lea     rdx, unk_180092B65
0x1800251f8  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800251fb  mov     rcx, rdi
0x1800251fe  mov     eax, [r8+48h]
0x180025202  add     r8, 8
0x180025206  mov     [rbp+57h+arg_8], eax
0x180025209  mov     eax, 1000000h
0x18002520e  mov     [rbp+57h+arg_10], rax
0x180025212  lea     rax, [rbp+57h+SRWLock]
0x180025216  mov     [rsp+110h+var_E0], rax
0x18002521b  lea     rax, [rbp+57h+arg_8]
0x18002521f  mov     [rsp+110h+var_E8], rax
0x180025224  lea     rax, [rbp+57h+arg_10]
0x180025228  mov     [rsp+110h+var_F0], rax
0x18002522d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025232  mov     rcx, rbx
0x180025235  add     rsp, 100h
0x18002523c  pop     rdi
0x18002523d  pop     rbx
0x18002523e  pop     rbp
0x18002523f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
