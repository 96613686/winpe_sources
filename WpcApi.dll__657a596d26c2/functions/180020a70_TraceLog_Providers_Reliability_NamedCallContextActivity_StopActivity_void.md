# TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(void)

- ea: `0x180020a70`
- end: `0x180020d3e`
- name: `?StopActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@MEAAXXZ`
- size: `718`
- prototype: `void __fastcall(TraceLog::Providers::Reliability::NamedCallContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x180010810`
- `0x1800203f8`
- `0x180020a70`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020aca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020aca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cdc`

## string_xrefs

- `0x180020cf7`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StopActivity(
        TraceLog::Providers::Reliability::NamedCallContextActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v17; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v19; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v20; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v22; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v23; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  __int64 v26[4]; // [rsp+120h] [rbp-20h] BYREF
  void *retaddr; // [rsp+148h] [rbp+8h]
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v5 > 4u )
    {
      v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v29 = v4[4];
      v17 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v30) = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)word_18003D53A,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        &v18,
        &v17,
        (__int64)&v29,
        (__int64)&SRWLock,
        &v16);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = TraceLog::Providers::Reliability::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v29 = *(_DWORD *)(v7 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)byte_18003D4E1,
        v7 + 8,
        v8,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v9 = (char *)this + 288;
    if ( *((_DWORD *)v9 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v9 + 6) = 0;
    v10 = *(__int64 **)v9;
    while ( 1 )
    {
      v11 = *v10;
      if ( !*v10 )
        break;
      if ( (char *)v11 == v9 )
      {
        *v10 = *((_QWORD *)v9 + 2);
        break;
      }
      v10 = (__int64 *)(v11 + 16);
      *(_QWORD *)v9 = v11 + 16;
    }
    *(_QWORD *)v9 = 0;
  }
}

```

## disassembly

