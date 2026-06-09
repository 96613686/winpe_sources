# wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser::StopActivity(void)

- ea: `0x180070970`
- end: `0x180070bea`
- name: `?StopActivity@GetPackageFamiliesForUser@StateRepoLogger@StateRepo@AppRepository@wpcplugs@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18002ae34`
- `0x18002c3c0`
- `0x18006f7e8`
- `0x180070970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070b7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070b7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800709ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070b68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800709ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070b68`

## pseudocode

```c
void __fastcall wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser::StopActivity(
        wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser *this)
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
    if ( *(_DWORD *)v5 > 4u )
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
        (__int64)byte_1800D6283,
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
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&byte_1800D63D7,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpcplugs::AppRepository::StateRepo::StateRepoLogger::GetPackageFamiliesForUser *)((char *)this + 288));
}

```

## disassembly

```asm
0x180070970  push    rbp
0x180070972  push    rbx
0x180070973  push    rdi
0x180070974  lea     rbp, [rsp+10h]
0x180070979  sub     rsp, 130h
0x180070980  mov     rbx, rcx
0x180070983  mov     rdi, [rcx+110h]
0x18007098a  mov     eax, [rdi+48h]
0x18007098d  test    eax, eax
0x18007098f  jns     loc_180070B49
0x180070995  add     rdi, 50h ; 'P'
0x180070999  cmp     eax, [rdi+8]
0x18007099c  jnz     loc_180070B49
0x1800709a2  test    rdi, rdi
0x1800709a5  jz      loc_180070B49
0x1800709ab  lea     rdx, [rbp+SRWLock]
0x1800709af  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800709b4  mov     rax, [rbx+110h]
0x1800709bb  mov     dword ptr [rax], 2
0x1800709c1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800709c5  test    rcx, rcx
0x1800709c8  jz      short loc_1800709D0
0x1800709ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800709d0  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x1800709d5  mov     r9, rax
0x1800709d8  mov     ecx, [rax]
0x1800709da  cmp     ecx, 4
0x1800709dd  jbe     loc_180070BCC
0x1800709e3  mov     rcx, [rdi+30h]
0x1800709e7  mov     [rbp+var_70], rcx
0x1800709eb  mov     ecx, [rdi+44h]
0x1800709ee  mov     dword ptr [rbp+SRWLock], ecx
0x1800709f1  mov     ecx, [rdi+10h]
0x1800709f4  mov     [rbp+arg_8], ecx
0x1800709f7  mov     rcx, [rdi+78h]
0x1800709fb  mov     [rbp+var_68], rcx
0x1800709ff  mov     rax, [rdi+70h]
0x180070a03  mov     [rbp+var_60], rax
0x180070a07  mov     eax, [rdi+68h]
0x180070a0a  mov     dword ptr [rbp+arg_10], eax
0x180070a0d  mov     rax, [rdi+60h]
0x180070a11  mov     [rbp+var_58], rax
0x180070a15  mov     rax, [rdi+58h]
0x180070a19  mov     [rbp+var_50], rax
0x180070a1d  mov     eax, [rdi+50h]
0x180070a20  mov     [rbp+arg_18], eax
0x180070a23  mov     rax, [rdi+48h]
0x180070a27  mov     [rbp+var_48], rax
0x180070a2b  mov     eax, [rdi+20h]
0x180070a2e  mov     [rbp+var_80], eax
0x180070a31  mov     rax, [rdi+18h]
0x180070a35  mov     [rbp+var_40], rax
0x180070a39  mov     eax, [rdi]
0x180070a3b  mov     [rbp+var_7C], eax
0x180070a3e  mov     rax, [rdi+80h]
0x180070a45  mov     [rbp+var_38], rax
0x180070a49  mov     eax, [rdi+40h]
0x180070a4c  mov     [rbp+var_78], eax
0x180070a4f  mov     rax, [rdi+38h]
0x180070a53  mov     [rbp+var_30], rax
0x180070a57  mov     eax, [rdi+8]
0x180070a5a  mov     [rbp+var_74], eax
0x180070a5d  mov     eax, 1000000h
0x180070a62  mov     [rbp+var_28], rax
0x180070a66  mov     [rbp+var_20], rax
0x180070a6a  mov     r8, [rbx+110h]
0x180070a71  add     r8, 8
0x180070a75  lea     rax, [rbp+var_70]
0x180070a79  mov     [rsp+140h+var_90], rax
0x180070a81  lea     rax, [rbp+SRWLock]
0x180070a85  mov     [rsp+140h+var_98], rax
0x180070a8d  lea     rax, [rbp+arg_8]
0x180070a91  mov     [rsp+140h+var_A0], rax
0x180070a99  lea     rax, [rbp+var_68]
0x180070a9d  mov     [rsp+140h+var_A8], rax
0x180070aa5  lea     rax, [rbp+var_60]
0x180070aa9  mov     [rsp+140h+var_B0], rax
0x180070ab1  lea     rax, [rbp+arg_10]
0x180070ab5  mov     [rsp+140h+var_B8], rax
0x180070abd  lea     rax, [rbp+var_58]
0x180070ac1  mov     [rsp+140h+var_C0], rax
0x180070ac9  lea     rax, [rbp+var_50]
0x180070acd  mov     [rsp+140h+var_C8], rax
0x180070ad2  lea     rax, [rbp+arg_18]
0x180070ad6  mov     [rsp+140h+var_D0], rax
0x180070adb  lea     rax, [rbp+var_48]
0x180070adf  mov     [rsp+140h+var_D8], rax
0x180070ae4  lea     rax, [rbp+var_80]
0x180070ae8  mov     [rsp+140h+var_E0], rax
0x180070aed  lea     rax, [rbp+var_40]
0x180070af1  mov     [rsp+140h+var_E8], rax
0x180070af6  lea     rax, [rbp+var_7C]
0x180070afa  mov     [rsp+140h+var_F0], rax
0x180070aff  lea     rax, [rbp+var_38]
0x180070b03  mov     [rsp+140h+var_F8], rax
0x180070b08  lea     rax, [rbp+var_78]
0x180070b0c  mov     [rsp+140h+var_100], rax
0x180070b11  lea     rax, [rbp+var_30]
0x180070b15  mov     [rsp+140h+var_108], rax
0x180070b1a  lea     rax, [rbp+var_74]
0x180070b1e  mov     [rsp+140h+var_110], rax
0x180070b23  lea     rax, [rbp+var_28]
0x180070b27  mov     [rsp+140h+var_118], rax
0x180070b2c  lea     rax, [rbp+var_20]
0x180070b30  mov     [rsp+140h+var_120], rax
0x180070b35  lea     rdx, byte_1800D6283
0x180070b3c  mov     rcx, r9
0x180070b3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180070b44  jmp     loc_180070BCC
0x180070b49  lea     rdx, [rbp+SRWLock]
0x180070b4d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180070b52  mov     rax, [rbx+110h]
0x180070b59  mov     dword ptr [rax], 2
0x180070b5f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180070b63  test    rcx, rcx
0x180070b66  jz      short loc_180070B6E
0x180070b68  call    cs:__imp_ReleaseSRWLockExclusive
0x180070b6e  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180070b73  mov     rdi, rax
0x180070b76  mov     ecx, [rax]
0x180070b78  cmp     ecx, 4
0x180070b7b  jbe     short loc_180070BCC
0x180070b7d  call    cs:__imp_GetCurrentThreadId
0x180070b83  mov     dword ptr [rbp+SRWLock], eax
0x180070b86  mov     r8, [rbx+110h]
0x180070b8d  mov     ecx, [r8+48h]
0x180070b91  mov     [rbp+arg_8], ecx
0x180070b94  mov     eax, 1000000h
0x180070b99  mov     [rbp+arg_10], rax
0x180070b9d  add     r8, 8
0x180070ba1  lea     rax, [rbp+SRWLock]
0x180070ba5  mov     [rsp+140h+var_110], rax
0x180070baa  lea     rax, [rbp+arg_8]
0x180070bae  mov     [rsp+140h+var_118], rax
0x180070bb3  lea     rax, [rbp+arg_10]
0x180070bb7  mov     [rsp+140h+var_120], rax
0x180070bbc  lea     rdx, byte_1800D63D7
0x180070bc3  mov     rcx, rdi
0x180070bc6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180070bcb  nop
0x180070bcc  lea     rcx, [rbx+120h]; this
0x180070bd3  cmp     dword ptr [rcx+18h], 0
0x180070bd7  jz      short loc_180070BDF
0x180070bd9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180070bde  nop
0x180070bdf  add     rsp, 130h
0x180070be6  pop     rdi
0x180070be7  pop     rbx
0x180070be8  pop     rbp
0x180070be9  retn
```
