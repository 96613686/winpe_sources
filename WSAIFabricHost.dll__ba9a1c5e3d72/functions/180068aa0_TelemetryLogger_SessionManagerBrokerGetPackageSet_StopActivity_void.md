# TelemetryLogger::SessionManagerBrokerGetPackageSet::StopActivity(void)

- ea: `0x180068aa0`
- end: `0x180068d85`
- name: `?StopActivity@SessionManagerBrokerGetPackageSet@TelemetryLogger@@MEAAXXZ`
- size: `741`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerGetPackageSet *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001100`
- `0x18000367c`
- `0x180017790`
- `0x1800625bc`
- `0x180068aa0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068afa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068afa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068d23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068d23`

## string_xrefs

- `0x180068d3e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TelemetryLogger::SessionManagerBrokerGetPackageSet::StopActivity(
        TelemetryLogger::SessionManagerBrokerGetPackageSet *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+A0h] [rbp-19h] BYREF
  int v13; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v14; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v15; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v16; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v17; // [rsp+C0h] [rbp+7h] BYREF
  const wchar_t *v18; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v19; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v20; // [rsp+D8h] [rbp+1Fh] BYREF
  const wchar_t *v21; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v22; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v23[4]; // [rsp+F0h] [rbp+37h] BYREF
  void *retaddr; // [rsp+118h] [rbp+5Fh]
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v14 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v15 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v16 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v17 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v26 = v4[20];
      v18 = (const wchar_t *)*((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v28 = *v4;
      v20 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v12 = v4[16];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v13 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v5,
        (__int64)&word_18009DD66,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v13,
        &v21,
        (__int64)&v12,
        &v20,
        (__int64)&v28,
        &v19,
        (__int64)&v27,
        &v18,
        (__int64)&v26,
        &v17,
        &v16,
        (__int64)&SRWLock,
        &v15,
        &v14);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v26 = *(_DWORD *)(v7 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&dword_18009DD04,
        v7 + 8,
        v8,
        (__int64)&v27,
        (__int64)&v26,
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
0x180068aa0  push    rbp
0x180068aa2  push    rbx
0x180068aa3  push    rdi
0x180068aa4  lea     rbp, [rsp-47h]
0x180068aa9  sub     rsp, 100h
0x180068ab0  mov     rbx, rcx
0x180068ab3  mov     rdi, [rcx+110h]
0x180068aba  mov     eax, [rdi+48h]
0x180068abd  test    eax, eax
0x180068abf  jns     loc_180068C6D
0x180068ac5  add     rdi, 50h ; 'P'
0x180068ac9  cmp     eax, [rdi+8]
0x180068acc  jnz     loc_180068C6D
0x180068ad2  test    rdi, rdi
0x180068ad5  jz      loc_180068C6D
0x180068adb  lea     rdx, [rbp+57h+SRWLock]
0x180068adf  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068ae4  mov     rax, [rbx+110h]
0x180068aeb  mov     dword ptr [rax], 2
0x180068af1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180068af5  test    rcx, rcx
0x180068af8  jz      short loc_180068B00
0x180068afa  call    cs:__imp_ReleaseSRWLockExclusive
0x180068b00  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068b05  mov     r9, [rax+8]
0x180068b09  mov     eax, [r9]
0x180068b0c  cmp     eax, 5
0x180068b0f  jbe     loc_180068D13
0x180068b15  mov     rdx, [r9+18h]
0x180068b19  mov     rax, [r9+10h]
0x180068b1d  mov     rcx, 200000000000h
0x180068b27  test    rcx, rax
0x180068b2a  jz      loc_180068D13
0x180068b30  mov     rax, rdx
0x180068b33  and     rax, rcx
0x180068b36  cmp     rax, rdx
0x180068b39  jnz     loc_180068D13
0x180068b3f  mov     rax, [rdi+78h]
0x180068b43  mov     [rbp+57h+var_68], rax
0x180068b47  mov     rax, [rdi+70h]
0x180068b4b  mov     [rbp+57h+var_60], rax
0x180068b4f  mov     eax, [rdi+68h]
0x180068b52  mov     dword ptr [rbp+57h+SRWLock], eax
0x180068b55  mov     rax, [rdi+60h]
0x180068b59  mov     [rbp+57h+var_58], rax
0x180068b5d  mov     rax, [rdi+58h]
0x180068b61  mov     [rbp+57h+var_50], rax
0x180068b65  mov     eax, [rdi+50h]
0x180068b68  mov     [rbp+57h+arg_8], eax
0x180068b6b  mov     rax, [rdi+48h]
0x180068b6f  mov     [rbp+57h+var_48], rax
0x180068b73  mov     eax, [rdi+20h]
0x180068b76  mov     dword ptr [rbp+57h+arg_10], eax
0x180068b79  mov     rax, [rdi+18h]
0x180068b7d  mov     [rbp+57h+var_40], rax
0x180068b81  mov     eax, [rdi]
0x180068b83  mov     [rbp+57h+arg_18], eax
0x180068b86  mov     rax, [rdi+80h]
0x180068b8d  mov     [rbp+57h+var_38], rax
0x180068b91  mov     eax, [rdi+40h]
0x180068b94  mov     [rbp+57h+var_70], eax
0x180068b97  mov     rax, [rdi+38h]
0x180068b9b  mov     [rbp+57h+var_30], rax
0x180068b9f  mov     eax, [rdi+8]
0x180068ba2  mov     [rbp+57h+var_6C], eax
0x180068ba5  mov     eax, 1000000h
0x180068baa  mov     [rbp+57h+var_28], rax
0x180068bae  mov     [rbp+57h+var_20], rax
0x180068bb2  mov     r8, [rbx+110h]
0x180068bb9  add     r8, 8
0x180068bbd  lea     rax, [rbp+57h+var_68]
0x180068bc1  mov     [rsp+110h+var_78], rax
0x180068bc9  lea     rax, [rbp+57h+var_60]
0x180068bcd  mov     [rsp+110h+var_80], rax
0x180068bd5  lea     rax, [rbp+57h+SRWLock]
0x180068bd9  mov     [rsp+110h+var_88], rax
0x180068be1  lea     rax, [rbp+57h+var_58]
0x180068be5  mov     [rsp+110h+var_90], rax
0x180068bed  lea     rax, [rbp+57h+var_50]
0x180068bf1  mov     [rsp+110h+var_98], rax
0x180068bf6  lea     rax, [rbp+57h+arg_8]
0x180068bfa  mov     [rsp+110h+var_A0], rax
0x180068bff  lea     rax, [rbp+57h+var_48]
0x180068c03  mov     [rsp+110h+var_A8], rax
0x180068c08  lea     rax, [rbp+57h+arg_10]
0x180068c0c  mov     [rsp+110h+var_B0], rax
0x180068c11  lea     rax, [rbp+57h+var_40]
0x180068c15  mov     [rsp+110h+var_B8], rax
0x180068c1a  lea     rax, [rbp+57h+arg_18]
0x180068c1e  mov     [rsp+110h+var_C0], rax
0x180068c23  lea     rax, [rbp+57h+var_38]
0x180068c27  mov     [rsp+110h+var_C8], rax
0x180068c2c  lea     rax, [rbp+57h+var_70]
0x180068c30  mov     [rsp+110h+var_D0], rax
0x180068c35  lea     rax, [rbp+57h+var_30]
0x180068c39  mov     [rsp+110h+var_D8], rax
0x180068c3e  lea     rax, [rbp+57h+var_6C]
0x180068c42  mov     [rsp+110h+var_E0], rax
0x180068c47  lea     rax, [rbp+57h+var_28]
0x180068c4b  mov     [rsp+110h+var_E8], rax
0x180068c50  lea     rax, [rbp+57h+var_20]
0x180068c54  mov     [rsp+110h+var_F0], rax
0x180068c59  lea     rdx, word_18009DD66
0x180068c60  mov     rcx, r9
0x180068c63  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180068c68  jmp     loc_180068D13
0x180068c6d  lea     rdx, [rbp+57h+SRWLock]
0x180068c71  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068c76  mov     rax, [rbx+110h]
0x180068c7d  mov     dword ptr [rax], 2
0x180068c83  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180068c87  test    rcx, rcx
0x180068c8a  jz      short loc_180068C92
0x180068c8c  call    cs:__imp_ReleaseSRWLockExclusive
0x180068c92  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068c97  mov     rdi, [rax+8]
0x180068c9b  mov     eax, [rdi]
0x180068c9d  cmp     eax, 5
0x180068ca0  jbe     short loc_180068D13
0x180068ca2  mov     rdx, [rdi+18h]
0x180068ca6  mov     rax, [rdi+10h]
0x180068caa  mov     rcx, 200000000000h
0x180068cb4  test    rcx, rax
0x180068cb7  jz      short loc_180068D13
0x180068cb9  mov     rax, rdx
0x180068cbc  and     rax, rcx
0x180068cbf  cmp     rax, rdx
0x180068cc2  jnz     short loc_180068D13
0x180068cc4  call    cs:__imp_GetCurrentThreadId
0x180068cca  mov     dword ptr [rbp+57h+SRWLock], eax
0x180068ccd  mov     r8, [rbx+110h]
0x180068cd4  mov     eax, [r8+48h]
0x180068cd8  mov     [rbp+57h+arg_8], eax
0x180068cdb  mov     eax, 1000000h
0x180068ce0  mov     [rbp+57h+arg_10], rax
0x180068ce4  add     r8, 8
0x180068ce8  lea     rax, [rbp+57h+SRWLock]
0x180068cec  mov     [rsp+110h+var_E0], rax
0x180068cf1  lea     rax, [rbp+57h+arg_8]
0x180068cf5  mov     [rsp+110h+var_E8], rax
0x180068cfa  lea     rax, [rbp+57h+arg_10]
0x180068cfe  mov     [rsp+110h+var_F0], rax
0x180068d03  lea     rdx, dword_18009DD04
0x180068d0a  mov     rcx, rdi
0x180068d0d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180068d12  nop
0x180068d13  cmp     dword ptr [rbx+138h], 0
0x180068d1a  jz      short loc_180068D7A
0x180068d1c  add     rbx, 120h
0x180068d23  call    cs:__imp_GetCurrentThreadId
0x180068d29  cmp     [rbx+18h], eax
0x180068d2c  jz      short loc_180068D4A
0x180068d2e  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180068d35  test    rax, rax
0x180068d38  jz      short loc_180068D4A
0x180068d3a  mov     rdx, [rbp+5Fh]
0x180068d3e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180068d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d4a  mov     dword ptr [rbx+18h], 0
0x180068d51  mov     rcx, [rbx]
0x180068d54  jmp     short loc_180068D62
0x180068d56  cmp     rax, rbx
0x180068d59  jz      short loc_180068D6C
0x180068d5b  lea     rcx, [rax+10h]
0x180068d5f  mov     [rbx], rcx
0x180068d62  mov     rax, [rcx]
0x180068d65  test    rax, rax
0x180068d68  jnz     short loc_180068D56
0x180068d6a  jmp     short loc_180068D73
0x180068d6c  mov     rax, [rbx+10h]
0x180068d70  mov     [rcx], rax
0x180068d73  mov     qword ptr [rbx], 0
0x180068d7a  add     rsp, 100h
0x180068d81  pop     rdi
0x180068d82  pop     rbx
0x180068d83  pop     rbp
0x180068d84  retn
```
