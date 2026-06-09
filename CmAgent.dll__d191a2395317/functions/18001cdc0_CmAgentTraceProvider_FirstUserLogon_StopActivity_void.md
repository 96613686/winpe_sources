# CmAgentTraceProvider::FirstUserLogon::StopActivity(void)

- ea: `0x18001cdc0`
- end: `0x18001d064`
- name: `?StopActivity@FirstUserLogon@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::FirstUserLogon *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001cdc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cff0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cff0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ce1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cfb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ce1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cfb2`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::FirstUserLogon::StopActivity(CmAgentTraceProvider::FirstUserLogon *this)
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
        (__int64)byte_180043F7B,
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
        (__int64)qword_1800437F8,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::FirstUserLogon *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001cdc0  push    rbp
0x18001cdc2  push    rbx
0x18001cdc3  push    rdi
0x18001cdc4  lea     rbp, [rsp-47h]
0x18001cdc9  sub     rsp, 100h
0x18001cdd0  mov     rbx, rcx
0x18001cdd3  mov     rdi, [rcx+110h]
0x18001cdda  mov     eax, [rdi+48h]
0x18001cddd  test    eax, eax
0x18001cddf  jns     loc_18001CF93
0x18001cde5  add     rdi, 50h ; 'P'
0x18001cde9  cmp     eax, [rdi+8]
0x18001cdec  jnz     loc_18001CF93
0x18001cdf2  test    rdi, rdi
0x18001cdf5  jz      loc_18001CF93
0x18001cdfb  lea     rdx, [rbp+57h+SRWLock]
0x18001cdff  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ce04  mov     rax, [rbx+110h]
0x18001ce0b  mov     dword ptr [rax], 2
0x18001ce11  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ce15  test    rcx, rcx
0x18001ce18  jz      short loc_18001CE26
0x18001ce1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ce21  nop     dword ptr [rax+rax+00h]
0x18001ce26  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001ce2b  mov     r9, [rax+8]
0x18001ce2f  mov     eax, [r9]
0x18001ce32  cmp     eax, 5
0x18001ce35  jbe     loc_18001D045
0x18001ce3b  mov     rdx, [r9+18h]
0x18001ce3f  mov     rax, [r9+10h]
0x18001ce43  mov     rcx, 400000000000h
0x18001ce4d  test    rcx, rax
0x18001ce50  jz      loc_18001D045
0x18001ce56  mov     rax, rdx
0x18001ce59  and     rax, rcx
0x18001ce5c  cmp     rax, rdx
0x18001ce5f  jnz     loc_18001D045
0x18001ce65  mov     rax, [rdi+78h]
0x18001ce69  mov     [rbp+57h+var_68], rax
0x18001ce6d  mov     rax, [rdi+70h]
0x18001ce71  mov     [rbp+57h+var_60], rax
0x18001ce75  mov     eax, [rdi+68h]
0x18001ce78  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001ce7b  mov     rax, [rdi+60h]
0x18001ce7f  mov     [rbp+57h+var_58], rax
0x18001ce83  mov     rax, [rdi+58h]
0x18001ce87  mov     [rbp+57h+var_50], rax
0x18001ce8b  mov     eax, [rdi+50h]
0x18001ce8e  mov     [rbp+57h+arg_8], eax
0x18001ce91  mov     rax, [rdi+48h]
0x18001ce95  mov     [rbp+57h+var_48], rax
0x18001ce99  mov     eax, [rdi+20h]
0x18001ce9c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001ce9f  mov     rax, [rdi+18h]
0x18001cea3  mov     [rbp+57h+var_40], rax
0x18001cea7  mov     eax, [rdi]
0x18001cea9  mov     [rbp+57h+arg_18], eax
0x18001ceac  mov     rax, [rdi+80h]
0x18001ceb3  mov     [rbp+57h+var_38], rax
0x18001ceb7  mov     eax, [rdi+40h]
0x18001ceba  mov     [rbp+57h+var_70], eax
0x18001cebd  mov     rax, [rdi+38h]
0x18001cec1  mov     [rbp+57h+var_30], rax
0x18001cec5  mov     eax, [rdi+8]
0x18001cec8  mov     [rbp+57h+var_6C], eax
0x18001cecb  mov     eax, 1000000h
0x18001ced0  mov     [rbp+57h+var_28], rax
0x18001ced4  mov     [rbp+57h+var_20], rax
0x18001ced8  mov     r8, [rbx+110h]
0x18001cedf  add     r8, 8
0x18001cee3  lea     rax, [rbp+57h+var_68]
0x18001cee7  mov     [rsp+110h+var_78], rax
0x18001ceef  lea     rax, [rbp+57h+var_60]
0x18001cef3  mov     [rsp+110h+var_80], rax
0x18001cefb  lea     rax, [rbp+57h+SRWLock]
0x18001ceff  mov     [rsp+110h+var_88], rax
0x18001cf07  lea     rax, [rbp+57h+var_58]
0x18001cf0b  mov     [rsp+110h+var_90], rax
0x18001cf13  lea     rax, [rbp+57h+var_50]
0x18001cf17  mov     [rsp+110h+var_98], rax
0x18001cf1c  lea     rax, [rbp+57h+arg_8]
0x18001cf20  mov     [rsp+110h+var_A0], rax
0x18001cf25  lea     rax, [rbp+57h+var_48]
0x18001cf29  mov     [rsp+110h+var_A8], rax
0x18001cf2e  lea     rax, [rbp+57h+arg_10]
0x18001cf32  mov     [rsp+110h+var_B0], rax
0x18001cf37  lea     rax, [rbp+57h+var_40]
0x18001cf3b  mov     [rsp+110h+var_B8], rax
0x18001cf40  lea     rax, [rbp+57h+arg_18]
0x18001cf44  mov     [rsp+110h+var_C0], rax
0x18001cf49  lea     rax, [rbp+57h+var_38]
0x18001cf4d  mov     [rsp+110h+var_C8], rax
0x18001cf52  lea     rax, [rbp+57h+var_70]
0x18001cf56  mov     [rsp+110h+var_D0], rax
0x18001cf5b  lea     rax, [rbp+57h+var_30]
0x18001cf5f  mov     [rsp+110h+var_D8], rax
0x18001cf64  lea     rax, [rbp+57h+var_6C]
0x18001cf68  mov     [rsp+110h+var_E0], rax
0x18001cf6d  lea     rax, [rbp+57h+var_28]
0x18001cf71  mov     [rsp+110h+var_E8], rax
0x18001cf76  lea     rax, [rbp+57h+var_20]
0x18001cf7a  mov     [rsp+110h+var_F0], rax
0x18001cf7f  lea     rdx, byte_180043F7B
0x18001cf86  mov     rcx, r9
0x18001cf89  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001cf8e  jmp     loc_18001D045
0x18001cf93  lea     rdx, [rbp+57h+SRWLock]
0x18001cf97  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001cf9c  mov     rax, [rbx+110h]
0x18001cfa3  mov     dword ptr [rax], 2
0x18001cfa9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001cfad  test    rcx, rcx
0x18001cfb0  jz      short loc_18001CFBE
0x18001cfb2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cfb9  nop     dword ptr [rax+rax+00h]
0x18001cfbe  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001cfc3  mov     rdi, [rax+8]
0x18001cfc7  mov     eax, [rdi]
0x18001cfc9  cmp     eax, 5
0x18001cfcc  jbe     short loc_18001D045
0x18001cfce  mov     rdx, [rdi+18h]
0x18001cfd2  mov     rax, [rdi+10h]
0x18001cfd6  mov     rcx, 400000000000h
0x18001cfe0  test    rcx, rax
0x18001cfe3  jz      short loc_18001D045
0x18001cfe5  mov     rax, rdx
0x18001cfe8  and     rax, rcx
0x18001cfeb  cmp     rax, rdx
0x18001cfee  jnz     short loc_18001D045
0x18001cff0  call    cs:__imp_GetCurrentThreadId
0x18001cff7  nop     dword ptr [rax+rax+00h]
0x18001cffc  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001cfff  mov     r8, [rbx+110h]
0x18001d006  mov     eax, [r8+48h]
0x18001d00a  mov     [rbp+57h+arg_8], eax
0x18001d00d  mov     eax, 1000000h
0x18001d012  mov     [rbp+57h+arg_10], rax
0x18001d016  add     r8, 8
0x18001d01a  lea     rax, [rbp+57h+SRWLock]
0x18001d01e  mov     [rsp+110h+var_E0], rax
0x18001d023  lea     rax, [rbp+57h+arg_8]
0x18001d027  mov     [rsp+110h+var_E8], rax
0x18001d02c  lea     rax, [rbp+57h+arg_10]
0x18001d030  mov     [rsp+110h+var_F0], rax
0x18001d035  lea     rdx, qword_1800437F8
0x18001d03c  mov     rcx, rdi
0x18001d03f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d044  nop
0x18001d045  lea     rcx, [rbx+120h]; this
0x18001d04c  cmp     dword ptr [rcx+18h], 0
0x18001d050  jz      short loc_18001D058
0x18001d052  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001d057  nop
0x18001d058  add     rsp, 100h
0x18001d05f  pop     rdi
0x18001d060  pop     rbx
0x18001d061  pop     rbp
0x18001d062  retn
```
