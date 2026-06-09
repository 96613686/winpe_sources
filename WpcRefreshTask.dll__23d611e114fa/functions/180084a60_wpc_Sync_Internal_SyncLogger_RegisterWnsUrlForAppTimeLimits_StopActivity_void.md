# wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForAppTimeLimits::StopActivity(void)

- ea: `0x180084a60`
- end: `0x180084cda`
- name: `?StopActivity@RegisterWnsUrlForAppTimeLimits@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForAppTimeLimits *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180084a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084c6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084c6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084c58`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForAppTimeLimits::StopActivity(
        wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForAppTimeLimits *this)
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
  __int64 v24[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v26; // [rsp+158h] [rbp+18h] BYREF
  __int64 v27; // [rsp+160h] [rbp+20h] BYREF
  int v28; // [rsp+168h] [rbp+28h] BYREF

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
    v5 = wpc::Sync::Internal::SyncLogger::Provider();
    if ( *(_DWORD *)v5 > 4u )
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
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)byte_1800D7269,
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
    wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = wpc::Sync::Internal::SyncLogger::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v26 = *(_DWORD *)(v8 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&word_1800D7096,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForAppTimeLimits *)((char *)this + 288));
}

```

## disassembly

```asm
0x180084a60  push    rbp
0x180084a62  push    rbx
0x180084a63  push    rdi
0x180084a64  lea     rbp, [rsp+10h]
0x180084a69  sub     rsp, 130h
0x180084a70  mov     rbx, rcx
0x180084a73  mov     rdi, [rcx+110h]
0x180084a7a  mov     eax, [rdi+48h]
0x180084a7d  test    eax, eax
0x180084a7f  jns     loc_180084C39
0x180084a85  add     rdi, 50h ; 'P'
0x180084a89  cmp     eax, [rdi+8]
0x180084a8c  jnz     loc_180084C39
0x180084a92  test    rdi, rdi
0x180084a95  jz      loc_180084C39
0x180084a9b  lea     rdx, [rbp+SRWLock]
0x180084a9f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084aa4  mov     rax, [rbx+110h]
0x180084aab  mov     dword ptr [rax], 2
0x180084ab1  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084ab5  test    rcx, rcx
0x180084ab8  jz      short loc_180084AC0
0x180084aba  call    cs:__imp_ReleaseSRWLockExclusive
0x180084ac0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084ac5  mov     r9, rax
0x180084ac8  mov     ecx, [rax]
0x180084aca  cmp     ecx, 4
0x180084acd  jbe     loc_180084CBC
0x180084ad3  mov     rcx, [rdi+30h]
0x180084ad7  mov     [rbp+var_70], rcx
0x180084adb  mov     ecx, [rdi+44h]
0x180084ade  mov     dword ptr [rbp+SRWLock], ecx
0x180084ae1  mov     ecx, [rdi+10h]
0x180084ae4  mov     [rbp+arg_8], ecx
0x180084ae7  mov     rcx, [rdi+78h]
0x180084aeb  mov     [rbp+var_68], rcx
0x180084aef  mov     rax, [rdi+70h]
0x180084af3  mov     [rbp+var_60], rax
0x180084af7  mov     eax, [rdi+68h]
0x180084afa  mov     dword ptr [rbp+arg_10], eax
0x180084afd  mov     rax, [rdi+60h]
0x180084b01  mov     [rbp+var_58], rax
0x180084b05  mov     rax, [rdi+58h]
0x180084b09  mov     [rbp+var_50], rax
0x180084b0d  mov     eax, [rdi+50h]
0x180084b10  mov     [rbp+arg_18], eax
0x180084b13  mov     rax, [rdi+48h]
0x180084b17  mov     [rbp+var_48], rax
0x180084b1b  mov     eax, [rdi+20h]
0x180084b1e  mov     [rbp+var_80], eax
0x180084b21  mov     rax, [rdi+18h]
0x180084b25  mov     [rbp+var_40], rax
0x180084b29  mov     eax, [rdi]
0x180084b2b  mov     [rbp+var_7C], eax
0x180084b2e  mov     rax, [rdi+80h]
0x180084b35  mov     [rbp+var_38], rax
0x180084b39  mov     eax, [rdi+40h]
0x180084b3c  mov     [rbp+var_78], eax
0x180084b3f  mov     rax, [rdi+38h]
0x180084b43  mov     [rbp+var_30], rax
0x180084b47  mov     eax, [rdi+8]
0x180084b4a  mov     [rbp+var_74], eax
0x180084b4d  mov     eax, 1000000h
0x180084b52  mov     [rbp+var_28], rax
0x180084b56  mov     [rbp+var_20], rax
0x180084b5a  mov     r8, [rbx+110h]
0x180084b61  add     r8, 8
0x180084b65  lea     rax, [rbp+var_70]
0x180084b69  mov     [rsp+140h+var_90], rax
0x180084b71  lea     rax, [rbp+SRWLock]
0x180084b75  mov     [rsp+140h+var_98], rax
0x180084b7d  lea     rax, [rbp+arg_8]
0x180084b81  mov     [rsp+140h+var_A0], rax
0x180084b89  lea     rax, [rbp+var_68]
0x180084b8d  mov     [rsp+140h+var_A8], rax
0x180084b95  lea     rax, [rbp+var_60]
0x180084b99  mov     [rsp+140h+var_B0], rax
0x180084ba1  lea     rax, [rbp+arg_10]
0x180084ba5  mov     [rsp+140h+var_B8], rax
0x180084bad  lea     rax, [rbp+var_58]
0x180084bb1  mov     [rsp+140h+var_C0], rax
0x180084bb9  lea     rax, [rbp+var_50]
0x180084bbd  mov     [rsp+140h+var_C8], rax
0x180084bc2  lea     rax, [rbp+arg_18]
0x180084bc6  mov     [rsp+140h+var_D0], rax
0x180084bcb  lea     rax, [rbp+var_48]
0x180084bcf  mov     [rsp+140h+var_D8], rax
0x180084bd4  lea     rax, [rbp+var_80]
0x180084bd8  mov     [rsp+140h+var_E0], rax
0x180084bdd  lea     rax, [rbp+var_40]
0x180084be1  mov     [rsp+140h+var_E8], rax
0x180084be6  lea     rax, [rbp+var_7C]
0x180084bea  mov     [rsp+140h+var_F0], rax
0x180084bef  lea     rax, [rbp+var_38]
0x180084bf3  mov     [rsp+140h+var_F8], rax
0x180084bf8  lea     rax, [rbp+var_78]
0x180084bfc  mov     [rsp+140h+var_100], rax
0x180084c01  lea     rax, [rbp+var_30]
0x180084c05  mov     [rsp+140h+var_108], rax
0x180084c0a  lea     rax, [rbp+var_74]
0x180084c0e  mov     [rsp+140h+var_110], rax
0x180084c13  lea     rax, [rbp+var_28]
0x180084c17  mov     [rsp+140h+var_118], rax
0x180084c1c  lea     rax, [rbp+var_20]
0x180084c20  mov     [rsp+140h+var_120], rax
0x180084c25  lea     rdx, byte_1800D7269
0x180084c2c  mov     rcx, r9
0x180084c2f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180084c34  jmp     loc_180084CBC
0x180084c39  lea     rdx, [rbp+SRWLock]
0x180084c3d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084c42  mov     rax, [rbx+110h]
0x180084c49  mov     dword ptr [rax], 2
0x180084c4f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084c53  test    rcx, rcx
0x180084c56  jz      short loc_180084C5E
0x180084c58  call    cs:__imp_ReleaseSRWLockExclusive
0x180084c5e  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084c63  mov     rdi, rax
0x180084c66  mov     ecx, [rax]
0x180084c68  cmp     ecx, 4
0x180084c6b  jbe     short loc_180084CBC
0x180084c6d  call    cs:__imp_GetCurrentThreadId
0x180084c73  mov     dword ptr [rbp+SRWLock], eax
0x180084c76  mov     r8, [rbx+110h]
0x180084c7d  mov     ecx, [r8+48h]
0x180084c81  mov     [rbp+arg_8], ecx
0x180084c84  mov     eax, 1000000h
0x180084c89  mov     [rbp+arg_10], rax
0x180084c8d  add     r8, 8
0x180084c91  lea     rax, [rbp+SRWLock]
0x180084c95  mov     [rsp+140h+var_110], rax
0x180084c9a  lea     rax, [rbp+arg_8]
0x180084c9e  mov     [rsp+140h+var_118], rax
0x180084ca3  lea     rax, [rbp+arg_10]
0x180084ca7  mov     [rsp+140h+var_120], rax
0x180084cac  lea     rdx, word_1800D7096
0x180084cb3  mov     rcx, rdi
0x180084cb6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180084cbb  nop
0x180084cbc  lea     rcx, [rbx+120h]; this
0x180084cc3  cmp     dword ptr [rcx+18h], 0
0x180084cc7  jz      short loc_180084CCF
0x180084cc9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180084cce  nop
0x180084ccf  add     rsp, 130h
0x180084cd6  pop     rdi
0x180084cd7  pop     rbx
0x180084cd8  pop     rbp
0x180084cd9  retn
```
