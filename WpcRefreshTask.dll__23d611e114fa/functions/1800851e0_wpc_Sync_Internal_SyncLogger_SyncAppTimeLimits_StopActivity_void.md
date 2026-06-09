# wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits::StopActivity(void)

- ea: `0x1800851e0`
- end: `0x18008545a`
- name: `?StopActivity@SyncAppTimeLimits@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x1800851e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800853ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800853ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008523a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800853d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008523a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800853d8`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits::StopActivity(
        wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits *this)
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
        (unsigned int)byte_1800D7A8B,
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
        (unsigned int)&byte_1800D7BD7,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800851e0  push    rbp
0x1800851e2  push    rbx
0x1800851e3  push    rdi
0x1800851e4  lea     rbp, [rsp+10h]
0x1800851e9  sub     rsp, 130h
0x1800851f0  mov     rbx, rcx
0x1800851f3  mov     rdi, [rcx+110h]
0x1800851fa  mov     eax, [rdi+48h]
0x1800851fd  test    eax, eax
0x1800851ff  jns     loc_1800853B9
0x180085205  add     rdi, 50h ; 'P'
0x180085209  cmp     eax, [rdi+8]
0x18008520c  jnz     loc_1800853B9
0x180085212  test    rdi, rdi
0x180085215  jz      loc_1800853B9
0x18008521b  lea     rdx, [rbp+SRWLock]
0x18008521f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180085224  mov     rax, [rbx+110h]
0x18008522b  mov     dword ptr [rax], 2
0x180085231  mov     rcx, [rbp+SRWLock]; SRWLock
0x180085235  test    rcx, rcx
0x180085238  jz      short loc_180085240
0x18008523a  call    cs:__imp_ReleaseSRWLockExclusive
0x180085240  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180085245  mov     r9, rax
0x180085248  mov     ecx, [rax]
0x18008524a  cmp     ecx, 4
0x18008524d  jbe     loc_18008543C
0x180085253  mov     rcx, [rdi+30h]
0x180085257  mov     [rbp+var_70], rcx
0x18008525b  mov     ecx, [rdi+44h]
0x18008525e  mov     dword ptr [rbp+SRWLock], ecx
0x180085261  mov     ecx, [rdi+10h]
0x180085264  mov     [rbp+arg_8], ecx
0x180085267  mov     rcx, [rdi+78h]
0x18008526b  mov     [rbp+var_68], rcx
0x18008526f  mov     rax, [rdi+70h]
0x180085273  mov     [rbp+var_60], rax
0x180085277  mov     eax, [rdi+68h]
0x18008527a  mov     dword ptr [rbp+arg_10], eax
0x18008527d  mov     rax, [rdi+60h]
0x180085281  mov     [rbp+var_58], rax
0x180085285  mov     rax, [rdi+58h]
0x180085289  mov     [rbp+var_50], rax
0x18008528d  mov     eax, [rdi+50h]
0x180085290  mov     [rbp+arg_18], eax
0x180085293  mov     rax, [rdi+48h]
0x180085297  mov     [rbp+var_48], rax
0x18008529b  mov     eax, [rdi+20h]
0x18008529e  mov     [rbp+var_80], eax
0x1800852a1  mov     rax, [rdi+18h]
0x1800852a5  mov     [rbp+var_40], rax
0x1800852a9  mov     eax, [rdi]
0x1800852ab  mov     [rbp+var_7C], eax
0x1800852ae  mov     rax, [rdi+80h]
0x1800852b5  mov     [rbp+var_38], rax
0x1800852b9  mov     eax, [rdi+40h]
0x1800852bc  mov     [rbp+var_78], eax
0x1800852bf  mov     rax, [rdi+38h]
0x1800852c3  mov     [rbp+var_30], rax
0x1800852c7  mov     eax, [rdi+8]
0x1800852ca  mov     [rbp+var_74], eax
0x1800852cd  mov     eax, 1000000h
0x1800852d2  mov     [rbp+var_28], rax
0x1800852d6  mov     [rbp+var_20], rax
0x1800852da  mov     r8, [rbx+110h]
0x1800852e1  add     r8, 8
0x1800852e5  lea     rax, [rbp+var_70]
0x1800852e9  mov     [rsp+140h+var_90], rax
0x1800852f1  lea     rax, [rbp+SRWLock]
0x1800852f5  mov     [rsp+140h+var_98], rax
0x1800852fd  lea     rax, [rbp+arg_8]
0x180085301  mov     [rsp+140h+var_A0], rax
0x180085309  lea     rax, [rbp+var_68]
0x18008530d  mov     [rsp+140h+var_A8], rax
0x180085315  lea     rax, [rbp+var_60]
0x180085319  mov     [rsp+140h+var_B0], rax
0x180085321  lea     rax, [rbp+arg_10]
0x180085325  mov     [rsp+140h+var_B8], rax
0x18008532d  lea     rax, [rbp+var_58]
0x180085331  mov     [rsp+140h+var_C0], rax
0x180085339  lea     rax, [rbp+var_50]
0x18008533d  mov     [rsp+140h+var_C8], rax
0x180085342  lea     rax, [rbp+arg_18]
0x180085346  mov     [rsp+140h+var_D0], rax
0x18008534b  lea     rax, [rbp+var_48]
0x18008534f  mov     [rsp+140h+var_D8], rax
0x180085354  lea     rax, [rbp+var_80]
0x180085358  mov     [rsp+140h+var_E0], rax
0x18008535d  lea     rax, [rbp+var_40]
0x180085361  mov     [rsp+140h+var_E8], rax
0x180085366  lea     rax, [rbp+var_7C]
0x18008536a  mov     [rsp+140h+var_F0], rax
0x18008536f  lea     rax, [rbp+var_38]
0x180085373  mov     [rsp+140h+var_F8], rax
0x180085378  lea     rax, [rbp+var_78]
0x18008537c  mov     [rsp+140h+var_100], rax
0x180085381  lea     rax, [rbp+var_30]
0x180085385  mov     [rsp+140h+var_108], rax
0x18008538a  lea     rax, [rbp+var_74]
0x18008538e  mov     [rsp+140h+var_110], rax
0x180085393  lea     rax, [rbp+var_28]
0x180085397  mov     [rsp+140h+var_118], rax
0x18008539c  lea     rax, [rbp+var_20]
0x1800853a0  mov     [rsp+140h+var_120], rax
0x1800853a5  lea     rdx, byte_1800D7A8B
0x1800853ac  mov     rcx, r9
0x1800853af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800853b4  jmp     loc_18008543C
0x1800853b9  lea     rdx, [rbp+SRWLock]
0x1800853bd  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800853c2  mov     rax, [rbx+110h]
0x1800853c9  mov     dword ptr [rax], 2
0x1800853cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800853d3  test    rcx, rcx
0x1800853d6  jz      short loc_1800853DE
0x1800853d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800853de  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800853e3  mov     rdi, rax
0x1800853e6  mov     ecx, [rax]
0x1800853e8  cmp     ecx, 4
0x1800853eb  jbe     short loc_18008543C
0x1800853ed  call    cs:__imp_GetCurrentThreadId
0x1800853f3  mov     dword ptr [rbp+SRWLock], eax
0x1800853f6  mov     r8, [rbx+110h]
0x1800853fd  mov     ecx, [r8+48h]
0x180085401  mov     [rbp+arg_8], ecx
0x180085404  mov     eax, 1000000h
0x180085409  mov     [rbp+arg_10], rax
0x18008540d  add     r8, 8
0x180085411  lea     rax, [rbp+SRWLock]
0x180085415  mov     [rsp+140h+var_110], rax
0x18008541a  lea     rax, [rbp+arg_8]
0x18008541e  mov     [rsp+140h+var_118], rax
0x180085423  lea     rax, [rbp+arg_10]
0x180085427  mov     [rsp+140h+var_120], rax
0x18008542c  lea     rdx, byte_1800D7BD7
0x180085433  mov     rcx, rdi
0x180085436  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008543b  nop
0x18008543c  lea     rcx, [rbx+120h]; this
0x180085443  cmp     dword ptr [rcx+18h], 0
0x180085447  jz      short loc_18008544F
0x180085449  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18008544e  nop
0x18008544f  add     rsp, 130h
0x180085456  pop     rdi
0x180085457  pop     rbx
0x180085458  pop     rbp
0x180085459  retn
```
