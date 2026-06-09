# wpc::Sync::Internal::SyncLogger::SyncScreenTimeLimits::StopActivity(void)

- ea: `0x180085460`
- end: `0x1800856da`
- name: `?StopActivity@SyncScreenTimeLimits@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::SyncScreenTimeLimits *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180085460`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008566d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008566d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800854ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085658`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800854ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085658`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::SyncScreenTimeLimits::StopActivity(
        wpc::Sync::Internal::SyncLogger::SyncScreenTimeLimits *this)
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
        (unsigned int)&dword_1800D793C,
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
        (unsigned int)byte_1800D77F3,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::SyncScreenTimeLimits *)((char *)this + 288));
}

```

## disassembly

```asm
0x180085460  push    rbp
0x180085462  push    rbx
0x180085463  push    rdi
0x180085464  lea     rbp, [rsp+10h]
0x180085469  sub     rsp, 130h
0x180085470  mov     rbx, rcx
0x180085473  mov     rdi, [rcx+110h]
0x18008547a  mov     eax, [rdi+48h]
0x18008547d  test    eax, eax
0x18008547f  jns     loc_180085639
0x180085485  add     rdi, 50h ; 'P'
0x180085489  cmp     eax, [rdi+8]
0x18008548c  jnz     loc_180085639
0x180085492  test    rdi, rdi
0x180085495  jz      loc_180085639
0x18008549b  lea     rdx, [rbp+SRWLock]
0x18008549f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800854a4  mov     rax, [rbx+110h]
0x1800854ab  mov     dword ptr [rax], 2
0x1800854b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800854b5  test    rcx, rcx
0x1800854b8  jz      short loc_1800854C0
0x1800854ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800854c0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800854c5  mov     r9, rax
0x1800854c8  mov     ecx, [rax]
0x1800854ca  cmp     ecx, 4
0x1800854cd  jbe     loc_1800856BC
0x1800854d3  mov     rcx, [rdi+30h]
0x1800854d7  mov     [rbp+var_70], rcx
0x1800854db  mov     ecx, [rdi+44h]
0x1800854de  mov     dword ptr [rbp+SRWLock], ecx
0x1800854e1  mov     ecx, [rdi+10h]
0x1800854e4  mov     [rbp+arg_8], ecx
0x1800854e7  mov     rcx, [rdi+78h]
0x1800854eb  mov     [rbp+var_68], rcx
0x1800854ef  mov     rax, [rdi+70h]
0x1800854f3  mov     [rbp+var_60], rax
0x1800854f7  mov     eax, [rdi+68h]
0x1800854fa  mov     dword ptr [rbp+arg_10], eax
0x1800854fd  mov     rax, [rdi+60h]
0x180085501  mov     [rbp+var_58], rax
0x180085505  mov     rax, [rdi+58h]
0x180085509  mov     [rbp+var_50], rax
0x18008550d  mov     eax, [rdi+50h]
0x180085510  mov     [rbp+arg_18], eax
0x180085513  mov     rax, [rdi+48h]
0x180085517  mov     [rbp+var_48], rax
0x18008551b  mov     eax, [rdi+20h]
0x18008551e  mov     [rbp+var_80], eax
0x180085521  mov     rax, [rdi+18h]
0x180085525  mov     [rbp+var_40], rax
0x180085529  mov     eax, [rdi]
0x18008552b  mov     [rbp+var_7C], eax
0x18008552e  mov     rax, [rdi+80h]
0x180085535  mov     [rbp+var_38], rax
0x180085539  mov     eax, [rdi+40h]
0x18008553c  mov     [rbp+var_78], eax
0x18008553f  mov     rax, [rdi+38h]
0x180085543  mov     [rbp+var_30], rax
0x180085547  mov     eax, [rdi+8]
0x18008554a  mov     [rbp+var_74], eax
0x18008554d  mov     eax, 1000000h
0x180085552  mov     [rbp+var_28], rax
0x180085556  mov     [rbp+var_20], rax
0x18008555a  mov     r8, [rbx+110h]
0x180085561  add     r8, 8
0x180085565  lea     rax, [rbp+var_70]
0x180085569  mov     [rsp+140h+var_90], rax
0x180085571  lea     rax, [rbp+SRWLock]
0x180085575  mov     [rsp+140h+var_98], rax
0x18008557d  lea     rax, [rbp+arg_8]
0x180085581  mov     [rsp+140h+var_A0], rax
0x180085589  lea     rax, [rbp+var_68]
0x18008558d  mov     [rsp+140h+var_A8], rax
0x180085595  lea     rax, [rbp+var_60]
0x180085599  mov     [rsp+140h+var_B0], rax
0x1800855a1  lea     rax, [rbp+arg_10]
0x1800855a5  mov     [rsp+140h+var_B8], rax
0x1800855ad  lea     rax, [rbp+var_58]
0x1800855b1  mov     [rsp+140h+var_C0], rax
0x1800855b9  lea     rax, [rbp+var_50]
0x1800855bd  mov     [rsp+140h+var_C8], rax
0x1800855c2  lea     rax, [rbp+arg_18]
0x1800855c6  mov     [rsp+140h+var_D0], rax
0x1800855cb  lea     rax, [rbp+var_48]
0x1800855cf  mov     [rsp+140h+var_D8], rax
0x1800855d4  lea     rax, [rbp+var_80]
0x1800855d8  mov     [rsp+140h+var_E0], rax
0x1800855dd  lea     rax, [rbp+var_40]
0x1800855e1  mov     [rsp+140h+var_E8], rax
0x1800855e6  lea     rax, [rbp+var_7C]
0x1800855ea  mov     [rsp+140h+var_F0], rax
0x1800855ef  lea     rax, [rbp+var_38]
0x1800855f3  mov     [rsp+140h+var_F8], rax
0x1800855f8  lea     rax, [rbp+var_78]
0x1800855fc  mov     [rsp+140h+var_100], rax
0x180085601  lea     rax, [rbp+var_30]
0x180085605  mov     [rsp+140h+var_108], rax
0x18008560a  lea     rax, [rbp+var_74]
0x18008560e  mov     [rsp+140h+var_110], rax
0x180085613  lea     rax, [rbp+var_28]
0x180085617  mov     [rsp+140h+var_118], rax
0x18008561c  lea     rax, [rbp+var_20]
0x180085620  mov     [rsp+140h+var_120], rax
0x180085625  lea     rdx, dword_1800D793C
0x18008562c  mov     rcx, r9
0x18008562f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180085634  jmp     loc_1800856BC
0x180085639  lea     rdx, [rbp+SRWLock]
0x18008563d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180085642  mov     rax, [rbx+110h]
0x180085649  mov     dword ptr [rax], 2
0x18008564f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180085653  test    rcx, rcx
0x180085656  jz      short loc_18008565E
0x180085658  call    cs:__imp_ReleaseSRWLockExclusive
0x18008565e  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180085663  mov     rdi, rax
0x180085666  mov     ecx, [rax]
0x180085668  cmp     ecx, 4
0x18008566b  jbe     short loc_1800856BC
0x18008566d  call    cs:__imp_GetCurrentThreadId
0x180085673  mov     dword ptr [rbp+SRWLock], eax
0x180085676  mov     r8, [rbx+110h]
0x18008567d  mov     ecx, [r8+48h]
0x180085681  mov     [rbp+arg_8], ecx
0x180085684  mov     eax, 1000000h
0x180085689  mov     [rbp+arg_10], rax
0x18008568d  add     r8, 8
0x180085691  lea     rax, [rbp+SRWLock]
0x180085695  mov     [rsp+140h+var_110], rax
0x18008569a  lea     rax, [rbp+arg_8]
0x18008569e  mov     [rsp+140h+var_118], rax
0x1800856a3  lea     rax, [rbp+arg_10]
0x1800856a7  mov     [rsp+140h+var_120], rax
0x1800856ac  lea     rdx, byte_1800D77F3
0x1800856b3  mov     rcx, rdi
0x1800856b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800856bb  nop
0x1800856bc  lea     rcx, [rbx+120h]; this
0x1800856c3  cmp     dword ptr [rcx+18h], 0
0x1800856c7  jz      short loc_1800856CF
0x1800856c9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800856ce  nop
0x1800856cf  add     rsp, 130h
0x1800856d6  pop     rdi
0x1800856d7  pop     rbx
0x1800856d8  pop     rbp
0x1800856d9  retn
```
