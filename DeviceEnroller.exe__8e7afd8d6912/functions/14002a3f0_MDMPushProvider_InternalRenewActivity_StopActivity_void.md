# MDMPushProvider::InternalRenewActivity::StopActivity(void)

- ea: `0x14002a3f0`
- end: `0x14002a680`
- name: `?StopActivity@InternalRenewActivity@MDMPushProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(MDMPushProvider::InternalRenewActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x14002a3f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a5dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a5dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a614`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a614`

## pseudocode

```c
void __fastcall MDMPushProvider::InternalRenewActivity::StopActivity(MDMPushProvider::InternalRenewActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const OLECHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v16; // [rsp+B0h] [rbp-9h] BYREF
  const OLECHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v18; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const OLECHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = MDMPushProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v15 = (const OLECHAR *)*((_QWORD *)v4 + 15);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = (const OLECHAR *)*((_QWORD *)v4 + 12);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = (const OLECHAR *)*((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&dword_14006E72C,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v28,
          &v20,
          (__int64)&v27,
          &v19,
          (__int64)&v26,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v16,
          &v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = MDMPushProvider::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)byte_14006DDB1,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::InternalRenewActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14002a3f0  push    rbp
0x14002a3f2  push    rbx
0x14002a3f3  push    rdi
0x14002a3f4  lea     rbp, [rsp-47h]
0x14002a3f9  sub     rsp, 100h
0x14002a400  mov     rbx, rcx
0x14002a403  mov     rdi, [rcx+110h]
0x14002a40a  mov     eax, [rdi+48h]
0x14002a40d  test    eax, eax
0x14002a40f  jns     loc_14002A5BE
0x14002a415  add     rdi, 50h ; 'P'
0x14002a419  cmp     eax, [rdi+8]
0x14002a41c  jnz     loc_14002A5BE
0x14002a422  test    rdi, rdi
0x14002a425  jz      loc_14002A5BE
0x14002a42b  lea     rdx, [rbp+57h+SRWLock]
0x14002a42f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002a434  mov     rax, [rbx+110h]
0x14002a43b  mov     dword ptr [rax], 2
0x14002a441  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14002a445  test    rcx, rcx
0x14002a448  jz      short loc_14002A450
0x14002a44a  call    cs:__imp_ReleaseSRWLockExclusive
0x14002a450  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14002a455  mov     r9, rax
0x14002a458  mov     ecx, [rax]
0x14002a45a  cmp     ecx, 5
0x14002a45d  jbe     loc_14002A662
0x14002a463  mov     rax, [rax+18h]
0x14002a467  mov     rcx, [r9+10h]
0x14002a46b  mov     rdx, 400000000000h
0x14002a475  test    rdx, rcx
0x14002a478  jz      loc_14002A662
0x14002a47e  mov     rcx, rax
0x14002a481  and     rcx, rdx
0x14002a484  cmp     rcx, rax
0x14002a487  jnz     loc_14002A662
0x14002a48d  mov     rax, [rdi+78h]
0x14002a491  mov     [rbp+57h+var_68], rax
0x14002a495  mov     rax, [rdi+70h]
0x14002a499  mov     [rbp+57h+var_60], rax
0x14002a49d  mov     eax, [rdi+68h]
0x14002a4a0  mov     dword ptr [rbp+57h+SRWLock], eax
0x14002a4a3  mov     rax, [rdi+60h]
0x14002a4a7  mov     [rbp+57h+var_58], rax
0x14002a4ab  mov     rax, [rdi+58h]
0x14002a4af  mov     [rbp+57h+var_50], rax
0x14002a4b3  mov     eax, [rdi+50h]
0x14002a4b6  mov     [rbp+57h+arg_8], eax
0x14002a4b9  mov     rax, [rdi+48h]
0x14002a4bd  mov     [rbp+57h+var_48], rax
0x14002a4c1  mov     eax, [rdi+20h]
0x14002a4c4  mov     dword ptr [rbp+57h+arg_10], eax
0x14002a4c7  mov     rax, [rdi+18h]
0x14002a4cb  mov     [rbp+57h+var_40], rax
0x14002a4cf  mov     eax, [rdi]
0x14002a4d1  mov     [rbp+57h+arg_18], eax
0x14002a4d4  mov     rax, [rdi+80h]
0x14002a4db  mov     [rbp+57h+var_38], rax
0x14002a4df  mov     eax, [rdi+40h]
0x14002a4e2  mov     [rbp+57h+var_70], eax
0x14002a4e5  mov     rax, [rdi+38h]
0x14002a4e9  mov     [rbp+57h+var_30], rax
0x14002a4ed  mov     eax, [rdi+8]
0x14002a4f0  mov     [rbp+57h+var_6C], eax
0x14002a4f3  mov     [rbp+57h+var_28], 1000000h
0x14002a4fb  mov     [rbp+57h+var_20], 0
0x14002a503  mov     r8, [rbx+110h]
0x14002a50a  add     r8, 8
0x14002a50e  lea     rax, [rbp+57h+var_68]
0x14002a512  mov     [rsp+110h+var_78], rax
0x14002a51a  lea     rax, [rbp+57h+var_60]
0x14002a51e  mov     [rsp+110h+var_80], rax
0x14002a526  lea     rax, [rbp+57h+SRWLock]
0x14002a52a  mov     [rsp+110h+var_88], rax
0x14002a532  lea     rax, [rbp+57h+var_58]
0x14002a536  mov     [rsp+110h+var_90], rax
0x14002a53e  lea     rax, [rbp+57h+var_50]
0x14002a542  mov     [rsp+110h+var_98], rax
0x14002a547  lea     rax, [rbp+57h+arg_8]
0x14002a54b  mov     [rsp+110h+var_A0], rax
0x14002a550  lea     rax, [rbp+57h+var_48]
0x14002a554  mov     [rsp+110h+var_A8], rax
0x14002a559  lea     rax, [rbp+57h+arg_10]
0x14002a55d  mov     [rsp+110h+var_B0], rax
0x14002a562  lea     rax, [rbp+57h+var_40]
0x14002a566  mov     [rsp+110h+var_B8], rax
0x14002a56b  lea     rax, [rbp+57h+arg_18]
0x14002a56f  mov     [rsp+110h+var_C0], rax
0x14002a574  lea     rax, [rbp+57h+var_38]
0x14002a578  mov     [rsp+110h+var_C8], rax
0x14002a57d  lea     rax, [rbp+57h+var_70]
0x14002a581  mov     [rsp+110h+var_D0], rax
0x14002a586  lea     rax, [rbp+57h+var_30]
0x14002a58a  mov     [rsp+110h+var_D8], rax
0x14002a58f  lea     rax, [rbp+57h+var_6C]
0x14002a593  mov     [rsp+110h+var_E0], rax
0x14002a598  lea     rax, [rbp+57h+var_28]
0x14002a59c  mov     [rsp+110h+var_E8], rax
0x14002a5a1  lea     rax, [rbp+57h+var_20]
0x14002a5a5  mov     [rsp+110h+var_F0], rax
0x14002a5aa  lea     rdx, dword_14006E72C
0x14002a5b1  mov     rcx, r9
0x14002a5b4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14002a5b9  jmp     loc_14002A662
0x14002a5be  lea     rdx, [rbp+57h+SRWLock]
0x14002a5c2  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002a5c7  mov     rax, [rbx+110h]
0x14002a5ce  mov     dword ptr [rax], 2
0x14002a5d4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14002a5d8  test    rcx, rcx
0x14002a5db  jz      short loc_14002A5E3
0x14002a5dd  call    cs:__imp_ReleaseSRWLockExclusive
0x14002a5e3  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14002a5e8  mov     rdi, rax
0x14002a5eb  mov     ecx, [rax]
0x14002a5ed  cmp     ecx, 5
0x14002a5f0  jbe     short loc_14002A662
0x14002a5f2  mov     rax, [rax+18h]
0x14002a5f6  mov     rcx, [rdi+10h]
0x14002a5fa  mov     rdx, 400000000000h
0x14002a604  test    rdx, rcx
0x14002a607  jz      short loc_14002A662
0x14002a609  mov     rcx, rax
0x14002a60c  and     rcx, rdx
0x14002a60f  cmp     rcx, rax
0x14002a612  jnz     short loc_14002A662
0x14002a614  call    cs:__imp_GetCurrentThreadId
0x14002a61a  mov     dword ptr [rbp+57h+SRWLock], eax
0x14002a61d  mov     r8, [rbx+110h]
0x14002a624  mov     eax, [r8+48h]
0x14002a628  mov     [rbp+57h+arg_8], eax
0x14002a62b  mov     [rbp+57h+arg_10], 0
0x14002a633  add     r8, 8
0x14002a637  lea     rax, [rbp+57h+SRWLock]
0x14002a63b  mov     [rsp+110h+var_E0], rax
0x14002a640  lea     rax, [rbp+57h+arg_8]
0x14002a644  mov     [rsp+110h+var_E8], rax
0x14002a649  lea     rax, [rbp+57h+arg_10]
0x14002a64d  mov     [rsp+110h+var_F0], rax
0x14002a652  lea     rdx, byte_14006DDB1
0x14002a659  mov     rcx, rdi
0x14002a65c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002a661  nop
0x14002a662  lea     rcx, [rbx+120h]; this
0x14002a669  cmp     dword ptr [rcx+18h], 0
0x14002a66d  jz      short loc_14002A675
0x14002a66f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14002a674  nop
0x14002a675  add     rsp, 100h
0x14002a67c  pop     rdi
0x14002a67d  pop     rbx
0x14002a67e  pop     rbp
0x14002a67f  retn
```
