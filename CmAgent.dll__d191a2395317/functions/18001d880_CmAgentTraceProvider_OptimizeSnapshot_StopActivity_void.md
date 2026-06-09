# CmAgentTraceProvider::OptimizeSnapshot::StopActivity(void)

- ea: `0x18001d880`
- end: `0x18001db24`
- name: `?StopActivity@OptimizeSnapshot@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::OptimizeSnapshot *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001d880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dab0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d8da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d8da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001da72`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::OptimizeSnapshot::StopActivity(CmAgentTraceProvider::OptimizeSnapshot *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+A0h] [rbp-19h] BYREF
  int v10; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v11; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v13; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v17; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v11 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)&unk_1800433B0,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v10,
        &v18,
        (__int64)&v9,
        &v17,
        (__int64)&v24,
        &v16,
        (__int64)&v23,
        &v15,
        (__int64)&v22,
        &v14,
        &v13,
        (__int64)&SRWLock,
        &v12,
        &v11);
    }
  }
  else
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&word_180043DAE,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::OptimizeSnapshot *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001d880  push    rbp
0x18001d882  push    rbx
0x18001d883  push    rdi
0x18001d884  lea     rbp, [rsp-47h]
0x18001d889  sub     rsp, 100h
0x18001d890  mov     rbx, rcx
0x18001d893  mov     rdi, [rcx+110h]
0x18001d89a  mov     eax, [rdi+48h]
0x18001d89d  test    eax, eax
0x18001d89f  jns     loc_18001DA53
0x18001d8a5  add     rdi, 50h ; 'P'
0x18001d8a9  cmp     eax, [rdi+8]
0x18001d8ac  jnz     loc_18001DA53
0x18001d8b2  test    rdi, rdi
0x18001d8b5  jz      loc_18001DA53
0x18001d8bb  lea     rdx, [rbp+57h+SRWLock]
0x18001d8bf  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001d8c4  mov     rax, [rbx+110h]
0x18001d8cb  mov     dword ptr [rax], 2
0x18001d8d1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001d8d5  test    rcx, rcx
0x18001d8d8  jz      short loc_18001D8E6
0x18001d8da  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d8e1  nop     dword ptr [rax+rax+00h]
0x18001d8e6  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001d8eb  mov     r9, [rax+8]
0x18001d8ef  mov     eax, [r9]
0x18001d8f2  cmp     eax, 5
0x18001d8f5  jbe     loc_18001DB05
0x18001d8fb  mov     rdx, [r9+18h]
0x18001d8ff  mov     rax, [r9+10h]
0x18001d903  mov     rcx, 400000000000h
0x18001d90d  test    rcx, rax
0x18001d910  jz      loc_18001DB05
0x18001d916  mov     rax, rdx
0x18001d919  and     rax, rcx
0x18001d91c  cmp     rax, rdx
0x18001d91f  jnz     loc_18001DB05
0x18001d925  mov     rax, [rdi+78h]
0x18001d929  mov     [rbp+57h+var_68], rax
0x18001d92d  mov     rax, [rdi+70h]
0x18001d931  mov     [rbp+57h+var_60], rax
0x18001d935  mov     eax, [rdi+68h]
0x18001d938  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001d93b  mov     rax, [rdi+60h]
0x18001d93f  mov     [rbp+57h+var_58], rax
0x18001d943  mov     rax, [rdi+58h]
0x18001d947  mov     [rbp+57h+var_50], rax
0x18001d94b  mov     eax, [rdi+50h]
0x18001d94e  mov     [rbp+57h+arg_8], eax
0x18001d951  mov     rax, [rdi+48h]
0x18001d955  mov     [rbp+57h+var_48], rax
0x18001d959  mov     eax, [rdi+20h]
0x18001d95c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001d95f  mov     rax, [rdi+18h]
0x18001d963  mov     [rbp+57h+var_40], rax
0x18001d967  mov     eax, [rdi]
0x18001d969  mov     [rbp+57h+arg_18], eax
0x18001d96c  mov     rax, [rdi+80h]
0x18001d973  mov     [rbp+57h+var_38], rax
0x18001d977  mov     eax, [rdi+40h]
0x18001d97a  mov     [rbp+57h+var_70], eax
0x18001d97d  mov     rax, [rdi+38h]
0x18001d981  mov     [rbp+57h+var_30], rax
0x18001d985  mov     eax, [rdi+8]
0x18001d988  mov     [rbp+57h+var_6C], eax
0x18001d98b  mov     eax, 1000000h
0x18001d990  mov     [rbp+57h+var_28], rax
0x18001d994  mov     [rbp+57h+var_20], rax
0x18001d998  mov     r8, [rbx+110h]
0x18001d99f  add     r8, 8
0x18001d9a3  lea     rax, [rbp+57h+var_68]
0x18001d9a7  mov     [rsp+110h+var_78], rax
0x18001d9af  lea     rax, [rbp+57h+var_60]
0x18001d9b3  mov     [rsp+110h+var_80], rax
0x18001d9bb  lea     rax, [rbp+57h+SRWLock]
0x18001d9bf  mov     [rsp+110h+var_88], rax
0x18001d9c7  lea     rax, [rbp+57h+var_58]
0x18001d9cb  mov     [rsp+110h+var_90], rax
0x18001d9d3  lea     rax, [rbp+57h+var_50]
0x18001d9d7  mov     [rsp+110h+var_98], rax
0x18001d9dc  lea     rax, [rbp+57h+arg_8]
0x18001d9e0  mov     [rsp+110h+var_A0], rax
0x18001d9e5  lea     rax, [rbp+57h+var_48]
0x18001d9e9  mov     [rsp+110h+var_A8], rax
0x18001d9ee  lea     rax, [rbp+57h+arg_10]
0x18001d9f2  mov     [rsp+110h+var_B0], rax
0x18001d9f7  lea     rax, [rbp+57h+var_40]
0x18001d9fb  mov     [rsp+110h+var_B8], rax
0x18001da00  lea     rax, [rbp+57h+arg_18]
0x18001da04  mov     [rsp+110h+var_C0], rax
0x18001da09  lea     rax, [rbp+57h+var_38]
0x18001da0d  mov     [rsp+110h+var_C8], rax
0x18001da12  lea     rax, [rbp+57h+var_70]
0x18001da16  mov     [rsp+110h+var_D0], rax
0x18001da1b  lea     rax, [rbp+57h+var_30]
0x18001da1f  mov     [rsp+110h+var_D8], rax
0x18001da24  lea     rax, [rbp+57h+var_6C]
0x18001da28  mov     [rsp+110h+var_E0], rax
0x18001da2d  lea     rax, [rbp+57h+var_28]
0x18001da31  mov     [rsp+110h+var_E8], rax
0x18001da36  lea     rax, [rbp+57h+var_20]
0x18001da3a  mov     [rsp+110h+var_F0], rax
0x18001da3f  lea     rdx, unk_1800433B0
0x18001da46  mov     rcx, r9
0x18001da49  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001da4e  jmp     loc_18001DB05
0x18001da53  lea     rdx, [rbp+57h+SRWLock]
0x18001da57  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001da5c  mov     rax, [rbx+110h]
0x18001da63  mov     dword ptr [rax], 2
0x18001da69  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001da6d  test    rcx, rcx
0x18001da70  jz      short loc_18001DA7E
0x18001da72  call    cs:__imp_ReleaseSRWLockExclusive
0x18001da79  nop     dword ptr [rax+rax+00h]
0x18001da7e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001da83  mov     rdi, [rax+8]
0x18001da87  mov     eax, [rdi]
0x18001da89  cmp     eax, 5
0x18001da8c  jbe     short loc_18001DB05
0x18001da8e  mov     rdx, [rdi+18h]
0x18001da92  mov     rax, [rdi+10h]
0x18001da96  mov     rcx, 400000000000h
0x18001daa0  test    rcx, rax
0x18001daa3  jz      short loc_18001DB05
0x18001daa5  mov     rax, rdx
0x18001daa8  and     rax, rcx
0x18001daab  cmp     rax, rdx
0x18001daae  jnz     short loc_18001DB05
0x18001dab0  call    cs:__imp_GetCurrentThreadId
0x18001dab7  nop     dword ptr [rax+rax+00h]
0x18001dabc  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001dabf  mov     r8, [rbx+110h]
0x18001dac6  mov     eax, [r8+48h]
0x18001daca  mov     [rbp+57h+arg_8], eax
0x18001dacd  mov     eax, 1000000h
0x18001dad2  mov     [rbp+57h+arg_10], rax
0x18001dad6  add     r8, 8
0x18001dada  lea     rax, [rbp+57h+SRWLock]
0x18001dade  mov     [rsp+110h+var_E0], rax
0x18001dae3  lea     rax, [rbp+57h+arg_8]
0x18001dae7  mov     [rsp+110h+var_E8], rax
0x18001daec  lea     rax, [rbp+57h+arg_10]
0x18001daf0  mov     [rsp+110h+var_F0], rax
0x18001daf5  lea     rdx, word_180043DAE
0x18001dafc  mov     rcx, rdi
0x18001daff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001db04  nop
0x18001db05  lea     rcx, [rbx+120h]; this
0x18001db0c  cmp     dword ptr [rcx+18h], 0
0x18001db10  jz      short loc_18001DB18
0x18001db12  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001db17  nop
0x18001db18  add     rsp, 100h
0x18001db1f  pop     rdi
0x18001db20  pop     rbx
0x18001db21  pop     rbp
0x18001db22  retn
```
