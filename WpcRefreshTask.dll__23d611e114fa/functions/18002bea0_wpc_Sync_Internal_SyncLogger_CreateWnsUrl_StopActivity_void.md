# wpc::Sync::Internal::SyncLogger::CreateWnsUrl::StopActivity(void)

- ea: `0x18002bea0`
- end: `0x18002c12e`
- name: `?StopActivity@CreateWnsUrl@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `654`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::CreateWnsUrl *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000119c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002bea0`
- `0x18002c3c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c0c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c0c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002befa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002befa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c08a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wpc::Sync::Internal::SyncLogger::CreateWnsUrl::StopActivity(
        wpc::Sync::Internal::SyncLogger::CreateWnsUrl *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // r9d
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
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

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
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        v15 = *((_QWORD *)v4 + 15);
        v16 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = *((_QWORD *)v4 + 12);
        v18 = *((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = *((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = *((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = *((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)word_1800D5002,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          (__int64)&v22,
          (__int64)&v13,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v20,
          (__int64)&v27,
          (__int64)&v19,
          (__int64)&v26,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&SRWLock,
          (__int64)&v16,
          (__int64)&v15);
      }
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
    v8 = wpc::Sync::Internal::SyncLogger::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800D4FB5,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::CreateWnsUrl *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002bea0  push    rbp
0x18002bea2  push    rbx
0x18002bea3  push    rdi
0x18002bea4  lea     rbp, [rsp-47h]
0x18002bea9  sub     rsp, 100h
0x18002beb0  mov     rbx, rcx
0x18002beb3  mov     rdi, [rcx+110h]
0x18002beba  mov     eax, [rdi+48h]
0x18002bebd  test    eax, eax
0x18002bebf  jns     loc_18002C06B
0x18002bec5  add     rdi, 50h ; 'P'
0x18002bec9  cmp     eax, [rdi+8]
0x18002becc  jnz     loc_18002C06B
0x18002bed2  test    rdi, rdi
0x18002bed5  jz      loc_18002C06B
0x18002bedb  lea     rdx, [rbp+57h+SRWLock]
0x18002bedf  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bee4  mov     rax, [rbx+110h]
0x18002beeb  mov     dword ptr [rax], 2
0x18002bef1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002bef5  test    rcx, rcx
0x18002bef8  jz      short loc_18002BF00
0x18002befa  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bf00  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x18002bf05  mov     r9, rax
0x18002bf08  mov     ecx, [rax]
0x18002bf0a  cmp     ecx, 4
0x18002bf0d  jbe     loc_18002C110
0x18002bf13  mov     rax, [rax+18h]
0x18002bf17  mov     rcx, [r9+10h]
0x18002bf1b  mov     rdx, 200000000000h
0x18002bf25  test    rdx, rcx
0x18002bf28  jz      loc_18002C110
0x18002bf2e  mov     rcx, rax
0x18002bf31  and     rcx, rdx
0x18002bf34  cmp     rcx, rax
0x18002bf37  jnz     loc_18002C110
0x18002bf3d  mov     rax, [rdi+78h]
0x18002bf41  mov     [rbp+57h+var_68], rax
0x18002bf45  mov     rax, [rdi+70h]
0x18002bf49  mov     [rbp+57h+var_60], rax
0x18002bf4d  mov     eax, [rdi+68h]
0x18002bf50  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002bf53  mov     rax, [rdi+60h]
0x18002bf57  mov     [rbp+57h+var_58], rax
0x18002bf5b  mov     rax, [rdi+58h]
0x18002bf5f  mov     [rbp+57h+var_50], rax
0x18002bf63  mov     eax, [rdi+50h]
0x18002bf66  mov     [rbp+57h+arg_8], eax
0x18002bf69  mov     rax, [rdi+48h]
0x18002bf6d  mov     [rbp+57h+var_48], rax
0x18002bf71  mov     eax, [rdi+20h]
0x18002bf74  mov     dword ptr [rbp+57h+arg_10], eax
0x18002bf77  mov     rax, [rdi+18h]
0x18002bf7b  mov     [rbp+57h+var_40], rax
0x18002bf7f  mov     eax, [rdi]
0x18002bf81  mov     [rbp+57h+arg_18], eax
0x18002bf84  mov     rax, [rdi+80h]
0x18002bf8b  mov     [rbp+57h+var_38], rax
0x18002bf8f  mov     eax, [rdi+40h]
0x18002bf92  mov     [rbp+57h+var_70], eax
0x18002bf95  mov     rax, [rdi+38h]
0x18002bf99  mov     [rbp+57h+var_30], rax
0x18002bf9d  mov     eax, [rdi+8]
0x18002bfa0  mov     [rbp+57h+var_6C], eax
0x18002bfa3  mov     eax, 1000000h
0x18002bfa8  mov     [rbp+57h+var_28], rax
0x18002bfac  mov     [rbp+57h+var_20], rax
0x18002bfb0  mov     r8, [rbx+110h]
0x18002bfb7  add     r8, 8
0x18002bfbb  lea     rax, [rbp+57h+var_68]
0x18002bfbf  mov     [rsp+110h+var_78], rax
0x18002bfc7  lea     rax, [rbp+57h+var_60]
0x18002bfcb  mov     [rsp+110h+var_80], rax
0x18002bfd3  lea     rax, [rbp+57h+SRWLock]
0x18002bfd7  mov     [rsp+110h+var_88], rax
0x18002bfdf  lea     rax, [rbp+57h+var_58]
0x18002bfe3  mov     [rsp+110h+var_90], rax
0x18002bfeb  lea     rax, [rbp+57h+var_50]
0x18002bfef  mov     [rsp+110h+var_98], rax
0x18002bff4  lea     rax, [rbp+57h+arg_8]
0x18002bff8  mov     [rsp+110h+var_A0], rax
0x18002bffd  lea     rax, [rbp+57h+var_48]
0x18002c001  mov     [rsp+110h+var_A8], rax
0x18002c006  lea     rax, [rbp+57h+arg_10]
0x18002c00a  mov     [rsp+110h+var_B0], rax
0x18002c00f  lea     rax, [rbp+57h+var_40]
0x18002c013  mov     [rsp+110h+var_B8], rax
0x18002c018  lea     rax, [rbp+57h+arg_18]
0x18002c01c  mov     [rsp+110h+var_C0], rax
0x18002c021  lea     rax, [rbp+57h+var_38]
0x18002c025  mov     [rsp+110h+var_C8], rax
0x18002c02a  lea     rax, [rbp+57h+var_70]
0x18002c02e  mov     [rsp+110h+var_D0], rax
0x18002c033  lea     rax, [rbp+57h+var_30]
0x18002c037  mov     [rsp+110h+var_D8], rax
0x18002c03c  lea     rax, [rbp+57h+var_6C]
0x18002c040  mov     [rsp+110h+var_E0], rax
0x18002c045  lea     rax, [rbp+57h+var_28]
0x18002c049  mov     [rsp+110h+var_E8], rax
0x18002c04e  lea     rax, [rbp+57h+var_20]
0x18002c052  mov     [rsp+110h+var_F0], rax
0x18002c057  lea     rdx, word_1800D5002
0x18002c05e  mov     rcx, r9
0x18002c061  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002c066  jmp     loc_18002C110
0x18002c06b  lea     rdx, [rbp+57h+SRWLock]
0x18002c06f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c074  mov     rax, [rbx+110h]
0x18002c07b  mov     dword ptr [rax], 2
0x18002c081  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002c085  test    rcx, rcx
0x18002c088  jz      short loc_18002C090
0x18002c08a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c090  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x18002c095  mov     rdi, rax
0x18002c098  mov     ecx, [rax]
0x18002c09a  cmp     ecx, 4
0x18002c09d  jbe     short loc_18002C110
0x18002c09f  mov     rax, [rax+18h]
0x18002c0a3  mov     rcx, [rdi+10h]
0x18002c0a7  mov     rdx, 200000000000h
0x18002c0b1  test    rdx, rcx
0x18002c0b4  jz      short loc_18002C110
0x18002c0b6  mov     rcx, rax
0x18002c0b9  and     rcx, rdx
0x18002c0bc  cmp     rcx, rax
0x18002c0bf  jnz     short loc_18002C110
0x18002c0c1  call    cs:__imp_GetCurrentThreadId
0x18002c0c7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002c0ca  mov     r8, [rbx+110h]
0x18002c0d1  mov     eax, [r8+48h]
0x18002c0d5  mov     [rbp+57h+arg_8], eax
0x18002c0d8  mov     eax, 1000000h
0x18002c0dd  mov     [rbp+57h+arg_10], rax
0x18002c0e1  add     r8, 8
0x18002c0e5  lea     rax, [rbp+57h+SRWLock]
0x18002c0e9  mov     [rsp+110h+var_E0], rax
0x18002c0ee  lea     rax, [rbp+57h+arg_8]
0x18002c0f2  mov     [rsp+110h+var_E8], rax
0x18002c0f7  lea     rax, [rbp+57h+arg_10]
0x18002c0fb  mov     [rsp+110h+var_F0], rax
0x18002c100  lea     rdx, byte_1800D4FB5
0x18002c107  mov     rcx, rdi
0x18002c10a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c10f  nop
0x18002c110  lea     rcx, [rbx+120h]; this
0x18002c117  cmp     dword ptr [rcx+18h], 0
0x18002c11b  jz      short loc_18002C123
0x18002c11d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002c122  nop
0x18002c123  add     rsp, 100h
0x18002c12a  pop     rdi
0x18002c12b  pop     rbx
0x18002c12c  pop     rbp
0x18002c12d  retn
```
