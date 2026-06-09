# WaasMedic::TelemetryProvider::DetectionActivity::StopActivity(void)

- ea: `0x18001b730`
- end: `0x18001b9b4`
- name: `?StopActivity@DetectionActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::DetectionActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18001b730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b78a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b91c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b78a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b91c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b954`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::DetectionActivity::StopActivity(
        WaasMedic::TelemetryProvider::DetectionActivity *this)
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
        (unsigned int)&word_180092326,
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
        (unsigned int)byte_180092865,
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
0x18001b730  push    rbp
0x18001b732  push    rbx
0x18001b733  push    rdi
0x18001b734  lea     rbp, [rsp-47h]
0x18001b739  sub     rsp, 100h
0x18001b740  mov     rdi, [rcx+110h]
0x18001b747  mov     rbx, rcx
0x18001b74a  mov     eax, [rdi+48h]
0x18001b74d  test    eax, eax
0x18001b74f  jns     loc_18001B8FD
0x18001b755  add     rdi, 50h ; 'P'
0x18001b759  cmp     eax, [rdi+8]
0x18001b75c  jnz     loc_18001B8FD
0x18001b762  test    rdi, rdi
0x18001b765  jz      loc_18001B8FD
0x18001b76b  lea     rdx, [rbp+57h+SRWLock]
0x18001b76f  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b774  mov     rax, [rbx+110h]
0x18001b77b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b77f  mov     dword ptr [rax], 2
0x18001b785  test    rcx, rcx
0x18001b788  jz      short loc_18001B790
0x18001b78a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b790  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b795  mov     r9, [rax+8]
0x18001b799  mov     eax, [r9]
0x18001b79c  cmp     eax, 5
0x18001b79f  jbe     loc_18001B9A2
0x18001b7a5  mov     rdx, [r9+18h]
0x18001b7a9  mov     rcx, 400000000000h
0x18001b7b3  mov     rax, [r9+10h]
0x18001b7b7  test    rcx, rax
0x18001b7ba  jz      loc_18001B9A2
0x18001b7c0  mov     rax, rdx
0x18001b7c3  and     rax, rcx
0x18001b7c6  cmp     rax, rdx
0x18001b7c9  jnz     loc_18001B9A2
0x18001b7cf  mov     rax, [rdi+78h]
0x18001b7d3  lea     rdx, word_180092326
0x18001b7da  mov     r8, [rbx+110h]
0x18001b7e1  mov     rcx, r9
0x18001b7e4  mov     [rbp+57h+var_68], rax
0x18001b7e8  add     r8, 8
0x18001b7ec  mov     rax, [rdi+70h]
0x18001b7f0  mov     [rbp+57h+var_60], rax
0x18001b7f4  mov     eax, [rdi+68h]
0x18001b7f7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b7fa  mov     rax, [rdi+60h]
0x18001b7fe  mov     [rbp+57h+var_58], rax
0x18001b802  mov     rax, [rdi+58h]
0x18001b806  mov     [rbp+57h+var_50], rax
0x18001b80a  mov     eax, [rdi+50h]
0x18001b80d  mov     [rbp+57h+arg_8], eax
0x18001b810  mov     rax, [rdi+48h]
0x18001b814  mov     [rbp+57h+var_48], rax
0x18001b818  mov     eax, [rdi+20h]
0x18001b81b  mov     dword ptr [rbp+57h+arg_10], eax
0x18001b81e  mov     rax, [rdi+18h]
0x18001b822  mov     [rbp+57h+var_40], rax
0x18001b826  mov     eax, [rdi]
0x18001b828  mov     [rbp+57h+arg_18], eax
0x18001b82b  mov     rax, [rdi+80h]
0x18001b832  mov     [rbp+57h+var_38], rax
0x18001b836  mov     eax, [rdi+40h]
0x18001b839  mov     [rbp+57h+var_70], eax
0x18001b83c  mov     rax, [rdi+38h]
0x18001b840  mov     [rbp+57h+var_30], rax
0x18001b844  mov     eax, [rdi+8]
0x18001b847  mov     [rbp+57h+var_6C], eax
0x18001b84a  mov     eax, 1000000h
0x18001b84f  mov     [rbp+57h+var_28], rax
0x18001b853  mov     [rbp+57h+var_20], rax
0x18001b857  lea     rax, [rbp+57h+var_68]
0x18001b85b  mov     [rsp+110h+var_78], rax
0x18001b863  lea     rax, [rbp+57h+var_60]
0x18001b867  mov     [rsp+110h+var_80], rax
0x18001b86f  lea     rax, [rbp+57h+SRWLock]
0x18001b873  mov     [rsp+110h+var_88], rax
0x18001b87b  lea     rax, [rbp+57h+var_58]
0x18001b87f  mov     [rsp+110h+var_90], rax
0x18001b887  lea     rax, [rbp+57h+var_50]
0x18001b88b  mov     [rsp+110h+var_98], rax
0x18001b890  lea     rax, [rbp+57h+arg_8]
0x18001b894  mov     [rsp+110h+var_A0], rax
0x18001b899  lea     rax, [rbp+57h+var_48]
0x18001b89d  mov     [rsp+110h+var_A8], rax
0x18001b8a2  lea     rax, [rbp+57h+arg_10]
0x18001b8a6  mov     [rsp+110h+var_B0], rax
0x18001b8ab  lea     rax, [rbp+57h+var_40]
0x18001b8af  mov     [rsp+110h+var_B8], rax
0x18001b8b4  lea     rax, [rbp+57h+arg_18]
0x18001b8b8  mov     [rsp+110h+var_C0], rax
0x18001b8bd  lea     rax, [rbp+57h+var_38]
0x18001b8c1  mov     [rsp+110h+var_C8], rax
0x18001b8c6  lea     rax, [rbp+57h+var_70]
0x18001b8ca  mov     [rsp+110h+var_D0], rax
0x18001b8cf  lea     rax, [rbp+57h+var_30]
0x18001b8d3  mov     [rsp+110h+var_D8], rax
0x18001b8d8  lea     rax, [rbp+57h+var_6C]
0x18001b8dc  mov     [rsp+110h+var_E0], rax
0x18001b8e1  lea     rax, [rbp+57h+var_28]
0x18001b8e5  mov     [rsp+110h+var_E8], rax
0x18001b8ea  lea     rax, [rbp+57h+var_20]
0x18001b8ee  mov     [rsp+110h+var_F0], rax
0x18001b8f3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b8f8  jmp     loc_18001B9A2
0x18001b8fd  lea     rdx, [rbp+57h+SRWLock]
0x18001b901  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b906  mov     rax, [rbx+110h]
0x18001b90d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b911  mov     dword ptr [rax], 2
0x18001b917  test    rcx, rcx
0x18001b91a  jz      short loc_18001B922
0x18001b91c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b922  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b927  mov     rdi, [rax+8]
0x18001b92b  mov     eax, [rdi]
0x18001b92d  cmp     eax, 5
0x18001b930  jbe     short loc_18001B9A2
0x18001b932  mov     rdx, [rdi+18h]
0x18001b936  mov     rcx, 400000000000h
0x18001b940  mov     rax, [rdi+10h]
0x18001b944  test    rcx, rax
0x18001b947  jz      short loc_18001B9A2
0x18001b949  mov     rax, rdx
0x18001b94c  and     rax, rcx
0x18001b94f  cmp     rax, rdx
0x18001b952  jnz     short loc_18001B9A2
0x18001b954  call    cs:__imp_GetCurrentThreadId
0x18001b95a  mov     r8, [rbx+110h]
0x18001b961  lea     rdx, byte_180092865
0x18001b968  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b96b  mov     rcx, rdi
0x18001b96e  mov     eax, [r8+48h]
0x18001b972  add     r8, 8
0x18001b976  mov     [rbp+57h+arg_8], eax
0x18001b979  mov     eax, 1000000h
0x18001b97e  mov     [rbp+57h+arg_10], rax
0x18001b982  lea     rax, [rbp+57h+SRWLock]
0x18001b986  mov     [rsp+110h+var_E0], rax
0x18001b98b  lea     rax, [rbp+57h+arg_8]
0x18001b98f  mov     [rsp+110h+var_E8], rax
0x18001b994  lea     rax, [rbp+57h+arg_10]
0x18001b998  mov     [rsp+110h+var_F0], rax
0x18001b99d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b9a2  mov     rcx, rbx
0x18001b9a5  add     rsp, 100h
0x18001b9ac  pop     rdi
0x18001b9ad  pop     rbx
0x18001b9ae  pop     rbp
0x18001b9af  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
