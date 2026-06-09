# wpc::Sync::Internal::SyncLogger::AppDeviceInfo::StopActivity(void)

- ea: `0x1800842e0`
- end: `0x18008455a`
- name: `?StopActivity@AppDeviceInfo@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::AppDeviceInfo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000187c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x1800842e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800844ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800844ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008433a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800844d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008433a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800844d8`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::AppDeviceInfo::StopActivity(
        wpc::Sync::Internal::SyncLogger::AppDeviceInfo *this)
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
    v5 = wpc::Sync::Internal::SyncLogger::Provider();
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
        (__int64)&byte_1800D6D4F,
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
    v6 = wpc::Sync::Internal::SyncLogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)byte_1800D6D01,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::AppDeviceInfo *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800842e0  push    rbp
0x1800842e2  push    rbx
0x1800842e3  push    rdi
0x1800842e4  lea     rbp, [rsp+10h]
0x1800842e9  sub     rsp, 130h
0x1800842f0  mov     rbx, rcx
0x1800842f3  mov     rdi, [rcx+110h]
0x1800842fa  mov     eax, [rdi+48h]
0x1800842fd  test    eax, eax
0x1800842ff  jns     loc_1800844B9
0x180084305  add     rdi, 50h ; 'P'
0x180084309  cmp     eax, [rdi+8]
0x18008430c  jnz     loc_1800844B9
0x180084312  test    rdi, rdi
0x180084315  jz      loc_1800844B9
0x18008431b  lea     rdx, [rbp+SRWLock]
0x18008431f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180084324  mov     rax, [rbx+110h]
0x18008432b  mov     dword ptr [rax], 2
0x180084331  mov     rcx, [rbp+SRWLock]; SRWLock
0x180084335  test    rcx, rcx
0x180084338  jz      short loc_180084340
0x18008433a  call    cs:__imp_ReleaseSRWLockExclusive
0x180084340  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180084345  mov     r9, rax
0x180084348  mov     ecx, [rax]
0x18008434a  cmp     ecx, 4
0x18008434d  jbe     loc_18008453C
0x180084353  mov     rcx, [rdi+30h]
0x180084357  mov     [rbp+var_70], rcx
0x18008435b  mov     ecx, [rdi+44h]
0x18008435e  mov     dword ptr [rbp+SRWLock], ecx
0x180084361  mov     ecx, [rdi+10h]
0x180084364  mov     [rbp+arg_8], ecx
0x180084367  mov     rcx, [rdi+78h]
0x18008436b  mov     [rbp+var_68], rcx
0x18008436f  mov     rax, [rdi+70h]
0x180084373  mov     [rbp+var_60], rax
0x180084377  mov     eax, [rdi+68h]
0x18008437a  mov     dword ptr [rbp+arg_10], eax
0x18008437d  mov     rax, [rdi+60h]
0x180084381  mov     [rbp+var_58], rax
0x180084385  mov     rax, [rdi+58h]
0x180084389  mov     [rbp+var_50], rax
0x18008438d  mov     eax, [rdi+50h]
0x180084390  mov     [rbp+arg_18], eax
0x180084393  mov     rax, [rdi+48h]
0x180084397  mov     [rbp+var_48], rax
0x18008439b  mov     eax, [rdi+20h]
0x18008439e  mov     [rbp+var_80], eax
0x1800843a1  mov     rax, [rdi+18h]
0x1800843a5  mov     [rbp+var_40], rax
0x1800843a9  mov     eax, [rdi]
0x1800843ab  mov     [rbp+var_7C], eax
0x1800843ae  mov     rax, [rdi+80h]
0x1800843b5  mov     [rbp+var_38], rax
0x1800843b9  mov     eax, [rdi+40h]
0x1800843bc  mov     [rbp+var_78], eax
0x1800843bf  mov     rax, [rdi+38h]
0x1800843c3  mov     [rbp+var_30], rax
0x1800843c7  mov     eax, [rdi+8]
0x1800843ca  mov     [rbp+var_74], eax
0x1800843cd  mov     eax, 1000000h
0x1800843d2  mov     [rbp+var_28], rax
0x1800843d6  mov     [rbp+var_20], rax
0x1800843da  mov     r8, [rbx+110h]
0x1800843e1  add     r8, 8
0x1800843e5  lea     rax, [rbp+var_70]
0x1800843e9  mov     [rsp+140h+var_90], rax
0x1800843f1  lea     rax, [rbp+SRWLock]
0x1800843f5  mov     [rsp+140h+var_98], rax
0x1800843fd  lea     rax, [rbp+arg_8]
0x180084401  mov     [rsp+140h+var_A0], rax
0x180084409  lea     rax, [rbp+var_68]
0x18008440d  mov     [rsp+140h+var_A8], rax
0x180084415  lea     rax, [rbp+var_60]
0x180084419  mov     [rsp+140h+var_B0], rax
0x180084421  lea     rax, [rbp+arg_10]
0x180084425  mov     [rsp+140h+var_B8], rax
0x18008442d  lea     rax, [rbp+var_58]
0x180084431  mov     [rsp+140h+var_C0], rax
0x180084439  lea     rax, [rbp+var_50]
0x18008443d  mov     [rsp+140h+var_C8], rax
0x180084442  lea     rax, [rbp+arg_18]
0x180084446  mov     [rsp+140h+var_D0], rax
0x18008444b  lea     rax, [rbp+var_48]
0x18008444f  mov     [rsp+140h+var_D8], rax
0x180084454  lea     rax, [rbp+var_80]
0x180084458  mov     [rsp+140h+var_E0], rax
0x18008445d  lea     rax, [rbp+var_40]
0x180084461  mov     [rsp+140h+var_E8], rax
0x180084466  lea     rax, [rbp+var_7C]
0x18008446a  mov     [rsp+140h+var_F0], rax
0x18008446f  lea     rax, [rbp+var_38]
0x180084473  mov     [rsp+140h+var_F8], rax
0x180084478  lea     rax, [rbp+var_78]
0x18008447c  mov     [rsp+140h+var_100], rax
0x180084481  lea     rax, [rbp+var_30]
0x180084485  mov     [rsp+140h+var_108], rax
0x18008448a  lea     rax, [rbp+var_74]
0x18008448e  mov     [rsp+140h+var_110], rax
0x180084493  lea     rax, [rbp+var_28]
0x180084497  mov     [rsp+140h+var_118], rax
0x18008449c  lea     rax, [rbp+var_20]
0x1800844a0  mov     [rsp+140h+var_120], rax
0x1800844a5  lea     rdx, byte_1800D6D4F
0x1800844ac  mov     rcx, r9
0x1800844af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800844b4  jmp     loc_18008453C
0x1800844b9  lea     rdx, [rbp+SRWLock]
0x1800844bd  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800844c2  mov     rax, [rbx+110h]
0x1800844c9  mov     dword ptr [rax], 2
0x1800844cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800844d3  test    rcx, rcx
0x1800844d6  jz      short loc_1800844DE
0x1800844d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800844de  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800844e3  mov     rdi, rax
0x1800844e6  mov     ecx, [rax]
0x1800844e8  cmp     ecx, 4
0x1800844eb  jbe     short loc_18008453C
0x1800844ed  call    cs:__imp_GetCurrentThreadId
0x1800844f3  mov     dword ptr [rbp+SRWLock], eax
0x1800844f6  mov     r8, [rbx+110h]
0x1800844fd  mov     ecx, [r8+48h]
0x180084501  mov     [rbp+arg_8], ecx
0x180084504  mov     eax, 1000000h
0x180084509  mov     [rbp+arg_10], rax
0x18008450d  add     r8, 8
0x180084511  lea     rax, [rbp+SRWLock]
0x180084515  mov     [rsp+140h+var_110], rax
0x18008451a  lea     rax, [rbp+arg_8]
0x18008451e  mov     [rsp+140h+var_118], rax
0x180084523  lea     rax, [rbp+arg_10]
0x180084527  mov     [rsp+140h+var_120], rax
0x18008452c  lea     rdx, byte_1800D6D01
0x180084533  mov     rcx, rdi
0x180084536  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008453b  nop
0x18008453c  lea     rcx, [rbx+120h]; this
0x180084543  cmp     dword ptr [rcx+18h], 0
0x180084547  jz      short loc_18008454F
0x180084549  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18008454e  nop
0x18008454f  add     rsp, 130h
0x180084556  pop     rdi
0x180084557  pop     rbx
0x180084558  pop     rbp
0x180084559  retn
```
