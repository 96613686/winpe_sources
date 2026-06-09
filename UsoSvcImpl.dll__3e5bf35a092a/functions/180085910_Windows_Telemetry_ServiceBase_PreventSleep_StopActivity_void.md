# Windows::Telemetry::ServiceBase::PreventSleep::StopActivity(void)

- ea: `0x180085910`
- end: `0x180085bf9`
- name: `?StopActivity@PreventSleep@ServiceBase@Telemetry@Windows@@MEAAXXZ`
- size: `745`
- prototype: `void __fastcall(Windows::Telemetry::ServiceBase::PreventSleep *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x1800857a8`
- `0x180085910`
- `0x18008c454`
- `0x18008d138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008597e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085b0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008597e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085b0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085b3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085b3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085b97`

## pseudocode

```c
void __fastcall Windows::Telemetry::ServiceBase::PreventSleep::StopActivity(
        Windows::Telemetry::ServiceBase::PreventSleep *this)
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
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
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
          (int)&byte_1801311A1,
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
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
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
      (unsigned int)&dword_180131154,
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
0x180085910  mov     [rsp-8+arg_8], rbx
0x180085915  mov     [rsp-8+arg_10], rsi
0x18008591a  push    rbp
0x18008591b  push    rdi
0x18008591c  push    r14
0x18008591e  lea     rbp, [rsp+10h]
0x180085923  sub     rsp, 110h
0x18008592a  lea     rsi, [rcx+110h]
0x180085931  mov     rbx, rcx
0x180085934  mov     rdi, [rsi]
0x180085937  mov     eax, [rdi+48h]
0x18008593a  test    eax, eax
0x18008593c  jns     loc_180085AE6
0x180085942  add     rdi, 50h ; 'P'
0x180085946  cmp     eax, [rdi+8]
0x180085949  jnz     loc_180085AE6
0x18008594f  mov     r14, rsi
0x180085952  test    rdi, rdi
0x180085955  jz      loc_180085AE9
0x18008595b  lea     rdx, [rbp+SRWLock]
0x18008595f  mov     [rbp+SRWLock], 0
0x180085967  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18008596c  mov     rax, [rsi]
0x18008596f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180085973  mov     dword ptr [rax], 2
0x180085979  test    rcx, rcx
0x18008597c  jz      short loc_180085984
0x18008597e  call    cs:__imp_ReleaseSRWLockExclusive
0x180085984  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180085989  mov     r9, [rax+8]
0x18008598d  cmp     dword ptr [r9], 5
0x180085991  jbe     loc_180085B87
0x180085997  mov     rcx, 400000000000h
0x1800859a1  test    [r9+10h], rcx
0x1800859a5  jz      loc_180085B87
0x1800859ab  mov     rax, [r9+18h]
0x1800859af  and     rax, rcx
0x1800859b2  cmp     rax, [r9+18h]
0x1800859b6  jnz     loc_180085B87
0x1800859bc  mov     rax, [rdi+78h]
0x1800859c0  lea     rdx, byte_1801311A1; int
0x1800859c7  mov     r8, [rsi]
0x1800859ca  mov     rcx, r9; int
0x1800859cd  mov     [rbp+var_58], rax
0x1800859d1  add     r8, 8; int
0x1800859d5  mov     rax, [rdi+70h]
0x1800859d9  mov     [rbp+var_50], rax
0x1800859dd  mov     eax, [rdi+68h]
0x1800859e0  mov     dword ptr [rbp+var_78+4], eax
0x1800859e3  mov     rax, [rdi+60h]
0x1800859e7  mov     [rbp+var_48], rax
0x1800859eb  mov     rax, [rdi+58h]
0x1800859ef  mov     [rbp+var_40], rax
0x1800859f3  mov     eax, [rdi+50h]
0x1800859f6  mov     dword ptr [rbp+var_70], eax
0x1800859f9  mov     rax, [rdi+48h]
0x1800859fd  mov     [rbp+var_38], rax
0x180085a01  mov     eax, [rdi+20h]
0x180085a04  mov     dword ptr [rbp+var_70+4], eax
0x180085a07  mov     rax, [rdi+18h]
0x180085a0b  mov     [rbp+var_30], rax
0x180085a0f  mov     eax, [rdi]
0x180085a11  mov     dword ptr [rbp+var_68], eax
0x180085a14  mov     rax, [rdi+80h]
0x180085a1b  mov     [rbp+var_28], rax
0x180085a1f  mov     eax, [rdi+40h]
0x180085a22  mov     dword ptr [rbp+var_78], eax
0x180085a25  mov     rax, [rdi+38h]
0x180085a29  mov     [rbp+var_20], rax
0x180085a2d  mov     eax, [rdi+8]
0x180085a30  mov     dword ptr [rbp+SRWLock], eax
0x180085a33  mov     eax, 1000000h
0x180085a38  mov     [rbp+var_18], rax
0x180085a3c  mov     [rbp+var_60], rax
0x180085a40  lea     rax, [rbp+var_58]
0x180085a44  mov     [rsp+120h+var_88], rax; __int64
0x180085a4c  lea     rax, [rbp+var_50]
0x180085a50  mov     [rsp+120h+var_90], rax; __int64
0x180085a58  lea     rax, [rbp+var_78+4]
0x180085a5c  mov     [rsp+120h+var_98], rax; __int64
0x180085a64  lea     rax, [rbp+var_48]
0x180085a68  mov     [rsp+120h+var_A0], rax; __int64
0x180085a70  lea     rax, [rbp+var_40]
0x180085a74  mov     [rsp+120h+var_A8], rax; __int64
0x180085a79  lea     rax, [rbp+var_70]
0x180085a7d  mov     [rsp+120h+var_B0], rax; __int64
0x180085a82  lea     rax, [rbp+var_38]
0x180085a86  mov     [rsp+120h+var_B8], rax; __int64
0x180085a8b  lea     rax, [rbp+var_70+4]
0x180085a8f  mov     [rsp+120h+var_C0], rax; __int64
0x180085a94  lea     rax, [rbp+var_30]
0x180085a98  mov     [rsp+120h+var_C8], rax; __int64
0x180085a9d  lea     rax, [rbp+var_68]
0x180085aa1  mov     [rsp+120h+var_D0], rax; __int64
0x180085aa6  lea     rax, [rbp+var_28]
0x180085aaa  mov     [rsp+120h+var_D8], rax; __int64
0x180085aaf  lea     rax, [rbp+var_78]
0x180085ab3  mov     [rsp+120h+var_E0], rax; __int64
0x180085ab8  lea     rax, [rbp+var_20]
0x180085abc  mov     [rsp+120h+var_E8], rax; __int64
0x180085ac1  lea     rax, [rbp+SRWLock]
0x180085ac5  mov     [rsp+120h+var_F0], rax; __int64
0x180085aca  lea     rax, [rbp+var_18]
0x180085ace  mov     [rsp+120h+var_F8], rax; __int64
0x180085ad3  lea     rax, [rbp+var_60]
0x180085ad7  mov     [rsp+120h+var_100], rax; __int64
0x180085adc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180085ae1  jmp     loc_180085B87
0x180085ae6  mov     r14, rsi
0x180085ae9  lea     rdx, [rbp+SRWLock]
0x180085aed  mov     [rbp+SRWLock], 0
0x180085af5  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180085afa  mov     rax, [r14]
0x180085afd  mov     rcx, [rbp+SRWLock]; SRWLock
0x180085b01  mov     dword ptr [rax], 2
0x180085b07  test    rcx, rcx
0x180085b0a  jz      short loc_180085B12
0x180085b0c  call    cs:__imp_ReleaseSRWLockExclusive
0x180085b12  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180085b17  mov     rdi, [rax+8]
0x180085b1b  cmp     dword ptr [rdi], 5
0x180085b1e  jbe     short loc_180085B87
0x180085b20  mov     rcx, 400000000000h
0x180085b2a  test    [rdi+10h], rcx
0x180085b2e  jz      short loc_180085B87
0x180085b30  mov     rax, [rdi+18h]
0x180085b34  and     rax, rcx
0x180085b37  cmp     rax, [rdi+18h]
0x180085b3b  jnz     short loc_180085B87
0x180085b3d  call    cs:__imp_GetCurrentThreadId
0x180085b43  mov     r8, [rsi]
0x180085b46  lea     rdx, dword_180131154
0x180085b4d  mov     dword ptr [rbp+SRWLock], eax
0x180085b50  mov     rcx, rdi
0x180085b53  mov     eax, [r8+48h]
0x180085b57  add     r8, 8
0x180085b5b  mov     dword ptr [rbp+var_78], eax
0x180085b5e  mov     eax, 1000000h
0x180085b63  mov     [rbp+var_60], rax
0x180085b67  lea     rax, [rbp+SRWLock]
0x180085b6b  mov     [rsp+120h+var_F0], rax
0x180085b70  lea     rax, [rbp+var_78]
0x180085b74  mov     [rsp+120h+var_F8], rax
0x180085b79  lea     rax, [rbp+var_60]
0x180085b7d  mov     [rsp+120h+var_100], rax; int
0x180085b82  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180085b87  cmp     dword ptr [rbx+138h], 0
0x180085b8e  jz      short loc_180085BE1
0x180085b90  add     rbx, 120h
0x180085b97  call    cs:__imp_GetCurrentThreadId
0x180085b9d  cmp     [rbx+18h], eax
0x180085ba0  jz      short loc_180085BB1
0x180085ba2  mov     rcx, [rbp+8]; this
0x180085ba6  mov     r9d, 8007029Ch; char *
0x180085bac  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180085bb1  mov     rcx, [rbx]
0x180085bb4  mov     dword ptr [rbx+18h], 0
0x180085bbb  jmp     short loc_180085BC9
0x180085bbd  cmp     rax, rbx
0x180085bc0  jz      short loc_180085BD3
0x180085bc2  lea     rcx, [rax+10h]
0x180085bc6  mov     [rbx], rcx
0x180085bc9  mov     rax, [rcx]
0x180085bcc  test    rax, rax
0x180085bcf  jnz     short loc_180085BBD
0x180085bd1  jmp     short loc_180085BDA
0x180085bd3  mov     rax, [rbx+10h]
0x180085bd7  mov     [rcx], rax
0x180085bda  mov     qword ptr [rbx], 0
0x180085be1  lea     r11, [rsp+120h+var_10]
0x180085be9  mov     rbx, [r11+28h]
0x180085bed  mov     rsi, [r11+30h]
0x180085bf1  mov     rsp, r11
0x180085bf4  pop     r14
0x180085bf6  pop     rdi
0x180085bf7  pop     rbp
0x180085bf8  retn
```
