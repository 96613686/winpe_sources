# CmAgentTraceProvider::ServiceStop::StopActivity(void)

- ea: `0x180008dd0`
- end: `0x180009074`
- name: `?StopActivity@ServiceStop@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::ServiceStop *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x180008dd0`
- `0x18000907c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009000`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008fc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008fc2`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::ServiceStop::StopActivity(CmAgentTraceProvider::ServiceStop *this)
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
        (__int64)word_180042D9A,
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
        (__int64)&byte_180043187,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::ServiceStop *)((char *)this + 288));
}

```

## disassembly

```asm
0x180008dd0  push    rbp
0x180008dd2  push    rbx
0x180008dd3  push    rdi
0x180008dd4  lea     rbp, [rsp-47h]
0x180008dd9  sub     rsp, 100h
0x180008de0  mov     rbx, rcx
0x180008de3  mov     rdi, [rcx+110h]
0x180008dea  mov     eax, [rdi+48h]
0x180008ded  test    eax, eax
0x180008def  jns     loc_180008FA3
0x180008df5  add     rdi, 50h ; 'P'
0x180008df9  cmp     eax, [rdi+8]
0x180008dfc  jnz     loc_180008FA3
0x180008e02  test    rdi, rdi
0x180008e05  jz      loc_180008FA3
0x180008e0b  lea     rdx, [rbp+57h+SRWLock]
0x180008e0f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008e14  mov     rax, [rbx+110h]
0x180008e1b  mov     dword ptr [rax], 2
0x180008e21  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180008e25  test    rcx, rcx
0x180008e28  jz      short loc_180008E36
0x180008e2a  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e31  nop     dword ptr [rax+rax+00h]
0x180008e36  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180008e3b  mov     r9, [rax+8]
0x180008e3f  mov     eax, [r9]
0x180008e42  cmp     eax, 5
0x180008e45  jbe     loc_180009055
0x180008e4b  mov     rdx, [r9+18h]
0x180008e4f  mov     rax, [r9+10h]
0x180008e53  mov     rcx, 400000000000h
0x180008e5d  test    rcx, rax
0x180008e60  jz      loc_180009055
0x180008e66  mov     rax, rdx
0x180008e69  and     rax, rcx
0x180008e6c  cmp     rax, rdx
0x180008e6f  jnz     loc_180009055
0x180008e75  mov     rax, [rdi+78h]
0x180008e79  mov     [rbp+57h+var_68], rax
0x180008e7d  mov     rax, [rdi+70h]
0x180008e81  mov     [rbp+57h+var_60], rax
0x180008e85  mov     eax, [rdi+68h]
0x180008e88  mov     dword ptr [rbp+57h+SRWLock], eax
0x180008e8b  mov     rax, [rdi+60h]
0x180008e8f  mov     [rbp+57h+var_58], rax
0x180008e93  mov     rax, [rdi+58h]
0x180008e97  mov     [rbp+57h+var_50], rax
0x180008e9b  mov     eax, [rdi+50h]
0x180008e9e  mov     [rbp+57h+arg_8], eax
0x180008ea1  mov     rax, [rdi+48h]
0x180008ea5  mov     [rbp+57h+var_48], rax
0x180008ea9  mov     eax, [rdi+20h]
0x180008eac  mov     dword ptr [rbp+57h+arg_10], eax
0x180008eaf  mov     rax, [rdi+18h]
0x180008eb3  mov     [rbp+57h+var_40], rax
0x180008eb7  mov     eax, [rdi]
0x180008eb9  mov     [rbp+57h+arg_18], eax
0x180008ebc  mov     rax, [rdi+80h]
0x180008ec3  mov     [rbp+57h+var_38], rax
0x180008ec7  mov     eax, [rdi+40h]
0x180008eca  mov     [rbp+57h+var_70], eax
0x180008ecd  mov     rax, [rdi+38h]
0x180008ed1  mov     [rbp+57h+var_30], rax
0x180008ed5  mov     eax, [rdi+8]
0x180008ed8  mov     [rbp+57h+var_6C], eax
0x180008edb  mov     eax, 1000000h
0x180008ee0  mov     [rbp+57h+var_28], rax
0x180008ee4  mov     [rbp+57h+var_20], rax
0x180008ee8  mov     r8, [rbx+110h]
0x180008eef  add     r8, 8
0x180008ef3  lea     rax, [rbp+57h+var_68]
0x180008ef7  mov     [rsp+110h+var_78], rax
0x180008eff  lea     rax, [rbp+57h+var_60]
0x180008f03  mov     [rsp+110h+var_80], rax
0x180008f0b  lea     rax, [rbp+57h+SRWLock]
0x180008f0f  mov     [rsp+110h+var_88], rax
0x180008f17  lea     rax, [rbp+57h+var_58]
0x180008f1b  mov     [rsp+110h+var_90], rax
0x180008f23  lea     rax, [rbp+57h+var_50]
0x180008f27  mov     [rsp+110h+var_98], rax
0x180008f2c  lea     rax, [rbp+57h+arg_8]
0x180008f30  mov     [rsp+110h+var_A0], rax
0x180008f35  lea     rax, [rbp+57h+var_48]
0x180008f39  mov     [rsp+110h+var_A8], rax
0x180008f3e  lea     rax, [rbp+57h+arg_10]
0x180008f42  mov     [rsp+110h+var_B0], rax
0x180008f47  lea     rax, [rbp+57h+var_40]
0x180008f4b  mov     [rsp+110h+var_B8], rax
0x180008f50  lea     rax, [rbp+57h+arg_18]
0x180008f54  mov     [rsp+110h+var_C0], rax
0x180008f59  lea     rax, [rbp+57h+var_38]
0x180008f5d  mov     [rsp+110h+var_C8], rax
0x180008f62  lea     rax, [rbp+57h+var_70]
0x180008f66  mov     [rsp+110h+var_D0], rax
0x180008f6b  lea     rax, [rbp+57h+var_30]
0x180008f6f  mov     [rsp+110h+var_D8], rax
0x180008f74  lea     rax, [rbp+57h+var_6C]
0x180008f78  mov     [rsp+110h+var_E0], rax
0x180008f7d  lea     rax, [rbp+57h+var_28]
0x180008f81  mov     [rsp+110h+var_E8], rax
0x180008f86  lea     rax, [rbp+57h+var_20]
0x180008f8a  mov     [rsp+110h+var_F0], rax
0x180008f8f  lea     rdx, word_180042D9A
0x180008f96  mov     rcx, r9
0x180008f99  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180008f9e  jmp     loc_180009055
0x180008fa3  lea     rdx, [rbp+57h+SRWLock]
0x180008fa7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008fac  mov     rax, [rbx+110h]
0x180008fb3  mov     dword ptr [rax], 2
0x180008fb9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180008fbd  test    rcx, rcx
0x180008fc0  jz      short loc_180008FCE
0x180008fc2  call    cs:__imp_ReleaseSRWLockExclusive
0x180008fc9  nop     dword ptr [rax+rax+00h]
0x180008fce  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180008fd3  mov     rdi, [rax+8]
0x180008fd7  mov     eax, [rdi]
0x180008fd9  cmp     eax, 5
0x180008fdc  jbe     short loc_180009055
0x180008fde  mov     rdx, [rdi+18h]
0x180008fe2  mov     rax, [rdi+10h]
0x180008fe6  mov     rcx, 400000000000h
0x180008ff0  test    rcx, rax
0x180008ff3  jz      short loc_180009055
0x180008ff5  mov     rax, rdx
0x180008ff8  and     rax, rcx
0x180008ffb  cmp     rax, rdx
0x180008ffe  jnz     short loc_180009055
0x180009000  call    cs:__imp_GetCurrentThreadId
0x180009007  nop     dword ptr [rax+rax+00h]
0x18000900c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000900f  mov     r8, [rbx+110h]
0x180009016  mov     eax, [r8+48h]
0x18000901a  mov     [rbp+57h+arg_8], eax
0x18000901d  mov     eax, 1000000h
0x180009022  mov     [rbp+57h+arg_10], rax
0x180009026  add     r8, 8
0x18000902a  lea     rax, [rbp+57h+SRWLock]
0x18000902e  mov     [rsp+110h+var_E0], rax
0x180009033  lea     rax, [rbp+57h+arg_8]
0x180009037  mov     [rsp+110h+var_E8], rax
0x18000903c  lea     rax, [rbp+57h+arg_10]
0x180009040  mov     [rsp+110h+var_F0], rax
0x180009045  lea     rdx, byte_180043187
0x18000904c  mov     rcx, rdi
0x18000904f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009054  nop
0x180009055  lea     rcx, [rbx+120h]; this
0x18000905c  cmp     dword ptr [rcx+18h], 0
0x180009060  jz      short loc_180009068
0x180009062  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180009067  nop
0x180009068  add     rsp, 100h
0x18000906f  pop     rdi
0x180009070  pop     rbx
0x180009071  pop     rbp
0x180009072  retn
```
