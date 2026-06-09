# CmAgentTraceProvider::MapFiles::StopActivity(void)

- ea: `0x18001d070`
- end: `0x18001d314`
- name: `?StopActivity@MapFiles@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::MapFiles *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001d070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d262`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d262`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::MapFiles::StopActivity(CmAgentTraceProvider::MapFiles *this)
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
        (__int64)byte_180044481,
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
        (__int64)byte_180043D65,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::MapFiles *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001d070  push    rbp
0x18001d072  push    rbx
0x18001d073  push    rdi
0x18001d074  lea     rbp, [rsp-47h]
0x18001d079  sub     rsp, 100h
0x18001d080  mov     rbx, rcx
0x18001d083  mov     rdi, [rcx+110h]
0x18001d08a  mov     eax, [rdi+48h]
0x18001d08d  test    eax, eax
0x18001d08f  jns     loc_18001D243
0x18001d095  add     rdi, 50h ; 'P'
0x18001d099  cmp     eax, [rdi+8]
0x18001d09c  jnz     loc_18001D243
0x18001d0a2  test    rdi, rdi
0x18001d0a5  jz      loc_18001D243
0x18001d0ab  lea     rdx, [rbp+57h+SRWLock]
0x18001d0af  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001d0b4  mov     rax, [rbx+110h]
0x18001d0bb  mov     dword ptr [rax], 2
0x18001d0c1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001d0c5  test    rcx, rcx
0x18001d0c8  jz      short loc_18001D0D6
0x18001d0ca  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d0d1  nop     dword ptr [rax+rax+00h]
0x18001d0d6  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001d0db  mov     r9, [rax+8]
0x18001d0df  mov     eax, [r9]
0x18001d0e2  cmp     eax, 5
0x18001d0e5  jbe     loc_18001D2F5
0x18001d0eb  mov     rdx, [r9+18h]
0x18001d0ef  mov     rax, [r9+10h]
0x18001d0f3  mov     rcx, 400000000000h
0x18001d0fd  test    rcx, rax
0x18001d100  jz      loc_18001D2F5
0x18001d106  mov     rax, rdx
0x18001d109  and     rax, rcx
0x18001d10c  cmp     rax, rdx
0x18001d10f  jnz     loc_18001D2F5
0x18001d115  mov     rax, [rdi+78h]
0x18001d119  mov     [rbp+57h+var_68], rax
0x18001d11d  mov     rax, [rdi+70h]
0x18001d121  mov     [rbp+57h+var_60], rax
0x18001d125  mov     eax, [rdi+68h]
0x18001d128  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001d12b  mov     rax, [rdi+60h]
0x18001d12f  mov     [rbp+57h+var_58], rax
0x18001d133  mov     rax, [rdi+58h]
0x18001d137  mov     [rbp+57h+var_50], rax
0x18001d13b  mov     eax, [rdi+50h]
0x18001d13e  mov     [rbp+57h+arg_8], eax
0x18001d141  mov     rax, [rdi+48h]
0x18001d145  mov     [rbp+57h+var_48], rax
0x18001d149  mov     eax, [rdi+20h]
0x18001d14c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001d14f  mov     rax, [rdi+18h]
0x18001d153  mov     [rbp+57h+var_40], rax
0x18001d157  mov     eax, [rdi]
0x18001d159  mov     [rbp+57h+arg_18], eax
0x18001d15c  mov     rax, [rdi+80h]
0x18001d163  mov     [rbp+57h+var_38], rax
0x18001d167  mov     eax, [rdi+40h]
0x18001d16a  mov     [rbp+57h+var_70], eax
0x18001d16d  mov     rax, [rdi+38h]
0x18001d171  mov     [rbp+57h+var_30], rax
0x18001d175  mov     eax, [rdi+8]
0x18001d178  mov     [rbp+57h+var_6C], eax
0x18001d17b  mov     eax, 1000000h
0x18001d180  mov     [rbp+57h+var_28], rax
0x18001d184  mov     [rbp+57h+var_20], rax
0x18001d188  mov     r8, [rbx+110h]
0x18001d18f  add     r8, 8
0x18001d193  lea     rax, [rbp+57h+var_68]
0x18001d197  mov     [rsp+110h+var_78], rax
0x18001d19f  lea     rax, [rbp+57h+var_60]
0x18001d1a3  mov     [rsp+110h+var_80], rax
0x18001d1ab  lea     rax, [rbp+57h+SRWLock]
0x18001d1af  mov     [rsp+110h+var_88], rax
0x18001d1b7  lea     rax, [rbp+57h+var_58]
0x18001d1bb  mov     [rsp+110h+var_90], rax
0x18001d1c3  lea     rax, [rbp+57h+var_50]
0x18001d1c7  mov     [rsp+110h+var_98], rax
0x18001d1cc  lea     rax, [rbp+57h+arg_8]
0x18001d1d0  mov     [rsp+110h+var_A0], rax
0x18001d1d5  lea     rax, [rbp+57h+var_48]
0x18001d1d9  mov     [rsp+110h+var_A8], rax
0x18001d1de  lea     rax, [rbp+57h+arg_10]
0x18001d1e2  mov     [rsp+110h+var_B0], rax
0x18001d1e7  lea     rax, [rbp+57h+var_40]
0x18001d1eb  mov     [rsp+110h+var_B8], rax
0x18001d1f0  lea     rax, [rbp+57h+arg_18]
0x18001d1f4  mov     [rsp+110h+var_C0], rax
0x18001d1f9  lea     rax, [rbp+57h+var_38]
0x18001d1fd  mov     [rsp+110h+var_C8], rax
0x18001d202  lea     rax, [rbp+57h+var_70]
0x18001d206  mov     [rsp+110h+var_D0], rax
0x18001d20b  lea     rax, [rbp+57h+var_30]
0x18001d20f  mov     [rsp+110h+var_D8], rax
0x18001d214  lea     rax, [rbp+57h+var_6C]
0x18001d218  mov     [rsp+110h+var_E0], rax
0x18001d21d  lea     rax, [rbp+57h+var_28]
0x18001d221  mov     [rsp+110h+var_E8], rax
0x18001d226  lea     rax, [rbp+57h+var_20]
0x18001d22a  mov     [rsp+110h+var_F0], rax
0x18001d22f  lea     rdx, byte_180044481
0x18001d236  mov     rcx, r9
0x18001d239  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001d23e  jmp     loc_18001D2F5
0x18001d243  lea     rdx, [rbp+57h+SRWLock]
0x18001d247  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001d24c  mov     rax, [rbx+110h]
0x18001d253  mov     dword ptr [rax], 2
0x18001d259  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001d25d  test    rcx, rcx
0x18001d260  jz      short loc_18001D26E
0x18001d262  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d269  nop     dword ptr [rax+rax+00h]
0x18001d26e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001d273  mov     rdi, [rax+8]
0x18001d277  mov     eax, [rdi]
0x18001d279  cmp     eax, 5
0x18001d27c  jbe     short loc_18001D2F5
0x18001d27e  mov     rdx, [rdi+18h]
0x18001d282  mov     rax, [rdi+10h]
0x18001d286  mov     rcx, 400000000000h
0x18001d290  test    rcx, rax
0x18001d293  jz      short loc_18001D2F5
0x18001d295  mov     rax, rdx
0x18001d298  and     rax, rcx
0x18001d29b  cmp     rax, rdx
0x18001d29e  jnz     short loc_18001D2F5
0x18001d2a0  call    cs:__imp_GetCurrentThreadId
0x18001d2a7  nop     dword ptr [rax+rax+00h]
0x18001d2ac  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001d2af  mov     r8, [rbx+110h]
0x18001d2b6  mov     eax, [r8+48h]
0x18001d2ba  mov     [rbp+57h+arg_8], eax
0x18001d2bd  mov     eax, 1000000h
0x18001d2c2  mov     [rbp+57h+arg_10], rax
0x18001d2c6  add     r8, 8
0x18001d2ca  lea     rax, [rbp+57h+SRWLock]
0x18001d2ce  mov     [rsp+110h+var_E0], rax
0x18001d2d3  lea     rax, [rbp+57h+arg_8]
0x18001d2d7  mov     [rsp+110h+var_E8], rax
0x18001d2dc  lea     rax, [rbp+57h+arg_10]
0x18001d2e0  mov     [rsp+110h+var_F0], rax
0x18001d2e5  lea     rdx, byte_180043D65
0x18001d2ec  mov     rcx, rdi
0x18001d2ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d2f4  nop
0x18001d2f5  lea     rcx, [rbx+120h]; this
0x18001d2fc  cmp     dword ptr [rcx+18h], 0
0x18001d300  jz      short loc_18001D308
0x18001d302  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001d307  nop
0x18001d308  add     rsp, 100h
0x18001d30f  pop     rdi
0x18001d310  pop     rbx
0x18001d311  pop     rbp
0x18001d312  retn
```
