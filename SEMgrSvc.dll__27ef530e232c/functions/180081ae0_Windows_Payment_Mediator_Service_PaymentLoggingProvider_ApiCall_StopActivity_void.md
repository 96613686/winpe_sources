# Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall::StopActivity(void)

- ea: `0x180081ae0`
- end: `0x180081d5c`
- name: `?StopActivity@ApiCall@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000197c`
- `0x18000202c`
- `0x18001da08`
- `0x18001f288`
- `0x180081704`
- `0x180081ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081cdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180081cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081cf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall::StopActivity(
        Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  __int64 v8; // r8
  int v9; // r9d
  int v10; // [rsp+C0h] [rbp-80h] BYREF
  int v11; // [rsp+C4h] [rbp-7Ch] BYREF
  int v12; // [rsp+C8h] [rbp-78h] BYREF
  int v13; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v14; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+100h] [rbp-40h] BYREF
  __int64 v21; // [rsp+108h] [rbp-38h] BYREF
  __int64 v22; // [rsp+110h] [rbp-30h] BYREF
  __int64 v23; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v24[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v26; // [rsp+158h] [rbp+18h] BYREF
  __int64 v27; // [rsp+160h] [rbp+20h] BYREF
  int v28; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v14 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v26 = v4[4];
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(v27) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v28 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      v10 = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v11 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v12 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v13 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)word_18011D72A,
        *((_QWORD *)this + 34) + 8,
        (_DWORD)v5,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v11,
        (__int64)&v20,
        (__int64)&v10,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v14);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v26 = *(_DWORD *)(v8 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&dword_18011D86C,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *)((char *)this + 288));
}

```

## disassembly

