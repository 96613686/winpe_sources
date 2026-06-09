# wpc::Sync::Internal::SyncLogger::SyncForUser::StopActivity(void)

- ea: `0x1800760d0`
- end: `0x18007635e`
- name: `?StopActivity@SyncForUser@SyncLogger@Internal@Sync@wpc@@MEAAXXZ`
- size: `654`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::SyncForUser *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000119c`
- `0x180001b90`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002c3c0`
- `0x1800760d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800762f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800762f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007612a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800762ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007612a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800762ba`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::SyncForUser::StopActivity(
        wpc::Sync::Internal::SyncLogger::SyncForUser *this)
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
          (unsigned int)&dword_1800D65B4,
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
          (unsigned int)byte_1800D6525,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::Sync::Internal::SyncLogger::SyncForUser *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800760d0  push    rbp
0x1800760d2  push    rbx
0x1800760d3  push    rdi
0x1800760d4  lea     rbp, [rsp-47h]
0x1800760d9  sub     rsp, 100h
0x1800760e0  mov     rbx, rcx
0x1800760e3  mov     rdi, [rcx+110h]
0x1800760ea  mov     eax, [rdi+48h]
0x1800760ed  test    eax, eax
0x1800760ef  jns     loc_18007629B
0x1800760f5  add     rdi, 50h ; 'P'
0x1800760f9  cmp     eax, [rdi+8]
0x1800760fc  jnz     loc_18007629B
0x180076102  test    rdi, rdi
0x180076105  jz      loc_18007629B
0x18007610b  lea     rdx, [rbp+57h+SRWLock]
0x18007610f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180076114  mov     rax, [rbx+110h]
0x18007611b  mov     dword ptr [rax], 2
0x180076121  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180076125  test    rcx, rcx
0x180076128  jz      short loc_180076130
0x18007612a  call    cs:__imp_ReleaseSRWLockExclusive
0x180076130  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180076135  mov     r9, rax
0x180076138  mov     ecx, [rax]
0x18007613a  cmp     ecx, 4
0x18007613d  jbe     loc_180076340
0x180076143  mov     rax, [rax+18h]
0x180076147  mov     rcx, [r9+10h]
0x18007614b  mov     rdx, 200000000000h
0x180076155  test    rdx, rcx
0x180076158  jz      loc_180076340
0x18007615e  mov     rcx, rax
0x180076161  and     rcx, rdx
0x180076164  cmp     rcx, rax
0x180076167  jnz     loc_180076340
0x18007616d  mov     rax, [rdi+78h]
0x180076171  mov     [rbp+57h+var_68], rax
0x180076175  mov     rax, [rdi+70h]
0x180076179  mov     [rbp+57h+var_60], rax
0x18007617d  mov     eax, [rdi+68h]
0x180076180  mov     dword ptr [rbp+57h+SRWLock], eax
0x180076183  mov     rax, [rdi+60h]
0x180076187  mov     [rbp+57h+var_58], rax
0x18007618b  mov     rax, [rdi+58h]
0x18007618f  mov     [rbp+57h+var_50], rax
0x180076193  mov     eax, [rdi+50h]
0x180076196  mov     [rbp+57h+arg_8], eax
0x180076199  mov     rax, [rdi+48h]
0x18007619d  mov     [rbp+57h+var_48], rax
0x1800761a1  mov     eax, [rdi+20h]
0x1800761a4  mov     dword ptr [rbp+57h+arg_10], eax
0x1800761a7  mov     rax, [rdi+18h]
0x1800761ab  mov     [rbp+57h+var_40], rax
0x1800761af  mov     eax, [rdi]
0x1800761b1  mov     [rbp+57h+arg_18], eax
0x1800761b4  mov     rax, [rdi+80h]
0x1800761bb  mov     [rbp+57h+var_38], rax
0x1800761bf  mov     eax, [rdi+40h]
0x1800761c2  mov     [rbp+57h+var_70], eax
0x1800761c5  mov     rax, [rdi+38h]
0x1800761c9  mov     [rbp+57h+var_30], rax
0x1800761cd  mov     eax, [rdi+8]
0x1800761d0  mov     [rbp+57h+var_6C], eax
0x1800761d3  mov     eax, 1000000h
0x1800761d8  mov     [rbp+57h+var_28], rax
0x1800761dc  mov     [rbp+57h+var_20], rax
0x1800761e0  mov     r8, [rbx+110h]
0x1800761e7  add     r8, 8
0x1800761eb  lea     rax, [rbp+57h+var_68]
0x1800761ef  mov     [rsp+110h+var_78], rax
0x1800761f7  lea     rax, [rbp+57h+var_60]
0x1800761fb  mov     [rsp+110h+var_80], rax
0x180076203  lea     rax, [rbp+57h+SRWLock]
0x180076207  mov     [rsp+110h+var_88], rax
0x18007620f  lea     rax, [rbp+57h+var_58]
0x180076213  mov     [rsp+110h+var_90], rax
0x18007621b  lea     rax, [rbp+57h+var_50]
0x18007621f  mov     [rsp+110h+var_98], rax
0x180076224  lea     rax, [rbp+57h+arg_8]
0x180076228  mov     [rsp+110h+var_A0], rax
0x18007622d  lea     rax, [rbp+57h+var_48]
0x180076231  mov     [rsp+110h+var_A8], rax
0x180076236  lea     rax, [rbp+57h+arg_10]
0x18007623a  mov     [rsp+110h+var_B0], rax
0x18007623f  lea     rax, [rbp+57h+var_40]
0x180076243  mov     [rsp+110h+var_B8], rax
0x180076248  lea     rax, [rbp+57h+arg_18]
0x18007624c  mov     [rsp+110h+var_C0], rax
0x180076251  lea     rax, [rbp+57h+var_38]
0x180076255  mov     [rsp+110h+var_C8], rax
0x18007625a  lea     rax, [rbp+57h+var_70]
0x18007625e  mov     [rsp+110h+var_D0], rax
0x180076263  lea     rax, [rbp+57h+var_30]
0x180076267  mov     [rsp+110h+var_D8], rax
0x18007626c  lea     rax, [rbp+57h+var_6C]
0x180076270  mov     [rsp+110h+var_E0], rax
0x180076275  lea     rax, [rbp+57h+var_28]
0x180076279  mov     [rsp+110h+var_E8], rax
0x18007627e  lea     rax, [rbp+57h+var_20]
0x180076282  mov     [rsp+110h+var_F0], rax
0x180076287  lea     rdx, dword_1800D65B4
0x18007628e  mov     rcx, r9
0x180076291  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180076296  jmp     loc_180076340
0x18007629b  lea     rdx, [rbp+57h+SRWLock]
0x18007629f  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800762a4  mov     rax, [rbx+110h]
0x1800762ab  mov     dword ptr [rax], 2
0x1800762b1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800762b5  test    rcx, rcx
0x1800762b8  jz      short loc_1800762C0
0x1800762ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800762c0  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800762c5  mov     rdi, rax
0x1800762c8  mov     ecx, [rax]
0x1800762ca  cmp     ecx, 4
0x1800762cd  jbe     short loc_180076340
0x1800762cf  mov     rax, [rax+18h]
0x1800762d3  mov     rcx, [rdi+10h]
0x1800762d7  mov     rdx, 200000000000h
0x1800762e1  test    rdx, rcx
0x1800762e4  jz      short loc_180076340
0x1800762e6  mov     rcx, rax
0x1800762e9  and     rcx, rdx
0x1800762ec  cmp     rcx, rax
0x1800762ef  jnz     short loc_180076340
0x1800762f1  call    cs:__imp_GetCurrentThreadId
0x1800762f7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800762fa  mov     r8, [rbx+110h]
0x180076301  mov     eax, [r8+48h]
0x180076305  mov     [rbp+57h+arg_8], eax
0x180076308  mov     eax, 1000000h
0x18007630d  mov     [rbp+57h+arg_10], rax
0x180076311  add     r8, 8
0x180076315  lea     rax, [rbp+57h+SRWLock]
0x180076319  mov     [rsp+110h+var_E0], rax
0x18007631e  lea     rax, [rbp+57h+arg_8]
0x180076322  mov     [rsp+110h+var_E8], rax
0x180076327  lea     rax, [rbp+57h+arg_10]
0x18007632b  mov     [rsp+110h+var_F0], rax
0x180076330  lea     rdx, byte_1800D6525
0x180076337  mov     rcx, rdi
0x18007633a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007633f  nop
0x180076340  lea     rcx, [rbx+120h]; this
0x180076347  cmp     dword ptr [rcx+18h], 0
0x18007634b  jz      short loc_180076353
0x18007634d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180076352  nop
0x180076353  add     rsp, 100h
0x18007635a  pop     rdi
0x18007635b  pop     rbx
0x18007635c  pop     rbp
0x18007635d  retn
```
