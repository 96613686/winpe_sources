# CmAgentTraceProvider::ServiceStart::StopActivity(void)

- ea: `0x180008b20`
- end: `0x180008dc4`
- name: `?StopActivity@ServiceStart@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::ServiceStart *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x180008b20`
- `0x18000907c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d12`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CmAgentTraceProvider::ServiceStart::StopActivity(CmAgentTraceProvider::ServiceStart *this)
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
        (__int64)word_180042FD2,
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
        (__int64)&word_1800430F6,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::ServiceStart *)((char *)this + 288));
}

```

## disassembly

```asm
0x180008b20  push    rbp
0x180008b22  push    rbx
0x180008b23  push    rdi
0x180008b24  lea     rbp, [rsp-47h]
0x180008b29  sub     rsp, 100h
0x180008b30  mov     rbx, rcx
0x180008b33  mov     rdi, [rcx+110h]
0x180008b3a  mov     eax, [rdi+48h]
0x180008b3d  test    eax, eax
0x180008b3f  jns     loc_180008CF3
0x180008b45  add     rdi, 50h ; 'P'
0x180008b49  cmp     eax, [rdi+8]
0x180008b4c  jnz     loc_180008CF3
0x180008b52  test    rdi, rdi
0x180008b55  jz      loc_180008CF3
0x180008b5b  lea     rdx, [rbp+57h+SRWLock]
0x180008b5f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008b64  mov     rax, [rbx+110h]
0x180008b6b  mov     dword ptr [rax], 2
0x180008b71  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180008b75  test    rcx, rcx
0x180008b78  jz      short loc_180008B86
0x180008b7a  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b81  nop     dword ptr [rax+rax+00h]
0x180008b86  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180008b8b  mov     r9, [rax+8]
0x180008b8f  mov     eax, [r9]
0x180008b92  cmp     eax, 5
0x180008b95  jbe     loc_180008DA5
0x180008b9b  mov     rdx, [r9+18h]
0x180008b9f  mov     rax, [r9+10h]
0x180008ba3  mov     rcx, 400000000000h
0x180008bad  test    rcx, rax
0x180008bb0  jz      loc_180008DA5
0x180008bb6  mov     rax, rdx
0x180008bb9  and     rax, rcx
0x180008bbc  cmp     rax, rdx
0x180008bbf  jnz     loc_180008DA5
0x180008bc5  mov     rax, [rdi+78h]
0x180008bc9  mov     [rbp+57h+var_68], rax
0x180008bcd  mov     rax, [rdi+70h]
0x180008bd1  mov     [rbp+57h+var_60], rax
0x180008bd5  mov     eax, [rdi+68h]
0x180008bd8  mov     dword ptr [rbp+57h+SRWLock], eax
0x180008bdb  mov     rax, [rdi+60h]
0x180008bdf  mov     [rbp+57h+var_58], rax
0x180008be3  mov     rax, [rdi+58h]
0x180008be7  mov     [rbp+57h+var_50], rax
0x180008beb  mov     eax, [rdi+50h]
0x180008bee  mov     [rbp+57h+arg_8], eax
0x180008bf1  mov     rax, [rdi+48h]
0x180008bf5  mov     [rbp+57h+var_48], rax
0x180008bf9  mov     eax, [rdi+20h]
0x180008bfc  mov     dword ptr [rbp+57h+arg_10], eax
0x180008bff  mov     rax, [rdi+18h]
0x180008c03  mov     [rbp+57h+var_40], rax
0x180008c07  mov     eax, [rdi]
0x180008c09  mov     [rbp+57h+arg_18], eax
0x180008c0c  mov     rax, [rdi+80h]
0x180008c13  mov     [rbp+57h+var_38], rax
0x180008c17  mov     eax, [rdi+40h]
0x180008c1a  mov     [rbp+57h+var_70], eax
0x180008c1d  mov     rax, [rdi+38h]
0x180008c21  mov     [rbp+57h+var_30], rax
0x180008c25  mov     eax, [rdi+8]
0x180008c28  mov     [rbp+57h+var_6C], eax
0x180008c2b  mov     eax, 1000000h
0x180008c30  mov     [rbp+57h+var_28], rax
0x180008c34  mov     [rbp+57h+var_20], rax
0x180008c38  mov     r8, [rbx+110h]
0x180008c3f  add     r8, 8
0x180008c43  lea     rax, [rbp+57h+var_68]
0x180008c47  mov     [rsp+110h+var_78], rax
0x180008c4f  lea     rax, [rbp+57h+var_60]
0x180008c53  mov     [rsp+110h+var_80], rax
0x180008c5b  lea     rax, [rbp+57h+SRWLock]
0x180008c5f  mov     [rsp+110h+var_88], rax
0x180008c67  lea     rax, [rbp+57h+var_58]
0x180008c6b  mov     [rsp+110h+var_90], rax
0x180008c73  lea     rax, [rbp+57h+var_50]
0x180008c77  mov     [rsp+110h+var_98], rax
0x180008c7c  lea     rax, [rbp+57h+arg_8]
0x180008c80  mov     [rsp+110h+var_A0], rax
0x180008c85  lea     rax, [rbp+57h+var_48]
0x180008c89  mov     [rsp+110h+var_A8], rax
0x180008c8e  lea     rax, [rbp+57h+arg_10]
0x180008c92  mov     [rsp+110h+var_B0], rax
0x180008c97  lea     rax, [rbp+57h+var_40]
0x180008c9b  mov     [rsp+110h+var_B8], rax
0x180008ca0  lea     rax, [rbp+57h+arg_18]
0x180008ca4  mov     [rsp+110h+var_C0], rax
0x180008ca9  lea     rax, [rbp+57h+var_38]
0x180008cad  mov     [rsp+110h+var_C8], rax
0x180008cb2  lea     rax, [rbp+57h+var_70]
0x180008cb6  mov     [rsp+110h+var_D0], rax
0x180008cbb  lea     rax, [rbp+57h+var_30]
0x180008cbf  mov     [rsp+110h+var_D8], rax
0x180008cc4  lea     rax, [rbp+57h+var_6C]
0x180008cc8  mov     [rsp+110h+var_E0], rax
0x180008ccd  lea     rax, [rbp+57h+var_28]
0x180008cd1  mov     [rsp+110h+var_E8], rax
0x180008cd6  lea     rax, [rbp+57h+var_20]
0x180008cda  mov     [rsp+110h+var_F0], rax
0x180008cdf  lea     rdx, word_180042FD2
0x180008ce6  mov     rcx, r9
0x180008ce9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180008cee  jmp     loc_180008DA5
0x180008cf3  lea     rdx, [rbp+57h+SRWLock]
0x180008cf7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008cfc  mov     rax, [rbx+110h]
0x180008d03  mov     dword ptr [rax], 2
0x180008d09  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180008d0d  test    rcx, rcx
0x180008d10  jz      short loc_180008D1E
0x180008d12  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d19  nop     dword ptr [rax+rax+00h]
0x180008d1e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x180008d23  mov     rdi, [rax+8]
0x180008d27  mov     eax, [rdi]
0x180008d29  cmp     eax, 5
0x180008d2c  jbe     short loc_180008DA5
0x180008d2e  mov     rdx, [rdi+18h]
0x180008d32  mov     rax, [rdi+10h]
0x180008d36  mov     rcx, 400000000000h
0x180008d40  test    rcx, rax
0x180008d43  jz      short loc_180008DA5
0x180008d45  mov     rax, rdx
0x180008d48  and     rax, rcx
0x180008d4b  cmp     rax, rdx
0x180008d4e  jnz     short loc_180008DA5
0x180008d50  call    cs:__imp_GetCurrentThreadId
0x180008d57  nop     dword ptr [rax+rax+00h]
0x180008d5c  mov     dword ptr [rbp+57h+SRWLock], eax
0x180008d5f  mov     r8, [rbx+110h]
0x180008d66  mov     eax, [r8+48h]
0x180008d6a  mov     [rbp+57h+arg_8], eax
0x180008d6d  mov     eax, 1000000h
0x180008d72  mov     [rbp+57h+arg_10], rax
0x180008d76  add     r8, 8
0x180008d7a  lea     rax, [rbp+57h+SRWLock]
0x180008d7e  mov     [rsp+110h+var_E0], rax
0x180008d83  lea     rax, [rbp+57h+arg_8]
0x180008d87  mov     [rsp+110h+var_E8], rax
0x180008d8c  lea     rax, [rbp+57h+arg_10]
0x180008d90  mov     [rsp+110h+var_F0], rax
0x180008d95  lea     rdx, word_1800430F6
0x180008d9c  mov     rcx, rdi
0x180008d9f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008da4  nop
0x180008da5  lea     rcx, [rbx+120h]; this
0x180008dac  cmp     dword ptr [rcx+18h], 0
0x180008db0  jz      short loc_180008DB8
0x180008db2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180008db7  nop
0x180008db8  add     rsp, 100h
0x180008dbf  pop     rdi
0x180008dc0  pop     rbx
0x180008dc1  pop     rbp
0x180008dc2  retn
```
