# WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StopActivity(void)

- ea: `0x18003b690`
- end: `0x18003b914`
- name: `?StopActivity@RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18003b690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b6ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b6ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b87c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b8b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b8b4`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StopActivity(
        WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *this)
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
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
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
        (unsigned int)&word_1800942D6,
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
      && (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x200000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_180094409,
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
0x18003b690  push    rbp
0x18003b692  push    rbx
0x18003b693  push    rdi
0x18003b694  lea     rbp, [rsp-47h]
0x18003b699  sub     rsp, 100h
0x18003b6a0  mov     rdi, [rcx+110h]
0x18003b6a7  mov     rbx, rcx
0x18003b6aa  mov     eax, [rdi+48h]
0x18003b6ad  test    eax, eax
0x18003b6af  jns     loc_18003B85D
0x18003b6b5  add     rdi, 50h ; 'P'
0x18003b6b9  cmp     eax, [rdi+8]
0x18003b6bc  jnz     loc_18003B85D
0x18003b6c2  test    rdi, rdi
0x18003b6c5  jz      loc_18003B85D
0x18003b6cb  lea     rdx, [rbp+57h+SRWLock]
0x18003b6cf  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b6d4  mov     rax, [rbx+110h]
0x18003b6db  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b6df  mov     dword ptr [rax], 2
0x18003b6e5  test    rcx, rcx
0x18003b6e8  jz      short loc_18003B6F0
0x18003b6ea  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b6f0  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b6f5  mov     r9, [rax+8]
0x18003b6f9  mov     eax, [r9]
0x18003b6fc  cmp     eax, 5
0x18003b6ff  jbe     loc_18003B902
0x18003b705  mov     rdx, [r9+18h]
0x18003b709  mov     rcx, 200000000000h
0x18003b713  mov     rax, [r9+10h]
0x18003b717  test    rcx, rax
0x18003b71a  jz      loc_18003B902
0x18003b720  mov     rax, rdx
0x18003b723  and     rax, rcx
0x18003b726  cmp     rax, rdx
0x18003b729  jnz     loc_18003B902
0x18003b72f  mov     rax, [rdi+78h]
0x18003b733  lea     rdx, word_1800942D6
0x18003b73a  mov     r8, [rbx+110h]
0x18003b741  mov     rcx, r9
0x18003b744  mov     [rbp+57h+var_68], rax
0x18003b748  add     r8, 8
0x18003b74c  mov     rax, [rdi+70h]
0x18003b750  mov     [rbp+57h+var_60], rax
0x18003b754  mov     eax, [rdi+68h]
0x18003b757  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b75a  mov     rax, [rdi+60h]
0x18003b75e  mov     [rbp+57h+var_58], rax
0x18003b762  mov     rax, [rdi+58h]
0x18003b766  mov     [rbp+57h+var_50], rax
0x18003b76a  mov     eax, [rdi+50h]
0x18003b76d  mov     [rbp+57h+arg_8], eax
0x18003b770  mov     rax, [rdi+48h]
0x18003b774  mov     [rbp+57h+var_48], rax
0x18003b778  mov     eax, [rdi+20h]
0x18003b77b  mov     dword ptr [rbp+57h+arg_10], eax
0x18003b77e  mov     rax, [rdi+18h]
0x18003b782  mov     [rbp+57h+var_40], rax
0x18003b786  mov     eax, [rdi]
0x18003b788  mov     [rbp+57h+arg_18], eax
0x18003b78b  mov     rax, [rdi+80h]
0x18003b792  mov     [rbp+57h+var_38], rax
0x18003b796  mov     eax, [rdi+40h]
0x18003b799  mov     [rbp+57h+var_70], eax
0x18003b79c  mov     rax, [rdi+38h]
0x18003b7a0  mov     [rbp+57h+var_30], rax
0x18003b7a4  mov     eax, [rdi+8]
0x18003b7a7  mov     [rbp+57h+var_6C], eax
0x18003b7aa  mov     eax, 1000000h
0x18003b7af  mov     [rbp+57h+var_28], rax
0x18003b7b3  mov     [rbp+57h+var_20], rax
0x18003b7b7  lea     rax, [rbp+57h+var_68]
0x18003b7bb  mov     [rsp+110h+var_78], rax
0x18003b7c3  lea     rax, [rbp+57h+var_60]
0x18003b7c7  mov     [rsp+110h+var_80], rax
0x18003b7cf  lea     rax, [rbp+57h+SRWLock]
0x18003b7d3  mov     [rsp+110h+var_88], rax
0x18003b7db  lea     rax, [rbp+57h+var_58]
0x18003b7df  mov     [rsp+110h+var_90], rax
0x18003b7e7  lea     rax, [rbp+57h+var_50]
0x18003b7eb  mov     [rsp+110h+var_98], rax
0x18003b7f0  lea     rax, [rbp+57h+arg_8]
0x18003b7f4  mov     [rsp+110h+var_A0], rax
0x18003b7f9  lea     rax, [rbp+57h+var_48]
0x18003b7fd  mov     [rsp+110h+var_A8], rax
0x18003b802  lea     rax, [rbp+57h+arg_10]
0x18003b806  mov     [rsp+110h+var_B0], rax
0x18003b80b  lea     rax, [rbp+57h+var_40]
0x18003b80f  mov     [rsp+110h+var_B8], rax
0x18003b814  lea     rax, [rbp+57h+arg_18]
0x18003b818  mov     [rsp+110h+var_C0], rax
0x18003b81d  lea     rax, [rbp+57h+var_38]
0x18003b821  mov     [rsp+110h+var_C8], rax
0x18003b826  lea     rax, [rbp+57h+var_70]
0x18003b82a  mov     [rsp+110h+var_D0], rax
0x18003b82f  lea     rax, [rbp+57h+var_30]
0x18003b833  mov     [rsp+110h+var_D8], rax
0x18003b838  lea     rax, [rbp+57h+var_6C]
0x18003b83c  mov     [rsp+110h+var_E0], rax
0x18003b841  lea     rax, [rbp+57h+var_28]
0x18003b845  mov     [rsp+110h+var_E8], rax
0x18003b84a  lea     rax, [rbp+57h+var_20]
0x18003b84e  mov     [rsp+110h+var_F0], rax
0x18003b853  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003b858  jmp     loc_18003B902
0x18003b85d  lea     rdx, [rbp+57h+SRWLock]
0x18003b861  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b866  mov     rax, [rbx+110h]
0x18003b86d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b871  mov     dword ptr [rax], 2
0x18003b877  test    rcx, rcx
0x18003b87a  jz      short loc_18003B882
0x18003b87c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b882  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b887  mov     rdi, [rax+8]
0x18003b88b  mov     eax, [rdi]
0x18003b88d  cmp     eax, 5
0x18003b890  jbe     short loc_18003B902
0x18003b892  mov     rdx, [rdi+18h]
0x18003b896  mov     rcx, 200000000000h
0x18003b8a0  mov     rax, [rdi+10h]
0x18003b8a4  test    rcx, rax
0x18003b8a7  jz      short loc_18003B902
0x18003b8a9  mov     rax, rdx
0x18003b8ac  and     rax, rcx
0x18003b8af  cmp     rax, rdx
0x18003b8b2  jnz     short loc_18003B902
0x18003b8b4  call    cs:__imp_GetCurrentThreadId
0x18003b8ba  mov     r8, [rbx+110h]
0x18003b8c1  lea     rdx, byte_180094409
0x18003b8c8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b8cb  mov     rcx, rdi
0x18003b8ce  mov     eax, [r8+48h]
0x18003b8d2  add     r8, 8
0x18003b8d6  mov     [rbp+57h+arg_8], eax
0x18003b8d9  mov     eax, 1000000h
0x18003b8de  mov     [rbp+57h+arg_10], rax
0x18003b8e2  lea     rax, [rbp+57h+SRWLock]
0x18003b8e6  mov     [rsp+110h+var_E0], rax
0x18003b8eb  lea     rax, [rbp+57h+arg_8]
0x18003b8ef  mov     [rsp+110h+var_E8], rax
0x18003b8f4  lea     rax, [rbp+57h+arg_10]
0x18003b8f8  mov     [rsp+110h+var_F0], rax
0x18003b8fd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b902  mov     rcx, rbx
0x18003b905  add     rsp, 100h
0x18003b90c  pop     rdi
0x18003b90d  pop     rbx
0x18003b90e  pop     rbp
0x18003b90f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
