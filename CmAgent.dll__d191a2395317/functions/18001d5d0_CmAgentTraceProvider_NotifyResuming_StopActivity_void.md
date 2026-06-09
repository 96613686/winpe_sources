# CmAgentTraceProvider::NotifyResuming::StopActivity(void)

- ea: `0x18001d5d0`
- end: `0x18001d874`
- name: `?StopActivity@NotifyResuming@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::NotifyResuming *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001d5d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d800`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d62a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d7c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d62a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d7c2`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::NotifyResuming::StopActivity(CmAgentTraceProvider::NotifyResuming *this)
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
        (__int64)&word_1800447A6,
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
        (__int64)byte_1800436B1,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::NotifyResuming *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001d5d0  push    rbp
0x18001d5d2  push    rbx
0x18001d5d3  push    rdi
0x18001d5d4  lea     rbp, [rsp-47h]
0x18001d5d9  sub     rsp, 100h
0x18001d5e0  mov     rbx, rcx
0x18001d5e3  mov     rdi, [rcx+110h]
0x18001d5ea  mov     eax, [rdi+48h]
0x18001d5ed  test    eax, eax
0x18001d5ef  jns     loc_18001D7A3
0x18001d5f5  add     rdi, 50h ; 'P'
0x18001d5f9  cmp     eax, [rdi+8]
0x18001d5fc  jnz     loc_18001D7A3
0x18001d602  test    rdi, rdi
0x18001d605  jz      loc_18001D7A3
0x18001d60b  lea     rdx, [rbp+57h+SRWLock]
0x18001d60f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001d614  mov     rax, [rbx+110h]
0x18001d61b  mov     dword ptr [rax], 2
0x18001d621  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001d625  test    rcx, rcx
0x18001d628  jz      short loc_18001D636
0x18001d62a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d631  nop     dword ptr [rax+rax+00h]
0x18001d636  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001d63b  mov     r9, [rax+8]
0x18001d63f  mov     eax, [r9]
0x18001d642  cmp     eax, 5
0x18001d645  jbe     loc_18001D855
0x18001d64b  mov     rdx, [r9+18h]
0x18001d64f  mov     rax, [r9+10h]
0x18001d653  mov     rcx, 400000000000h
0x18001d65d  test    rcx, rax
0x18001d660  jz      loc_18001D855
0x18001d666  mov     rax, rdx
0x18001d669  and     rax, rcx
0x18001d66c  cmp     rax, rdx
0x18001d66f  jnz     loc_18001D855
0x18001d675  mov     rax, [rdi+78h]
0x18001d679  mov     [rbp+57h+var_68], rax
0x18001d67d  mov     rax, [rdi+70h]
0x18001d681  mov     [rbp+57h+var_60], rax
0x18001d685  mov     eax, [rdi+68h]
0x18001d688  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001d68b  mov     rax, [rdi+60h]
0x18001d68f  mov     [rbp+57h+var_58], rax
0x18001d693  mov     rax, [rdi+58h]
0x18001d697  mov     [rbp+57h+var_50], rax
0x18001d69b  mov     eax, [rdi+50h]
0x18001d69e  mov     [rbp+57h+arg_8], eax
0x18001d6a1  mov     rax, [rdi+48h]
0x18001d6a5  mov     [rbp+57h+var_48], rax
0x18001d6a9  mov     eax, [rdi+20h]
0x18001d6ac  mov     dword ptr [rbp+57h+arg_10], eax
0x18001d6af  mov     rax, [rdi+18h]
0x18001d6b3  mov     [rbp+57h+var_40], rax
0x18001d6b7  mov     eax, [rdi]
0x18001d6b9  mov     [rbp+57h+arg_18], eax
0x18001d6bc  mov     rax, [rdi+80h]
0x18001d6c3  mov     [rbp+57h+var_38], rax
0x18001d6c7  mov     eax, [rdi+40h]
0x18001d6ca  mov     [rbp+57h+var_70], eax
0x18001d6cd  mov     rax, [rdi+38h]
0x18001d6d1  mov     [rbp+57h+var_30], rax
0x18001d6d5  mov     eax, [rdi+8]
0x18001d6d8  mov     [rbp+57h+var_6C], eax
0x18001d6db  mov     eax, 1000000h
0x18001d6e0  mov     [rbp+57h+var_28], rax
0x18001d6e4  mov     [rbp+57h+var_20], rax
0x18001d6e8  mov     r8, [rbx+110h]
0x18001d6ef  add     r8, 8
0x18001d6f3  lea     rax, [rbp+57h+var_68]
0x18001d6f7  mov     [rsp+110h+var_78], rax
0x18001d6ff  lea     rax, [rbp+57h+var_60]
0x18001d703  mov     [rsp+110h+var_80], rax
0x18001d70b  lea     rax, [rbp+57h+SRWLock]
0x18001d70f  mov     [rsp+110h+var_88], rax
0x18001d717  lea     rax, [rbp+57h+var_58]
0x18001d71b  mov     [rsp+110h+var_90], rax
0x18001d723  lea     rax, [rbp+57h+var_50]
0x18001d727  mov     [rsp+110h+var_98], rax
0x18001d72c  lea     rax, [rbp+57h+arg_8]
0x18001d730  mov     [rsp+110h+var_A0], rax
0x18001d735  lea     rax, [rbp+57h+var_48]
0x18001d739  mov     [rsp+110h+var_A8], rax
0x18001d73e  lea     rax, [rbp+57h+arg_10]
0x18001d742  mov     [rsp+110h+var_B0], rax
0x18001d747  lea     rax, [rbp+57h+var_40]
0x18001d74b  mov     [rsp+110h+var_B8], rax
0x18001d750  lea     rax, [rbp+57h+arg_18]
0x18001d754  mov     [rsp+110h+var_C0], rax
0x18001d759  lea     rax, [rbp+57h+var_38]
0x18001d75d  mov     [rsp+110h+var_C8], rax
0x18001d762  lea     rax, [rbp+57h+var_70]
0x18001d766  mov     [rsp+110h+var_D0], rax
0x18001d76b  lea     rax, [rbp+57h+var_30]
0x18001d76f  mov     [rsp+110h+var_D8], rax
0x18001d774  lea     rax, [rbp+57h+var_6C]
0x18001d778  mov     [rsp+110h+var_E0], rax
0x18001d77d  lea     rax, [rbp+57h+var_28]
0x18001d781  mov     [rsp+110h+var_E8], rax
0x18001d786  lea     rax, [rbp+57h+var_20]
0x18001d78a  mov     [rsp+110h+var_F0], rax
0x18001d78f  lea     rdx, word_1800447A6
0x18001d796  mov     rcx, r9
0x18001d799  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001d79e  jmp     loc_18001D855
0x18001d7a3  lea     rdx, [rbp+57h+SRWLock]
0x18001d7a7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001d7ac  mov     rax, [rbx+110h]
0x18001d7b3  mov     dword ptr [rax], 2
0x18001d7b9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001d7bd  test    rcx, rcx
0x18001d7c0  jz      short loc_18001D7CE
0x18001d7c2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d7c9  nop     dword ptr [rax+rax+00h]
0x18001d7ce  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001d7d3  mov     rdi, [rax+8]
0x18001d7d7  mov     eax, [rdi]
0x18001d7d9  cmp     eax, 5
0x18001d7dc  jbe     short loc_18001D855
0x18001d7de  mov     rdx, [rdi+18h]
0x18001d7e2  mov     rax, [rdi+10h]
0x18001d7e6  mov     rcx, 400000000000h
0x18001d7f0  test    rcx, rax
0x18001d7f3  jz      short loc_18001D855
0x18001d7f5  mov     rax, rdx
0x18001d7f8  and     rax, rcx
0x18001d7fb  cmp     rax, rdx
0x18001d7fe  jnz     short loc_18001D855
0x18001d800  call    cs:__imp_GetCurrentThreadId
0x18001d807  nop     dword ptr [rax+rax+00h]
0x18001d80c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001d80f  mov     r8, [rbx+110h]
0x18001d816  mov     eax, [r8+48h]
0x18001d81a  mov     [rbp+57h+arg_8], eax
0x18001d81d  mov     eax, 1000000h
0x18001d822  mov     [rbp+57h+arg_10], rax
0x18001d826  add     r8, 8
0x18001d82a  lea     rax, [rbp+57h+SRWLock]
0x18001d82e  mov     [rsp+110h+var_E0], rax
0x18001d833  lea     rax, [rbp+57h+arg_8]
0x18001d837  mov     [rsp+110h+var_E8], rax
0x18001d83c  lea     rax, [rbp+57h+arg_10]
0x18001d840  mov     [rsp+110h+var_F0], rax
0x18001d845  lea     rdx, byte_1800436B1
0x18001d84c  mov     rcx, rdi
0x18001d84f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d854  nop
0x18001d855  lea     rcx, [rbx+120h]; this
0x18001d85c  cmp     dword ptr [rcx+18h], 0
0x18001d860  jz      short loc_18001D868
0x18001d862  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001d867  nop
0x18001d868  add     rsp, 100h
0x18001d86f  pop     rdi
0x18001d870  pop     rbx
0x18001d871  pop     rbp
0x18001d872  retn
```
