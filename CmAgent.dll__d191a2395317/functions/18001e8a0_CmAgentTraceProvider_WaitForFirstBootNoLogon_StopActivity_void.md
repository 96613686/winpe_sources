# CmAgentTraceProvider::WaitForFirstBootNoLogon::StopActivity(void)

- ea: `0x18001e8a0`
- end: `0x18001eb44`
- name: `?StopActivity@WaitForFirstBootNoLogon@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForFirstBootNoLogon *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001e8a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ead0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ead0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ea92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ea92`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForFirstBootNoLogon::StopActivity(
        CmAgentTraceProvider::WaitForFirstBootNoLogon *this)
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
        (__int64)byte_1800438A5,
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
        (__int64)&word_1800440F6,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::WaitForFirstBootNoLogon *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001e8a0  push    rbp
0x18001e8a2  push    rbx
0x18001e8a3  push    rdi
0x18001e8a4  lea     rbp, [rsp-47h]
0x18001e8a9  sub     rsp, 100h
0x18001e8b0  mov     rbx, rcx
0x18001e8b3  mov     rdi, [rcx+110h]
0x18001e8ba  mov     eax, [rdi+48h]
0x18001e8bd  test    eax, eax
0x18001e8bf  jns     loc_18001EA73
0x18001e8c5  add     rdi, 50h ; 'P'
0x18001e8c9  cmp     eax, [rdi+8]
0x18001e8cc  jnz     loc_18001EA73
0x18001e8d2  test    rdi, rdi
0x18001e8d5  jz      loc_18001EA73
0x18001e8db  lea     rdx, [rbp+57h+SRWLock]
0x18001e8df  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e8e4  mov     rax, [rbx+110h]
0x18001e8eb  mov     dword ptr [rax], 2
0x18001e8f1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e8f5  test    rcx, rcx
0x18001e8f8  jz      short loc_18001E906
0x18001e8fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e901  nop     dword ptr [rax+rax+00h]
0x18001e906  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e90b  mov     r9, [rax+8]
0x18001e90f  mov     eax, [r9]
0x18001e912  cmp     eax, 5
0x18001e915  jbe     loc_18001EB25
0x18001e91b  mov     rdx, [r9+18h]
0x18001e91f  mov     rax, [r9+10h]
0x18001e923  mov     rcx, 400000000000h
0x18001e92d  test    rcx, rax
0x18001e930  jz      loc_18001EB25
0x18001e936  mov     rax, rdx
0x18001e939  and     rax, rcx
0x18001e93c  cmp     rax, rdx
0x18001e93f  jnz     loc_18001EB25
0x18001e945  mov     rax, [rdi+78h]
0x18001e949  mov     [rbp+57h+var_68], rax
0x18001e94d  mov     rax, [rdi+70h]
0x18001e951  mov     [rbp+57h+var_60], rax
0x18001e955  mov     eax, [rdi+68h]
0x18001e958  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e95b  mov     rax, [rdi+60h]
0x18001e95f  mov     [rbp+57h+var_58], rax
0x18001e963  mov     rax, [rdi+58h]
0x18001e967  mov     [rbp+57h+var_50], rax
0x18001e96b  mov     eax, [rdi+50h]
0x18001e96e  mov     [rbp+57h+arg_8], eax
0x18001e971  mov     rax, [rdi+48h]
0x18001e975  mov     [rbp+57h+var_48], rax
0x18001e979  mov     eax, [rdi+20h]
0x18001e97c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001e97f  mov     rax, [rdi+18h]
0x18001e983  mov     [rbp+57h+var_40], rax
0x18001e987  mov     eax, [rdi]
0x18001e989  mov     [rbp+57h+arg_18], eax
0x18001e98c  mov     rax, [rdi+80h]
0x18001e993  mov     [rbp+57h+var_38], rax
0x18001e997  mov     eax, [rdi+40h]
0x18001e99a  mov     [rbp+57h+var_70], eax
0x18001e99d  mov     rax, [rdi+38h]
0x18001e9a1  mov     [rbp+57h+var_30], rax
0x18001e9a5  mov     eax, [rdi+8]
0x18001e9a8  mov     [rbp+57h+var_6C], eax
0x18001e9ab  mov     eax, 1000000h
0x18001e9b0  mov     [rbp+57h+var_28], rax
0x18001e9b4  mov     [rbp+57h+var_20], rax
0x18001e9b8  mov     r8, [rbx+110h]
0x18001e9bf  add     r8, 8
0x18001e9c3  lea     rax, [rbp+57h+var_68]
0x18001e9c7  mov     [rsp+110h+var_78], rax
0x18001e9cf  lea     rax, [rbp+57h+var_60]
0x18001e9d3  mov     [rsp+110h+var_80], rax
0x18001e9db  lea     rax, [rbp+57h+SRWLock]
0x18001e9df  mov     [rsp+110h+var_88], rax
0x18001e9e7  lea     rax, [rbp+57h+var_58]
0x18001e9eb  mov     [rsp+110h+var_90], rax
0x18001e9f3  lea     rax, [rbp+57h+var_50]
0x18001e9f7  mov     [rsp+110h+var_98], rax
0x18001e9fc  lea     rax, [rbp+57h+arg_8]
0x18001ea00  mov     [rsp+110h+var_A0], rax
0x18001ea05  lea     rax, [rbp+57h+var_48]
0x18001ea09  mov     [rsp+110h+var_A8], rax
0x18001ea0e  lea     rax, [rbp+57h+arg_10]
0x18001ea12  mov     [rsp+110h+var_B0], rax
0x18001ea17  lea     rax, [rbp+57h+var_40]
0x18001ea1b  mov     [rsp+110h+var_B8], rax
0x18001ea20  lea     rax, [rbp+57h+arg_18]
0x18001ea24  mov     [rsp+110h+var_C0], rax
0x18001ea29  lea     rax, [rbp+57h+var_38]
0x18001ea2d  mov     [rsp+110h+var_C8], rax
0x18001ea32  lea     rax, [rbp+57h+var_70]
0x18001ea36  mov     [rsp+110h+var_D0], rax
0x18001ea3b  lea     rax, [rbp+57h+var_30]
0x18001ea3f  mov     [rsp+110h+var_D8], rax
0x18001ea44  lea     rax, [rbp+57h+var_6C]
0x18001ea48  mov     [rsp+110h+var_E0], rax
0x18001ea4d  lea     rax, [rbp+57h+var_28]
0x18001ea51  mov     [rsp+110h+var_E8], rax
0x18001ea56  lea     rax, [rbp+57h+var_20]
0x18001ea5a  mov     [rsp+110h+var_F0], rax
0x18001ea5f  lea     rdx, byte_1800438A5
0x18001ea66  mov     rcx, r9
0x18001ea69  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001ea6e  jmp     loc_18001EB25
0x18001ea73  lea     rdx, [rbp+57h+SRWLock]
0x18001ea77  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ea7c  mov     rax, [rbx+110h]
0x18001ea83  mov     dword ptr [rax], 2
0x18001ea89  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ea8d  test    rcx, rcx
0x18001ea90  jz      short loc_18001EA9E
0x18001ea92  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ea99  nop     dword ptr [rax+rax+00h]
0x18001ea9e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001eaa3  mov     rdi, [rax+8]
0x18001eaa7  mov     eax, [rdi]
0x18001eaa9  cmp     eax, 5
0x18001eaac  jbe     short loc_18001EB25
0x18001eaae  mov     rdx, [rdi+18h]
0x18001eab2  mov     rax, [rdi+10h]
0x18001eab6  mov     rcx, 400000000000h
0x18001eac0  test    rcx, rax
0x18001eac3  jz      short loc_18001EB25
0x18001eac5  mov     rax, rdx
0x18001eac8  and     rax, rcx
0x18001eacb  cmp     rax, rdx
0x18001eace  jnz     short loc_18001EB25
0x18001ead0  call    cs:__imp_GetCurrentThreadId
0x18001ead7  nop     dword ptr [rax+rax+00h]
0x18001eadc  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001eadf  mov     r8, [rbx+110h]
0x18001eae6  mov     eax, [r8+48h]
0x18001eaea  mov     [rbp+57h+arg_8], eax
0x18001eaed  mov     eax, 1000000h
0x18001eaf2  mov     [rbp+57h+arg_10], rax
0x18001eaf6  add     r8, 8
0x18001eafa  lea     rax, [rbp+57h+SRWLock]
0x18001eafe  mov     [rsp+110h+var_E0], rax
0x18001eb03  lea     rax, [rbp+57h+arg_8]
0x18001eb07  mov     [rsp+110h+var_E8], rax
0x18001eb0c  lea     rax, [rbp+57h+arg_10]
0x18001eb10  mov     [rsp+110h+var_F0], rax
0x18001eb15  lea     rdx, word_1800440F6
0x18001eb1c  mov     rcx, rdi
0x18001eb1f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001eb24  nop
0x18001eb25  lea     rcx, [rbx+120h]; this
0x18001eb2c  cmp     dword ptr [rcx+18h], 0
0x18001eb30  jz      short loc_18001EB38
0x18001eb32  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001eb37  nop
0x18001eb38  add     rsp, 100h
0x18001eb3f  pop     rdi
0x18001eb40  pop     rbx
0x18001eb41  pop     rbp
0x18001eb42  retn
```
