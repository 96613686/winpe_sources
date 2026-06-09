# ContextApplierProvider::ApplyContextActivity::StopActivity(void)

- ea: `0x14003f620`
- end: `0x14003f8b0`
- name: `?StopActivity@ApplyContextActivity@ContextApplierProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(ContextApplierProvider::ApplyContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14003abc4`
- `0x14003f620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f67a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f80d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f67a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f80d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003f844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003f844`

## pseudocode

```c
void __fastcall ContextApplierProvider::ApplyContextActivity::StopActivity(
        ContextApplierProvider::ApplyContextActivity *this)
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
    v5 = DynamoProvider::Provider();
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
          (__int64)word_140070DBA,
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
    v8 = DynamoProvider::Provider();
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
          (__int64)byte_140070F3D,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContextApplierProvider::ApplyContextActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003f620  push    rbp
0x14003f622  push    rbx
0x14003f623  push    rdi
0x14003f624  lea     rbp, [rsp-47h]
0x14003f629  sub     rsp, 100h
0x14003f630  mov     rbx, rcx
0x14003f633  mov     rdi, [rcx+110h]
0x14003f63a  mov     eax, [rdi+48h]
0x14003f63d  test    eax, eax
0x14003f63f  jns     loc_14003F7EE
0x14003f645  add     rdi, 50h ; 'P'
0x14003f649  cmp     eax, [rdi+8]
0x14003f64c  jnz     loc_14003F7EE
0x14003f652  test    rdi, rdi
0x14003f655  jz      loc_14003F7EE
0x14003f65b  lea     rdx, [rbp+57h+SRWLock]
0x14003f65f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003f664  mov     rax, [rbx+110h]
0x14003f66b  mov     dword ptr [rax], 2
0x14003f671  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003f675  test    rcx, rcx
0x14003f678  jz      short loc_14003F680
0x14003f67a  call    cs:__imp_ReleaseSRWLockExclusive
0x14003f680  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003f685  mov     r9, rax
0x14003f688  mov     ecx, [rax]
0x14003f68a  cmp     ecx, 5
0x14003f68d  jbe     loc_14003F892
0x14003f693  mov     rax, [rax+18h]
0x14003f697  mov     rcx, [r9+10h]
0x14003f69b  mov     rdx, 400000000000h
0x14003f6a5  test    rdx, rcx
0x14003f6a8  jz      loc_14003F892
0x14003f6ae  mov     rcx, rax
0x14003f6b1  and     rcx, rdx
0x14003f6b4  cmp     rcx, rax
0x14003f6b7  jnz     loc_14003F892
0x14003f6bd  mov     rax, [rdi+78h]
0x14003f6c1  mov     [rbp+57h+var_68], rax
0x14003f6c5  mov     rax, [rdi+70h]
0x14003f6c9  mov     [rbp+57h+var_60], rax
0x14003f6cd  mov     eax, [rdi+68h]
0x14003f6d0  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003f6d3  mov     rax, [rdi+60h]
0x14003f6d7  mov     [rbp+57h+var_58], rax
0x14003f6db  mov     rax, [rdi+58h]
0x14003f6df  mov     [rbp+57h+var_50], rax
0x14003f6e3  mov     eax, [rdi+50h]
0x14003f6e6  mov     [rbp+57h+arg_8], eax
0x14003f6e9  mov     rax, [rdi+48h]
0x14003f6ed  mov     [rbp+57h+var_48], rax
0x14003f6f1  mov     eax, [rdi+20h]
0x14003f6f4  mov     dword ptr [rbp+57h+arg_10], eax
0x14003f6f7  mov     rax, [rdi+18h]
0x14003f6fb  mov     [rbp+57h+var_40], rax
0x14003f6ff  mov     eax, [rdi]
0x14003f701  mov     [rbp+57h+arg_18], eax
0x14003f704  mov     rax, [rdi+80h]
0x14003f70b  mov     [rbp+57h+var_38], rax
0x14003f70f  mov     eax, [rdi+40h]
0x14003f712  mov     [rbp+57h+var_70], eax
0x14003f715  mov     rax, [rdi+38h]
0x14003f719  mov     [rbp+57h+var_30], rax
0x14003f71d  mov     eax, [rdi+8]
0x14003f720  mov     [rbp+57h+var_6C], eax
0x14003f723  mov     [rbp+57h+var_28], 1000000h
0x14003f72b  mov     [rbp+57h+var_20], 0
0x14003f733  mov     r8, [rbx+110h]
0x14003f73a  add     r8, 8
0x14003f73e  lea     rax, [rbp+57h+var_68]
0x14003f742  mov     [rsp+110h+var_78], rax
0x14003f74a  lea     rax, [rbp+57h+var_60]
0x14003f74e  mov     [rsp+110h+var_80], rax
0x14003f756  lea     rax, [rbp+57h+SRWLock]
0x14003f75a  mov     [rsp+110h+var_88], rax
0x14003f762  lea     rax, [rbp+57h+var_58]
0x14003f766  mov     [rsp+110h+var_90], rax
0x14003f76e  lea     rax, [rbp+57h+var_50]
0x14003f772  mov     [rsp+110h+var_98], rax
0x14003f777  lea     rax, [rbp+57h+arg_8]
0x14003f77b  mov     [rsp+110h+var_A0], rax
0x14003f780  lea     rax, [rbp+57h+var_48]
0x14003f784  mov     [rsp+110h+var_A8], rax
0x14003f789  lea     rax, [rbp+57h+arg_10]
0x14003f78d  mov     [rsp+110h+var_B0], rax
0x14003f792  lea     rax, [rbp+57h+var_40]
0x14003f796  mov     [rsp+110h+var_B8], rax
0x14003f79b  lea     rax, [rbp+57h+arg_18]
0x14003f79f  mov     [rsp+110h+var_C0], rax
0x14003f7a4  lea     rax, [rbp+57h+var_38]
0x14003f7a8  mov     [rsp+110h+var_C8], rax
0x14003f7ad  lea     rax, [rbp+57h+var_70]
0x14003f7b1  mov     [rsp+110h+var_D0], rax
0x14003f7b6  lea     rax, [rbp+57h+var_30]
0x14003f7ba  mov     [rsp+110h+var_D8], rax
0x14003f7bf  lea     rax, [rbp+57h+var_6C]
0x14003f7c3  mov     [rsp+110h+var_E0], rax
0x14003f7c8  lea     rax, [rbp+57h+var_28]
0x14003f7cc  mov     [rsp+110h+var_E8], rax
0x14003f7d1  lea     rax, [rbp+57h+var_20]
0x14003f7d5  mov     [rsp+110h+var_F0], rax
0x14003f7da  lea     rdx, word_140070DBA
0x14003f7e1  mov     rcx, r9
0x14003f7e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14003f7e9  jmp     loc_14003F892
0x14003f7ee  lea     rdx, [rbp+57h+SRWLock]
0x14003f7f2  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003f7f7  mov     rax, [rbx+110h]
0x14003f7fe  mov     dword ptr [rax], 2
0x14003f804  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003f808  test    rcx, rcx
0x14003f80b  jz      short loc_14003F813
0x14003f80d  call    cs:__imp_ReleaseSRWLockExclusive
0x14003f813  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003f818  mov     rdi, rax
0x14003f81b  mov     ecx, [rax]
0x14003f81d  cmp     ecx, 5
0x14003f820  jbe     short loc_14003F892
0x14003f822  mov     rax, [rax+18h]
0x14003f826  mov     rcx, [rdi+10h]
0x14003f82a  mov     rdx, 400000000000h
0x14003f834  test    rdx, rcx
0x14003f837  jz      short loc_14003F892
0x14003f839  mov     rcx, rax
0x14003f83c  and     rcx, rdx
0x14003f83f  cmp     rcx, rax
0x14003f842  jnz     short loc_14003F892
0x14003f844  call    cs:__imp_GetCurrentThreadId
0x14003f84a  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003f84d  mov     r8, [rbx+110h]
0x14003f854  mov     eax, [r8+48h]
0x14003f858  mov     [rbp+57h+arg_8], eax
0x14003f85b  mov     [rbp+57h+arg_10], 0
0x14003f863  add     r8, 8
0x14003f867  lea     rax, [rbp+57h+SRWLock]
0x14003f86b  mov     [rsp+110h+var_E0], rax
0x14003f870  lea     rax, [rbp+57h+arg_8]
0x14003f874  mov     [rsp+110h+var_E8], rax
0x14003f879  lea     rax, [rbp+57h+arg_10]
0x14003f87d  mov     [rsp+110h+var_F0], rax
0x14003f882  lea     rdx, byte_140070F3D
0x14003f889  mov     rcx, rdi
0x14003f88c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003f891  nop
0x14003f892  lea     rcx, [rbx+120h]; this
0x14003f899  cmp     dword ptr [rcx+18h], 0
0x14003f89d  jz      short loc_14003F8A5
0x14003f89f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003f8a4  nop
0x14003f8a5  add     rsp, 100h
0x14003f8ac  pop     rdi
0x14003f8ad  pop     rbx
0x14003f8ae  pop     rbp
0x14003f8af  retn
```
