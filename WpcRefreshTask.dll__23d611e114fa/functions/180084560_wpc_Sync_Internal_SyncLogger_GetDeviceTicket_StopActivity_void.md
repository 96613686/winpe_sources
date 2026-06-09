# wpc::Sync::Internal::SyncLogger::GetDeviceTicket::StopActivity(void)

- ea: `0x180084560`
- end: `0x1800847da`
- name: `?StopActivity@GetDeviceTicket@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::GetDeviceTicket *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x180084560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008476d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008476d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800845ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084758`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800845ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084758`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::GetDeviceTicket::StopActivity(
        wpc::Sync::Internal::SyncLogger::GetDeviceTicket *this)
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
        (unsigned int)byte_1800D7C79,
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
        (unsigned int)byte_1800D7C29,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::GetDeviceTicket *)((char *)this + 288));
}

```

## disassembly

```asm
0x180084560  push    rbp
0x180084562  push    rbx
0x180084563  push    rdi
0x180084564  lea     rbp, [rsp+10h]
0x180084569  sub     rsp, 130h
0x180084570  mov     rbx, rcx
0x180084573  mov     rdi, [rcx+110h]
0x18008457a  mov     eax, [rdi+48h]
0x18008457d  test    eax, eax
0x18008457f  jns     loc_180084739
0x180084585  add     rdi, 50h ; 'P'
0x180084589  cmp     eax, [rdi+8]
0x18008458c  jnz     loc_180084739
0x180084592  test    rdi, rdi
0x180084595  jz      loc_180084739
0x18008459b  lea     rdx, [rbp+SRWLock]
0x18008459f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800845a4  mov     rax, [rbx+110h]
0x1800845ab  mov     dword ptr [rax], 2
0x1800845b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800845b5  test    rcx, rcx
0x1800845b8  jz      short loc_1800845C0
0x1800845ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800845c0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800845c5  mov     r9, rax
0x1800845c8  mov     ecx, [rax]
0x1800845ca  cmp     ecx, 4
0x1800845cd  jbe     loc_1800847BC
0x1800845d3  mov     rcx, [rdi+30h]
0x1800845d7  mov     [rbp+var_70], rcx
0x1800845db  mov     ecx, [rdi+44h]
0x1800845de  mov     dword ptr [rbp+SRWLock], ecx
0x1800845e1  mov     ecx, [rdi+10h]
0x1800845e4  mov     [rbp+arg_8], ecx
0x1800845e7  mov     rcx, [rdi+78h]
0x1800845eb  mov     [rbp+var_68], rcx
0x1800845ef  mov     rax, [rdi+70h]
0x1800845f3  mov     [rbp+var_60], rax
0x1800845f7  mov     eax, [rdi+68h]
0x1800845fa  mov     dword ptr [rbp+arg_10], eax
0x1800845fd  mov     rax, [rdi+60h]
0x180084601  mov     [rbp+var_58], rax
0x180084605  mov     rax, [rdi+58h]
0x180084609  mov     [rbp+var_50], rax
0x18008460d  mov     eax, [rdi+50h]
0x180084610  mov     [rbp+arg_18], eax
0x180084613  mov     rax, [rdi+48h]
0x180084617  mov     [rbp+var_48], rax
0x18008461b  mov     eax, [rdi+20h]
0x18008461e  mov     [rbp+var_80], eax
0x180084621  mov     rax, [rdi+18h]
0x180084625  mov     [rbp+var_40], rax
0x180084629  mov     eax, [rdi]
0x18008462b  mov     [rbp+var_7C], eax
0x18008462e  mov     rax, [rdi+80h]
0x180084635  mov     [rbp+var_38], rax
0x180084639  mov     eax, [rdi+40h]
0x18008463c  mov     [rbp+var_78], eax
0x18008463f  mov     rax, [rdi+38h]
0x180084643  mov     [rbp+var_30], rax
0x180084647  mov     eax, [rdi+8]
0x18008464a  mov     [rbp+var_74], eax
0x18008464d  mov     eax, 1000000h
0x180084652  mov     [rbp+var_28], rax
0x180084656  mov     [rbp+var_20], rax
0x18008465a  mov     r8, [rbx+110h]
0x180084661  add     r8, 8
0x180084665  lea     rax, [rbp+var_70]
0x180084669  mov     [rsp+140h+var_90], rax
0x180084671  lea     rax, [rbp+SRWLock]
0x180084675  mov     [rsp+140h+var_98], rax
0x18008467d  lea     rax, [rbp+arg_8]
0x180084681  mov     [rsp+140h+var_A0], rax
0x180084689  lea     rax, [rbp+var_68]
0x18008468d  mov     [rsp+140h+var_A8], rax
0x180084695  lea     rax, [rbp+var_60]
0x180084699  mov     [rsp+140h+var_B0], rax
0x1800846a1  lea     rax, [rbp+arg_10]
0x1800846a5  mov     [rsp+140h+var_B8], rax
0x1800846ad  lea     rax, [rbp+var_58]
0x1800846b1  mov     [rsp+140h+var_C0], rax
0x1800846b9  lea     rax, [rbp+var_50]
0x1800846bd  mov     [rsp+140h+var_C8], rax
0x1800846c2  lea     rax, [rbp+arg_18]
0x1800846c6  mov     [rsp+140h+var_D0], rax
0x1800846cb  lea     rax, [rbp+var_48]
0x1800846cf  mov     [rsp+140h+var_D8], rax
0x1800846d4  lea     rax, [rbp+var_80]
0x1800846d8  mov     [rsp+140h+var_E0], rax
0x1800846dd  lea     rax, [rbp+var_40]
0x1800846e1  mov     [rsp+140h+var_E8], rax
0x1800846e6  lea     rax, [rbp+var_7C]
0x1800846ea  mov     [rsp+140h+var_F0], rax
0x1800846ef  lea     rax, [rbp+var_38]
0x1800846f3  mov     [rsp+140h+var_F8], rax
0x1800846f8  lea     rax, [rbp+var_78]
0x1800846fc  mov     [rsp+140h+var_100], rax
0x180084701  lea     rax, [rbp+var_30]
0x180084705  mov     [rsp+140h+var_108], rax
0x18008470a  lea     rax, [rbp+var_74]
0x18008470e  mov     [rsp+140h+var_110], rax
0x180084713  lea     rax, [rbp+var_28]
0x180084717  mov     [rsp+140h+var_118], rax
0x18008471c  lea     rax, [rbp+var_20]
0x180084720  mov     [rsp+140h+var_120], rax
0x180084725  lea     rdx, byte_1800D7C79
0x18008472c  mov     rcx, r9
0x18008472f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180084734  jmp     loc_1800847BC
0x180084739  lea     rdx, [rbp+SRWLock]
0x18008473d  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084742  mov     rax, [rbx+110h]
0x180084749  mov     dword ptr [rax], 2
0x18008474f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084753  test    rcx, rcx
0x180084756  jz      short loc_18008475E
0x180084758  call    cs:__imp_ReleaseSRWLockExclusive
0x18008475e  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084763  mov     rdi, rax
0x180084766  mov     ecx, [rax]
0x180084768  cmp     ecx, 4
0x18008476b  jbe     short loc_1800847BC
0x18008476d  call    cs:__imp_GetCurrentThreadId
0x180084773  mov     dword ptr [rbp+SRWLock], eax
0x180084776  mov     r8, [rbx+110h]
0x18008477d  mov     ecx, [r8+48h]
0x180084781  mov     [rbp+arg_8], ecx
0x180084784  mov     eax, 1000000h
0x180084789  mov     [rbp+arg_10], rax
0x18008478d  add     r8, 8
0x180084791  lea     rax, [rbp+SRWLock]
0x180084795  mov     [rsp+140h+var_110], rax
0x18008479a  lea     rax, [rbp+arg_8]
0x18008479e  mov     [rsp+140h+var_118], rax
0x1800847a3  lea     rax, [rbp+arg_10]
0x1800847a7  mov     [rsp+140h+var_120], rax
0x1800847ac  lea     rdx, byte_1800D7C29
0x1800847b3  mov     rcx, rdi
0x1800847b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800847bb  nop
0x1800847bc  lea     rcx, [rbx+120h]; this
0x1800847c3  cmp     dword ptr [rcx+18h], 0
0x1800847c7  jz      short loc_1800847CF
0x1800847c9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800847ce  nop
0x1800847cf  add     rsp, 130h
0x1800847d6  pop     rdi
0x1800847d7  pop     rbx
0x1800847d8  pop     rbp
0x1800847d9  retn
```
