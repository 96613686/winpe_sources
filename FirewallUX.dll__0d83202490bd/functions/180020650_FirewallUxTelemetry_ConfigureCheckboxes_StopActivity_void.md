# FirewallUxTelemetry::ConfigureCheckboxes::StopActivity(void)

- ea: `0x180020650`
- end: `0x1800208bf`
- name: `?StopActivity@ConfigureCheckboxes@FirewallUxTelemetry@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(FirewallUxTelemetry::ConfigureCheckboxes *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x1800080a4`
- `0x18000812c`
- `0x180008820`
- `0x180020650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800206aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002084b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800206aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002084b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020860`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::ConfigureCheckboxes::StopActivity(FirewallUxTelemetry::ConfigureCheckboxes *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const wchar_t *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const wchar_t *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v7;
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)&unk_180033929,
        v8 + 8,
        (__int64)v6,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&unk_180033A77,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180020650  push    rbp
0x180020652  push    rbx
0x180020653  push    rdi
0x180020654  lea     rbp, [rsp+10h]
0x180020659  sub     rsp, 130h
0x180020660  mov     rdi, [rcx+110h]
0x180020667  mov     rbx, rcx
0x18002066a  mov     eax, [rdi+48h]
0x18002066d  test    eax, eax
0x18002066f  jns     loc_18002082C
0x180020675  add     rdi, 50h ; 'P'
0x180020679  cmp     eax, [rdi+8]
0x18002067c  jnz     loc_18002082C
0x180020682  test    rdi, rdi
0x180020685  jz      loc_18002082C
0x18002068b  lea     rdx, [rbp+SRWLock]
0x18002068f  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020694  mov     rax, [rbx+110h]
0x18002069b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002069f  mov     dword ptr [rax], 2
0x1800206a5  test    rcx, rcx
0x1800206a8  jz      short loc_1800206B0
0x1800206aa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800206b0  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800206b5  mov     r9, rax
0x1800206b8  mov     ecx, [rax]
0x1800206ba  cmp     ecx, 5
0x1800206bd  jbe     loc_1800208AD
0x1800206c3  mov     rax, [rdi+70h]
0x1800206c7  lea     rdx, unk_180033929
0x1800206ce  mov     rcx, [rdi+30h]
0x1800206d2  mov     [rbp+var_60], rax
0x1800206d6  mov     eax, [rdi+68h]
0x1800206d9  mov     r8, [rbx+110h]
0x1800206e0  mov     dword ptr [rbp+arg_10], eax
0x1800206e3  add     r8, 8
0x1800206e7  mov     rax, [rdi+60h]
0x1800206eb  mov     [rbp+var_58], rax
0x1800206ef  mov     rax, [rdi+58h]
0x1800206f3  mov     [rbp+var_50], rax
0x1800206f7  mov     eax, [rdi+50h]
0x1800206fa  mov     [rbp+arg_18], eax
0x1800206fd  mov     rax, [rdi+48h]
0x180020701  mov     [rbp+var_48], rax
0x180020705  mov     eax, [rdi+20h]
0x180020708  mov     [rbp+var_80], eax
0x18002070b  mov     rax, [rdi+18h]
0x18002070f  mov     [rbp+var_40], rax
0x180020713  mov     eax, [rdi]
0x180020715  mov     [rbp+var_7C], eax
0x180020718  mov     rax, [rdi+80h]
0x18002071f  mov     [rbp+var_38], rax
0x180020723  mov     eax, [rdi+40h]
0x180020726  mov     [rbp+var_78], eax
0x180020729  mov     rax, [rdi+38h]
0x18002072d  mov     [rbp+var_30], rax
0x180020731  mov     eax, [rdi+8]
0x180020734  mov     [rbp+var_74], eax
0x180020737  lea     rax, [rbp+var_70]
0x18002073b  mov     [rsp+140h+var_90], rax
0x180020743  lea     rax, [rbp+SRWLock]
0x180020747  mov     [rsp+140h+var_98], rax
0x18002074f  lea     rax, [rbp+arg_8]
0x180020753  mov     [rsp+140h+var_A0], rax
0x18002075b  lea     rax, [rbp+var_68]
0x18002075f  mov     [rsp+140h+var_A8], rax
0x180020767  lea     rax, [rbp+var_60]
0x18002076b  mov     [rsp+140h+var_B0], rax
0x180020773  lea     rax, [rbp+arg_10]
0x180020777  mov     [rsp+140h+var_B8], rax
0x18002077f  lea     rax, [rbp+var_58]
0x180020783  mov     [rsp+140h+var_C0], rax
0x18002078b  lea     rax, [rbp+var_50]
0x18002078f  mov     [rsp+140h+var_C8], rax
0x180020794  lea     rax, [rbp+arg_18]
0x180020798  mov     [rsp+140h+var_D0], rax
0x18002079d  lea     rax, [rbp+var_48]
0x1800207a1  mov     [rsp+140h+var_D8], rax
0x1800207a6  lea     rax, [rbp+var_80]
0x1800207aa  mov     [rsp+140h+var_E0], rax
0x1800207af  lea     rax, [rbp+var_40]
0x1800207b3  mov     [rsp+140h+var_E8], rax
0x1800207b8  lea     rax, [rbp+var_7C]
0x1800207bc  mov     [rsp+140h+var_F0], rax
0x1800207c1  lea     rax, [rbp+var_38]
0x1800207c5  mov     [rsp+140h+var_F8], rax
0x1800207ca  lea     rax, [rbp+var_78]
0x1800207ce  mov     [rsp+140h+var_100], rax
0x1800207d3  lea     rax, [rbp+var_30]
0x1800207d7  mov     [rsp+140h+var_108], rax
0x1800207dc  lea     rax, [rbp+var_74]
0x1800207e0  mov     [rbp+var_70], rcx
0x1800207e4  mov     ecx, [rdi+44h]
0x1800207e7  mov     [rsp+140h+var_110], rax
0x1800207ec  lea     rax, [rbp+var_28]
0x1800207f0  mov     dword ptr [rbp+SRWLock], ecx
0x1800207f3  mov     ecx, [rdi+10h]
0x1800207f6  mov     [rbp+arg_8], ecx
0x1800207f9  mov     rcx, [rdi+78h]
0x1800207fd  mov     [rsp+140h+var_118], rax
0x180020802  lea     rax, [rbp+var_20]
0x180020806  mov     [rbp+var_68], rcx
0x18002080a  mov     rcx, r9
0x18002080d  mov     [rsp+140h+var_120], rax
0x180020812  mov     [rbp+var_28], 1000000h
0x18002081a  mov     [rbp+var_20], 0
0x180020822  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020827  jmp     loc_1800208AD
0x18002082c  lea     rdx, [rbp+SRWLock]
0x180020830  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020835  mov     rax, [rbx+110h]
0x18002083c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180020840  mov     dword ptr [rax], 2
0x180020846  test    rcx, rcx
0x180020849  jz      short loc_180020851
0x18002084b  call    cs:__imp_ReleaseSRWLockExclusive
0x180020851  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180020856  mov     rdi, rax
0x180020859  mov     ecx, [rax]
0x18002085b  cmp     ecx, 5
0x18002085e  jbe     short loc_1800208AD
0x180020860  call    cs:__imp_GetCurrentThreadId
0x180020866  mov     r8, [rbx+110h]
0x18002086d  lea     rdx, unk_180033A77
0x180020874  mov     dword ptr [rbp+SRWLock], eax
0x180020877  lea     rax, [rbp+SRWLock]
0x18002087b  mov     [rsp+140h+var_110], rax
0x180020880  lea     rax, [rbp+arg_8]
0x180020884  mov     [rsp+140h+var_118], rax
0x180020889  lea     rax, [rbp+arg_10]
0x18002088d  mov     ecx, [r8+48h]
0x180020891  add     r8, 8
0x180020895  mov     [rbp+arg_8], ecx
0x180020898  mov     rcx, rdi
0x18002089b  mov     [rsp+140h+var_120], rax
0x1800208a0  mov     [rbp+arg_10], 0
0x1800208a8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800208ad  mov     rcx, rbx
0x1800208b0  add     rsp, 130h
0x1800208b7  pop     rdi
0x1800208b8  pop     rbx
0x1800208b9  pop     rbp
0x1800208ba  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
