# SsdmTelemetryProvider::PersonalizationDuration::StopActivity(void)

- ea: `0x18000b840`
- end: `0x18000bb83`
- name: `?StopActivity@PersonalizationDuration@SsdmTelemetryProvider@@MEAAXXZ`
- size: `835`
- prototype: `void __fastcall(SsdmTelemetryProvider::PersonalizationDuration *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001008`
- `0x18000163c`
- `0x1800063b4`
- `0x18000a8cc`
- `0x18000b840`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bb0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba44`

## string_xrefs

- `0x18000bb26`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall SsdmTelemetryProvider::PersonalizationDuration::StopActivity(
        SsdmTelemetryProvider::PersonalizationDuration *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  char *v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v13; // [rsp+B0h] [rbp-70h] BYREF
  int v14; // [rsp+B8h] [rbp-68h] BYREF
  int v15; // [rsp+BCh] [rbp-64h] BYREF
  int v16; // [rsp+C0h] [rbp-60h] BYREF
  int v17; // [rsp+C4h] [rbp-5Ch] BYREF
  char *v18; // [rsp+C8h] [rbp-58h] BYREF
  const wchar_t *v19; // [rsp+D0h] [rbp-50h] BYREF
  char *v20; // [rsp+D8h] [rbp-48h] BYREF
  const wchar_t *v21; // [rsp+E0h] [rbp-40h] BYREF
  const wchar_t *v22; // [rsp+E8h] [rbp-38h] BYREF
  char *v23; // [rsp+F0h] [rbp-30h] BYREF
  const wchar_t *v24; // [rsp+F8h] [rbp-28h] BYREF
  const wchar_t *v25; // [rsp+100h] [rbp-20h] BYREF
  __int64 v26; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v27[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v28; // [rsp+130h] [rbp+10h]
  __int64 v29; // [rsp+138h] [rbp+18h]
  int *v30; // [rsp+140h] [rbp+20h]
  __int64 v31; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v33; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v18 = (char *)*((_QWORD *)v4 + 15);
      v19 = (const wchar_t *)*((_QWORD *)v4 + 14);
      v14 = v4[26];
      v20 = (char *)*((_QWORD *)v4 + 12);
      v21 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v15 = v4[20];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 9);
      v16 = v4[8];
      v23 = (char *)*((_QWORD *)v4 + 3);
      v17 = *v4;
      v24 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v25 = (const wchar_t *)*((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v13 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v5,
        (__int64)&byte_1800178E7,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)&v13,
        (__int64)&v26,
        (__int64)&SRWLock,
        &v25,
        (__int64)&v11,
        &v24,
        (__int64)&v17,
        &v23,
        (__int64)&v16,
        &v22,
        (__int64)&v15,
        &v21,
        &v20,
        (__int64)&v14,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v13);
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v6 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v11 = *(_DWORD *)(v7 + 72);
      v13 = 0;
      p_SRWLock = &SRWLock;
      v33 = 4;
      v30 = &v11;
      v31 = 4;
      v28 = &v13;
      v29 = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, &word_180017A16, v7 + 8, 0, 5, v27);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( *((_DWORD *)v8 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v8 + 6) = 0;
    v9 = *(__int64 **)v8;
    while ( 1 )
    {
      v10 = *v9;
      if ( !*v9 )
        break;
      if ( (char *)v10 == v8 )
      {
        *v9 = *((_QWORD *)v8 + 2);
        break;
      }
      v9 = (__int64 *)(v10 + 16);
      *(_QWORD *)v8 = v10 + 16;
    }
    *(_QWORD *)v8 = 0;
  }
}

```

## disassembly

