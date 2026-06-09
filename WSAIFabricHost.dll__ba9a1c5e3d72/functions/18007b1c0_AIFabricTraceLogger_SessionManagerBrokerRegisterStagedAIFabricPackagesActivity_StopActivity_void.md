# AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::StopActivity(void)

- ea: `0x18007b1c0`
- end: `0x18007b490`
- name: `?StopActivity@SessionManagerBrokerRegisterStagedAIFabricPackagesActivity@AIFabricTraceLogger@@MEAAXXZ`
- size: `720`
- prototype: `void __fastcall(AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002428`
- `0x18000367c`
- `0x1800625bc`
- `0x180065380`
- `0x18007b1c0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b21a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b3bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b21a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b3bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b42e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b42e`

## string_xrefs

- `0x18007b449`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity::StopActivity(
        AIFabricTraceLogger::SessionManagerBrokerRegisterStagedAIFabricPackagesActivity *this)
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
  const wchar_t *v16; // [rsp+D0h] [rbp-70h] BYREF
  const wchar_t *v17; // [rsp+D8h] [rbp-68h] BYREF
  const wchar_t *v18; // [rsp+E0h] [rbp-60h] BYREF
  const wchar_t *v19; // [rsp+E8h] [rbp-58h] BYREF
  const wchar_t *v20; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v21; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v22; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v23; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v24; // [rsp+110h] [rbp-30h] BYREF
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
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = AIFabricTraceLogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v16 = (const wchar_t *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v29 = v4[4];
      v17 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(v30) = v4[26];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v20 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)byte_18009E969,
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
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = AIFabricTraceLogger::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v29 = *(_DWORD *)(v7 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&word_18009EADE,
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
0x18007b1c0  push    rbp
0x18007b1c2  push    rbx
0x18007b1c3  push    rdi
0x18007b1c4  lea     rbp, [rsp+10h]
0x18007b1c9  sub     rsp, 130h
0x18007b1d0  mov     rbx, rcx
0x18007b1d3  mov     rdi, [rcx+110h]
0x18007b1da  mov     eax, [rdi+48h]
0x18007b1dd  test    eax, eax
0x18007b1df  jns     loc_18007B39C
0x18007b1e5  add     rdi, 50h ; 'P'
0x18007b1e9  cmp     eax, [rdi+8]
0x18007b1ec  jnz     loc_18007B39C
0x18007b1f2  test    rdi, rdi
0x18007b1f5  jz      loc_18007B39C
0x18007b1fb  lea     rdx, [rbp+SRWLock]
0x18007b1ff  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007b204  mov     rax, [rbx+110h]
0x18007b20b  mov     dword ptr [rax], 2
0x18007b211  mov     rcx, [rbp+SRWLock]; SRWLock
0x18007b215  test    rcx, rcx
0x18007b218  jz      short loc_18007B220
0x18007b21a  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b220  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007b225  mov     r9, rax
0x18007b228  mov     ecx, [rax]
0x18007b22a  cmp     ecx, 5
0x18007b22d  jbe     loc_18007B41E
0x18007b233  mov     rcx, [rdi+30h]
0x18007b237  mov     [rbp+var_70], rcx
0x18007b23b  mov     ecx, [rdi+44h]
0x18007b23e  mov     dword ptr [rbp+SRWLock], ecx
0x18007b241  mov     ecx, [rdi+10h]
0x18007b244  mov     [rbp+arg_8], ecx
0x18007b247  mov     rcx, [rdi+78h]
0x18007b24b  mov     [rbp+var_68], rcx
0x18007b24f  mov     rax, [rdi+70h]
0x18007b253  mov     [rbp+var_60], rax
0x18007b257  mov     eax, [rdi+68h]
0x18007b25a  mov     dword ptr [rbp+arg_10], eax
0x18007b25d  mov     rax, [rdi+60h]
0x18007b261  mov     [rbp+var_58], rax
0x18007b265  mov     rax, [rdi+58h]
0x18007b269  mov     [rbp+var_50], rax
0x18007b26d  mov     eax, [rdi+50h]
0x18007b270  mov     [rbp+arg_18], eax
0x18007b273  mov     rax, [rdi+48h]
0x18007b277  mov     [rbp+var_48], rax
0x18007b27b  mov     eax, [rdi+20h]
0x18007b27e  mov     [rbp+var_80], eax
0x18007b281  mov     rax, [rdi+18h]
0x18007b285  mov     [rbp+var_40], rax
0x18007b289  mov     eax, [rdi]
0x18007b28b  mov     [rbp+var_7C], eax
0x18007b28e  mov     rax, [rdi+80h]
0x18007b295  mov     [rbp+var_38], rax
0x18007b299  mov     eax, [rdi+40h]
0x18007b29c  mov     [rbp+var_78], eax
0x18007b29f  mov     rax, [rdi+38h]
0x18007b2a3  mov     [rbp+var_30], rax
0x18007b2a7  mov     eax, [rdi+8]
0x18007b2aa  mov     [rbp+var_74], eax
0x18007b2ad  mov     [rbp+var_28], 1000000h
0x18007b2b5  mov     [rbp+var_20], 0
0x18007b2bd  mov     r8, [rbx+110h]
0x18007b2c4  add     r8, 8
0x18007b2c8  lea     rax, [rbp+var_70]
0x18007b2cc  mov     [rsp+140h+var_90], rax
0x18007b2d4  lea     rax, [rbp+SRWLock]
0x18007b2d8  mov     [rsp+140h+var_98], rax
0x18007b2e0  lea     rax, [rbp+arg_8]
0x18007b2e4  mov     [rsp+140h+var_A0], rax
0x18007b2ec  lea     rax, [rbp+var_68]
0x18007b2f0  mov     [rsp+140h+var_A8], rax
0x18007b2f8  lea     rax, [rbp+var_60]
0x18007b2fc  mov     [rsp+140h+var_B0], rax
0x18007b304  lea     rax, [rbp+arg_10]
0x18007b308  mov     [rsp+140h+var_B8], rax
0x18007b310  lea     rax, [rbp+var_58]
0x18007b314  mov     [rsp+140h+var_C0], rax
0x18007b31c  lea     rax, [rbp+var_50]
0x18007b320  mov     [rsp+140h+var_C8], rax
0x18007b325  lea     rax, [rbp+arg_18]
0x18007b329  mov     [rsp+140h+var_D0], rax
0x18007b32e  lea     rax, [rbp+var_48]
0x18007b332  mov     [rsp+140h+var_D8], rax
0x18007b337  lea     rax, [rbp+var_80]
0x18007b33b  mov     [rsp+140h+var_E0], rax
0x18007b340  lea     rax, [rbp+var_40]
0x18007b344  mov     [rsp+140h+var_E8], rax
0x18007b349  lea     rax, [rbp+var_7C]
0x18007b34d  mov     [rsp+140h+var_F0], rax
0x18007b352  lea     rax, [rbp+var_38]
0x18007b356  mov     [rsp+140h+var_F8], rax
0x18007b35b  lea     rax, [rbp+var_78]
0x18007b35f  mov     [rsp+140h+var_100], rax
0x18007b364  lea     rax, [rbp+var_30]
0x18007b368  mov     [rsp+140h+var_108], rax
0x18007b36d  lea     rax, [rbp+var_74]
0x18007b371  mov     [rsp+140h+var_110], rax
0x18007b376  lea     rax, [rbp+var_28]
0x18007b37a  mov     [rsp+140h+var_118], rax
0x18007b37f  lea     rax, [rbp+var_20]
0x18007b383  mov     [rsp+140h+var_120], rax
0x18007b388  lea     rdx, byte_18009E969
0x18007b38f  mov     rcx, r9
0x18007b392  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007b397  jmp     loc_18007B41E
0x18007b39c  lea     rdx, [rbp+SRWLock]
0x18007b3a0  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18007b3a5  mov     rax, [rbx+110h]
0x18007b3ac  mov     dword ptr [rax], 2
0x18007b3b2  mov     rcx, [rbp+SRWLock]; SRWLock
0x18007b3b6  test    rcx, rcx
0x18007b3b9  jz      short loc_18007B3C1
0x18007b3bb  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b3c1  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18007b3c6  mov     rdi, rax
0x18007b3c9  mov     ecx, [rax]
0x18007b3cb  cmp     ecx, 5
0x18007b3ce  jbe     short loc_18007B41E
0x18007b3d0  call    cs:__imp_GetCurrentThreadId
0x18007b3d6  mov     dword ptr [rbp+SRWLock], eax
0x18007b3d9  mov     r8, [rbx+110h]
0x18007b3e0  mov     ecx, [r8+48h]
0x18007b3e4  mov     [rbp+arg_8], ecx
0x18007b3e7  mov     [rbp+arg_10], 0
0x18007b3ef  add     r8, 8
0x18007b3f3  lea     rax, [rbp+SRWLock]
0x18007b3f7  mov     [rsp+140h+var_110], rax
0x18007b3fc  lea     rax, [rbp+arg_8]
0x18007b400  mov     [rsp+140h+var_118], rax
0x18007b405  lea     rax, [rbp+arg_10]
0x18007b409  mov     [rsp+140h+var_120], rax
0x18007b40e  lea     rdx, word_18009EADE
0x18007b415  mov     rcx, rdi
0x18007b418  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007b41d  nop
0x18007b41e  cmp     dword ptr [rbx+138h], 0
0x18007b425  jz      short loc_18007B485
0x18007b427  add     rbx, 120h
0x18007b42e  call    cs:__imp_GetCurrentThreadId
0x18007b434  cmp     [rbx+18h], eax
0x18007b437  jz      short loc_18007B455
0x18007b439  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18007b440  test    rax, rax
0x18007b443  jz      short loc_18007B455
0x18007b445  mov     rdx, [rbp+8]
0x18007b449  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18007b450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b455  mov     dword ptr [rbx+18h], 0
0x18007b45c  mov     rcx, [rbx]
0x18007b45f  jmp     short loc_18007B46D
0x18007b461  cmp     rax, rbx
0x18007b464  jz      short loc_18007B477
0x18007b466  lea     rcx, [rax+10h]
0x18007b46a  mov     [rbx], rcx
0x18007b46d  mov     rax, [rcx]
0x18007b470  test    rax, rax
0x18007b473  jnz     short loc_18007B461
0x18007b475  jmp     short loc_18007B47E
0x18007b477  mov     rax, [rbx+10h]
0x18007b47b  mov     [rcx], rax
0x18007b47e  mov     qword ptr [rbx], 0
0x18007b485  add     rsp, 130h
0x18007b48c  pop     rdi
0x18007b48d  pop     rbx
0x18007b48e  pop     rbp
0x18007b48f  retn
```
