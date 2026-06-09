# MtfPlatformTelemetry::UpdateDataSource::StopActivity(void)

- ea: `0x18001c400`
- end: `0x18001c66e`
- name: `?StopActivity@UpdateDataSource@MtfPlatformTelemetry@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateDataSource *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800016dc`
- `0x1800019f0`
- `0x1800053cc`
- `0x180018c84`
- `0x180018d00`
- `0x18001c400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c60f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c60f`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateDataSource::StopActivity(MtfPlatformTelemetry::UpdateDataSource *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  _DWORD *v6; // rcx
  int v7; // r9d
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v6 > 5u )
    {
      v18 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)byte_18003662D,
        v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)qword_180036778,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001c400  push    rbp
0x18001c402  push    rbx
0x18001c403  push    rdi
0x18001c404  lea     rbp, [rsp+10h]
0x18001c409  sub     rsp, 130h
0x18001c410  mov     rdi, [rcx+110h]
0x18001c417  mov     rbx, rcx
0x18001c41a  mov     eax, [rdi+48h]
0x18001c41d  test    eax, eax
0x18001c41f  jns     loc_18001C5DA
0x18001c425  add     rdi, 50h ; 'P'
0x18001c429  cmp     eax, [rdi+8]
0x18001c42c  jnz     loc_18001C5DA
0x18001c432  test    rdi, rdi
0x18001c435  jz      loc_18001C5DA
0x18001c43b  lea     rdx, [rbp+SRWLock]
0x18001c43f  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c444  mov     rax, [rbx+110h]
0x18001c44b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001c44f  mov     dword ptr [rax], 2
0x18001c455  test    rcx, rcx
0x18001c458  jz      short loc_18001C460
0x18001c45a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c460  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001c465  mov     rcx, [rax+8]
0x18001c469  mov     eax, [rcx]
0x18001c46b  cmp     eax, 5
0x18001c46e  jbe     loc_18001C65C
0x18001c474  mov     rax, [rdi+30h]
0x18001c478  lea     rdx, byte_18003662D
0x18001c47f  mov     [rbp+var_70], rax
0x18001c483  mov     eax, [rdi+44h]
0x18001c486  mov     dword ptr [rbp+SRWLock], eax
0x18001c489  mov     eax, [rdi+10h]
0x18001c48c  mov     [rbp+arg_8], eax
0x18001c48f  mov     rax, [rdi+78h]
0x18001c493  mov     [rbp+var_68], rax
0x18001c497  mov     rax, [rdi+70h]
0x18001c49b  mov     [rbp+var_60], rax
0x18001c49f  mov     eax, [rdi+68h]
0x18001c4a2  mov     r8, [rbx+110h]
0x18001c4a9  mov     dword ptr [rbp+arg_10], eax
0x18001c4ac  add     r8, 8
0x18001c4b0  mov     rax, [rdi+60h]
0x18001c4b4  mov     [rbp+var_58], rax
0x18001c4b8  mov     rax, [rdi+58h]
0x18001c4bc  mov     [rbp+var_50], rax
0x18001c4c0  mov     eax, [rdi+50h]
0x18001c4c3  mov     [rbp+arg_18], eax
0x18001c4c6  mov     rax, [rdi+48h]
0x18001c4ca  mov     [rbp+var_48], rax
0x18001c4ce  mov     eax, [rdi+20h]
0x18001c4d1  mov     [rbp+var_80], eax
0x18001c4d4  mov     rax, [rdi+18h]
0x18001c4d8  mov     [rbp+var_40], rax
0x18001c4dc  mov     eax, [rdi]
0x18001c4de  mov     [rbp+var_7C], eax
0x18001c4e1  mov     rax, [rdi+80h]
0x18001c4e8  mov     [rbp+var_38], rax
0x18001c4ec  mov     eax, [rdi+40h]
0x18001c4ef  mov     [rbp+var_78], eax
0x18001c4f2  mov     rax, [rdi+38h]
0x18001c4f6  mov     [rbp+var_30], rax
0x18001c4fa  mov     eax, [rdi+8]
0x18001c4fd  mov     [rbp+var_74], eax
0x18001c500  lea     rax, [rbp+var_70]
0x18001c504  mov     [rsp+140h+var_90], rax
0x18001c50c  lea     rax, [rbp+SRWLock]
0x18001c510  mov     [rsp+140h+var_98], rax
0x18001c518  lea     rax, [rbp+arg_8]
0x18001c51c  mov     [rsp+140h+var_A0], rax
0x18001c524  lea     rax, [rbp+var_68]
0x18001c528  mov     [rsp+140h+var_A8], rax
0x18001c530  lea     rax, [rbp+var_60]
0x18001c534  mov     [rsp+140h+var_B0], rax
0x18001c53c  lea     rax, [rbp+arg_10]
0x18001c540  mov     [rsp+140h+var_B8], rax
0x18001c548  lea     rax, [rbp+var_58]
0x18001c54c  mov     [rsp+140h+var_C0], rax
0x18001c554  lea     rax, [rbp+var_50]
0x18001c558  mov     [rsp+140h+var_C8], rax
0x18001c55d  lea     rax, [rbp+arg_18]
0x18001c561  mov     [rsp+140h+var_D0], rax
0x18001c566  lea     rax, [rbp+var_48]
0x18001c56a  mov     [rsp+140h+var_D8], rax
0x18001c56f  lea     rax, [rbp+var_80]
0x18001c573  mov     [rsp+140h+var_E0], rax
0x18001c578  lea     rax, [rbp+var_40]
0x18001c57c  mov     [rsp+140h+var_E8], rax
0x18001c581  lea     rax, [rbp+var_7C]
0x18001c585  mov     [rsp+140h+var_F0], rax
0x18001c58a  lea     rax, [rbp+var_38]
0x18001c58e  mov     [rsp+140h+var_F8], rax
0x18001c593  lea     rax, [rbp+var_78]
0x18001c597  mov     [rsp+140h+var_100], rax
0x18001c59c  lea     rax, [rbp+var_30]
0x18001c5a0  mov     [rsp+140h+var_108], rax
0x18001c5a5  lea     rax, [rbp+var_74]
0x18001c5a9  mov     [rsp+140h+var_110], rax
0x18001c5ae  lea     rax, [rbp+var_28]
0x18001c5b2  mov     [rsp+140h+var_118], rax
0x18001c5b7  lea     rax, [rbp+var_20]
0x18001c5bb  mov     [rsp+140h+var_120], rax
0x18001c5c0  mov     [rbp+var_28], 1000000h
0x18001c5c8  mov     [rbp+var_20], 0
0x18001c5d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001c5d5  jmp     loc_18001C65C
0x18001c5da  lea     rdx, [rbp+SRWLock]
0x18001c5de  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c5e3  mov     rax, [rbx+110h]
0x18001c5ea  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001c5ee  mov     dword ptr [rax], 2
0x18001c5f4  test    rcx, rcx
0x18001c5f7  jz      short loc_18001C5FF
0x18001c5f9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c5ff  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001c604  mov     rdi, [rax+8]
0x18001c608  mov     eax, [rdi]
0x18001c60a  cmp     eax, 5
0x18001c60d  jbe     short loc_18001C65C
0x18001c60f  call    cs:__imp_GetCurrentThreadId
0x18001c615  mov     r8, [rbx+110h]
0x18001c61c  lea     rdx, qword_180036778
0x18001c623  mov     dword ptr [rbp+SRWLock], eax
0x18001c626  mov     rcx, rdi
0x18001c629  mov     eax, [r8+48h]
0x18001c62d  add     r8, 8
0x18001c631  mov     [rbp+arg_8], eax
0x18001c634  lea     rax, [rbp+SRWLock]
0x18001c638  mov     [rsp+140h+var_110], rax
0x18001c63d  lea     rax, [rbp+arg_8]
0x18001c641  mov     [rsp+140h+var_118], rax
0x18001c646  lea     rax, [rbp+arg_10]
0x18001c64a  mov     [rsp+140h+var_120], rax
0x18001c64f  mov     [rbp+arg_10], 0
0x18001c657  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c65c  mov     rcx, rbx
0x18001c65f  add     rsp, 130h
0x18001c666  pop     rdi
0x18001c667  pop     rbx
0x18001c668  pop     rbp
0x18001c669  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
