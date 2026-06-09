# Windows::Telemetry::Base::PreventSleep::StopActivity(void)

- ea: `0x180052ed0`
- end: `0x180053154`
- name: `?StopActivity@PreventSleep@Base@Telemetry@Windows@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(Windows::Telemetry::Base::PreventSleep *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800013a4`
- `0x1800020d8`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x180052ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800530bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800530bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800530f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800530f4`

## pseudocode

```c
void __fastcall Windows::Telemetry::Base::PreventSleep::StopActivity(Windows::Telemetry::Base::PreventSleep *this)
{
  __int64 v1; // rdi
  int v3; // eax
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
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
  __int64 v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = v1 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
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
        (int)&unk_180082790,
        v7 + 8,
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
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v26) = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_180082743,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180052ed0  push    rbp
0x180052ed2  push    rbx
0x180052ed3  push    rdi
0x180052ed4  lea     rbp, [rsp-47h]
0x180052ed9  sub     rsp, 100h
0x180052ee0  mov     rdi, [rcx+110h]
0x180052ee7  mov     rbx, rcx
0x180052eea  mov     eax, [rdi+48h]
0x180052eed  test    eax, eax
0x180052eef  jns     loc_18005309D
0x180052ef5  add     rdi, 50h ; 'P'
0x180052ef9  cmp     eax, [rdi+8]
0x180052efc  jnz     loc_18005309D
0x180052f02  test    rdi, rdi
0x180052f05  jz      loc_18005309D
0x180052f0b  lea     rdx, [rbp+57h+SRWLock]
0x180052f0f  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180052f14  mov     rax, [rbx+110h]
0x180052f1b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180052f1f  mov     dword ptr [rax], 2
0x180052f25  test    rcx, rcx
0x180052f28  jz      short loc_180052F30
0x180052f2a  call    cs:__imp_ReleaseSRWLockExclusive
0x180052f30  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180052f35  mov     r9, [rax+8]
0x180052f39  mov     eax, [r9]
0x180052f3c  cmp     eax, 5
0x180052f3f  jbe     loc_180053142
0x180052f45  mov     rdx, [r9+18h]
0x180052f49  mov     rcx, 400000000000h
0x180052f53  mov     rax, [r9+10h]
0x180052f57  test    rcx, rax
0x180052f5a  jz      loc_180053142
0x180052f60  mov     rax, rdx
0x180052f63  and     rax, rcx
0x180052f66  cmp     rax, rdx
0x180052f69  jnz     loc_180053142
0x180052f6f  mov     rax, [rdi+78h]
0x180052f73  lea     rdx, unk_180082790; int
0x180052f7a  mov     r8, [rbx+110h]
0x180052f81  mov     rcx, r9; int
0x180052f84  mov     [rbp+57h+var_68], rax
0x180052f88  add     r8, 8; int
0x180052f8c  mov     rax, [rdi+70h]
0x180052f90  mov     [rbp+57h+var_60], rax
0x180052f94  mov     eax, [rdi+68h]
0x180052f97  mov     dword ptr [rbp+57h+SRWLock], eax
0x180052f9a  mov     rax, [rdi+60h]
0x180052f9e  mov     [rbp+57h+var_58], rax
0x180052fa2  mov     rax, [rdi+58h]
0x180052fa6  mov     [rbp+57h+var_50], rax
0x180052faa  mov     eax, [rdi+50h]
0x180052fad  mov     dword ptr [rbp+57h+arg_8], eax
0x180052fb0  mov     rax, [rdi+48h]
0x180052fb4  mov     [rbp+57h+var_48], rax
0x180052fb8  mov     eax, [rdi+20h]
0x180052fbb  mov     dword ptr [rbp+57h+arg_10], eax
0x180052fbe  mov     rax, [rdi+18h]
0x180052fc2  mov     [rbp+57h+var_40], rax
0x180052fc6  mov     eax, [rdi]
0x180052fc8  mov     dword ptr [rbp+57h+arg_18], eax
0x180052fcb  mov     rax, [rdi+80h]
0x180052fd2  mov     [rbp+57h+var_38], rax
0x180052fd6  mov     eax, [rdi+40h]
0x180052fd9  mov     dword ptr [rbp+57h+var_70], eax
0x180052fdc  mov     rax, [rdi+38h]
0x180052fe0  mov     [rbp+57h+var_30], rax
0x180052fe4  mov     eax, [rdi+8]
0x180052fe7  mov     dword ptr [rbp+57h+var_70+4], eax
0x180052fea  mov     eax, 1000000h
0x180052fef  mov     [rbp+57h+var_28], rax
0x180052ff3  mov     [rbp+57h+var_20], rax
0x180052ff7  lea     rax, [rbp+57h+var_68]
0x180052ffb  mov     [rsp+110h+var_78], rax; __int64
0x180053003  lea     rax, [rbp+57h+var_60]
0x180053007  mov     [rsp+110h+var_80], rax; __int64
0x18005300f  lea     rax, [rbp+57h+SRWLock]
0x180053013  mov     [rsp+110h+var_88], rax; __int64
0x18005301b  lea     rax, [rbp+57h+var_58]
0x18005301f  mov     [rsp+110h+var_90], rax; __int64
0x180053027  lea     rax, [rbp+57h+var_50]
0x18005302b  mov     [rsp+110h+var_98], rax; __int64
0x180053030  lea     rax, [rbp+57h+arg_8]
0x180053034  mov     [rsp+110h+var_A0], rax; __int64
0x180053039  lea     rax, [rbp+57h+var_48]
0x18005303d  mov     [rsp+110h+var_A8], rax; __int64
0x180053042  lea     rax, [rbp+57h+arg_10]
0x180053046  mov     [rsp+110h+var_B0], rax; __int64
0x18005304b  lea     rax, [rbp+57h+var_40]
0x18005304f  mov     [rsp+110h+var_B8], rax; __int64
0x180053054  lea     rax, [rbp+57h+arg_18]
0x180053058  mov     [rsp+110h+var_C0], rax; __int64
0x18005305d  lea     rax, [rbp+57h+var_38]
0x180053061  mov     [rsp+110h+var_C8], rax; __int64
0x180053066  lea     rax, [rbp+57h+var_70]
0x18005306a  mov     [rsp+110h+var_D0], rax; __int64
0x18005306f  lea     rax, [rbp+57h+var_30]
0x180053073  mov     [rsp+110h+var_D8], rax; __int64
0x180053078  lea     rax, [rbp+57h+var_70+4]
0x18005307c  mov     [rsp+110h+var_E0], rax; __int64
0x180053081  lea     rax, [rbp+57h+var_28]
0x180053085  mov     [rsp+110h+var_E8], rax; __int64
0x18005308a  lea     rax, [rbp+57h+var_20]
0x18005308e  mov     [rsp+110h+var_F0], rax; __int64
0x180053093  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180053098  jmp     loc_180053142
0x18005309d  lea     rdx, [rbp+57h+SRWLock]
0x1800530a1  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800530a6  mov     rax, [rbx+110h]
0x1800530ad  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800530b1  mov     dword ptr [rax], 2
0x1800530b7  test    rcx, rcx
0x1800530ba  jz      short loc_1800530C2
0x1800530bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800530c2  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800530c7  mov     rdi, [rax+8]
0x1800530cb  mov     eax, [rdi]
0x1800530cd  cmp     eax, 5
0x1800530d0  jbe     short loc_180053142
0x1800530d2  mov     rdx, [rdi+18h]
0x1800530d6  mov     rcx, 400000000000h
0x1800530e0  mov     rax, [rdi+10h]
0x1800530e4  test    rcx, rax
0x1800530e7  jz      short loc_180053142
0x1800530e9  mov     rax, rdx
0x1800530ec  and     rax, rcx
0x1800530ef  cmp     rax, rdx
0x1800530f2  jnz     short loc_180053142
0x1800530f4  call    cs:__imp_GetCurrentThreadId
0x1800530fa  mov     r8, [rbx+110h]
0x180053101  lea     rdx, byte_180082743
0x180053108  mov     dword ptr [rbp+57h+SRWLock], eax
0x18005310b  mov     rcx, rdi
0x18005310e  mov     eax, [r8+48h]
0x180053112  add     r8, 8
0x180053116  mov     dword ptr [rbp+57h+arg_8], eax
0x180053119  mov     eax, 1000000h
0x18005311e  mov     [rbp+57h+arg_10], rax
0x180053122  lea     rax, [rbp+57h+SRWLock]
0x180053126  mov     [rsp+110h+var_E0], rax
0x18005312b  lea     rax, [rbp+57h+arg_8]
0x18005312f  mov     [rsp+110h+var_E8], rax
0x180053134  lea     rax, [rbp+57h+arg_10]
0x180053138  mov     [rsp+110h+var_F0], rax
0x18005313d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180053142  mov     rcx, rbx
0x180053145  add     rsp, 100h
0x18005314c  pop     rdi
0x18005314d  pop     rbx
0x18005314e  pop     rbp
0x18005314f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
