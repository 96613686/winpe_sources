# wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForSettings::StopActivity(void)

- ea: `0x180084f60`
- end: `0x1800851da`
- name: `?StopActivity@RegisterWnsUrlForSettings@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForSettings *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180084f60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008516d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008516d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084fba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085158`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084fba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085158`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForSettings::StopActivity(
        wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForSettings *this)
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
        (unsigned int)&byte_1800D6E97,
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
        (unsigned int)&dword_1800D703C,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::RegisterWnsUrlForSettings *)((char *)this + 288));
}

```

## disassembly

```asm
0x180084f60  push    rbp
0x180084f62  push    rbx
0x180084f63  push    rdi
0x180084f64  lea     rbp, [rsp+10h]
0x180084f69  sub     rsp, 130h
0x180084f70  mov     rbx, rcx
0x180084f73  mov     rdi, [rcx+110h]
0x180084f7a  mov     eax, [rdi+48h]
0x180084f7d  test    eax, eax
0x180084f7f  jns     loc_180085139
0x180084f85  add     rdi, 50h ; 'P'
0x180084f89  cmp     eax, [rdi+8]
0x180084f8c  jnz     loc_180085139
0x180084f92  test    rdi, rdi
0x180084f95  jz      loc_180085139
0x180084f9b  lea     rdx, [rbp+SRWLock]
0x180084f9f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084fa4  mov     rax, [rbx+110h]
0x180084fab  mov     dword ptr [rax], 2
0x180084fb1  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084fb5  test    rcx, rcx
0x180084fb8  jz      short loc_180084FC0
0x180084fba  call    cs:__imp_ReleaseSRWLockExclusive
0x180084fc0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084fc5  mov     r9, rax
0x180084fc8  mov     ecx, [rax]
0x180084fca  cmp     ecx, 4
0x180084fcd  jbe     loc_1800851BC
0x180084fd3  mov     rcx, [rdi+30h]
0x180084fd7  mov     [rbp+var_70], rcx
0x180084fdb  mov     ecx, [rdi+44h]
0x180084fde  mov     dword ptr [rbp+SRWLock], ecx
0x180084fe1  mov     ecx, [rdi+10h]
0x180084fe4  mov     [rbp+arg_8], ecx
0x180084fe7  mov     rcx, [rdi+78h]
0x180084feb  mov     [rbp+var_68], rcx
0x180084fef  mov     rax, [rdi+70h]
0x180084ff3  mov     [rbp+var_60], rax
0x180084ff7  mov     eax, [rdi+68h]
0x180084ffa  mov     dword ptr [rbp+arg_10], eax
0x180084ffd  mov     rax, [rdi+60h]
0x180085001  mov     [rbp+var_58], rax
0x180085005  mov     rax, [rdi+58h]
0x180085009  mov     [rbp+var_50], rax
0x18008500d  mov     eax, [rdi+50h]
0x180085010  mov     [rbp+arg_18], eax
0x180085013  mov     rax, [rdi+48h]
0x180085017  mov     [rbp+var_48], rax
0x18008501b  mov     eax, [rdi+20h]
0x18008501e  mov     [rbp+var_80], eax
0x180085021  mov     rax, [rdi+18h]
0x180085025  mov     [rbp+var_40], rax
0x180085029  mov     eax, [rdi]
0x18008502b  mov     [rbp+var_7C], eax
0x18008502e  mov     rax, [rdi+80h]
0x180085035  mov     [rbp+var_38], rax
0x180085039  mov     eax, [rdi+40h]
0x18008503c  mov     [rbp+var_78], eax
0x18008503f  mov     rax, [rdi+38h]
0x180085043  mov     [rbp+var_30], rax
0x180085047  mov     eax, [rdi+8]
0x18008504a  mov     [rbp+var_74], eax
0x18008504d  mov     eax, 1000000h
0x180085052  mov     [rbp+var_28], rax
0x180085056  mov     [rbp+var_20], rax
0x18008505a  mov     r8, [rbx+110h]
0x180085061  add     r8, 8
0x180085065  lea     rax, [rbp+var_70]
0x180085069  mov     [rsp+140h+var_90], rax
0x180085071  lea     rax, [rbp+SRWLock]
0x180085075  mov     [rsp+140h+var_98], rax
0x18008507d  lea     rax, [rbp+arg_8]
0x180085081  mov     [rsp+140h+var_A0], rax
0x180085089  lea     rax, [rbp+var_68]
0x18008508d  mov     [rsp+140h+var_A8], rax
0x180085095  lea     rax, [rbp+var_60]
0x180085099  mov     [rsp+140h+var_B0], rax
0x1800850a1  lea     rax, [rbp+arg_10]
0x1800850a5  mov     [rsp+140h+var_B8], rax
0x1800850ad  lea     rax, [rbp+var_58]
0x1800850b1  mov     [rsp+140h+var_C0], rax
0x1800850b9  lea     rax, [rbp+var_50]
0x1800850bd  mov     [rsp+140h+var_C8], rax
0x1800850c2  lea     rax, [rbp+arg_18]
0x1800850c6  mov     [rsp+140h+var_D0], rax
0x1800850cb  lea     rax, [rbp+var_48]
0x1800850cf  mov     [rsp+140h+var_D8], rax
0x1800850d4  lea     rax, [rbp+var_80]
0x1800850d8  mov     [rsp+140h+var_E0], rax
0x1800850dd  lea     rax, [rbp+var_40]
0x1800850e1  mov     [rsp+140h+var_E8], rax
0x1800850e6  lea     rax, [rbp+var_7C]
0x1800850ea  mov     [rsp+140h+var_F0], rax
0x1800850ef  lea     rax, [rbp+var_38]
0x1800850f3  mov     [rsp+140h+var_F8], rax
0x1800850f8  lea     rax, [rbp+var_78]
0x1800850fc  mov     [rsp+140h+var_100], rax
0x180085101  lea     rax, [rbp+var_30]
0x180085105  mov     [rsp+140h+var_108], rax
0x18008510a  lea     rax, [rbp+var_74]
0x18008510e  mov     [rsp+140h+var_110], rax
0x180085113  lea     rax, [rbp+var_28]
0x180085117  mov     [rsp+140h+var_118], rax
0x18008511c  lea     rax, [rbp+var_20]
0x180085120  mov     [rsp+140h+var_120], rax
0x180085125  lea     rdx, byte_1800D6E97
0x18008512c  mov     rcx, r9
0x18008512f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180085134  jmp     loc_1800851BC
0x180085139  lea     rdx, [rbp+SRWLock]
0x18008513d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180085142  mov     rax, [rbx+110h]
0x180085149  mov     dword ptr [rax], 2
0x18008514f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180085153  test    rcx, rcx
0x180085156  jz      short loc_18008515E
0x180085158  call    cs:__imp_ReleaseSRWLockExclusive
0x18008515e  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180085163  mov     rdi, rax
0x180085166  mov     ecx, [rax]
0x180085168  cmp     ecx, 4
0x18008516b  jbe     short loc_1800851BC
0x18008516d  call    cs:__imp_GetCurrentThreadId
0x180085173  mov     dword ptr [rbp+SRWLock], eax
0x180085176  mov     r8, [rbx+110h]
0x18008517d  mov     ecx, [r8+48h]
0x180085181  mov     [rbp+arg_8], ecx
0x180085184  mov     eax, 1000000h
0x180085189  mov     [rbp+arg_10], rax
0x18008518d  add     r8, 8
0x180085191  lea     rax, [rbp+SRWLock]
0x180085195  mov     [rsp+140h+var_110], rax
0x18008519a  lea     rax, [rbp+arg_8]
0x18008519e  mov     [rsp+140h+var_118], rax
0x1800851a3  lea     rax, [rbp+arg_10]
0x1800851a7  mov     [rsp+140h+var_120], rax
0x1800851ac  lea     rdx, dword_1800D703C
0x1800851b3  mov     rcx, rdi
0x1800851b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800851bb  nop
0x1800851bc  lea     rcx, [rbx+120h]; this
0x1800851c3  cmp     dword ptr [rcx+18h], 0
0x1800851c7  jz      short loc_1800851CF
0x1800851c9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800851ce  nop
0x1800851cf  add     rsp, 130h
0x1800851d6  pop     rdi
0x1800851d7  pop     rbx
0x1800851d8  pop     rbp
0x1800851d9  retn
```