```asm
0x180020a70  push    rbp
0x180020a72  push    rbx
0x180020a73  push    rdi
0x180020a74  lea     rbp, [rsp+10h]
0x180020a79  sub     rsp, 130h
0x180020a80  mov     rbx, rcx
0x180020a83  mov     rdi, [rcx+110h]
0x180020a8a  mov     eax, [rdi+48h]
0x180020a8d  test    eax, eax
0x180020a8f  jns     loc_180020C49
0x180020a95  add     rdi, 50h ; 'P'
0x180020a99  cmp     eax, [rdi+8]
0x180020a9c  jnz     loc_180020C49
0x180020aa2  test    rdi, rdi
0x180020aa5  jz      loc_180020C49
0x180020aab  lea     rdx, [rbp+SRWLock]
0x180020aaf  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020ab4  mov     rax, [rbx+110h]
0x180020abb  mov     dword ptr [rax], 2
0x180020ac1  mov     rcx, [rbp+SRWLock]; SRWLock
0x180020ac5  test    rcx, rcx
0x180020ac8  jz      short loc_180020AD0
0x180020aca  call    cs:__imp_ReleaseSRWLockExclusive
0x180020ad0  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180020ad5  mov     r9, rax
0x180020ad8  mov     ecx, [rax]
0x180020ada  cmp     ecx, 4
0x180020add  jbe     loc_180020CCC
0x180020ae3  mov     rcx, [rdi+30h]
0x180020ae7  mov     [rbp+var_70], rcx
0x180020aeb  mov     ecx, [rdi+44h]
0x180020aee  mov     dword ptr [rbp+SRWLock], ecx
0x180020af1  mov     ecx, [rdi+10h]
0x180020af4  mov     [rbp+arg_8], ecx
0x180020af7  mov     rcx, [rdi+78h]
0x180020afb  mov     [rbp+var_68], rcx
0x180020aff  mov     rax, [rdi+70h]
0x180020b03  mov     [rbp+var_60], rax
0x180020b07  mov     eax, [rdi+68h]
0x180020b0a  mov     dword ptr [rbp+arg_10], eax
0x180020b0d  mov     rax, [rdi+60h]
0x180020b11  mov     [rbp+var_58], rax
0x180020b15  mov     rax, [rdi+58h]
0x180020b19  mov     [rbp+var_50], rax
0x180020b1d  mov     eax, [rdi+50h]
0x180020b20  mov     [rbp+arg_18], eax
0x180020b23  mov     rax, [rdi+48h]
0x180020b27  mov     [rbp+var_48], rax
0x180020b2b  mov     eax, [rdi+20h]
0x180020b2e  mov     [rbp+var_80], eax
0x180020b31  mov     rax, [rdi+18h]
0x180020b35  mov     [rbp+var_40], rax
0x180020b39  mov     eax, [rdi]
0x180020b3b  mov     [rbp+var_7C], eax
0x180020b3e  mov     rax, [rdi+80h]
0x180020b45  mov     [rbp+var_38], rax
0x180020b49  mov     eax, [rdi+40h]
0x180020b4c  mov     [rbp+var_78], eax
0x180020b4f  mov     rax, [rdi+38h]
0x180020b53  mov     [rbp+var_30], rax
0x180020b57  mov     eax, [rdi+8]
0x180020b5a  mov     [rbp+var_74], eax
0x180020b5d  mov     eax, 1000000h
0x180020b62  mov     [rbp+var_28], rax
0x180020b66  mov     [rbp+var_20], rax
0x180020b6a  mov     r8, [rbx+110h]
0x180020b71  add     r8, 8
0x180020b75  lea     rax, [rbp+var_70]
0x180020b79  mov     [rsp+140h+var_90], rax
0x180020b81  lea     rax, [rbp+SRWLock]
0x180020b85  mov     [rsp+140h+var_98], rax
0x180020b8d  lea     rax, [rbp+arg_8]
0x180020b91  mov     [rsp+140h+var_A0], rax
0x180020b99  lea     rax, [rbp+var_68]
0x180020b9d  mov     [rsp+140h+var_A8], rax
0x180020ba5  lea     rax, [rbp+var_60]
0x180020ba9  mov     [rsp+140h+var_B0], rax
0x180020bb1  lea     rax, [rbp+arg_10]
0x180020bb5  mov     [rsp+140h+var_B8], rax
0x180020bbd  lea     rax, [rbp+var_58]
0x180020bc1  mov     [rsp+140h+var_C0], rax
0x180020bc9  lea     rax, [rbp+var_50]
0x180020bcd  mov     [rsp+140h+var_C8], rax
0x180020bd2  lea     rax, [rbp+arg_18]
0x180020bd6  mov     [rsp+140h+var_D0], rax
0x180020bdb  lea     rax, [rbp+var_48]
0x180020bdf  mov     [rsp+140h+var_D8], rax
0x180020be4  lea     rax, [rbp+var_80]
0x180020be8  mov     [rsp+140h+var_E0], rax
0x180020bed  lea     rax, [rbp+var_40]
0x180020bf1  mov     [rsp+140h+var_E8], rax
0x180020bf6  lea     rax, [rbp+var_7C]
0x180020bfa  mov     [rsp+140h+var_F0], rax
0x180020bff  lea     rax, [rbp+var_38]
0x180020c03  mov     [rsp+140h+var_F8], rax
0x180020c08  lea     rax, [rbp+var_78]
0x180020c0c  mov     [rsp+140h+var_100], rax
0x180020c11  lea     rax, [rbp+var_30]
0x180020c15  mov     [rsp+140h+var_108], rax
0x180020c1a  lea     rax, [rbp+var_74]
0x180020c1e  mov     [rsp+140h+var_110], rax
0x180020c23  lea     rax, [rbp+var_28]
0x180020c27  mov     [rsp+140h+var_118], rax
0x180020c2c  lea     rax, [rbp+var_20]
0x180020c30  mov     [rsp+140h+var_120], rax
0x180020c35  lea     rdx, word_18003D53A
0x180020c3c  mov     rcx, r9
0x180020c3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020c44  jmp     loc_180020CCC
0x180020c49  lea     rdx, [rbp+SRWLock]
0x180020c4d  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020c52  mov     rax, [rbx+110h]
0x180020c59  mov     dword ptr [rax], 2
0x180020c5f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180020c63  test    rcx, rcx
0x180020c66  jz      short loc_180020C6E
0x180020c68  call    cs:__imp_ReleaseSRWLockExclusive
0x180020c6e  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180020c73  mov     rdi, rax
0x180020c76  mov     ecx, [rax]
0x180020c78  cmp     ecx, 4
0x180020c7b  jbe     short loc_180020CCC
0x180020c7d  call    cs:__imp_GetCurrentThreadId
0x180020c83  mov     dword ptr [rbp+SRWLock], eax
0x180020c86  mov     r8, [rbx+110h]
0x180020c8d  mov     ecx, [r8+48h]
0x180020c91  mov     [rbp+arg_8], ecx
0x180020c94  mov     eax, 1000000h
0x180020c99  mov     [rbp+arg_10], rax
0x180020c9d  add     r8, 8
0x180020ca1  lea     rax, [rbp+SRWLock]
0x180020ca5  mov     [rsp+140h+var_110], rax
0x180020caa  lea     rax, [rbp+arg_8]
0x180020cae  mov     [rsp+140h+var_118], rax
0x180020cb3  lea     rax, [rbp+arg_10]
0x180020cb7  mov     [rsp+140h+var_120], rax
0x180020cbc  lea     rdx, byte_18003D4E1
0x180020cc3  mov     rcx, rdi
0x180020cc6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020ccb  nop
0x180020ccc  cmp     dword ptr [rbx+138h], 0
0x180020cd3  jz      short loc_180020D33
0x180020cd5  add     rbx, 120h
0x180020cdc  call    cs:__imp_GetCurrentThreadId
0x180020ce2  cmp     [rbx+18h], eax
0x180020ce5  jz      short loc_180020D03
0x180020ce7  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180020cee  test    rax, rax
0x180020cf1  jz      short loc_180020D03
0x180020cf3  mov     rdx, [rbp+8]
0x180020cf7  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180020cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d03  mov     dword ptr [rbx+18h], 0
0x180020d0a  mov     rcx, [rbx]
0x180020d0d  jmp     short loc_180020D1B
0x180020d0f  cmp     rax, rbx
0x180020d12  jz      short loc_180020D25
0x180020d14  lea     rcx, [rax+10h]
0x180020d18  mov     [rbx], rcx
0x180020d1b  mov     rax, [rcx]
0x180020d1e  test    rax, rax
0x180020d21  jnz     short loc_180020D0F
0x180020d23  jmp     short loc_180020D2C
0x180020d25  mov     rax, [rbx+10h]
0x180020d29  mov     [rcx], rax
0x180020d2c  mov     qword ptr [rbx], 0
0x180020d33  add     rsp, 130h
0x180020d3a  pop     rdi
0x180020d3b  pop     rbx
0x180020d3c  pop     rbp
0x180020d3d  retn
```
