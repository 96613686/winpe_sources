# wpcplugs::AppRepository::StateRepo::StateRepoLogger::Xbox_LookupIsDlc::StopActivity(void)

- ea: `0x180070bf0`
- end: `0x180070e6a`
- name: `?StopActivity@Xbox_LookupIsDlc@StateRepoLogger@StateRepo@AppRepository@wpcplugs@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpcplugs::AppRepository::StateRepo::StateRepoLogger::Xbox_LookupIsDlc *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18002ae34`
- `0x18002c3c0`
- `0x18006f7e8`
- `0x180070bf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070dfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070c4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070de8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070c4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070de8`

## pseudocode

```c
void __fastcall wpcplugs::AppRepository::StateRepo::StateRepoLogger::Xbox_LookupIsDlc::StopActivity(
        wpcplugs::AppRepository::StateRepo::StateRepoLogger::Xbox_LookupIsDlc *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&byte_1800D60E7,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&word_1800D6096,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpcplugs::AppRepository::StateRepo::StateRepoLogger::Xbox_LookupIsDlc *)((char *)this + 288));
}

```

## disassembly

```asm
0x180070bf0  push    rbp
0x180070bf2  push    rbx
0x180070bf3  push    rdi
0x180070bf4  lea     rbp, [rsp+10h]
0x180070bf9  sub     rsp, 130h
0x180070c00  mov     rbx, rcx
0x180070c03  mov     rdi, [rcx+110h]
0x180070c0a  mov     eax, [rdi+48h]
0x180070c0d  test    eax, eax
0x180070c0f  jns     loc_180070DC9
0x180070c15  add     rdi, 50h ; 'P'
0x180070c19  cmp     eax, [rdi+8]
0x180070c1c  jnz     loc_180070DC9
0x180070c22  test    rdi, rdi
0x180070c25  jz      loc_180070DC9
0x180070c2b  lea     rdx, [rbp+SRWLock]
0x180070c2f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180070c34  mov     rax, [rbx+110h]
0x180070c3b  mov     dword ptr [rax], 2
0x180070c41  mov     rcx, [rbp+SRWLock]; SRWLock
0x180070c45  test    rcx, rcx
0x180070c48  jz      short loc_180070C50
0x180070c4a  call    cs:__imp_ReleaseSRWLockExclusive
0x180070c50  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180070c55  mov     r9, rax
0x180070c58  mov     ecx, [rax]
0x180070c5a  cmp     ecx, 5
0x180070c5d  jbe     loc_180070E4C
0x180070c63  mov     rcx, [rdi+30h]
0x180070c67  mov     [rbp+var_70], rcx
0x180070c6b  mov     ecx, [rdi+44h]
0x180070c6e  mov     dword ptr [rbp+SRWLock], ecx
0x180070c71  mov     ecx, [rdi+10h]
0x180070c74  mov     [rbp+arg_8], ecx
0x180070c77  mov     rcx, [rdi+78h]
0x180070c7b  mov     [rbp+var_68], rcx
0x180070c7f  mov     rax, [rdi+70h]
0x180070c83  mov     [rbp+var_60], rax
0x180070c87  mov     eax, [rdi+68h]
0x180070c8a  mov     dword ptr [rbp+arg_10], eax
0x180070c8d  mov     rax, [rdi+60h]
0x180070c91  mov     [rbp+var_58], rax
0x180070c95  mov     rax, [rdi+58h]
0x180070c99  mov     [rbp+var_50], rax
0x180070c9d  mov     eax, [rdi+50h]
0x180070ca0  mov     [rbp+arg_18], eax
0x180070ca3  mov     rax, [rdi+48h]
0x180070ca7  mov     [rbp+var_48], rax
0x180070cab  mov     eax, [rdi+20h]
0x180070cae  mov     [rbp+var_80], eax
0x180070cb1  mov     rax, [rdi+18h]
0x180070cb5  mov     [rbp+var_40], rax
0x180070cb9  mov     eax, [rdi]
0x180070cbb  mov     [rbp+var_7C], eax
0x180070cbe  mov     rax, [rdi+80h]
0x180070cc5  mov     [rbp+var_38], rax
0x180070cc9  mov     eax, [rdi+40h]
0x180070ccc  mov     [rbp+var_78], eax
0x180070ccf  mov     rax, [rdi+38h]
0x180070cd3  mov     [rbp+var_30], rax
0x180070cd7  mov     eax, [rdi+8]
0x180070cda  mov     [rbp+var_74], eax
0x180070cdd  mov     eax, 1000000h
0x180070ce2  mov     [rbp+var_28], rax
0x180070ce6  mov     [rbp+var_20], rax
0x180070cea  mov     r8, [rbx+110h]
0x180070cf1  add     r8, 8
0x180070cf5  lea     rax, [rbp+var_70]
0x180070cf9  mov     [rsp+140h+var_90], rax
0x180070d01  lea     rax, [rbp+SRWLock]
0x180070d05  mov     [rsp+140h+var_98], rax
0x180070d0d  lea     rax, [rbp+arg_8]
0x180070d11  mov     [rsp+140h+var_A0], rax
0x180070d19  lea     rax, [rbp+var_68]
0x180070d1d  mov     [rsp+140h+var_A8], rax
0x180070d25  lea     rax, [rbp+var_60]
0x180070d29  mov     [rsp+140h+var_B0], rax
0x180070d31  lea     rax, [rbp+arg_10]
0x180070d35  mov     [rsp+140h+var_B8], rax
0x180070d3d  lea     rax, [rbp+var_58]
0x180070d41  mov     [rsp+140h+var_C0], rax
0x180070d49  lea     rax, [rbp+var_50]
0x180070d4d  mov     [rsp+140h+var_C8], rax
0x180070d52  lea     rax, [rbp+arg_18]
0x180070d56  mov     [rsp+140h+var_D0], rax
0x180070d5b  lea     rax, [rbp+var_48]
0x180070d5f  mov     [rsp+140h+var_D8], rax
0x180070d64  lea     rax, [rbp+var_80]
0x180070d68  mov     [rsp+140h+var_E0], rax
0x180070d6d  lea     rax, [rbp+var_40]
0x180070d71  mov     [rsp+140h+var_E8], rax
0x180070d76  lea     rax, [rbp+var_7C]
0x180070d7a  mov     [rsp+140h+var_F0], rax
0x180070d7f  lea     rax, [rbp+var_38]
0x180070d83  mov     [rsp+140h+var_F8], rax
0x180070d88  lea     rax, [rbp+var_78]
0x180070d8c  mov     [rsp+140h+var_100], rax
0x180070d91  lea     rax, [rbp+var_30]
0x180070d95  mov     [rsp+140h+var_108], rax
0x180070d9a  lea     rax, [rbp+var_74]
0x180070d9e  mov     [rsp+140h+var_110], rax
0x180070da3  lea     rax, [rbp+var_28]
0x180070da7  mov     [rsp+140h+var_118], rax
0x180070dac  lea     rax, [rbp+var_20]
0x180070db0  mov     [rsp+140h+var_120], rax
0x180070db5  lea     rdx, byte_1800D60E7
0x180070dbc  mov     rcx, r9
0x180070dbf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180070dc4  jmp     loc_180070E4C
0x180070dc9  lea     rdx, [rbp+SRWLock]
0x180070dcd  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180070dd2  mov     rax, [rbx+110h]
0x180070dd9  mov     dword ptr [rax], 2
0x180070ddf  mov     rcx, [rbp+SRWLock]; SRWLock
0x180070de3  test    rcx, rcx
0x180070de6  jz      short loc_180070DEE
0x180070de8  call    cs:__imp_ReleaseSRWLockExclusive
0x180070dee  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180070df3  mov     rdi, rax
0x180070df6  mov     ecx, [rax]
0x180070df8  cmp     ecx, 5
0x180070dfb  jbe     short loc_180070E4C
0x180070dfd  call    cs:__imp_GetCurrentThreadId
0x180070e03  mov     dword ptr [rbp+SRWLock], eax
0x180070e06  mov     r8, [rbx+110h]
0x180070e0d  mov     ecx, [r8+48h]
0x180070e11  mov     [rbp+arg_8], ecx
0x180070e14  mov     eax, 1000000h
0x180070e19  mov     [rbp+arg_10], rax
0x180070e1d  add     r8, 8
0x180070e21  lea     rax, [rbp+SRWLock]
0x180070e25  mov     [rsp+140h+var_110], rax
0x180070e2a  lea     rax, [rbp+arg_8]
0x180070e2e  mov     [rsp+140h+var_118], rax
0x180070e33  lea     rax, [rbp+arg_10]
0x180070e37  mov     [rsp+140h+var_120], rax
0x180070e3c  lea     rdx, word_1800D6096
0x180070e43  mov     rcx, rdi
0x180070e46  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180070e4b  nop
0x180070e4c  lea     rcx, [rbx+120h]; this
0x180070e53  cmp     dword ptr [rcx+18h], 0
0x180070e57  jz      short loc_180070E5F
0x180070e59  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180070e5e  nop
0x180070e5f  add     rsp, 130h
0x180070e66  pop     rdi
0x180070e67  pop     rbx
0x180070e68  pop     rbp
0x180070e69  retn
```
