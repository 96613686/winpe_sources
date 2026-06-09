# OfflineMapsTelemetry::ClientOpenConnectionActivity::StopActivity(void)

- ea: `0x18000b5c0`
- end: `0x18000b8e2`
- name: `?StopActivity@ClientOpenConnectionActivity@OfflineMapsTelemetry@@MEAAXXZ`
- size: `802`
- prototype: `void __fastcall(OfflineMapsTelemetry::ClientOpenConnectionActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180002550`
- `0x180005c50`
- `0x180009bb4`
- `0x18000b5c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b62f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b62f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b86a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b86a`

## string_xrefs

- `0x18000b885`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::ClientOpenConnectionActivity::StopActivity(
        OfflineMapsTelemetry::ClientOpenConnectionActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  char *v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v13; // [rsp+D0h] [rbp-70h] BYREF
  int v14; // [rsp+D8h] [rbp-68h] BYREF
  int v15; // [rsp+DCh] [rbp-64h] BYREF
  int v16; // [rsp+E0h] [rbp-60h] BYREF
  int v17; // [rsp+E4h] [rbp-5Ch] BYREF
  int v18; // [rsp+E8h] [rbp-58h] BYREF
  int v19; // [rsp+ECh] [rbp-54h] BYREF
  const unsigned __int16 *v20; // [rsp+F0h] [rbp-50h] BYREF
  char *v21; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v22; // [rsp+100h] [rbp-40h] BYREF
  char *v23; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v25; // [rsp+118h] [rbp-28h] BYREF
  char *v26; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v27; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v28; // [rsp+130h] [rbp-10h] BYREF
  __int64 v29; // [rsp+138h] [rbp-8h] BYREF
  _BYTE v30[32]; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v31; // [rsp+160h] [rbp+20h]
  __int64 v32; // [rsp+168h] [rbp+28h]
  int *v33; // [rsp+170h] [rbp+30h]
  __int64 v34; // [rsp+178h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+40h]
  __int64 v36; // [rsp+188h] [rbp+48h]
  void *retaddr; // [rsp+1A8h] [rbp+68h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = OfflineMapsTraceLogging::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v14 = v4[17];
      v15 = v4[4];
      v21 = (char *)*((_QWORD *)v4 + 15);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v16 = v4[26];
      v23 = (char *)*((_QWORD *)v4 + 12);
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v17 = v4[20];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v18 = v4[8];
      v26 = (char *)*((_QWORD *)v4 + 3);
      v19 = *v4;
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v29 = 0x1000000;
      v13 = (PSRWLOCK)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)word_180017F3A,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)&v13,
        (__int64)&v29,
        (__int64)&SRWLock,
        &v28,
        (__int64)&v11,
        &v27,
        (__int64)&v19,
        &v26,
        (__int64)&v18,
        &v25,
        (__int64)&v17,
        &v24,
        &v23,
        (__int64)&v16,
        &v22,
        &v21,
        (__int64)&v15,
        (__int64)&v14,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v13);
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v6 = OfflineMapsTraceLogging::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v11 = *(_DWORD *)(v7 + 72);
      v13 = (PSRWLOCK)0x1000000;
      p_SRWLock = &SRWLock;
      v36 = 4;
      v33 = &v11;
      v34 = 4;
      v31 = &v13;
      v32 = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, byte_180017EDD, v7 + 8, 0, 5, v30);
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
0x18000b5c0  mov     [rsp-8+arg_8], rbx
0x18000b5c5  mov     [rsp-8+arg_10], rdi
0x18000b5ca  push    rbp
0x18000b5cb  lea     rbp, [rsp-60h]
0x18000b5d0  sub     rsp, 1A0h
0x18000b5d7  mov     rax, cs:__security_cookie
0x18000b5de  xor     rax, rsp
0x18000b5e1  mov     [rbp+60h+var_10], rax
0x18000b5e5  mov     rbx, rcx
0x18000b5e8  mov     rdi, [rcx+110h]
0x18000b5ef  mov     eax, [rdi+48h]
0x18000b5f2  test    eax, eax
0x18000b5f4  jns     loc_18000B7AE
0x18000b5fa  add     rdi, 50h ; 'P'
0x18000b5fe  cmp     eax, [rdi+8]
0x18000b601  jnz     loc_18000B7AE
0x18000b607  test    rdi, rdi
0x18000b60a  jz      loc_18000B7AE
0x18000b610  lea     rdx, [rbp+60h+SRWLock]
0x18000b614  call    ?LockExclusive@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b619  mov     rax, [rbx+110h]
0x18000b620  mov     dword ptr [rax], 2
0x18000b626  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x18000b62a  test    rcx, rcx
0x18000b62d  jz      short loc_18000B635
0x18000b62f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b635  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b63a  mov     r9, rax
0x18000b63d  mov     ecx, [rax]
0x18000b63f  cmp     ecx, 5
0x18000b642  jbe     loc_18000B85A
0x18000b648  mov     rcx, [rdi+30h]
0x18000b64c  mov     [rbp+60h+var_B0], rcx
0x18000b650  mov     ecx, [rdi+44h]
0x18000b653  mov     [rbp+60h+var_C8], ecx
0x18000b656  mov     ecx, [rdi+10h]
0x18000b659  mov     [rbp+60h+var_C4], ecx
0x18000b65c  mov     rcx, [rdi+78h]
0x18000b660  mov     [rbp+60h+var_A8], rcx
0x18000b664  mov     rax, [rdi+70h]
0x18000b668  mov     [rbp+60h+var_A0], rax
0x18000b66c  mov     eax, [rdi+68h]
0x18000b66f  mov     [rbp+60h+var_C0], eax
0x18000b672  mov     rax, [rdi+60h]
0x18000b676  mov     [rbp+60h+var_98], rax
0x18000b67a  mov     rax, [rdi+58h]
0x18000b67e  mov     [rbp+60h+var_90], rax
0x18000b682  mov     eax, [rdi+50h]
0x18000b685  mov     [rbp+60h+var_BC], eax
0x18000b688  mov     rax, [rdi+48h]
0x18000b68c  mov     [rbp+60h+var_88], rax
0x18000b690  mov     eax, [rdi+20h]
0x18000b693  mov     [rbp+60h+var_B8], eax
0x18000b696  mov     rax, [rdi+18h]
0x18000b69a  mov     [rbp+60h+var_80], rax
0x18000b69e  mov     eax, [rdi]
0x18000b6a0  mov     [rbp+60h+var_B4], eax
0x18000b6a3  mov     rax, [rdi+80h]
0x18000b6aa  mov     [rbp+60h+var_78], rax
0x18000b6ae  mov     eax, [rdi+40h]
0x18000b6b1  mov     [rbp+60h+var_E0], eax
0x18000b6b4  mov     rax, [rdi+38h]
0x18000b6b8  mov     [rbp+60h+var_70], rax
0x18000b6bc  mov     eax, [rdi+8]
0x18000b6bf  mov     dword ptr [rbp+60h+SRWLock], eax
0x18000b6c2  mov     eax, 1000000h
0x18000b6c7  mov     [rbp+60h+var_68], rax
0x18000b6cb  mov     [rbp+60h+var_D0], rax
0x18000b6cf  mov     r8, [rbx+110h]
0x18000b6d6  add     r8, 8
0x18000b6da  lea     rax, [rbp+60h+var_B0]
0x18000b6de  mov     [rsp+1A0h+var_F0], rax
0x18000b6e6  lea     rax, [rbp+60h+var_C8]
0x18000b6ea  mov     [rsp+1A0h+var_F8], rax
0x18000b6f2  lea     rax, [rbp+60h+var_C4]
0x18000b6f6  mov     [rsp+1A0h+var_100], rax
0x18000b6fe  lea     rax, [rbp+60h+var_A8]
0x18000b702  mov     [rsp+1A0h+var_108], rax
0x18000b70a  lea     rax, [rbp+60h+var_A0]
0x18000b70e  mov     [rsp+1A0h+var_110], rax
0x18000b716  lea     rax, [rbp+60h+var_C0]
0x18000b71a  mov     [rsp+1A0h+var_118], rax
0x18000b722  lea     rax, [rbp+60h+var_98]
0x18000b726  mov     [rsp+1A0h+var_120], rax
0x18000b72e  lea     rax, [rbp+60h+var_90]
0x18000b732  mov     [rsp+1A0h+var_128], rax
0x18000b737  lea     rax, [rbp+60h+var_BC]
0x18000b73b  mov     [rsp+1A0h+var_130], rax
0x18000b740  lea     rax, [rbp+60h+var_88]
0x18000b744  mov     [rsp+1A0h+var_138], rax
0x18000b749  lea     rax, [rbp+60h+var_B8]
0x18000b74d  mov     [rsp+1A0h+var_140], rax
0x18000b752  lea     rax, [rbp+60h+var_80]
0x18000b756  mov     [rsp+1A0h+var_148], rax
0x18000b75b  lea     rax, [rbp+60h+var_B4]
0x18000b75f  mov     [rsp+1A0h+var_150], rax
0x18000b764  lea     rax, [rbp+60h+var_78]
0x18000b768  mov     [rsp+1A0h+var_158], rax
0x18000b76d  lea     rax, [rbp+60h+var_E0]
0x18000b771  mov     [rsp+1A0h+var_160], rax
0x18000b776  lea     rax, [rbp+60h+var_70]
0x18000b77a  mov     [rsp+1A0h+var_168], rax
0x18000b77f  lea     rax, [rbp+60h+SRWLock]
0x18000b783  mov     [rsp+1A0h+var_170], rax
0x18000b788  lea     rax, [rbp+60h+var_68]
0x18000b78c  mov     [rsp+1A0h+var_178], rax
0x18000b791  lea     rax, [rbp+60h+var_D0]
0x18000b795  mov     [rsp+1A0h+var_180], rax
0x18000b79a  lea     rdx, word_180017F3A
0x18000b7a1  mov     rcx, r9
0x18000b7a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b7a9  jmp     loc_18000B85A
0x18000b7ae  lea     rdx, [rbp+60h+var_D0]
0x18000b7b2  call    ?LockExclusive@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b7b7  mov     rax, [rbx+110h]
0x18000b7be  mov     dword ptr [rax], 2
0x18000b7c4  mov     rcx, [rbp+60h+var_D0]; SRWLock
0x18000b7c8  test    rcx, rcx
0x18000b7cb  jz      short loc_18000B7D3
0x18000b7cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b7d3  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b7d8  mov     rdi, rax
0x18000b7db  mov     ecx, [rax]
0x18000b7dd  cmp     ecx, 5
0x18000b7e0  jbe     short loc_18000B85A
0x18000b7e2  call    cs:__imp_GetCurrentThreadId
0x18000b7e8  mov     dword ptr [rbp+60h+SRWLock], eax
0x18000b7eb  mov     r8, [rbx+110h]
0x18000b7f2  mov     ecx, [r8+48h]
0x18000b7f6  mov     [rbp+60h+var_E0], ecx
0x18000b7f9  mov     eax, 1000000h
0x18000b7fe  mov     [rbp+60h+var_D0], rax
0x18000b802  lea     rax, [rbp+60h+SRWLock]
0x18000b806  mov     [rbp+60h+var_20], rax
0x18000b80a  mov     [rbp+60h+var_18], 4
0x18000b812  lea     rax, [rbp+60h+var_E0]
0x18000b816  mov     [rbp+60h+var_30], rax
0x18000b81a  mov     [rbp+60h+var_28], 4
0x18000b822  lea     rax, [rbp+60h+var_D0]
0x18000b826  mov     [rbp+60h+var_40], rax
0x18000b82a  mov     [rbp+60h+var_38], 8
0x18000b832  add     r8, 8
0x18000b836  lea     rax, [rbp+60h+var_60]
0x18000b83a  mov     [rsp+1A0h+var_178], rax
0x18000b83f  mov     dword ptr [rsp+1A0h+var_180], 5
0x18000b847  xor     r9d, r9d
0x18000b84a  lea     rdx, byte_180017EDD
0x18000b851  mov     rcx, rdi
0x18000b854  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b859  nop
0x18000b85a  cmp     dword ptr [rbx+138h], 0
0x18000b861  jz      short loc_18000B8C1
0x18000b863  add     rbx, 120h
0x18000b86a  call    cs:__imp_GetCurrentThreadId
0x18000b870  cmp     [rbx+18h], eax
0x18000b873  jz      short loc_18000B891
0x18000b875  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000b87c  test    rax, rax
0x18000b87f  jz      short loc_18000B891
0x18000b881  mov     rdx, [rbp+68h]
0x18000b885  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000b88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b891  mov     dword ptr [rbx+18h], 0
0x18000b898  mov     rcx, [rbx]
0x18000b89b  jmp     short loc_18000B8A9
0x18000b89d  cmp     rax, rbx
0x18000b8a0  jz      short loc_18000B8B3
0x18000b8a2  lea     rcx, [rax+10h]
0x18000b8a6  mov     [rbx], rcx
0x18000b8a9  mov     rax, [rcx]
0x18000b8ac  test    rax, rax
0x18000b8af  jnz     short loc_18000B89D
0x18000b8b1  jmp     short loc_18000B8BA
0x18000b8b3  mov     rax, [rbx+10h]
0x18000b8b7  mov     [rcx], rax
0x18000b8ba  mov     qword ptr [rbx], 0
0x18000b8c1  mov     rcx, [rbp+60h+var_10]
0x18000b8c5  xor     rcx, rsp; StackCookie
0x18000b8c8  call    __security_check_cookie
0x18000b8cd  lea     r11, [rsp+1A0h+var_s0]
0x18000b8d5  mov     rbx, [r11+18h]
0x18000b8d9  mov     rdi, [r11+20h]
0x18000b8dd  mov     rsp, r11
0x18000b8e0  pop     rbp
0x18000b8e1  retn
```
