# LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity::StopActivity(void)

- ea: `0x18005b670`
- end: `0x18005b903`
- name: `?StopActivity@DeprecatedLanguageMigrationTaskActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18005b670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b6ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b85f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b6ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b85f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b897`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity::StopActivity(
        LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *this)
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
  __int64 v20[4]; // [rsp+F0h] [rbp+37h] BYREF
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
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
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
      v20[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_1800796ED,
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
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)byte_180079685,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005b670  push    rbp
0x18005b672  push    rbx
0x18005b673  push    rdi
0x18005b674  lea     rbp, [rsp-47h]
0x18005b679  sub     rsp, 100h
0x18005b680  mov     rbx, rcx
0x18005b683  mov     rdi, [rcx+110h]
0x18005b68a  mov     eax, [rdi+48h]
0x18005b68d  test    eax, eax
0x18005b68f  jns     loc_18005B840
0x18005b695  add     rdi, 50h ; 'P'
0x18005b699  cmp     eax, [rdi+8]
0x18005b69c  jnz     loc_18005B840
0x18005b6a2  test    rdi, rdi
0x18005b6a5  jz      loc_18005B840
0x18005b6ab  lea     rdx, [rbp+57h+SRWLock]
0x18005b6af  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005b6b4  mov     rax, [rbx+110h]
0x18005b6bb  mov     dword ptr [rax], 2
0x18005b6c1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005b6c5  test    rcx, rcx
0x18005b6c8  jz      short loc_18005B6D0
0x18005b6ca  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b6d0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18005b6d5  mov     r9, [rax+8]
0x18005b6d9  mov     eax, [r9]
0x18005b6dc  cmp     eax, 5
0x18005b6df  jbe     loc_18005B8E5
0x18005b6e5  mov     rdx, [r9+18h]
0x18005b6e9  mov     rax, [r9+10h]
0x18005b6ed  mov     rcx, 400000000000h
0x18005b6f7  test    rcx, rax
0x18005b6fa  jz      loc_18005B8E5
0x18005b700  mov     rax, rdx
0x18005b703  and     rax, rcx
0x18005b706  cmp     rax, rdx
0x18005b709  jnz     loc_18005B8E5
0x18005b70f  mov     rax, [rdi+78h]
0x18005b713  mov     [rbp+57h+var_68], rax
0x18005b717  mov     rax, [rdi+70h]
0x18005b71b  mov     [rbp+57h+var_60], rax
0x18005b71f  mov     eax, [rdi+68h]
0x18005b722  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005b725  mov     rax, [rdi+60h]
0x18005b729  mov     [rbp+57h+var_58], rax
0x18005b72d  mov     rax, [rdi+58h]
0x18005b731  mov     [rbp+57h+var_50], rax
0x18005b735  mov     eax, [rdi+50h]
0x18005b738  mov     [rbp+57h+arg_8], eax
0x18005b73b  mov     rax, [rdi+48h]
0x18005b73f  mov     [rbp+57h+var_48], rax
0x18005b743  mov     eax, [rdi+20h]
0x18005b746  mov     dword ptr [rbp+57h+arg_10], eax
0x18005b749  mov     rax, [rdi+18h]
0x18005b74d  mov     [rbp+57h+var_40], rax
0x18005b751  mov     eax, [rdi]
0x18005b753  mov     [rbp+57h+arg_18], eax
0x18005b756  mov     rax, [rdi+80h]
0x18005b75d  mov     [rbp+57h+var_38], rax
0x18005b761  mov     eax, [rdi+40h]
0x18005b764  mov     [rbp+57h+var_70], eax
0x18005b767  mov     rax, [rdi+38h]
0x18005b76b  mov     [rbp+57h+var_30], rax
0x18005b76f  mov     eax, [rdi+8]
0x18005b772  mov     [rbp+57h+var_6C], eax
0x18005b775  mov     [rbp+57h+var_28], 1000000h
0x18005b77d  mov     [rbp+57h+var_20], 3000000h
0x18005b785  mov     r8, [rbx+110h]
0x18005b78c  add     r8, 8
0x18005b790  lea     rax, [rbp+57h+var_68]
0x18005b794  mov     [rsp+110h+var_78], rax
0x18005b79c  lea     rax, [rbp+57h+var_60]
0x18005b7a0  mov     [rsp+110h+var_80], rax
0x18005b7a8  lea     rax, [rbp+57h+SRWLock]
0x18005b7ac  mov     [rsp+110h+var_88], rax
0x18005b7b4  lea     rax, [rbp+57h+var_58]
0x18005b7b8  mov     [rsp+110h+var_90], rax
0x18005b7c0  lea     rax, [rbp+57h+var_50]
0x18005b7c4  mov     [rsp+110h+var_98], rax
0x18005b7c9  lea     rax, [rbp+57h+arg_8]
0x18005b7cd  mov     [rsp+110h+var_A0], rax
0x18005b7d2  lea     rax, [rbp+57h+var_48]
0x18005b7d6  mov     [rsp+110h+var_A8], rax
0x18005b7db  lea     rax, [rbp+57h+arg_10]
0x18005b7df  mov     [rsp+110h+var_B0], rax
0x18005b7e4  lea     rax, [rbp+57h+var_40]
0x18005b7e8  mov     [rsp+110h+var_B8], rax
0x18005b7ed  lea     rax, [rbp+57h+arg_18]
0x18005b7f1  mov     [rsp+110h+var_C0], rax
0x18005b7f6  lea     rax, [rbp+57h+var_38]
0x18005b7fa  mov     [rsp+110h+var_C8], rax
0x18005b7ff  lea     rax, [rbp+57h+var_70]
0x18005b803  mov     [rsp+110h+var_D0], rax
0x18005b808  lea     rax, [rbp+57h+var_30]
0x18005b80c  mov     [rsp+110h+var_D8], rax
0x18005b811  lea     rax, [rbp+57h+var_6C]
0x18005b815  mov     [rsp+110h+var_E0], rax
0x18005b81a  lea     rax, [rbp+57h+var_28]
0x18005b81e  mov     [rsp+110h+var_E8], rax
0x18005b823  lea     rax, [rbp+57h+var_20]
0x18005b827  mov     [rsp+110h+var_F0], rax
0x18005b82c  lea     rdx, byte_1800796ED
0x18005b833  mov     rcx, r9
0x18005b836  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18005b83b  jmp     loc_18005B8E5
0x18005b840  lea     rdx, [rbp+57h+SRWLock]
0x18005b844  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005b849  mov     rax, [rbx+110h]
0x18005b850  mov     dword ptr [rax], 2
0x18005b856  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005b85a  test    rcx, rcx
0x18005b85d  jz      short loc_18005B865
0x18005b85f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b865  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18005b86a  mov     rdi, [rax+8]
0x18005b86e  mov     eax, [rdi]
0x18005b870  cmp     eax, 5
0x18005b873  jbe     short loc_18005B8E5
0x18005b875  mov     rdx, [rdi+18h]
0x18005b879  mov     rax, [rdi+10h]
0x18005b87d  mov     rcx, 400000000000h
0x18005b887  test    rcx, rax
0x18005b88a  jz      short loc_18005B8E5
0x18005b88c  mov     rax, rdx
0x18005b88f  and     rax, rcx
0x18005b892  cmp     rax, rdx
0x18005b895  jnz     short loc_18005B8E5
0x18005b897  call    cs:__imp_GetCurrentThreadId
0x18005b89d  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005b8a0  mov     r8, [rbx+110h]
0x18005b8a7  mov     eax, [r8+48h]
0x18005b8ab  mov     [rbp+57h+arg_8], eax
0x18005b8ae  mov     [rbp+57h+arg_10], 3000000h
0x18005b8b6  add     r8, 8
0x18005b8ba  lea     rax, [rbp+57h+SRWLock]
0x18005b8be  mov     [rsp+110h+var_E0], rax
0x18005b8c3  lea     rax, [rbp+57h+arg_8]
0x18005b8c7  mov     [rsp+110h+var_E8], rax
0x18005b8cc  lea     rax, [rbp+57h+arg_10]
0x18005b8d0  mov     [rsp+110h+var_F0], rax
0x18005b8d5  lea     rdx, byte_180079685
0x18005b8dc  mov     rcx, rdi
0x18005b8df  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005b8e4  nop
0x18005b8e5  lea     rcx, [rbx+120h]; this
0x18005b8ec  cmp     dword ptr [rcx+18h], 0
0x18005b8f0  jz      short loc_18005B8F8
0x18005b8f2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005b8f7  nop
0x18005b8f8  add     rsp, 100h
0x18005b8ff  pop     rdi
0x18005b900  pop     rbx
0x18005b901  pop     rbp
0x18005b902  retn
```
