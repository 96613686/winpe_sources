# WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StopActivity(void)

- ea: `0x18003b400`
- end: `0x18003b684`
- name: `?StopActivity@AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AddProtectedTaskActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18003b400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b5ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b5ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b624`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StopActivity(
        WaasMedic::TelemetryProvider::AddProtectedTaskActivity *this)
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
        (unsigned int)&unk_180094943,
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
        (unsigned int)&unk_180094A73,
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
0x18003b400  push    rbp
0x18003b402  push    rbx
0x18003b403  push    rdi
0x18003b404  lea     rbp, [rsp-47h]
0x18003b409  sub     rsp, 100h
0x18003b410  mov     rdi, [rcx+110h]
0x18003b417  mov     rbx, rcx
0x18003b41a  mov     eax, [rdi+48h]
0x18003b41d  test    eax, eax
0x18003b41f  jns     loc_18003B5CD
0x18003b425  add     rdi, 50h ; 'P'
0x18003b429  cmp     eax, [rdi+8]
0x18003b42c  jnz     loc_18003B5CD
0x18003b432  test    rdi, rdi
0x18003b435  jz      loc_18003B5CD
0x18003b43b  lea     rdx, [rbp+57h+SRWLock]
0x18003b43f  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b444  mov     rax, [rbx+110h]
0x18003b44b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b44f  mov     dword ptr [rax], 2
0x18003b455  test    rcx, rcx
0x18003b458  jz      short loc_18003B460
0x18003b45a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b460  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b465  mov     r9, [rax+8]
0x18003b469  mov     eax, [r9]
0x18003b46c  cmp     eax, 5
0x18003b46f  jbe     loc_18003B672
0x18003b475  mov     rdx, [r9+18h]
0x18003b479  mov     rcx, 200000000000h
0x18003b483  mov     rax, [r9+10h]
0x18003b487  test    rcx, rax
0x18003b48a  jz      loc_18003B672
0x18003b490  mov     rax, rdx
0x18003b493  and     rax, rcx
0x18003b496  cmp     rax, rdx
0x18003b499  jnz     loc_18003B672
0x18003b49f  mov     rax, [rdi+78h]
0x18003b4a3  lea     rdx, unk_180094943
0x18003b4aa  mov     r8, [rbx+110h]
0x18003b4b1  mov     rcx, r9
0x18003b4b4  mov     [rbp+57h+var_68], rax
0x18003b4b8  add     r8, 8
0x18003b4bc  mov     rax, [rdi+70h]
0x18003b4c0  mov     [rbp+57h+var_60], rax
0x18003b4c4  mov     eax, [rdi+68h]
0x18003b4c7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b4ca  mov     rax, [rdi+60h]
0x18003b4ce  mov     [rbp+57h+var_58], rax
0x18003b4d2  mov     rax, [rdi+58h]
0x18003b4d6  mov     [rbp+57h+var_50], rax
0x18003b4da  mov     eax, [rdi+50h]
0x18003b4dd  mov     [rbp+57h+arg_8], eax
0x18003b4e0  mov     rax, [rdi+48h]
0x18003b4e4  mov     [rbp+57h+var_48], rax
0x18003b4e8  mov     eax, [rdi+20h]
0x18003b4eb  mov     dword ptr [rbp+57h+arg_10], eax
0x18003b4ee  mov     rax, [rdi+18h]
0x18003b4f2  mov     [rbp+57h+var_40], rax
0x18003b4f6  mov     eax, [rdi]
0x18003b4f8  mov     [rbp+57h+arg_18], eax
0x18003b4fb  mov     rax, [rdi+80h]
0x18003b502  mov     [rbp+57h+var_38], rax
0x18003b506  mov     eax, [rdi+40h]
0x18003b509  mov     [rbp+57h+var_70], eax
0x18003b50c  mov     rax, [rdi+38h]
0x18003b510  mov     [rbp+57h+var_30], rax
0x18003b514  mov     eax, [rdi+8]
0x18003b517  mov     [rbp+57h+var_6C], eax
0x18003b51a  mov     eax, 1000000h
0x18003b51f  mov     [rbp+57h+var_28], rax
0x18003b523  mov     [rbp+57h+var_20], rax
0x18003b527  lea     rax, [rbp+57h+var_68]
0x18003b52b  mov     [rsp+110h+var_78], rax
0x18003b533  lea     rax, [rbp+57h+var_60]
0x18003b537  mov     [rsp+110h+var_80], rax
0x18003b53f  lea     rax, [rbp+57h+SRWLock]
0x18003b543  mov     [rsp+110h+var_88], rax
0x18003b54b  lea     rax, [rbp+57h+var_58]
0x18003b54f  mov     [rsp+110h+var_90], rax
0x18003b557  lea     rax, [rbp+57h+var_50]
0x18003b55b  mov     [rsp+110h+var_98], rax
0x18003b560  lea     rax, [rbp+57h+arg_8]
0x18003b564  mov     [rsp+110h+var_A0], rax
0x18003b569  lea     rax, [rbp+57h+var_48]
0x18003b56d  mov     [rsp+110h+var_A8], rax
0x18003b572  lea     rax, [rbp+57h+arg_10]
0x18003b576  mov     [rsp+110h+var_B0], rax
0x18003b57b  lea     rax, [rbp+57h+var_40]
0x18003b57f  mov     [rsp+110h+var_B8], rax
0x18003b584  lea     rax, [rbp+57h+arg_18]
0x18003b588  mov     [rsp+110h+var_C0], rax
0x18003b58d  lea     rax, [rbp+57h+var_38]
0x18003b591  mov     [rsp+110h+var_C8], rax
0x18003b596  lea     rax, [rbp+57h+var_70]
0x18003b59a  mov     [rsp+110h+var_D0], rax
0x18003b59f  lea     rax, [rbp+57h+var_30]
0x18003b5a3  mov     [rsp+110h+var_D8], rax
0x18003b5a8  lea     rax, [rbp+57h+var_6C]
0x18003b5ac  mov     [rsp+110h+var_E0], rax
0x18003b5b1  lea     rax, [rbp+57h+var_28]
0x18003b5b5  mov     [rsp+110h+var_E8], rax
0x18003b5ba  lea     rax, [rbp+57h+var_20]
0x18003b5be  mov     [rsp+110h+var_F0], rax
0x18003b5c3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003b5c8  jmp     loc_18003B672
0x18003b5cd  lea     rdx, [rbp+57h+SRWLock]
0x18003b5d1  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b5d6  mov     rax, [rbx+110h]
0x18003b5dd  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003b5e1  mov     dword ptr [rax], 2
0x18003b5e7  test    rcx, rcx
0x18003b5ea  jz      short loc_18003B5F2
0x18003b5ec  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b5f2  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b5f7  mov     rdi, [rax+8]
0x18003b5fb  mov     eax, [rdi]
0x18003b5fd  cmp     eax, 5
0x18003b600  jbe     short loc_18003B672
0x18003b602  mov     rdx, [rdi+18h]
0x18003b606  mov     rcx, 200000000000h
0x18003b610  mov     rax, [rdi+10h]
0x18003b614  test    rcx, rax
0x18003b617  jz      short loc_18003B672
0x18003b619  mov     rax, rdx
0x18003b61c  and     rax, rcx
0x18003b61f  cmp     rax, rdx
0x18003b622  jnz     short loc_18003B672
0x18003b624  call    cs:__imp_GetCurrentThreadId
0x18003b62a  mov     r8, [rbx+110h]
0x18003b631  lea     rdx, unk_180094A73
0x18003b638  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003b63b  mov     rcx, rdi
0x18003b63e  mov     eax, [r8+48h]
0x18003b642  add     r8, 8
0x18003b646  mov     [rbp+57h+arg_8], eax
0x18003b649  mov     eax, 1000000h
0x18003b64e  mov     [rbp+57h+arg_10], rax
0x18003b652  lea     rax, [rbp+57h+SRWLock]
0x18003b656  mov     [rsp+110h+var_E0], rax
0x18003b65b  lea     rax, [rbp+57h+arg_8]
0x18003b65f  mov     [rsp+110h+var_E8], rax
0x18003b664  lea     rax, [rbp+57h+arg_10]
0x18003b668  mov     [rsp+110h+var_F0], rax
0x18003b66d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b672  mov     rcx, rbx
0x18003b675  add     rsp, 100h
0x18003b67c  pop     rdi
0x18003b67d  pop     rbx
0x18003b67e  pop     rbp
0x18003b67f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
