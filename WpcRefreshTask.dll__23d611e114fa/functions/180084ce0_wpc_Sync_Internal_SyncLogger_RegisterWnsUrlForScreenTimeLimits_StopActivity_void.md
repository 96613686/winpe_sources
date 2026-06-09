# wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForScreenTimeLimits::StopActivity(void)

- ea: `0x180084ce0`
- end: `0x180084f5a`
- name: `?StopActivity@RegisterWnsUrlForScreenTimeLimits@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForScreenTimeLimits *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180084ce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084eed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084ed8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084d3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084ed8`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForScreenTimeLimits::StopActivity(
        wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForScreenTimeLimits *this)
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
        (unsigned int)byte_1800D7473,
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
        (unsigned int)byte_1800D7411,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForScreenTimeLimits *)((char *)this + 288));
}

```

## disassembly

```asm
0x180084ce0  push    rbp
0x180084ce2  push    rbx
0x180084ce3  push    rdi
0x180084ce4  lea     rbp, [rsp+10h]
0x180084ce9  sub     rsp, 130h
0x180084cf0  mov     rbx, rcx
0x180084cf3  mov     rdi, [rcx+110h]
0x180084cfa  mov     eax, [rdi+48h]
0x180084cfd  test    eax, eax
0x180084cff  jns     loc_180084EB9
0x180084d05  add     rdi, 50h ; 'P'
0x180084d09  cmp     eax, [rdi+8]
0x180084d0c  jnz     loc_180084EB9
0x180084d12  test    rdi, rdi
0x180084d15  jz      loc_180084EB9
0x180084d1b  lea     rdx, [rbp+SRWLock]
0x180084d1f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084d24  mov     rax, [rbx+110h]
0x180084d2b  mov     dword ptr [rax], 2
0x180084d31  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084d35  test    rcx, rcx
0x180084d38  jz      short loc_180084D40
0x180084d3a  call    cs:__imp_ReleaseSRWLockExclusive
0x180084d40  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084d45  mov     r9, rax
0x180084d48  mov     ecx, [rax]
0x180084d4a  cmp     ecx, 4
0x180084d4d  jbe     loc_180084F3C
0x180084d53  mov     rcx, [rdi+30h]
0x180084d57  mov     [rbp+var_70], rcx
0x180084d5b  mov     ecx, [rdi+44h]
0x180084d5e  mov     dword ptr [rbp+SRWLock], ecx
0x180084d61  mov     ecx, [rdi+10h]
0x180084d64  mov     [rbp+arg_8], ecx
0x180084d67  mov     rcx, [rdi+78h]
0x180084d6b  mov     [rbp+var_68], rcx
0x180084d6f  mov     rax, [rdi+70h]
0x180084d73  mov     [rbp+var_60], rax
0x180084d77  mov     eax, [rdi+68h]
0x180084d7a  mov     dword ptr [rbp+arg_10], eax
0x180084d7d  mov     rax, [rdi+60h]
0x180084d81  mov     [rbp+var_58], rax
0x180084d85  mov     rax, [rdi+58h]
0x180084d89  mov     [rbp+var_50], rax
0x180084d8d  mov     eax, [rdi+50h]
0x180084d90  mov     [rbp+arg_18], eax
0x180084d93  mov     rax, [rdi+48h]
0x180084d97  mov     [rbp+var_48], rax
0x180084d9b  mov     eax, [rdi+20h]
0x180084d9e  mov     [rbp+var_80], eax
0x180084da1  mov     rax, [rdi+18h]
0x180084da5  mov     [rbp+var_40], rax
0x180084da9  mov     eax, [rdi]
0x180084dab  mov     [rbp+var_7C], eax
0x180084dae  mov     rax, [rdi+80h]
0x180084db5  mov     [rbp+var_38], rax
0x180084db9  mov     eax, [rdi+40h]
0x180084dbc  mov     [rbp+var_78], eax
0x180084dbf  mov     rax, [rdi+38h]
0x180084dc3  mov     [rbp+var_30], rax
0x180084dc7  mov     eax, [rdi+8]
0x180084dca  mov     [rbp+var_74], eax
0x180084dcd  mov     eax, 1000000h
0x180084dd2  mov     [rbp+var_28], rax
0x180084dd6  mov     [rbp+var_20], rax
0x180084dda  mov     r8, [rbx+110h]
0x180084de1  add     r8, 8
0x180084de5  lea     rax, [rbp+var_70]
0x180084de9  mov     [rsp+140h+var_90], rax
0x180084df1  lea     rax, [rbp+SRWLock]
0x180084df5  mov     [rsp+140h+var_98], rax
0x180084dfd  lea     rax, [rbp+arg_8]
0x180084e01  mov     [rsp+140h+var_A0], rax
0x180084e09  lea     rax, [rbp+var_68]
0x180084e0d  mov     [rsp+140h+var_A8], rax
0x180084e15  lea     rax, [rbp+var_60]
0x180084e19  mov     [rsp+140h+var_B0], rax
0x180084e21  lea     rax, [rbp+arg_10]
0x180084e25  mov     [rsp+140h+var_B8], rax
0x180084e2d  lea     rax, [rbp+var_58]
0x180084e31  mov     [rsp+140h+var_C0], rax
0x180084e39  lea     rax, [rbp+var_50]
0x180084e3d  mov     [rsp+140h+var_C8], rax
0x180084e42  lea     rax, [rbp+arg_18]
0x180084e46  mov     [rsp+140h+var_D0], rax
0x180084e4b  lea     rax, [rbp+var_48]
0x180084e4f  mov     [rsp+140h+var_D8], rax
0x180084e54  lea     rax, [rbp+var_80]
0x180084e58  mov     [rsp+140h+var_E0], rax
0x180084e5d  lea     rax, [rbp+var_40]
0x180084e61  mov     [rsp+140h+var_E8], rax
0x180084e66  lea     rax, [rbp+var_7C]
0x180084e6a  mov     [rsp+140h+var_F0], rax
0x180084e6f  lea     rax, [rbp+var_38]
0x180084e73  mov     [rsp+140h+var_F8], rax
0x180084e78  lea     rax, [rbp+var_78]
0x180084e7c  mov     [rsp+140h+var_100], rax
0x180084e81  lea     rax, [rbp+var_30]
0x180084e85  mov     [rsp+140h+var_108], rax
0x180084e8a  lea     rax, [rbp+var_74]
0x180084e8e  mov     [rsp+140h+var_110], rax
0x180084e93  lea     rax, [rbp+var_28]
0x180084e97  mov     [rsp+140h+var_118], rax
0x180084e9c  lea     rax, [rbp+var_20]
0x180084ea0  mov     [rsp+140h+var_120], rax
0x180084ea5  lea     rdx, byte_1800D7473
0x180084eac  mov     rcx, r9
0x180084eaf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180084eb4  jmp     loc_180084F3C
0x180084eb9  lea     rdx, [rbp+SRWLock]
0x180084ebd  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084ec2  mov     rax, [rbx+110h]
0x180084ec9  mov     dword ptr [rax], 2
0x180084ecf  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084ed3  test    rcx, rcx
0x180084ed6  jz      short loc_180084EDE
0x180084ed8  call    cs:__imp_ReleaseSRWLockExclusive
0x180084ede  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084ee3  mov     rdi, rax
0x180084ee6  mov     ecx, [rax]
0x180084ee8  cmp     ecx, 4
0x180084eeb  jbe     short loc_180084F3C
0x180084eed  call    cs:__imp_GetCurrentThreadId
0x180084ef3  mov     dword ptr [rbp+SRWLock], eax
0x180084ef6  mov     r8, [rbx+110h]
0x180084efd  mov     ecx, [r8+48h]
0x180084f01  mov     [rbp+arg_8], ecx
0x180084f04  mov     eax, 1000000h
0x180084f09  mov     [rbp+arg_10], rax
0x180084f0d  add     r8, 8
0x180084f11  lea     rax, [rbp+SRWLock]
0x180084f15  mov     [rsp+140h+var_110], rax
0x180084f1a  lea     rax, [rbp+arg_8]
0x180084f1e  mov     [rsp+140h+var_118], rax
0x180084f23  lea     rax, [rbp+arg_10]
0x180084f27  mov     [rsp+140h+var_120], rax
0x180084f2c  lea     rdx, byte_1800D7411
0x180084f33  mov     rcx, rdi
0x180084f36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180084f3b  nop
0x180084f3c  lea     rcx, [rbx+120h]; this
0x180084f43  cmp     dword ptr [rcx+18h], 0
0x180084f47  jz      short loc_180084F4F
0x180084f49  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180084f4e  nop
0x180084f4f  add     rsp, 130h
0x180084f56  pop     rdi
0x180084f57  pop     rbx
0x180084f58  pop     rbp
0x180084f59  retn
```
