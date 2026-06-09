# wpc::Sync::Internal::SyncLogger::RegisterChildAccountMapping::StopActivity(void)

- ea: `0x1800847e0`
- end: `0x180084a5a`
- name: `?StopActivity@RegisterChildAccountMapping@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::RegisterChildAccountMapping *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x1800847e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800849ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800849ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008483a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800849d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008483a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800849d8`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::RegisterChildAccountMapping::StopActivity(
        wpc::Sync::Internal::SyncLogger::RegisterChildAccountMapping *this)
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
        (unsigned int)&word_1800D6AAE,
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
        (unsigned int)&dword_1800D6C04,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::RegisterChildAccountMapping *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800847e0  push    rbp
0x1800847e2  push    rbx
0x1800847e3  push    rdi
0x1800847e4  lea     rbp, [rsp+10h]
0x1800847e9  sub     rsp, 130h
0x1800847f0  mov     rbx, rcx
0x1800847f3  mov     rdi, [rcx+110h]
0x1800847fa  mov     eax, [rdi+48h]
0x1800847fd  test    eax, eax
0x1800847ff  jns     loc_1800849B9
0x180084805  add     rdi, 50h ; 'P'
0x180084809  cmp     eax, [rdi+8]
0x18008480c  jnz     loc_1800849B9
0x180084812  test    rdi, rdi
0x180084815  jz      loc_1800849B9
0x18008481b  lea     rdx, [rbp+SRWLock]
0x18008481f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084824  mov     rax, [rbx+110h]
0x18008482b  mov     dword ptr [rax], 2
0x180084831  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084835  test    rcx, rcx
0x180084838  jz      short loc_180084840
0x18008483a  call    cs:__imp_ReleaseSRWLockExclusive
0x180084840  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084845  mov     r9, rax
0x180084848  mov     ecx, [rax]
0x18008484a  cmp     ecx, 4
0x18008484d  jbe     loc_180084A3C
0x180084853  mov     rcx, [rdi+30h]
0x180084857  mov     [rbp+var_70], rcx
0x18008485b  mov     ecx, [rdi+44h]
0x18008485e  mov     dword ptr [rbp+SRWLock], ecx
0x180084861  mov     ecx, [rdi+10h]
0x180084864  mov     [rbp+arg_8], ecx
0x180084867  mov     rcx, [rdi+78h]
0x18008486b  mov     [rbp+var_68], rcx
0x18008486f  mov     rax, [rdi+70h]
0x180084873  mov     [rbp+var_60], rax
0x180084877  mov     eax, [rdi+68h]
0x18008487a  mov     dword ptr [rbp+arg_10], eax
0x18008487d  mov     rax, [rdi+60h]
0x180084881  mov     [rbp+var_58], rax
0x180084885  mov     rax, [rdi+58h]
0x180084889  mov     [rbp+var_50], rax
0x18008488d  mov     eax, [rdi+50h]
0x180084890  mov     [rbp+arg_18], eax
0x180084893  mov     rax, [rdi+48h]
0x180084897  mov     [rbp+var_48], rax
0x18008489b  mov     eax, [rdi+20h]
0x18008489e  mov     [rbp+var_80], eax
0x1800848a1  mov     rax, [rdi+18h]
0x1800848a5  mov     [rbp+var_40], rax
0x1800848a9  mov     eax, [rdi]
0x1800848ab  mov     [rbp+var_7C], eax
0x1800848ae  mov     rax, [rdi+80h]
0x1800848b5  mov     [rbp+var_38], rax
0x1800848b9  mov     eax, [rdi+40h]
0x1800848bc  mov     [rbp+var_78], eax
0x1800848bf  mov     rax, [rdi+38h]
0x1800848c3  mov     [rbp+var_30], rax
0x1800848c7  mov     eax, [rdi+8]
0x1800848ca  mov     [rbp+var_74], eax
0x1800848cd  mov     eax, 1000000h
0x1800848d2  mov     [rbp+var_28], rax
0x1800848d6  mov     [rbp+var_20], rax
0x1800848da  mov     r8, [rbx+110h]
0x1800848e1  add     r8, 8
0x1800848e5  lea     rax, [rbp+var_70]
0x1800848e9  mov     [rsp+140h+var_90], rax
0x1800848f1  lea     rax, [rbp+SRWLock]
0x1800848f5  mov     [rsp+140h+var_98], rax
0x1800848fd  lea     rax, [rbp+arg_8]
0x180084901  mov     [rsp+140h+var_A0], rax
0x180084909  lea     rax, [rbp+var_68]
0x18008490d  mov     [rsp+140h+var_A8], rax
0x180084915  lea     rax, [rbp+var_60]
0x180084919  mov     [rsp+140h+var_B0], rax
0x180084921  lea     rax, [rbp+arg_10]
0x180084925  mov     [rsp+140h+var_B8], rax
0x18008492d  lea     rax, [rbp+var_58]
0x180084931  mov     [rsp+140h+var_C0], rax
0x180084939  lea     rax, [rbp+var_50]
0x18008493d  mov     [rsp+140h+var_C8], rax
0x180084942  lea     rax, [rbp+arg_18]
0x180084946  mov     [rsp+140h+var_D0], rax
0x18008494b  lea     rax, [rbp+var_48]
0x18008494f  mov     [rsp+140h+var_D8], rax
0x180084954  lea     rax, [rbp+var_80]
0x180084958  mov     [rsp+140h+var_E0], rax
0x18008495d  lea     rax, [rbp+var_40]
0x180084961  mov     [rsp+140h+var_E8], rax
0x180084966  lea     rax, [rbp+var_7C]
0x18008496a  mov     [rsp+140h+var_F0], rax
0x18008496f  lea     rax, [rbp+var_38]
0x180084973  mov     [rsp+140h+var_F8], rax
0x180084978  lea     rax, [rbp+var_78]
0x18008497c  mov     [rsp+140h+var_100], rax
0x180084981  lea     rax, [rbp+var_30]
0x180084985  mov     [rsp+140h+var_108], rax
0x18008498a  lea     rax, [rbp+var_74]
0x18008498e  mov     [rsp+140h+var_110], rax
0x180084993  lea     rax, [rbp+var_28]
0x180084997  mov     [rsp+140h+var_118], rax
0x18008499c  lea     rax, [rbp+var_20]
0x1800849a0  mov     [rsp+140h+var_120], rax
0x1800849a5  lea     rdx, word_1800D6AAE
0x1800849ac  mov     rcx, r9
0x1800849af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800849b4  jmp     loc_180084A3C
0x1800849b9  lea     rdx, [rbp+SRWLock]
0x1800849bd  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800849c2  mov     rax, [rbx+110h]
0x1800849c9  mov     dword ptr [rax], 2
0x1800849cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800849d3  test    rcx, rcx
0x1800849d6  jz      short loc_1800849DE
0x1800849d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800849de  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800849e3  mov     rdi, rax
0x1800849e6  mov     ecx, [rax]
0x1800849e8  cmp     ecx, 4
0x1800849eb  jbe     short loc_180084A3C
0x1800849ed  call    cs:__imp_GetCurrentThreadId
0x1800849f3  mov     dword ptr [rbp+SRWLock], eax
0x1800849f6  mov     r8, [rbx+110h]
0x1800849fd  mov     ecx, [r8+48h]
0x180084a01  mov     [rbp+arg_8], ecx
0x180084a04  mov     eax, 1000000h
0x180084a09  mov     [rbp+arg_10], rax
0x180084a0d  add     r8, 8
0x180084a11  lea     rax, [rbp+SRWLock]
0x180084a15  mov     [rsp+140h+var_110], rax
0x180084a1a  lea     rax, [rbp+arg_8]
0x180084a1e  mov     [rsp+140h+var_118], rax
0x180084a23  lea     rax, [rbp+arg_10]
0x180084a27  mov     [rsp+140h+var_120], rax
0x180084a2c  lea     rdx, dword_1800D6C04
0x180084a33  mov     rcx, rdi
0x180084a36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180084a3b  nop
0x180084a3c  lea     rcx, [rbx+120h]; this
0x180084a43  cmp     dword ptr [rcx+18h], 0
0x180084a47  jz      short loc_180084A4F
0x180084a49  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180084a4e  nop
0x180084a4f  add     rsp, 130h
0x180084a56  pop     rdi
0x180084a57  pop     rbx
0x180084a58  pop     rbp
0x180084a59  retn
```
