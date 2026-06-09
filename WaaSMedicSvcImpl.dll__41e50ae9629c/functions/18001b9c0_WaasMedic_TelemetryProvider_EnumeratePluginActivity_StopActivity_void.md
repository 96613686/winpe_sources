# WaasMedic::TelemetryProvider::EnumeratePluginActivity::StopActivity(void)

- ea: `0x18001b9c0`
- end: `0x18001bc44`
- name: `?StopActivity@EnumeratePluginActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::EnumeratePluginActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18001b9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bbac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bbac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bbe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bbe4`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::EnumeratePluginActivity::StopActivity(
        WaasMedic::TelemetryProvider::EnumeratePluginActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
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
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
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
        v6,
        (unsigned int)&unk_1800921A3,
        v7 + 8,
        v6,
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&unk_18009244F,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001b9c0  push    rbp
0x18001b9c2  push    rbx
0x18001b9c3  push    rdi
0x18001b9c4  lea     rbp, [rsp-47h]
0x18001b9c9  sub     rsp, 100h
0x18001b9d0  mov     rdi, [rcx+110h]
0x18001b9d7  mov     rbx, rcx
0x18001b9da  mov     eax, [rdi+48h]
0x18001b9dd  test    eax, eax
0x18001b9df  jns     loc_18001BB8D
0x18001b9e5  add     rdi, 50h ; 'P'
0x18001b9e9  cmp     eax, [rdi+8]
0x18001b9ec  jnz     loc_18001BB8D
0x18001b9f2  test    rdi, rdi
0x18001b9f5  jz      loc_18001BB8D
0x18001b9fb  lea     rdx, [rbp+57h+SRWLock]
0x18001b9ff  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ba04  mov     rax, [rbx+110h]
0x18001ba0b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ba0f  mov     dword ptr [rax], 2
0x18001ba15  test    rcx, rcx
0x18001ba18  jz      short loc_18001BA20
0x18001ba1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ba20  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001ba25  mov     r9, [rax+8]
0x18001ba29  mov     eax, [r9]
0x18001ba2c  cmp     eax, 5
0x18001ba2f  jbe     loc_18001BC32
0x18001ba35  mov     rdx, [r9+18h]
0x18001ba39  mov     rcx, 400000000000h
0x18001ba43  mov     rax, [r9+10h]
0x18001ba47  test    rcx, rax
0x18001ba4a  jz      loc_18001BC32
0x18001ba50  mov     rax, rdx
0x18001ba53  and     rax, rcx
0x18001ba56  cmp     rax, rdx
0x18001ba59  jnz     loc_18001BC32
0x18001ba5f  mov     rax, [rdi+78h]
0x18001ba63  lea     rdx, unk_1800921A3
0x18001ba6a  mov     r8, [rbx+110h]
0x18001ba71  mov     rcx, r9
0x18001ba74  mov     [rbp+57h+var_68], rax
0x18001ba78  add     r8, 8
0x18001ba7c  mov     rax, [rdi+70h]
0x18001ba80  mov     [rbp+57h+var_60], rax
0x18001ba84  mov     eax, [rdi+68h]
0x18001ba87  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001ba8a  mov     rax, [rdi+60h]
0x18001ba8e  mov     [rbp+57h+var_58], rax
0x18001ba92  mov     rax, [rdi+58h]
0x18001ba96  mov     [rbp+57h+var_50], rax
0x18001ba9a  mov     eax, [rdi+50h]
0x18001ba9d  mov     [rbp+57h+arg_8], eax
0x18001baa0  mov     rax, [rdi+48h]
0x18001baa4  mov     [rbp+57h+var_48], rax
0x18001baa8  mov     eax, [rdi+20h]
0x18001baab  mov     dword ptr [rbp+57h+arg_10], eax
0x18001baae  mov     rax, [rdi+18h]
0x18001bab2  mov     [rbp+57h+var_40], rax
0x18001bab6  mov     eax, [rdi]
0x18001bab8  mov     [rbp+57h+arg_18], eax
0x18001babb  mov     rax, [rdi+80h]
0x18001bac2  mov     [rbp+57h+var_38], rax
0x18001bac6  mov     eax, [rdi+40h]
0x18001bac9  mov     [rbp+57h+var_70], eax
0x18001bacc  mov     rax, [rdi+38h]
0x18001bad0  mov     [rbp+57h+var_30], rax
0x18001bad4  mov     eax, [rdi+8]
0x18001bad7  mov     [rbp+57h+var_6C], eax
0x18001bada  mov     eax, 1000000h
0x18001badf  mov     [rbp+57h+var_28], rax
0x18001bae3  mov     [rbp+57h+var_20], rax
0x18001bae7  lea     rax, [rbp+57h+var_68]
0x18001baeb  mov     [rsp+110h+var_78], rax
0x18001baf3  lea     rax, [rbp+57h+var_60]
0x18001baf7  mov     [rsp+110h+var_80], rax
0x18001baff  lea     rax, [rbp+57h+SRWLock]
0x18001bb03  mov     [rsp+110h+var_88], rax
0x18001bb0b  lea     rax, [rbp+57h+var_58]
0x18001bb0f  mov     [rsp+110h+var_90], rax
0x18001bb17  lea     rax, [rbp+57h+var_50]
0x18001bb1b  mov     [rsp+110h+var_98], rax
0x18001bb20  lea     rax, [rbp+57h+arg_8]
0x18001bb24  mov     [rsp+110h+var_A0], rax
0x18001bb29  lea     rax, [rbp+57h+var_48]
0x18001bb2d  mov     [rsp+110h+var_A8], rax
0x18001bb32  lea     rax, [rbp+57h+arg_10]
0x18001bb36  mov     [rsp+110h+var_B0], rax
0x18001bb3b  lea     rax, [rbp+57h+var_40]
0x18001bb3f  mov     [rsp+110h+var_B8], rax
0x18001bb44  lea     rax, [rbp+57h+arg_18]
0x18001bb48  mov     [rsp+110h+var_C0], rax
0x18001bb4d  lea     rax, [rbp+57h+var_38]
0x18001bb51  mov     [rsp+110h+var_C8], rax
0x18001bb56  lea     rax, [rbp+57h+var_70]
0x18001bb5a  mov     [rsp+110h+var_D0], rax
0x18001bb5f  lea     rax, [rbp+57h+var_30]
0x18001bb63  mov     [rsp+110h+var_D8], rax
0x18001bb68  lea     rax, [rbp+57h+var_6C]
0x18001bb6c  mov     [rsp+110h+var_E0], rax
0x18001bb71  lea     rax, [rbp+57h+var_28]
0x18001bb75  mov     [rsp+110h+var_E8], rax
0x18001bb7a  lea     rax, [rbp+57h+var_20]
0x18001bb7e  mov     [rsp+110h+var_F0], rax
0x18001bb83  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001bb88  jmp     loc_18001BC32
0x18001bb8d  lea     rdx, [rbp+57h+SRWLock]
0x18001bb91  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001bb96  mov     rax, [rbx+110h]
0x18001bb9d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001bba1  mov     dword ptr [rax], 2
0x18001bba7  test    rcx, rcx
0x18001bbaa  jz      short loc_18001BBB2
0x18001bbac  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bbb2  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001bbb7  mov     rdi, [rax+8]
0x18001bbbb  mov     eax, [rdi]
0x18001bbbd  cmp     eax, 5
0x18001bbc0  jbe     short loc_18001BC32
0x18001bbc2  mov     rdx, [rdi+18h]
0x18001bbc6  mov     rcx, 400000000000h
0x18001bbd0  mov     rax, [rdi+10h]
0x18001bbd4  test    rcx, rax
0x18001bbd7  jz      short loc_18001BC32
0x18001bbd9  mov     rax, rdx
0x18001bbdc  and     rax, rcx
0x18001bbdf  cmp     rax, rdx
0x18001bbe2  jnz     short loc_18001BC32
0x18001bbe4  call    cs:__imp_GetCurrentThreadId
0x18001bbea  mov     r8, [rbx+110h]
0x18001bbf1  lea     rdx, unk_18009244F
0x18001bbf8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001bbfb  mov     rcx, rdi
0x18001bbfe  mov     eax, [r8+48h]
0x18001bc02  add     r8, 8
0x18001bc06  mov     [rbp+57h+arg_8], eax
0x18001bc09  mov     eax, 1000000h
0x18001bc0e  mov     [rbp+57h+arg_10], rax
0x18001bc12  lea     rax, [rbp+57h+SRWLock]
0x18001bc16  mov     [rsp+110h+var_E0], rax
0x18001bc1b  lea     rax, [rbp+57h+arg_8]
0x18001bc1f  mov     [rsp+110h+var_E8], rax
0x18001bc24  lea     rax, [rbp+57h+arg_10]
0x18001bc28  mov     [rsp+110h+var_F0], rax
0x18001bc2d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001bc32  mov     rcx, rbx
0x18001bc35  add     rsp, 100h
0x18001bc3c  pop     rdi
0x18001bc3d  pop     rbx
0x18001bc3e  pop     rbp
0x18001bc3f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
