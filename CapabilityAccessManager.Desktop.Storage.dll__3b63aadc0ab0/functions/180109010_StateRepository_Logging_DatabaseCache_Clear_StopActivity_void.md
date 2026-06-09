# StateRepository::Logging::DatabaseCache::Clear::StopActivity(void)

- ea: `0x180109010`
- end: `0x1801092e1`
- name: `?StopActivity@Clear@DatabaseCache@Logging@StateRepository@@MEAAXXZ`
- size: `721`
- prototype: `void __fastcall(StateRepository::Logging::DatabaseCache::Clear *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001b58`
- `0x180001e6c`
- `0x1800f9e44`
- `0x1800fb134`
- `0x180109010`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010906a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010920c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010906a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010920c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010927f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010927f`

## string_xrefs

- `0x18010929a`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StateRepository::Logging::DatabaseCache::Clear::StopActivity(
        StateRepository::Logging::DatabaseCache::Clear *this)
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
  const char *v16; // [rsp+D0h] [rbp-70h] BYREF
  int *v17; // [rsp+D8h] [rbp-68h] BYREF
  const char *v18; // [rsp+E0h] [rbp-60h] BYREF
  int *v19; // [rsp+E8h] [rbp-58h] BYREF
  const char *v20; // [rsp+F0h] [rbp-50h] BYREF
  const char *v21; // [rsp+F8h] [rbp-48h] BYREF
  int *v22; // [rsp+100h] [rbp-40h] BYREF
  const char *v23; // [rsp+108h] [rbp-38h] BYREF
  const char *v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v26[4]; // [rsp+120h] [rbp-20h] BYREF
  void *retaddr; // [rsp+148h] [rbp+8h]
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = StateRepository::Tracing::Service::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v16 = (const char *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v29 = v4[4];
      v17 = (int *)*((_QWORD *)v4 + 15);
      v18 = (const char *)*((_QWORD *)v4 + 14);
      LODWORD(v30) = v4[26];
      v19 = (int *)*((_QWORD *)v4 + 12);
      v20 = (const char *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v21 = (const char *)*((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = (int *)*((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = (const char *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = (const char *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&dword_18012A894,
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
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = StateRepository::Tracing::Service::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v29 = *(_DWORD *)(v7 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&dword_18012A9D4,
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
0x180109010  push    rbp
0x180109012  push    rbx
0x180109013  push    rdi
0x180109014  lea     rbp, [rsp+10h]
0x180109019  sub     rsp, 130h
0x180109020  mov     rbx, rcx
0x180109023  mov     rdi, [rcx+110h]
0x18010902a  mov     eax, [rdi+48h]
0x18010902d  test    eax, eax
0x18010902f  jns     loc_1801091ED
0x180109035  add     rdi, 50h ; 'P'
0x180109039  cmp     eax, [rdi+8]
0x18010903c  jnz     loc_1801091ED
0x180109042  test    rdi, rdi
0x180109045  jz      loc_1801091ED
0x18010904b  lea     rdx, [rbp+SRWLock]
0x18010904f  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180109054  mov     rax, [rbx+110h]
0x18010905b  mov     dword ptr [rax], 2
0x180109061  mov     rcx, [rbp+SRWLock]; SRWLock
0x180109065  test    rcx, rcx
0x180109068  jz      short loc_180109071
0x18010906a  call    cs:__imp_ReleaseSRWLockExclusive
0x180109070  nop
0x180109071  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180109076  mov     r9, rax
0x180109079  mov     ecx, [rax]
0x18010907b  cmp     ecx, 5
0x18010907e  jbe     loc_18010926F
0x180109084  mov     rcx, [rdi+30h]
0x180109088  mov     [rbp+var_70], rcx
0x18010908c  mov     ecx, [rdi+44h]
0x18010908f  mov     dword ptr [rbp+SRWLock], ecx
0x180109092  mov     ecx, [rdi+10h]
0x180109095  mov     [rbp+arg_8], ecx
0x180109098  mov     rcx, [rdi+78h]
0x18010909c  mov     [rbp+var_68], rcx
0x1801090a0  mov     rax, [rdi+70h]
0x1801090a4  mov     [rbp+var_60], rax
0x1801090a8  mov     eax, [rdi+68h]
0x1801090ab  mov     dword ptr [rbp+arg_10], eax
0x1801090ae  mov     rax, [rdi+60h]
0x1801090b2  mov     [rbp+var_58], rax
0x1801090b6  mov     rax, [rdi+58h]
0x1801090ba  mov     [rbp+var_50], rax
0x1801090be  mov     eax, [rdi+50h]
0x1801090c1  mov     [rbp+arg_18], eax
0x1801090c4  mov     rax, [rdi+48h]
0x1801090c8  mov     [rbp+var_48], rax
0x1801090cc  mov     eax, [rdi+20h]
0x1801090cf  mov     [rbp+var_80], eax
0x1801090d2  mov     rax, [rdi+18h]
0x1801090d6  mov     [rbp+var_40], rax
0x1801090da  mov     eax, [rdi]
0x1801090dc  mov     [rbp+var_7C], eax
0x1801090df  mov     rax, [rdi+80h]
0x1801090e6  mov     [rbp+var_38], rax
0x1801090ea  mov     eax, [rdi+40h]
0x1801090ed  mov     [rbp+var_78], eax
0x1801090f0  mov     rax, [rdi+38h]
0x1801090f4  mov     [rbp+var_30], rax
0x1801090f8  mov     eax, [rdi+8]
0x1801090fb  mov     [rbp+var_74], eax
0x1801090fe  mov     [rbp+var_28], 1000000h
0x180109106  mov     [rbp+var_20], 0
0x18010910e  mov     r8, [rbx+110h]
0x180109115  add     r8, 8
0x180109119  lea     rax, [rbp+var_70]
0x18010911d  mov     [rsp+140h+var_90], rax
0x180109125  lea     rax, [rbp+SRWLock]
0x180109129  mov     [rsp+140h+var_98], rax
0x180109131  lea     rax, [rbp+arg_8]
0x180109135  mov     [rsp+140h+var_A0], rax
0x18010913d  lea     rax, [rbp+var_68]
0x180109141  mov     [rsp+140h+var_A8], rax
0x180109149  lea     rax, [rbp+var_60]
0x18010914d  mov     [rsp+140h+var_B0], rax
0x180109155  lea     rax, [rbp+arg_10]
0x180109159  mov     [rsp+140h+var_B8], rax
0x180109161  lea     rax, [rbp+var_58]
0x180109165  mov     [rsp+140h+var_C0], rax
0x18010916d  lea     rax, [rbp+var_50]
0x180109171  mov     [rsp+140h+var_C8], rax
0x180109176  lea     rax, [rbp+arg_18]
0x18010917a  mov     [rsp+140h+var_D0], rax
0x18010917f  lea     rax, [rbp+var_48]
0x180109183  mov     [rsp+140h+var_D8], rax
0x180109188  lea     rax, [rbp+var_80]
0x18010918c  mov     [rsp+140h+var_E0], rax
0x180109191  lea     rax, [rbp+var_40]
0x180109195  mov     [rsp+140h+var_E8], rax
0x18010919a  lea     rax, [rbp+var_7C]
0x18010919e  mov     [rsp+140h+var_F0], rax
0x1801091a3  lea     rax, [rbp+var_38]
0x1801091a7  mov     [rsp+140h+var_F8], rax
0x1801091ac  lea     rax, [rbp+var_78]
0x1801091b0  mov     [rsp+140h+var_100], rax
0x1801091b5  lea     rax, [rbp+var_30]
0x1801091b9  mov     [rsp+140h+var_108], rax
0x1801091be  lea     rax, [rbp+var_74]
0x1801091c2  mov     [rsp+140h+var_110], rax
0x1801091c7  lea     rax, [rbp+var_28]
0x1801091cb  mov     [rsp+140h+var_118], rax
0x1801091d0  lea     rax, [rbp+var_20]
0x1801091d4  mov     [rsp+140h+var_120], rax
0x1801091d9  lea     rdx, dword_18012A894
0x1801091e0  mov     rcx, r9
0x1801091e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801091e8  jmp     loc_18010926F
0x1801091ed  lea     rdx, [rbp+SRWLock]
0x1801091f1  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1801091f6  mov     rax, [rbx+110h]
0x1801091fd  mov     dword ptr [rax], 2
0x180109203  mov     rcx, [rbp+SRWLock]; SRWLock
0x180109207  test    rcx, rcx
0x18010920a  jz      short loc_180109213
0x18010920c  call    cs:__imp_ReleaseSRWLockExclusive
0x180109212  nop
0x180109213  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180109218  mov     rdi, rax
0x18010921b  mov     ecx, [rax]
0x18010921d  cmp     ecx, 5
0x180109220  jbe     short loc_18010926F
0x180109222  call    cs:__imp_GetCurrentThreadId
0x180109228  mov     dword ptr [rbp+SRWLock], eax
0x18010922b  mov     r8, [rbx+110h]
0x180109232  mov     ecx, [r8+48h]
0x180109236  mov     [rbp+arg_8], ecx
0x180109239  mov     [rbp+arg_10], 0
0x180109241  add     r8, 8
0x180109245  lea     rax, [rbp+SRWLock]
0x180109249  mov     [rsp+140h+var_110], rax
0x18010924e  lea     rax, [rbp+arg_8]
0x180109252  mov     [rsp+140h+var_118], rax
0x180109257  lea     rax, [rbp+arg_10]
0x18010925b  mov     [rsp+140h+var_120], rax
0x180109260  lea     rdx, dword_18012A9D4
0x180109267  mov     rcx, rdi
0x18010926a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010926f  cmp     dword ptr [rbx+138h], 0
0x180109276  jz      short loc_1801092D6
0x180109278  add     rbx, 120h
0x18010927f  call    cs:__imp_GetCurrentThreadId
0x180109285  cmp     [rbx+18h], eax
0x180109288  jz      short loc_1801092A6
0x18010928a  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180109291  test    rax, rax
0x180109294  jz      short loc_1801092A6
0x180109296  mov     rdx, [rbp+8]
0x18010929a  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1801092a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801092a6  mov     dword ptr [rbx+18h], 0
0x1801092ad  mov     rcx, [rbx]
0x1801092b0  jmp     short loc_1801092BE
0x1801092b2  cmp     rax, rbx
0x1801092b5  jz      short loc_1801092C8
0x1801092b7  lea     rcx, [rax+10h]
0x1801092bb  mov     [rbx], rcx
0x1801092be  mov     rax, [rcx]
0x1801092c1  test    rax, rax
0x1801092c4  jnz     short loc_1801092B2
0x1801092c6  jmp     short loc_1801092CF
0x1801092c8  mov     rax, [rbx+10h]
0x1801092cc  mov     [rcx], rax
0x1801092cf  mov     qword ptr [rbx], 0
0x1801092d6  add     rsp, 130h
0x1801092dd  pop     rdi
0x1801092de  pop     rbx
0x1801092df  pop     rbp
0x1801092e0  retn
```
