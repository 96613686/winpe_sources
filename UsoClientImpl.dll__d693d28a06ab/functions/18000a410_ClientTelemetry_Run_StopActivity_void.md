# ClientTelemetry::Run::StopActivity(void)

- ea: `0x18000a410`
- end: `0x18000a6f9`
- name: `?StopActivity@Run@ClientTelemetry@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(ClientTelemetry::Run *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001c1c`
- `0x180001cac`
- `0x18000a2ac`
- `0x18000a410`
- `0x18001a1bc`
- `0x180035ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a47e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a60c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a47e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a60c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a63d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a63d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a697`

## pseudocode

```c
void __fastcall ClientTelemetry::Run::StopActivity(ClientTelemetry::Run *this)
{
  _DWORD **v1; // rsi
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdi
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  _DWORD *v13; // r8
  int v14; // r9d
  char *v15; // rbx
  void *v16; // rdx
  unsigned int v17; // r8d
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // [rsp+20h] [rbp-100h]
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v22; // [rsp+A8h] [rbp-78h] BYREF
  int v23; // [rsp+ACh] [rbp-74h] BYREF
  int v24; // [rsp+B0h] [rbp-70h] BYREF
  int v25; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v26; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v35; // [rsp+100h] [rbp-20h] BYREF
  __int64 v36; // [rsp+108h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+8h]

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = *((_QWORD *)ClientTelemetry::Instance() + 1);
      if ( *(_DWORD *)v8 > 5u
        && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
      {
        v9 = *v1;
        v28 = *(_QWORD *)(v5 + 120);
        v29 = *(_QWORD *)(v5 + 112);
        v23 = *(_DWORD *)(v5 + 104);
        v30 = *(_QWORD *)(v5 + 96);
        v31 = *(_QWORD *)(v5 + 88);
        v24 = *(_DWORD *)(v5 + 80);
        v32 = *(_QWORD *)(v5 + 72);
        v25 = *(_DWORD *)(v5 + 32);
        v33 = *(_QWORD *)(v5 + 24);
        LODWORD(v26) = *(_DWORD *)v5;
        v34 = *(_QWORD *)(v5 + 128);
        v22 = *(_DWORD *)(v5 + 64);
        v35 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v36 = 0x1000000;
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v8,
          (int)&byte_180090C2D,
          (_DWORD)v9 + 8,
          (__int64)&v27,
          (__int64)&v36,
          (__int64)&SRWLock,
          (__int64)&v35,
          (__int64)&v22,
          (__int64)&v34,
          (__int64)&v26,
          (__int64)&v33,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v23,
          (__int64)&v29,
          (__int64)&v28);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = *((_QWORD *)ClientTelemetry::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u
    && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v22 = v13[18];
    v27 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)byte_180090BE9,
      (_DWORD)v13 + 8,
      v14,
      (__int64)&v27,
      (__int64)&v22,
      (__int64)&SRWLock);
  }
LABEL_17:
  if ( *((_DWORD *)this + 78) )
  {
    v15 = (char *)this + 288;
    if ( *((_DWORD *)v15 + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v16, v17, (const char *)0x8007029CLL, v20);
    v18 = *(__int64 **)v15;
    *((_DWORD *)v15 + 6) = 0;
    while ( 1 )
    {
      v19 = *v18;
      if ( !*v18 )
        break;
      if ( (char *)v19 == v15 )
      {
        *v18 = *((_QWORD *)v15 + 2);
        break;
      }
      v18 = (__int64 *)(v19 + 16);
      *(_QWORD *)v15 = v19 + 16;
    }
    *(_QWORD *)v15 = 0;
  }
}

```

## disassembly

