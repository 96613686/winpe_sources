# LanguageOverlayTraceProvider::ServiceStopActivity::StopActivity(void)

- ea: `0x180010b30`
- end: `0x180010dc3`
- name: `?StopActivity@ServiceStopActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::ServiceStopActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010b30`
- `0x180010dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010d1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d57`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::ServiceStopActivity::StopActivity(
        LanguageOverlayTraceProvider::ServiceStopActivity *this)
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
  const int *v11; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-9h] BYREF
  const int *v13; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+Fh] BYREF
  const int *v16; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v17; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v11 = (const int *)*((_QWORD *)v4 + 15);
      v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v13 = (const int *)*((_QWORD *)v4 + 12);
      v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = (const int *)*((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)&dword_180076384,
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
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&unk_180076330,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::ServiceStopActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010b30  push    rbp
0x180010b32  push    rbx
0x180010b33  push    rdi
0x180010b34  lea     rbp, [rsp-47h]
0x180010b39  sub     rsp, 100h
0x180010b40  mov     rbx, rcx
0x180010b43  mov     rdi, [rcx+110h]
0x180010b4a  mov     eax, [rdi+48h]
0x180010b4d  test    eax, eax
0x180010b4f  jns     loc_180010D00
0x180010b55  add     rdi, 50h ; 'P'
0x180010b59  cmp     eax, [rdi+8]
0x180010b5c  jnz     loc_180010D00
0x180010b62  test    rdi, rdi
0x180010b65  jz      loc_180010D00
0x180010b6b  lea     rdx, [rbp+57h+SRWLock]
0x180010b6f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010b74  mov     rax, [rbx+110h]
0x180010b7b  mov     dword ptr [rax], 2
0x180010b81  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180010b85  test    rcx, rcx
0x180010b88  jz      short loc_180010B90
0x180010b8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180010b90  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180010b95  mov     r9, [rax+8]
0x180010b99  mov     eax, [r9]
0x180010b9c  cmp     eax, 5
0x180010b9f  jbe     loc_180010DA5
0x180010ba5  mov     rdx, [r9+18h]
0x180010ba9  mov     rax, [r9+10h]
0x180010bad  mov     rcx, 200000000000h
0x180010bb7  test    rcx, rax
0x180010bba  jz      loc_180010DA5
0x180010bc0  mov     rax, rdx
0x180010bc3  and     rax, rcx
0x180010bc6  cmp     rax, rdx
0x180010bc9  jnz     loc_180010DA5
0x180010bcf  mov     rax, [rdi+78h]
0x180010bd3  mov     [rbp+57h+var_68], rax
0x180010bd7  mov     rax, [rdi+70h]
0x180010bdb  mov     [rbp+57h+var_60], rax
0x180010bdf  mov     eax, [rdi+68h]
0x180010be2  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010be5  mov     rax, [rdi+60h]
0x180010be9  mov     [rbp+57h+var_58], rax
0x180010bed  mov     rax, [rdi+58h]
0x180010bf1  mov     [rbp+57h+var_50], rax
0x180010bf5  mov     eax, [rdi+50h]
0x180010bf8  mov     [rbp+57h+arg_8], eax
0x180010bfb  mov     rax, [rdi+48h]
0x180010bff  mov     [rbp+57h+var_48], rax
0x180010c03  mov     eax, [rdi+20h]
0x180010c06  mov     dword ptr [rbp+57h+arg_10], eax
0x180010c09  mov     rax, [rdi+18h]
0x180010c0d  mov     [rbp+57h+var_40], rax
0x180010c11  mov     eax, [rdi]
0x180010c13  mov     [rbp+57h+arg_18], eax
0x180010c16  mov     rax, [rdi+80h]
0x180010c1d  mov     [rbp+57h+var_38], rax
0x180010c21  mov     eax, [rdi+40h]
0x180010c24  mov     [rbp+57h+var_70], eax
0x180010c27  mov     rax, [rdi+38h]
0x180010c2b  mov     [rbp+57h+var_30], rax
0x180010c2f  mov     eax, [rdi+8]
0x180010c32  mov     [rbp+57h+var_6C], eax
0x180010c35  mov     [rbp+57h+var_28], 1000000h
0x180010c3d  mov     [rbp+57h+var_20], 0
0x180010c45  mov     r8, [rbx+110h]
0x180010c4c  add     r8, 8
0x180010c50  lea     rax, [rbp+57h+var_68]
0x180010c54  mov     [rsp+110h+var_78], rax
0x180010c5c  lea     rax, [rbp+57h+var_60]
0x180010c60  mov     [rsp+110h+var_80], rax
0x180010c68  lea     rax, [rbp+57h+SRWLock]
0x180010c6c  mov     [rsp+110h+var_88], rax
0x180010c74  lea     rax, [rbp+57h+var_58]
0x180010c78  mov     [rsp+110h+var_90], rax
0x180010c80  lea     rax, [rbp+57h+var_50]
0x180010c84  mov     [rsp+110h+var_98], rax
0x180010c89  lea     rax, [rbp+57h+arg_8]
0x180010c8d  mov     [rsp+110h+var_A0], rax
0x180010c92  lea     rax, [rbp+57h+var_48]
0x180010c96  mov     [rsp+110h+var_A8], rax
0x180010c9b  lea     rax, [rbp+57h+arg_10]
0x180010c9f  mov     [rsp+110h+var_B0], rax
0x180010ca4  lea     rax, [rbp+57h+var_40]
0x180010ca8  mov     [rsp+110h+var_B8], rax
0x180010cad  lea     rax, [rbp+57h+arg_18]
0x180010cb1  mov     [rsp+110h+var_C0], rax
0x180010cb6  lea     rax, [rbp+57h+var_38]
0x180010cba  mov     [rsp+110h+var_C8], rax
0x180010cbf  lea     rax, [rbp+57h+var_70]
0x180010cc3  mov     [rsp+110h+var_D0], rax
0x180010cc8  lea     rax, [rbp+57h+var_30]
0x180010ccc  mov     [rsp+110h+var_D8], rax
0x180010cd1  lea     rax, [rbp+57h+var_6C]
0x180010cd5  mov     [rsp+110h+var_E0], rax
0x180010cda  lea     rax, [rbp+57h+var_28]
0x180010cde  mov     [rsp+110h+var_E8], rax
0x180010ce3  lea     rax, [rbp+57h+var_20]
0x180010ce7  mov     [rsp+110h+var_F0], rax
0x180010cec  lea     rdx, dword_180076384
0x180010cf3  mov     rcx, r9
0x180010cf6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010cfb  jmp     loc_180010DA5
0x180010d00  lea     rdx, [rbp+57h+SRWLock]
0x180010d04  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010d09  mov     rax, [rbx+110h]
0x180010d10  mov     dword ptr [rax], 2
0x180010d16  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180010d1a  test    rcx, rcx
0x180010d1d  jz      short loc_180010D25
0x180010d1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180010d25  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180010d2a  mov     rdi, [rax+8]
0x180010d2e  mov     eax, [rdi]
0x180010d30  cmp     eax, 5
0x180010d33  jbe     short loc_180010DA5
0x180010d35  mov     rdx, [rdi+18h]
0x180010d39  mov     rax, [rdi+10h]
0x180010d3d  mov     rcx, 200000000000h
0x180010d47  test    rcx, rax
0x180010d4a  jz      short loc_180010DA5
0x180010d4c  mov     rax, rdx
0x180010d4f  and     rax, rcx
0x180010d52  cmp     rax, rdx
0x180010d55  jnz     short loc_180010DA5
0x180010d57  call    cs:__imp_GetCurrentThreadId
0x180010d5d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010d60  mov     r8, [rbx+110h]
0x180010d67  mov     eax, [r8+48h]
0x180010d6b  mov     [rbp+57h+arg_8], eax
0x180010d6e  mov     [rbp+57h+arg_10], 0
0x180010d76  add     r8, 8
0x180010d7a  lea     rax, [rbp+57h+SRWLock]
0x180010d7e  mov     [rsp+110h+var_E0], rax
0x180010d83  lea     rax, [rbp+57h+arg_8]
0x180010d87  mov     [rsp+110h+var_E8], rax
0x180010d8c  lea     rax, [rbp+57h+arg_10]
0x180010d90  mov     [rsp+110h+var_F0], rax
0x180010d95  lea     rdx, unk_180076330
0x180010d9c  mov     rcx, rdi
0x180010d9f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010da4  nop
0x180010da5  lea     rcx, [rbx+120h]; this
0x180010dac  cmp     dword ptr [rcx+18h], 0
0x180010db0  jz      short loc_180010DB8
0x180010db2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010db7  nop
0x180010db8  add     rsp, 100h
0x180010dbf  pop     rdi
0x180010dc0  pop     rbx
0x180010dc1  pop     rbp
0x180010dc2  retn
```