```asm
0x180081ae0  push    rbp
0x180081ae2  push    rbx
0x180081ae3  push    rdi
0x180081ae4  lea     rbp, [rsp+10h]
0x180081ae9  sub     rsp, 130h
0x180081af0  mov     rbx, rcx
0x180081af3  mov     rdi, [rcx+110h]
0x180081afa  mov     eax, [rdi+48h]
0x180081afd  test    eax, eax
0x180081aff  jns     loc_180081CBC
0x180081b05  add     rdi, 50h ; 'P'
0x180081b09  cmp     eax, [rdi+8]
0x180081b0c  jnz     loc_180081CBC
0x180081b12  test    rdi, rdi
0x180081b15  jz      loc_180081CBC
0x180081b1b  lea     rdx, [rbp+SRWLock]
0x180081b1f  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180081b24  mov     rax, [rbx+110h]
0x180081b2b  mov     dword ptr [rax], 2
0x180081b31  mov     rcx, [rbp+SRWLock]; SRWLock
0x180081b35  test    rcx, rcx
0x180081b38  jz      short loc_180081B40
0x180081b3a  call    cs:__imp_ReleaseSRWLockExclusive
0x180081b40  call    ?Provider@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider(void)
0x180081b45  mov     r9, rax
0x180081b48  mov     ecx, [rax]
0x180081b4a  cmp     ecx, 5
0x180081b4d  jbe     loc_180081D3E
0x180081b53  mov     rcx, [rdi+30h]
0x180081b57  mov     [rbp+var_70], rcx
0x180081b5b  mov     ecx, [rdi+44h]
0x180081b5e  mov     dword ptr [rbp+SRWLock], ecx
0x180081b61  mov     ecx, [rdi+10h]
0x180081b64  mov     [rbp+arg_8], ecx
0x180081b67  mov     rcx, [rdi+78h]
0x180081b6b  mov     [rbp+var_68], rcx
0x180081b6f  mov     rax, [rdi+70h]
0x180081b73  mov     [rbp+var_60], rax
0x180081b77  mov     eax, [rdi+68h]
0x180081b7a  mov     dword ptr [rbp+arg_10], eax
0x180081b7d  mov     rax, [rdi+60h]
0x180081b81  mov     [rbp+var_58], rax
0x180081b85  mov     rax, [rdi+58h]
0x180081b89  mov     [rbp+var_50], rax
0x180081b8d  mov     eax, [rdi+50h]
0x180081b90  mov     [rbp+arg_18], eax
0x180081b93  mov     rax, [rdi+48h]
0x180081b97  mov     [rbp+var_48], rax
0x180081b9b  mov     eax, [rdi+20h]
0x180081b9e  mov     [rbp+var_80], eax
0x180081ba1  mov     rax, [rdi+18h]
0x180081ba5  mov     [rbp+var_40], rax
0x180081ba9  mov     eax, [rdi]
0x180081bab  mov     [rbp+var_7C], eax
0x180081bae  mov     rax, [rdi+80h]
0x180081bb5  mov     [rbp+var_38], rax
0x180081bb9  mov     eax, [rdi+40h]
0x180081bbc  mov     [rbp+var_78], eax
0x180081bbf  mov     rax, [rdi+38h]
0x180081bc3  mov     [rbp+var_30], rax
0x180081bc7  mov     eax, [rdi+8]
0x180081bca  mov     [rbp+var_74], eax
0x180081bcd  mov     [rbp+var_28], 1000000h
0x180081bd5  mov     [rbp+var_20], 0
0x180081bdd  mov     r8, [rbx+110h]
0x180081be4  add     r8, 8
0x180081be8  lea     rax, [rbp+var_70]
0x180081bec  mov     [rsp+140h+var_90], rax
0x180081bf4  lea     rax, [rbp+SRWLock]
0x180081bf8  mov     [rsp+140h+var_98], rax
0x180081c00  lea     rax, [rbp+arg_8]
0x180081c04  mov     [rsp+140h+var_A0], rax
0x180081c0c  lea     rax, [rbp+var_68]
0x180081c10  mov     [rsp+140h+var_A8], rax
0x180081c18  lea     rax, [rbp+var_60]
0x180081c1c  mov     [rsp+140h+var_B0], rax
0x180081c24  lea     rax, [rbp+arg_10]
0x180081c28  mov     [rsp+140h+var_B8], rax
0x180081c30  lea     rax, [rbp+var_58]
0x180081c34  mov     [rsp+140h+var_C0], rax
0x180081c3c  lea     rax, [rbp+var_50]
0x180081c40  mov     [rsp+140h+var_C8], rax
0x180081c45  lea     rax, [rbp+arg_18]
0x180081c49  mov     [rsp+140h+var_D0], rax
0x180081c4e  lea     rax, [rbp+var_48]
0x180081c52  mov     [rsp+140h+var_D8], rax
0x180081c57  lea     rax, [rbp+var_80]
0x180081c5b  mov     [rsp+140h+var_E0], rax
0x180081c60  lea     rax, [rbp+var_40]
0x180081c64  mov     [rsp+140h+var_E8], rax
0x180081c69  lea     rax, [rbp+var_7C]
0x180081c6d  mov     [rsp+140h+var_F0], rax
0x180081c72  lea     rax, [rbp+var_38]
0x180081c76  mov     [rsp+140h+var_F8], rax
0x180081c7b  lea     rax, [rbp+var_78]
0x180081c7f  mov     [rsp+140h+var_100], rax
0x180081c84  lea     rax, [rbp+var_30]
0x180081c88  mov     [rsp+140h+var_108], rax
0x180081c8d  lea     rax, [rbp+var_74]
0x180081c91  mov     [rsp+140h+var_110], rax
0x180081c96  lea     rax, [rbp+var_28]
0x180081c9a  mov     [rsp+140h+var_118], rax
0x180081c9f  lea     rax, [rbp+var_20]
0x180081ca3  mov     [rsp+140h+var_120], rax
0x180081ca8  lea     rdx, word_18011D72A
0x180081caf  mov     rcx, r9
0x180081cb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180081cb7  jmp     loc_180081D3E
0x180081cbc  lea     rdx, [rbp+SRWLock]
0x180081cc0  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180081cc5  mov     rax, [rbx+110h]
0x180081ccc  mov     dword ptr [rax], 2
0x180081cd2  mov     rcx, [rbp+SRWLock]; SRWLock
0x180081cd6  test    rcx, rcx
0x180081cd9  jz      short loc_180081CE1
0x180081cdb  call    cs:__imp_ReleaseSRWLockExclusive
0x180081ce1  call    ?Provider@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider(void)
0x180081ce6  mov     rdi, rax
0x180081ce9  mov     ecx, [rax]
0x180081ceb  cmp     ecx, 5
0x180081cee  jbe     short loc_180081D3E
0x180081cf0  call    cs:__imp_GetCurrentThreadId
0x180081cf6  mov     dword ptr [rbp+SRWLock], eax
0x180081cf9  mov     r8, [rbx+110h]
0x180081d00  mov     ecx, [r8+48h]
0x180081d04  mov     [rbp+arg_8], ecx
0x180081d07  mov     [rbp+arg_10], 0
0x180081d0f  add     r8, 8
0x180081d13  lea     rax, [rbp+SRWLock]
0x180081d17  mov     [rsp+140h+var_110], rax
0x180081d1c  lea     rax, [rbp+arg_8]
0x180081d20  mov     [rsp+140h+var_118], rax
0x180081d25  lea     rax, [rbp+arg_10]
0x180081d29  mov     [rsp+140h+var_120], rax
0x180081d2e  lea     rdx, dword_18011D86C
0x180081d35  mov     rcx, rdi
0x180081d38  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180081d3d  nop
0x180081d3e  lea     rcx, [rbx+120h]; this
0x180081d45  cmp     dword ptr [rcx+18h], 0
0x180081d49  jz      short loc_180081D51
0x180081d4b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180081d50  nop
0x180081d51  add     rsp, 130h
0x180081d58  pop     rdi
0x180081d59  pop     rbx
0x180081d5a  pop     rbp
0x180081d5b  retn
```