```asm
0x18000a410  mov     [rsp-8+arg_8], rbx
0x18000a415  mov     [rsp-8+arg_10], rsi
0x18000a41a  push    rbp
0x18000a41b  push    rdi
0x18000a41c  push    r14
0x18000a41e  lea     rbp, [rsp+10h]
0x18000a423  sub     rsp, 110h
0x18000a42a  lea     rsi, [rcx+110h]
0x18000a431  mov     rbx, rcx
0x18000a434  mov     rdi, [rsi]
0x18000a437  mov     eax, [rdi+48h]
0x18000a43a  test    eax, eax
0x18000a43c  jns     loc_18000A5E6
0x18000a442  add     rdi, 50h ; 'P'
0x18000a446  cmp     eax, [rdi+8]
0x18000a449  jnz     loc_18000A5E6
0x18000a44f  mov     r14, rsi
0x18000a452  test    rdi, rdi
0x18000a455  jz      loc_18000A5E9
0x18000a45b  lea     rdx, [rbp+SRWLock]
0x18000a45f  mov     [rbp+SRWLock], 0
0x18000a467  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a46c  mov     rax, [rsi]
0x18000a46f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000a473  mov     dword ptr [rax], 2
0x18000a479  test    rcx, rcx
0x18000a47c  jz      short loc_18000A484
0x18000a47e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a484  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000a489  mov     r9, [rax+8]
0x18000a48d  cmp     dword ptr [r9], 5
0x18000a491  jbe     loc_18000A687
0x18000a497  mov     rcx, 400000000000h
0x18000a4a1  test    [r9+10h], rcx
0x18000a4a5  jz      loc_18000A687
0x18000a4ab  mov     rax, [r9+18h]
0x18000a4af  and     rax, rcx
0x18000a4b2  cmp     rax, [r9+18h]
0x18000a4b6  jnz     loc_18000A687
0x18000a4bc  mov     rax, [rdi+78h]
0x18000a4c0  lea     rdx, byte_180090C2D; int
0x18000a4c7  mov     r8, [rsi]
0x18000a4ca  mov     rcx, r9; int
0x18000a4cd  mov     [rbp+var_58], rax
0x18000a4d1  add     r8, 8; int
0x18000a4d5  mov     rax, [rdi+70h]
0x18000a4d9  mov     [rbp+var_50], rax
0x18000a4dd  mov     eax, [rdi+68h]
0x18000a4e0  mov     dword ptr [rbp+var_78+4], eax
0x18000a4e3  mov     rax, [rdi+60h]
0x18000a4e7  mov     [rbp+var_48], rax
0x18000a4eb  mov     rax, [rdi+58h]
0x18000a4ef  mov     [rbp+var_40], rax
0x18000a4f3  mov     eax, [rdi+50h]
0x18000a4f6  mov     dword ptr [rbp+var_70], eax
0x18000a4f9  mov     rax, [rdi+48h]
0x18000a4fd  mov     [rbp+var_38], rax
0x18000a501  mov     eax, [rdi+20h]
0x18000a504  mov     dword ptr [rbp+var_70+4], eax
0x18000a507  mov     rax, [rdi+18h]
0x18000a50b  mov     [rbp+var_30], rax
0x18000a50f  mov     eax, [rdi]
0x18000a511  mov     dword ptr [rbp+var_68], eax
0x18000a514  mov     rax, [rdi+80h]
0x18000a51b  mov     [rbp+var_28], rax
0x18000a51f  mov     eax, [rdi+40h]
0x18000a522  mov     dword ptr [rbp+var_78], eax
0x18000a525  mov     rax, [rdi+38h]
0x18000a529  mov     [rbp+var_20], rax
0x18000a52d  mov     eax, [rdi+8]
0x18000a530  mov     dword ptr [rbp+SRWLock], eax
0x18000a533  mov     eax, 1000000h
0x18000a538  mov     [rbp+var_18], rax
0x18000a53c  mov     [rbp+var_60], rax
0x18000a540  lea     rax, [rbp+var_58]
0x18000a544  mov     [rsp+120h+var_88], rax; __int64
0x18000a54c  lea     rax, [rbp+var_50]
0x18000a550  mov     [rsp+120h+var_90], rax; __int64
0x18000a558  lea     rax, [rbp+var_78+4]
0x18000a55c  mov     [rsp+120h+var_98], rax; __int64
0x18000a564  lea     rax, [rbp+var_48]
0x18000a568  mov     [rsp+120h+var_A0], rax; __int64
0x18000a570  lea     rax, [rbp+var_40]
0x18000a574  mov     [rsp+120h+var_A8], rax; __int64
0x18000a579  lea     rax, [rbp+var_70]
0x18000a57d  mov     [rsp+120h+var_B0], rax; __int64
0x18000a582  lea     rax, [rbp+var_38]
0x18000a586  mov     [rsp+120h+var_B8], rax; __int64
0x18000a58b  lea     rax, [rbp+var_70+4]
0x18000a58f  mov     [rsp+120h+var_C0], rax; __int64
0x18000a594  lea     rax, [rbp+var_30]
0x18000a598  mov     [rsp+120h+var_C8], rax; __int64
0x18000a59d  lea     rax, [rbp+var_68]
0x18000a5a1  mov     [rsp+120h+var_D0], rax; __int64
0x18000a5a6  lea     rax, [rbp+var_28]
0x18000a5aa  mov     [rsp+120h+var_D8], rax; __int64
0x18000a5af  lea     rax, [rbp+var_78]
0x18000a5b3  mov     [rsp+120h+var_E0], rax; __int64
0x18000a5b8  lea     rax, [rbp+var_20]
0x18000a5bc  mov     [rsp+120h+var_E8], rax; __int64
0x18000a5c1  lea     rax, [rbp+SRWLock]
0x18000a5c5  mov     [rsp+120h+var_F0], rax; __int64
0x18000a5ca  lea     rax, [rbp+var_18]
0x18000a5ce  mov     [rsp+120h+var_F8], rax; __int64
0x18000a5d3  lea     rax, [rbp+var_60]
0x18000a5d7  mov     [rsp+120h+var_100], rax; __int64
0x18000a5dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18000a5e1  jmp     loc_18000A687
0x18000a5e6  mov     r14, rsi
0x18000a5e9  lea     rdx, [rbp+SRWLock]
0x18000a5ed  mov     [rbp+SRWLock], 0
0x18000a5f5  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a5fa  mov     rax, [r14]
0x18000a5fd  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000a601  mov     dword ptr [rax], 2
0x18000a607  test    rcx, rcx
0x18000a60a  jz      short loc_18000A612
0x18000a60c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a612  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000a617  mov     rdi, [rax+8]
0x18000a61b  cmp     dword ptr [rdi], 5
0x18000a61e  jbe     short loc_18000A687
0x18000a620  mov     rcx, 400000000000h
0x18000a62a  test    [rdi+10h], rcx
0x18000a62e  jz      short loc_18000A687
0x18000a630  mov     rax, [rdi+18h]
0x18000a634  and     rax, rcx
0x18000a637  cmp     rax, [rdi+18h]
0x18000a63b  jnz     short loc_18000A687
0x18000a63d  call    cs:__imp_GetCurrentThreadId
0x18000a643  mov     r8, [rsi]
0x18000a646  lea     rdx, byte_180090BE9
0x18000a64d  mov     dword ptr [rbp+SRWLock], eax
0x18000a650  mov     rcx, rdi
0x18000a653  mov     eax, [r8+48h]
0x18000a657  add     r8, 8
0x18000a65b  mov     dword ptr [rbp+var_78], eax
0x18000a65e  mov     eax, 1000000h
0x18000a663  mov     [rbp+var_60], rax
0x18000a667  lea     rax, [rbp+SRWLock]
0x18000a66b  mov     [rsp+120h+var_F0], rax
0x18000a670  lea     rax, [rbp+var_78]
0x18000a674  mov     [rsp+120h+var_F8], rax
0x18000a679  lea     rax, [rbp+var_60]
0x18000a67d  mov     [rsp+120h+var_100], rax; int
0x18000a682  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a687  cmp     dword ptr [rbx+138h], 0
0x18000a68e  jz      short loc_18000A6E1
0x18000a690  add     rbx, 120h
0x18000a697  call    cs:__imp_GetCurrentThreadId
0x18000a69d  cmp     [rbx+18h], eax
0x18000a6a0  jz      short loc_18000A6B1
0x18000a6a2  mov     rcx, [rbp+8]; this
0x18000a6a6  mov     r9d, 8007029Ch; char *
0x18000a6ac  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000a6b1  mov     rcx, [rbx]
0x18000a6b4  mov     dword ptr [rbx+18h], 0
0x18000a6bb  jmp     short loc_18000A6C9
0x18000a6bd  cmp     rax, rbx
0x18000a6c0  jz      short loc_18000A6D3
0x18000a6c2  lea     rcx, [rax+10h]
0x18000a6c6  mov     [rbx], rcx
0x18000a6c9  mov     rax, [rcx]
0x18000a6cc  test    rax, rax
0x18000a6cf  jnz     short loc_18000A6BD
0x18000a6d1  jmp     short loc_18000A6DA
0x18000a6d3  mov     rax, [rbx+10h]
0x18000a6d7  mov     [rcx], rax
0x18000a6da  mov     qword ptr [rbx], 0
0x18000a6e1  lea     r11, [rsp+120h+var_10]
0x18000a6e9  mov     rbx, [r11+28h]
0x18000a6ed  mov     rsi, [r11+30h]
0x18000a6f1  mov     rsp, r11
0x18000a6f4  pop     r14
0x18000a6f6  pop     rdi
0x18000a6f7  pop     rbp
0x18000a6f8  retn
```
