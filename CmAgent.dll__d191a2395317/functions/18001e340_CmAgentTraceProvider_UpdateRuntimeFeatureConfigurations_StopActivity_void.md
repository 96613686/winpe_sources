# CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StopActivity(void)

- ea: `0x18001e340`
- end: `0x18001e5e4`
- name: `?StopActivity@UpdateRuntimeFeatureConfigurations@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001e340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e570`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e532`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e532`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations::StopActivity(
        CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *this)
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
        (__int64)byte_1800445A1,
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
        (__int64)&dword_1800448CC,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::UpdateRuntimeFeatureConfigurations *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001e340  push    rbp
0x18001e342  push    rbx
0x18001e343  push    rdi
0x18001e344  lea     rbp, [rsp-47h]
0x18001e349  sub     rsp, 100h
0x18001e350  mov     rbx, rcx
0x18001e353  mov     rdi, [rcx+110h]
0x18001e35a  mov     eax, [rdi+48h]
0x18001e35d  test    eax, eax
0x18001e35f  jns     loc_18001E513
0x18001e365  add     rdi, 50h ; 'P'
0x18001e369  cmp     eax, [rdi+8]
0x18001e36c  jnz     loc_18001E513
0x18001e372  test    rdi, rdi
0x18001e375  jz      loc_18001E513
0x18001e37b  lea     rdx, [rbp+57h+SRWLock]
0x18001e37f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e384  mov     rax, [rbx+110h]
0x18001e38b  mov     dword ptr [rax], 2
0x18001e391  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e395  test    rcx, rcx
0x18001e398  jz      short loc_18001E3A6
0x18001e39a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e3a1  nop     dword ptr [rax+rax+00h]
0x18001e3a6  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e3ab  mov     r9, [rax+8]
0x18001e3af  mov     eax, [r9]
0x18001e3b2  cmp     eax, 5
0x18001e3b5  jbe     loc_18001E5C5
0x18001e3bb  mov     rdx, [r9+18h]
0x18001e3bf  mov     rax, [r9+10h]
0x18001e3c3  mov     rcx, 400000000000h
0x18001e3cd  test    rcx, rax
0x18001e3d0  jz      loc_18001E5C5
0x18001e3d6  mov     rax, rdx
0x18001e3d9  and     rax, rcx
0x18001e3dc  cmp     rax, rdx
0x18001e3df  jnz     loc_18001E5C5
0x18001e3e5  mov     rax, [rdi+78h]
0x18001e3e9  mov     [rbp+57h+var_68], rax
0x18001e3ed  mov     rax, [rdi+70h]
0x18001e3f1  mov     [rbp+57h+var_60], rax
0x18001e3f5  mov     eax, [rdi+68h]
0x18001e3f8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e3fb  mov     rax, [rdi+60h]
0x18001e3ff  mov     [rbp+57h+var_58], rax
0x18001e403  mov     rax, [rdi+58h]
0x18001e407  mov     [rbp+57h+var_50], rax
0x18001e40b  mov     eax, [rdi+50h]
0x18001e40e  mov     [rbp+57h+arg_8], eax
0x18001e411  mov     rax, [rdi+48h]
0x18001e415  mov     [rbp+57h+var_48], rax
0x18001e419  mov     eax, [rdi+20h]
0x18001e41c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001e41f  mov     rax, [rdi+18h]
0x18001e423  mov     [rbp+57h+var_40], rax
0x18001e427  mov     eax, [rdi]
0x18001e429  mov     [rbp+57h+arg_18], eax
0x18001e42c  mov     rax, [rdi+80h]
0x18001e433  mov     [rbp+57h+var_38], rax
0x18001e437  mov     eax, [rdi+40h]
0x18001e43a  mov     [rbp+57h+var_70], eax
0x18001e43d  mov     rax, [rdi+38h]
0x18001e441  mov     [rbp+57h+var_30], rax
0x18001e445  mov     eax, [rdi+8]
0x18001e448  mov     [rbp+57h+var_6C], eax
0x18001e44b  mov     eax, 1000000h
0x18001e450  mov     [rbp+57h+var_28], rax
0x18001e454  mov     [rbp+57h+var_20], rax
0x18001e458  mov     r8, [rbx+110h]
0x18001e45f  add     r8, 8
0x18001e463  lea     rax, [rbp+57h+var_68]
0x18001e467  mov     [rsp+110h+var_78], rax
0x18001e46f  lea     rax, [rbp+57h+var_60]
0x18001e473  mov     [rsp+110h+var_80], rax
0x18001e47b  lea     rax, [rbp+57h+SRWLock]
0x18001e47f  mov     [rsp+110h+var_88], rax
0x18001e487  lea     rax, [rbp+57h+var_58]
0x18001e48b  mov     [rsp+110h+var_90], rax
0x18001e493  lea     rax, [rbp+57h+var_50]
0x18001e497  mov     [rsp+110h+var_98], rax
0x18001e49c  lea     rax, [rbp+57h+arg_8]
0x18001e4a0  mov     [rsp+110h+var_A0], rax
0x18001e4a5  lea     rax, [rbp+57h+var_48]
0x18001e4a9  mov     [rsp+110h+var_A8], rax
0x18001e4ae  lea     rax, [rbp+57h+arg_10]
0x18001e4b2  mov     [rsp+110h+var_B0], rax
0x18001e4b7  lea     rax, [rbp+57h+var_40]
0x18001e4bb  mov     [rsp+110h+var_B8], rax
0x18001e4c0  lea     rax, [rbp+57h+arg_18]
0x18001e4c4  mov     [rsp+110h+var_C0], rax
0x18001e4c9  lea     rax, [rbp+57h+var_38]
0x18001e4cd  mov     [rsp+110h+var_C8], rax
0x18001e4d2  lea     rax, [rbp+57h+var_70]
0x18001e4d6  mov     [rsp+110h+var_D0], rax
0x18001e4db  lea     rax, [rbp+57h+var_30]
0x18001e4df  mov     [rsp+110h+var_D8], rax
0x18001e4e4  lea     rax, [rbp+57h+var_6C]
0x18001e4e8  mov     [rsp+110h+var_E0], rax
0x18001e4ed  lea     rax, [rbp+57h+var_28]
0x18001e4f1  mov     [rsp+110h+var_E8], rax
0x18001e4f6  lea     rax, [rbp+57h+var_20]
0x18001e4fa  mov     [rsp+110h+var_F0], rax
0x18001e4ff  lea     rdx, byte_1800445A1
0x18001e506  mov     rcx, r9
0x18001e509  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001e50e  jmp     loc_18001E5C5
0x18001e513  lea     rdx, [rbp+57h+SRWLock]
0x18001e517  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e51c  mov     rax, [rbx+110h]
0x18001e523  mov     dword ptr [rax], 2
0x18001e529  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e52d  test    rcx, rcx
0x18001e530  jz      short loc_18001E53E
0x18001e532  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e539  nop     dword ptr [rax+rax+00h]
0x18001e53e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e543  mov     rdi, [rax+8]
0x18001e547  mov     eax, [rdi]
0x18001e549  cmp     eax, 5
0x18001e54c  jbe     short loc_18001E5C5
0x18001e54e  mov     rdx, [rdi+18h]
0x18001e552  mov     rax, [rdi+10h]
0x18001e556  mov     rcx, 400000000000h
0x18001e560  test    rcx, rax
0x18001e563  jz      short loc_18001E5C5
0x18001e565  mov     rax, rdx
0x18001e568  and     rax, rcx
0x18001e56b  cmp     rax, rdx
0x18001e56e  jnz     short loc_18001E5C5
0x18001e570  call    cs:__imp_GetCurrentThreadId
0x18001e577  nop     dword ptr [rax+rax+00h]
0x18001e57c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e57f  mov     r8, [rbx+110h]
0x18001e586  mov     eax, [r8+48h]
0x18001e58a  mov     [rbp+57h+arg_8], eax
0x18001e58d  mov     eax, 1000000h
0x18001e592  mov     [rbp+57h+arg_10], rax
0x18001e596  add     r8, 8
0x18001e59a  lea     rax, [rbp+57h+SRWLock]
0x18001e59e  mov     [rsp+110h+var_E0], rax
0x18001e5a3  lea     rax, [rbp+57h+arg_8]
0x18001e5a7  mov     [rsp+110h+var_E8], rax
0x18001e5ac  lea     rax, [rbp+57h+arg_10]
0x18001e5b0  mov     [rsp+110h+var_F0], rax
0x18001e5b5  lea     rdx, dword_1800448CC
0x18001e5bc  mov     rcx, rdi
0x18001e5bf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e5c4  nop
0x18001e5c5  lea     rcx, [rbx+120h]; this
0x18001e5cc  cmp     dword ptr [rcx+18h], 0
0x18001e5d0  jz      short loc_18001E5D8
0x18001e5d2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001e5d7  nop
0x18001e5d8  add     rsp, 100h
0x18001e5df  pop     rdi
0x18001e5e0  pop     rbx
0x18001e5e1  pop     rbp
0x18001e5e2  retn
```
