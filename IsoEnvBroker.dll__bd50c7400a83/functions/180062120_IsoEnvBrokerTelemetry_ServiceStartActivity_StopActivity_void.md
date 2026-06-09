# IsoEnvBrokerTelemetry::ServiceStartActivity::StopActivity(void)

- ea: `0x180062120`
- end: `0x1800623a4`
- name: `?StopActivity@ServiceStartActivity@IsoEnvBrokerTelemetry@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::ServiceStartActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001098`
- `0x18000176c`
- `0x180011d64`
- `0x18006019c`
- `0x18006075c`
- `0x180062120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006217a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006230c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006217a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006230c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062344`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::ServiceStartActivity::StopActivity(
        IsoEnvBrokerTelemetry::ServiceStartActivity *this)
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
  const WCHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v18; // [rsp+C0h] [rbp+7h] BYREF
  const wchar_t *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
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
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v16 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v6,
        (__int64)&byte_1800AC0F7,
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
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x200000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)word_1800AC0A2,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180062120  push    rbp
0x180062122  push    rbx
0x180062123  push    rdi
0x180062124  lea     rbp, [rsp-47h]
0x180062129  sub     rsp, 100h
0x180062130  mov     rdi, [rcx+110h]
0x180062137  mov     rbx, rcx
0x18006213a  mov     eax, [rdi+48h]
0x18006213d  test    eax, eax
0x18006213f  jns     loc_1800622ED
0x180062145  add     rdi, 50h ; 'P'
0x180062149  cmp     eax, [rdi+8]
0x18006214c  jnz     loc_1800622ED
0x180062152  test    rdi, rdi
0x180062155  jz      loc_1800622ED
0x18006215b  lea     rdx, [rbp+57h+SRWLock]
0x18006215f  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180062164  mov     rax, [rbx+110h]
0x18006216b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006216f  mov     dword ptr [rax], 2
0x180062175  test    rcx, rcx
0x180062178  jz      short loc_180062180
0x18006217a  call    cs:__imp_ReleaseSRWLockExclusive
0x180062180  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180062185  mov     r9, [rax+8]
0x180062189  mov     eax, [r9]
0x18006218c  cmp     eax, 5
0x18006218f  jbe     loc_180062392
0x180062195  mov     rdx, [r9+18h]
0x180062199  mov     rcx, 200000000000h
0x1800621a3  mov     rax, [r9+10h]
0x1800621a7  test    rcx, rax
0x1800621aa  jz      loc_180062392
0x1800621b0  mov     rax, rdx
0x1800621b3  and     rax, rcx
0x1800621b6  cmp     rax, rdx
0x1800621b9  jnz     loc_180062392
0x1800621bf  mov     rax, [rdi+78h]
0x1800621c3  lea     rdx, byte_1800AC0F7
0x1800621ca  mov     r8, [rbx+110h]
0x1800621d1  mov     rcx, r9
0x1800621d4  mov     [rbp+57h+var_68], rax
0x1800621d8  add     r8, 8
0x1800621dc  mov     rax, [rdi+70h]
0x1800621e0  mov     [rbp+57h+var_60], rax
0x1800621e4  mov     eax, [rdi+68h]
0x1800621e7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800621ea  mov     rax, [rdi+60h]
0x1800621ee  mov     [rbp+57h+var_58], rax
0x1800621f2  mov     rax, [rdi+58h]
0x1800621f6  mov     [rbp+57h+var_50], rax
0x1800621fa  mov     eax, [rdi+50h]
0x1800621fd  mov     [rbp+57h+arg_8], eax
0x180062200  mov     rax, [rdi+48h]
0x180062204  mov     [rbp+57h+var_48], rax
0x180062208  mov     eax, [rdi+20h]
0x18006220b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006220e  mov     rax, [rdi+18h]
0x180062212  mov     [rbp+57h+var_40], rax
0x180062216  mov     eax, [rdi]
0x180062218  mov     [rbp+57h+arg_18], eax
0x18006221b  mov     rax, [rdi+80h]
0x180062222  mov     [rbp+57h+var_38], rax
0x180062226  mov     eax, [rdi+40h]
0x180062229  mov     [rbp+57h+var_70], eax
0x18006222c  mov     rax, [rdi+38h]
0x180062230  mov     [rbp+57h+var_30], rax
0x180062234  mov     eax, [rdi+8]
0x180062237  mov     [rbp+57h+var_6C], eax
0x18006223a  mov     eax, 1000000h
0x18006223f  mov     [rbp+57h+var_28], rax
0x180062243  mov     [rbp+57h+var_20], rax
0x180062247  lea     rax, [rbp+57h+var_68]
0x18006224b  mov     [rsp+110h+var_78], rax
0x180062253  lea     rax, [rbp+57h+var_60]
0x180062257  mov     [rsp+110h+var_80], rax
0x18006225f  lea     rax, [rbp+57h+SRWLock]
0x180062263  mov     [rsp+110h+var_88], rax
0x18006226b  lea     rax, [rbp+57h+var_58]
0x18006226f  mov     [rsp+110h+var_90], rax
0x180062277  lea     rax, [rbp+57h+var_50]
0x18006227b  mov     [rsp+110h+var_98], rax
0x180062280  lea     rax, [rbp+57h+arg_8]
0x180062284  mov     [rsp+110h+var_A0], rax
0x180062289  lea     rax, [rbp+57h+var_48]
0x18006228d  mov     [rsp+110h+var_A8], rax
0x180062292  lea     rax, [rbp+57h+arg_10]
0x180062296  mov     [rsp+110h+var_B0], rax
0x18006229b  lea     rax, [rbp+57h+var_40]
0x18006229f  mov     [rsp+110h+var_B8], rax
0x1800622a4  lea     rax, [rbp+57h+arg_18]
0x1800622a8  mov     [rsp+110h+var_C0], rax
0x1800622ad  lea     rax, [rbp+57h+var_38]
0x1800622b1  mov     [rsp+110h+var_C8], rax
0x1800622b6  lea     rax, [rbp+57h+var_70]
0x1800622ba  mov     [rsp+110h+var_D0], rax
0x1800622bf  lea     rax, [rbp+57h+var_30]
0x1800622c3  mov     [rsp+110h+var_D8], rax
0x1800622c8  lea     rax, [rbp+57h+var_6C]
0x1800622cc  mov     [rsp+110h+var_E0], rax
0x1800622d1  lea     rax, [rbp+57h+var_28]
0x1800622d5  mov     [rsp+110h+var_E8], rax
0x1800622da  lea     rax, [rbp+57h+var_20]
0x1800622de  mov     [rsp+110h+var_F0], rax
0x1800622e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800622e8  jmp     loc_180062392
0x1800622ed  lea     rdx, [rbp+57h+SRWLock]
0x1800622f1  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800622f6  mov     rax, [rbx+110h]
0x1800622fd  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180062301  mov     dword ptr [rax], 2
0x180062307  test    rcx, rcx
0x18006230a  jz      short loc_180062312
0x18006230c  call    cs:__imp_ReleaseSRWLockExclusive
0x180062312  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180062317  mov     rdi, [rax+8]
0x18006231b  mov     eax, [rdi]
0x18006231d  cmp     eax, 5
0x180062320  jbe     short loc_180062392
0x180062322  mov     rdx, [rdi+18h]
0x180062326  mov     rcx, 200000000000h
0x180062330  mov     rax, [rdi+10h]
0x180062334  test    rcx, rax
0x180062337  jz      short loc_180062392
0x180062339  mov     rax, rdx
0x18006233c  and     rax, rcx
0x18006233f  cmp     rax, rdx
0x180062342  jnz     short loc_180062392
0x180062344  call    cs:__imp_GetCurrentThreadId
0x18006234a  mov     r8, [rbx+110h]
0x180062351  lea     rdx, word_1800AC0A2
0x180062358  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006235b  mov     rcx, rdi
0x18006235e  mov     eax, [r8+48h]
0x180062362  add     r8, 8
0x180062366  mov     [rbp+57h+arg_8], eax
0x180062369  mov     eax, 1000000h
0x18006236e  mov     [rbp+57h+arg_10], rax
0x180062372  lea     rax, [rbp+57h+SRWLock]
0x180062376  mov     [rsp+110h+var_E0], rax
0x18006237b  lea     rax, [rbp+57h+arg_8]
0x18006237f  mov     [rsp+110h+var_E8], rax
0x180062384  lea     rax, [rbp+57h+arg_10]
0x180062388  mov     [rsp+110h+var_F0], rax
0x18006238d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062392  mov     rcx, rbx
0x180062395  add     rsp, 100h
0x18006239c  pop     rdi
0x18006239d  pop     rbx
0x18006239e  pop     rbp
0x18006239f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