```asm
0x18000b840  mov     [rsp-8+arg_8], rbx
0x18000b845  mov     [rsp-8+arg_10], rdi
0x18000b84a  push    rbp
0x18000b84b  lea     rbp, [rsp-50h]
0x18000b850  sub     rsp, 170h
0x18000b857  mov     rax, cs:__security_cookie
0x18000b85e  xor     rax, rsp
0x18000b861  mov     [rbp+50h+var_10], rax
0x18000b865  mov     rbx, rcx
0x18000b868  mov     rdi, [rcx+110h]
0x18000b86f  mov     eax, [rdi+48h]
0x18000b872  test    eax, eax
0x18000b874  jns     loc_18000BA25
0x18000b87a  add     rdi, 50h ; 'P'
0x18000b87e  cmp     eax, [rdi+8]
0x18000b881  jnz     loc_18000BA25
0x18000b887  test    rdi, rdi
0x18000b88a  jz      loc_18000BA25
0x18000b890  lea     rdx, [rbp+50h+SRWLock]
0x18000b894  call    ?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b899  mov     rax, [rbx+110h]
0x18000b8a0  mov     dword ptr [rax], 2
0x18000b8a6  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000b8aa  test    rcx, rcx
0x18000b8ad  jz      short loc_18000B8B5
0x18000b8af  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8b5  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000b8ba  mov     r9, [rax+8]
0x18000b8be  mov     eax, [r9]
0x18000b8c1  cmp     eax, 5
0x18000b8c4  jbe     loc_18000BAFB
0x18000b8ca  mov     rdx, [r9+18h]
0x18000b8ce  mov     rax, [r9+10h]
0x18000b8d2  mov     rcx, 200000000000h
0x18000b8dc  test    rcx, rax
0x18000b8df  jz      loc_18000BAFB
0x18000b8e5  mov     rax, rdx
0x18000b8e8  and     rax, rcx
0x18000b8eb  cmp     rax, rdx
0x18000b8ee  jnz     loc_18000BAFB
0x18000b8f4  mov     rax, [rdi+78h]
0x18000b8f8  mov     [rbp+50h+var_A8], rax
0x18000b8fc  mov     rax, [rdi+70h]
0x18000b900  mov     [rbp+50h+var_A0], rax
0x18000b904  mov     eax, [rdi+68h]
0x18000b907  mov     [rbp+50h+var_B8], eax
0x18000b90a  mov     rax, [rdi+60h]
0x18000b90e  mov     [rbp+50h+var_98], rax
0x18000b912  mov     rax, [rdi+58h]
0x18000b916  mov     [rbp+50h+var_90], rax
0x18000b91a  mov     eax, [rdi+50h]
0x18000b91d  mov     [rbp+50h+var_B4], eax
0x18000b920  mov     rax, [rdi+48h]
0x18000b924  mov     [rbp+50h+var_88], rax
0x18000b928  mov     eax, [rdi+20h]
0x18000b92b  mov     [rbp+50h+var_B0], eax
0x18000b92e  mov     rax, [rdi+18h]
0x18000b932  mov     [rbp+50h+var_80], rax
0x18000b936  mov     eax, [rdi]
0x18000b938  mov     [rbp+50h+var_AC], eax
0x18000b93b  mov     rax, [rdi+80h]
0x18000b942  mov     [rbp+50h+var_78], rax
0x18000b946  mov     eax, [rdi+40h]
0x18000b949  mov     [rbp+50h+var_D0], eax
0x18000b94c  mov     rax, [rdi+38h]
0x18000b950  mov     [rbp+50h+var_70], rax
0x18000b954  mov     eax, [rdi+8]
0x18000b957  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b95a  mov     [rbp+50h+var_68], 1000000h
0x18000b962  mov     [rbp+50h+var_C0], 0
0x18000b96a  mov     r8, [rbx+110h]
0x18000b971  add     r8, 8
0x18000b975  lea     rax, [rbp+50h+var_A8]
0x18000b979  mov     [rsp+170h+var_D8], rax
0x18000b981  lea     rax, [rbp+50h+var_A0]
0x18000b985  mov     [rsp+170h+var_E0], rax
0x18000b98d  lea     rax, [rbp+50h+var_B8]
0x18000b991  mov     [rsp+170h+var_E8], rax
0x18000b999  lea     rax, [rbp+50h+var_98]
0x18000b99d  mov     [rsp+170h+var_F0], rax
0x18000b9a5  lea     rax, [rbp+50h+var_90]
0x18000b9a9  mov     [rsp+170h+var_F8], rax
0x18000b9ae  lea     rax, [rbp+50h+var_B4]
0x18000b9b2  mov     [rsp+170h+var_100], rax
0x18000b9b7  lea     rax, [rbp+50h+var_88]
0x18000b9bb  mov     [rsp+170h+var_108], rax
0x18000b9c0  lea     rax, [rbp+50h+var_B0]
0x18000b9c4  mov     [rsp+170h+var_110], rax
0x18000b9c9  lea     rax, [rbp+50h+var_80]
0x18000b9cd  mov     [rsp+170h+var_118], rax
0x18000b9d2  lea     rax, [rbp+50h+var_AC]
0x18000b9d6  mov     [rsp+170h+var_120], rax
0x18000b9db  lea     rax, [rbp+50h+var_78]
0x18000b9df  mov     [rsp+170h+var_128], rax
0x18000b9e4  lea     rax, [rbp+50h+var_D0]
0x18000b9e8  mov     [rsp+170h+var_130], rax
0x18000b9ed  lea     rax, [rbp+50h+var_70]
0x18000b9f1  mov     [rsp+170h+var_138], rax
0x18000b9f6  lea     rax, [rbp+50h+SRWLock]
0x18000b9fa  mov     [rsp+170h+var_140], rax
0x18000b9ff  lea     rax, [rbp+50h+var_68]
0x18000ba03  mov     [rsp+170h+var_148], rax
0x18000ba08  lea     rax, [rbp+50h+var_C0]
0x18000ba0c  mov     [rsp+170h+var_150], rax
0x18000ba11  lea     rdx, byte_1800178E7
0x18000ba18  mov     rcx, r9
0x18000ba1b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18000ba20  jmp     loc_18000BAFB
0x18000ba25  lea     rdx, [rbp+50h+var_C0]
0x18000ba29  call    ?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ba2e  mov     rax, [rbx+110h]
0x18000ba35  mov     dword ptr [rax], 2
0x18000ba3b  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000ba3f  test    rcx, rcx
0x18000ba42  jz      short loc_18000BA4A
0x18000ba44  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba4a  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000ba4f  mov     rdi, [rax+8]
0x18000ba53  mov     eax, [rdi]
0x18000ba55  cmp     eax, 5
0x18000ba58  jbe     loc_18000BAFB
0x18000ba5e  mov     rdx, [rdi+18h]
0x18000ba62  mov     rax, [rdi+10h]
0x18000ba66  mov     rcx, 200000000000h
0x18000ba70  test    rcx, rax
0x18000ba73  jz      loc_18000BAFB
0x18000ba79  mov     rax, rdx
0x18000ba7c  and     rax, rcx
0x18000ba7f  cmp     rax, rdx
0x18000ba82  jnz     short loc_18000BAFB
0x18000ba84  call    cs:__imp_GetCurrentThreadId
0x18000ba8a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000ba8d  mov     r8, [rbx+110h]
0x18000ba94  mov     eax, [r8+48h]
0x18000ba98  mov     [rbp+50h+var_D0], eax
0x18000ba9b  mov     [rbp+50h+var_C0], 0
0x18000baa3  lea     rax, [rbp+50h+SRWLock]
0x18000baa7  mov     [rbp+50h+var_20], rax
0x18000baab  mov     [rbp+50h+var_18], 4
0x18000bab3  lea     rax, [rbp+50h+var_D0]
0x18000bab7  mov     [rbp+50h+var_30], rax
0x18000babb  mov     [rbp+50h+var_28], 4
0x18000bac3  lea     rax, [rbp+50h+var_C0]
0x18000bac7  mov     [rbp+50h+var_40], rax
0x18000bacb  mov     [rbp+50h+var_38], 8
0x18000bad3  add     r8, 8
0x18000bad7  lea     rax, [rbp+50h+var_60]
0x18000badb  mov     [rsp+170h+var_148], rax
0x18000bae0  mov     dword ptr [rsp+170h+var_150], 5
0x18000bae8  xor     r9d, r9d
0x18000baeb  lea     rdx, word_180017A16
0x18000baf2  mov     rcx, rdi
0x18000baf5  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bafa  nop
0x18000bafb  cmp     dword ptr [rbx+138h], 0
0x18000bb02  jz      short loc_18000BB62
0x18000bb04  add     rbx, 120h
0x18000bb0b  call    cs:__imp_GetCurrentThreadId
0x18000bb11  cmp     [rbx+18h], eax
0x18000bb14  jz      short loc_18000BB32
0x18000bb16  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000bb1d  test    rax, rax
0x18000bb20  jz      short loc_18000BB32
0x18000bb22  mov     rdx, [rbp+58h]
0x18000bb26  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000bb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb32  mov     dword ptr [rbx+18h], 0
0x18000bb39  mov     rcx, [rbx]
0x18000bb3c  jmp     short loc_18000BB4A
0x18000bb3e  cmp     rax, rbx
0x18000bb41  jz      short loc_18000BB54
0x18000bb43  lea     rcx, [rax+10h]
0x18000bb47  mov     [rbx], rcx
0x18000bb4a  mov     rax, [rcx]
0x18000bb4d  test    rax, rax
0x18000bb50  jnz     short loc_18000BB3E
0x18000bb52  jmp     short loc_18000BB5B
0x18000bb54  mov     rax, [rbx+10h]
0x18000bb58  mov     [rcx], rax
0x18000bb5b  mov     qword ptr [rbx], 0
0x18000bb62  mov     rcx, [rbp+50h+var_10]
0x18000bb66  xor     rcx, rsp; StackCookie
0x18000bb69  call    __security_check_cookie
0x18000bb6e  lea     r11, [rsp+170h+var_s0]
0x18000bb76  mov     rbx, [r11+18h]
0x18000bb7a  mov     rdi, [r11+20h]
0x18000bb7e  mov     rsp, r11
0x18000bb81  pop     rbp
0x18000bb82  retn
```
