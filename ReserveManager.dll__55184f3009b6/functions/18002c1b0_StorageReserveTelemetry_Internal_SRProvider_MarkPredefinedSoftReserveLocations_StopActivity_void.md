# StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StopActivity(void)

- ea: `0x18002c1b0`
- end: `0x18002c43b`
- name: `?StopActivity@MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@MEAAXXZ`
- size: `651`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800018ec`
- `0x1800029d8`
- `0x180028494`
- `0x180028738`
- `0x18002939c`
- `0x18002c1b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c212`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c212`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c3db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c3db`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StopActivity(
        StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *this)
{
  __int64 v2; // rdi
  int v3; // eax
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  __int64 v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v24[1] = -2;
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = v2 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v15 = *(_QWORD *)(v4 + 120);
        v16 = *(_QWORD *)(v4 + 112);
        LODWORD(SRWLock) = *(_DWORD *)(v4 + 104);
        v17 = *(_QWORD *)(v4 + 96);
        v18 = *(_QWORD *)(v4 + 88);
        LODWORD(v26) = *(_DWORD *)(v4 + 80);
        v19 = *(_QWORD *)(v4 + 72);
        LODWORD(v27) = *(_DWORD *)(v4 + 32);
        v20 = *(_QWORD *)(v4 + 24);
        LODWORD(v28) = *(_DWORD *)v4;
        v21 = *(_QWORD *)(v4 + 128);
        v13 = *(_DWORD *)(v4 + 64);
        v22 = *(_QWORD *)(v4 + 56);
        v14 = *(_DWORD *)(v4 + 8);
        v23 = 0x1000000;
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (int)&byte_180043B8B,
          *((_QWORD *)this + 34) + 8,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          (const wchar_t **)&v22,
          (__int64)&v13,
          (const wchar_t **)&v21,
          (__int64)&v28,
          (const unsigned __int16 **)&v20,
          (__int64)&v27,
          (const wchar_t **)&v19,
          (__int64)&v26,
          (const wchar_t **)&v18,
          (const unsigned __int16 **)&v17,
          (__int64)&SRWLock,
          (const wchar_t **)&v16,
          (const unsigned __int16 **)&v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        LODWORD(v26) = *(_DWORD *)(v11 + 72);
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v9,
          (int)&unk_180043B28,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002c1b0  push    rbp
0x18002c1b2  push    rbx
0x18002c1b3  push    rdi
0x18002c1b4  lea     rbp, [rsp-47h]
0x18002c1b9  sub     rsp, 100h
0x18002c1c0  mov     [rbp+57h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002c1c8  mov     rbx, rcx
0x18002c1cb  mov     rdi, [rcx+110h]
0x18002c1d2  mov     eax, [rdi+48h]
0x18002c1d5  test    eax, eax
0x18002c1d7  jns     loc_18002C384
0x18002c1dd  add     rdi, 50h ; 'P'
0x18002c1e1  cmp     eax, [rdi+8]
0x18002c1e4  jnz     loc_18002C384
0x18002c1ea  test    rdi, rdi
0x18002c1ed  jz      loc_18002C384
0x18002c1f3  lea     rdx, [rbp+57h+SRWLock]
0x18002c1f7  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c1fc  mov     rax, [rbx+110h]
0x18002c203  mov     dword ptr [rax], 2
0x18002c209  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002c20d  test    rcx, rcx
0x18002c210  jz      short loc_18002C219
0x18002c212  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c218  nop
0x18002c219  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002c21e  mov     r9, rax
0x18002c221  mov     ecx, [rax]
0x18002c223  cmp     ecx, 5
0x18002c226  jbe     loc_18002C429
0x18002c22c  mov     rax, [rax+18h]
0x18002c230  mov     rcx, [r9+10h]
0x18002c234  mov     rdx, 400000000000h
0x18002c23e  test    rdx, rcx
0x18002c241  jz      loc_18002C429
0x18002c247  mov     rcx, rax
0x18002c24a  and     rcx, rdx
0x18002c24d  cmp     rcx, rax
0x18002c250  jnz     loc_18002C429
0x18002c256  mov     rax, [rdi+78h]
0x18002c25a  mov     [rbp+57h+var_68], rax
0x18002c25e  mov     rax, [rdi+70h]
0x18002c262  mov     [rbp+57h+var_60], rax
0x18002c266  mov     eax, [rdi+68h]
0x18002c269  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002c26c  mov     rax, [rdi+60h]
0x18002c270  mov     [rbp+57h+var_58], rax
0x18002c274  mov     rax, [rdi+58h]
0x18002c278  mov     [rbp+57h+var_50], rax
0x18002c27c  mov     eax, [rdi+50h]
0x18002c27f  mov     dword ptr [rbp+57h+arg_8], eax
0x18002c282  mov     rax, [rdi+48h]
0x18002c286  mov     [rbp+57h+var_48], rax
0x18002c28a  mov     eax, [rdi+20h]
0x18002c28d  mov     dword ptr [rbp+57h+arg_10], eax
0x18002c290  mov     rax, [rdi+18h]
0x18002c294  mov     [rbp+57h+var_40], rax
0x18002c298  mov     eax, [rdi]
0x18002c29a  mov     dword ptr [rbp+57h+arg_18], eax
0x18002c29d  mov     rax, [rdi+80h]
0x18002c2a4  mov     [rbp+57h+var_38], rax
0x18002c2a8  mov     eax, [rdi+40h]
0x18002c2ab  mov     dword ptr [rbp+57h+var_70], eax
0x18002c2ae  mov     rax, [rdi+38h]
0x18002c2b2  mov     [rbp+57h+var_30], rax
0x18002c2b6  mov     eax, [rdi+8]
0x18002c2b9  mov     dword ptr [rbp+57h+var_70+4], eax
0x18002c2bc  mov     eax, 1000000h
0x18002c2c1  mov     [rbp+57h+var_28], rax
0x18002c2c5  mov     [rbp+57h+var_20], rax
0x18002c2c9  mov     r8, [rbx+110h]
0x18002c2d0  add     r8, 8; int
0x18002c2d4  lea     rax, [rbp+57h+var_68]
0x18002c2d8  mov     [rsp+110h+var_78], rax; __int64
0x18002c2e0  lea     rax, [rbp+57h+var_60]
0x18002c2e4  mov     [rsp+110h+var_80], rax; __int64
0x18002c2ec  lea     rax, [rbp+57h+SRWLock]
0x18002c2f0  mov     [rsp+110h+var_88], rax; __int64
0x18002c2f8  lea     rax, [rbp+57h+var_58]
0x18002c2fc  mov     [rsp+110h+var_90], rax; __int64
0x18002c304  lea     rax, [rbp+57h+var_50]
0x18002c308  mov     [rsp+110h+var_98], rax; __int64
0x18002c30d  lea     rax, [rbp+57h+arg_8]
0x18002c311  mov     [rsp+110h+var_A0], rax; __int64
0x18002c316  lea     rax, [rbp+57h+var_48]
0x18002c31a  mov     [rsp+110h+var_A8], rax; __int64
0x18002c31f  lea     rax, [rbp+57h+arg_10]
0x18002c323  mov     [rsp+110h+var_B0], rax; __int64
0x18002c328  lea     rax, [rbp+57h+var_40]
0x18002c32c  mov     [rsp+110h+var_B8], rax; __int64
0x18002c331  lea     rax, [rbp+57h+arg_18]
0x18002c335  mov     [rsp+110h+var_C0], rax; __int64
0x18002c33a  lea     rax, [rbp+57h+var_38]
0x18002c33e  mov     [rsp+110h+var_C8], rax; __int64
0x18002c343  lea     rax, [rbp+57h+var_70]
0x18002c347  mov     [rsp+110h+var_D0], rax; __int64
0x18002c34c  lea     rax, [rbp+57h+var_30]
0x18002c350  mov     [rsp+110h+var_D8], rax; __int64
0x18002c355  lea     rax, [rbp+57h+var_70+4]
0x18002c359  mov     [rsp+110h+var_E0], rax; __int64
0x18002c35e  lea     rax, [rbp+57h+var_28]
0x18002c362  mov     [rsp+110h+var_E8], rax; __int64
0x18002c367  lea     rax, [rbp+57h+var_20]
0x18002c36b  mov     [rsp+110h+var_F0], rax; __int64
0x18002c370  lea     rdx, byte_180043B8B; int
0x18002c377  mov     rcx, r9; int
0x18002c37a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002c37f  jmp     loc_18002C429
0x18002c384  lea     rdx, [rbp+57h+SRWLock]
0x18002c388  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c38d  mov     rax, [rbx+110h]
0x18002c394  mov     dword ptr [rax], 2
0x18002c39a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002c39e  test    rcx, rcx
0x18002c3a1  jz      short loc_18002C3AA
0x18002c3a3  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c3a9  nop
0x18002c3aa  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002c3af  mov     rdi, rax
0x18002c3b2  mov     ecx, [rax]
0x18002c3b4  cmp     ecx, 5
0x18002c3b7  jbe     short loc_18002C429
0x18002c3b9  mov     rax, [rax+18h]
0x18002c3bd  mov     rcx, [rdi+10h]
0x18002c3c1  mov     rdx, 400000000000h
0x18002c3cb  test    rdx, rcx
0x18002c3ce  jz      short loc_18002C429
0x18002c3d0  mov     rcx, rax
0x18002c3d3  and     rcx, rdx
0x18002c3d6  cmp     rcx, rax
0x18002c3d9  jnz     short loc_18002C429
0x18002c3db  call    cs:__imp_GetCurrentThreadId
0x18002c3e1  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002c3e4  mov     r8, [rbx+110h]
0x18002c3eb  mov     eax, [r8+48h]
0x18002c3ef  mov     dword ptr [rbp+57h+arg_8], eax
0x18002c3f2  mov     eax, 1000000h
0x18002c3f7  mov     [rbp+57h+arg_10], rax
0x18002c3fb  add     r8, 8
0x18002c3ff  lea     rax, [rbp+57h+SRWLock]
0x18002c403  mov     [rsp+110h+var_E0], rax
0x18002c408  lea     rax, [rbp+57h+arg_8]
0x18002c40c  mov     [rsp+110h+var_E8], rax
0x18002c411  lea     rax, [rbp+57h+arg_10]
0x18002c415  mov     [rsp+110h+var_F0], rax
0x18002c41a  lea     rdx, unk_180043B28
0x18002c421  mov     rcx, rdi
0x18002c424  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c429  mov     rcx, rbx
0x18002c42c  add     rsp, 100h
0x18002c433  pop     rdi
0x18002c434  pop     rbx
0x18002c435  pop     rbp
0x18002c436  jmp     ?IgnoreCurrentThread@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
