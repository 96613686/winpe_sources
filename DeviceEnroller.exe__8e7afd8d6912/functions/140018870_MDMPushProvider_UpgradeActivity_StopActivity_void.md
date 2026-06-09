# MDMPushProvider::UpgradeActivity::StopActivity(void)

- ea: `0x140018870`
- end: `0x140018b00`
- name: `?StopActivity@UpgradeActivity@MDMPushProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(MDMPushProvider::UpgradeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018870`
- `0x140018b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400188ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018a5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400188ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018a94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018a94`

## pseudocode

```c
void __fastcall MDMPushProvider::UpgradeActivity::StopActivity(MDMPushProvider::UpgradeActivity *this)
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
          (__int64)&byte_14006D8C7,
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
          (__int64)&word_14006D5CE,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::UpgradeActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140018870  push    rbp
0x140018872  push    rbx
0x140018873  push    rdi
0x140018874  lea     rbp, [rsp-47h]
0x140018879  sub     rsp, 100h
0x140018880  mov     rbx, rcx
0x140018883  mov     rdi, [rcx+110h]
0x14001888a  mov     eax, [rdi+48h]
0x14001888d  test    eax, eax
0x14001888f  jns     loc_140018A3E
0x140018895  add     rdi, 50h ; 'P'
0x140018899  cmp     eax, [rdi+8]
0x14001889c  jnz     loc_140018A3E
0x1400188a2  test    rdi, rdi
0x1400188a5  jz      loc_140018A3E
0x1400188ab  lea     rdx, [rbp+57h+SRWLock]
0x1400188af  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400188b4  mov     rax, [rbx+110h]
0x1400188bb  mov     dword ptr [rax], 2
0x1400188c1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400188c5  test    rcx, rcx
0x1400188c8  jz      short loc_1400188D0
0x1400188ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1400188d0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400188d5  mov     r9, rax
0x1400188d8  mov     ecx, [rax]
0x1400188da  cmp     ecx, 5
0x1400188dd  jbe     loc_140018AE2
0x1400188e3  mov     rax, [rax+18h]
0x1400188e7  mov     rcx, [r9+10h]
0x1400188eb  mov     rdx, 400000000000h
0x1400188f5  test    rdx, rcx
0x1400188f8  jz      loc_140018AE2
0x1400188fe  mov     rcx, rax
0x140018901  and     rcx, rdx
0x140018904  cmp     rcx, rax
0x140018907  jnz     loc_140018AE2
0x14001890d  mov     rax, [rdi+78h]
0x140018911  mov     [rbp+57h+var_68], rax
0x140018915  mov     rax, [rdi+70h]
0x140018919  mov     [rbp+57h+var_60], rax
0x14001891d  mov     eax, [rdi+68h]
0x140018920  mov     dword ptr [rbp+57h+SRWLock], eax
0x140018923  mov     rax, [rdi+60h]
0x140018927  mov     [rbp+57h+var_58], rax
0x14001892b  mov     rax, [rdi+58h]
0x14001892f  mov     [rbp+57h+var_50], rax
0x140018933  mov     eax, [rdi+50h]
0x140018936  mov     [rbp+57h+arg_8], eax
0x140018939  mov     rax, [rdi+48h]
0x14001893d  mov     [rbp+57h+var_48], rax
0x140018941  mov     eax, [rdi+20h]
0x140018944  mov     dword ptr [rbp+57h+arg_10], eax
0x140018947  mov     rax, [rdi+18h]
0x14001894b  mov     [rbp+57h+var_40], rax
0x14001894f  mov     eax, [rdi]
0x140018951  mov     [rbp+57h+arg_18], eax
0x140018954  mov     rax, [rdi+80h]
0x14001895b  mov     [rbp+57h+var_38], rax
0x14001895f  mov     eax, [rdi+40h]
0x140018962  mov     [rbp+57h+var_70], eax
0x140018965  mov     rax, [rdi+38h]
0x140018969  mov     [rbp+57h+var_30], rax
0x14001896d  mov     eax, [rdi+8]
0x140018970  mov     [rbp+57h+var_6C], eax
0x140018973  mov     [rbp+57h+var_28], 1000000h
0x14001897b  mov     [rbp+57h+var_20], 0
0x140018983  mov     r8, [rbx+110h]
0x14001898a  add     r8, 8
0x14001898e  lea     rax, [rbp+57h+var_68]
0x140018992  mov     [rsp+110h+var_78], rax
0x14001899a  lea     rax, [rbp+57h+var_60]
0x14001899e  mov     [rsp+110h+var_80], rax
0x1400189a6  lea     rax, [rbp+57h+SRWLock]
0x1400189aa  mov     [rsp+110h+var_88], rax
0x1400189b2  lea     rax, [rbp+57h+var_58]
0x1400189b6  mov     [rsp+110h+var_90], rax
0x1400189be  lea     rax, [rbp+57h+var_50]
0x1400189c2  mov     [rsp+110h+var_98], rax
0x1400189c7  lea     rax, [rbp+57h+arg_8]
0x1400189cb  mov     [rsp+110h+var_A0], rax
0x1400189d0  lea     rax, [rbp+57h+var_48]
0x1400189d4  mov     [rsp+110h+var_A8], rax
0x1400189d9  lea     rax, [rbp+57h+arg_10]
0x1400189dd  mov     [rsp+110h+var_B0], rax
0x1400189e2  lea     rax, [rbp+57h+var_40]
0x1400189e6  mov     [rsp+110h+var_B8], rax
0x1400189eb  lea     rax, [rbp+57h+arg_18]
0x1400189ef  mov     [rsp+110h+var_C0], rax
0x1400189f4  lea     rax, [rbp+57h+var_38]
0x1400189f8  mov     [rsp+110h+var_C8], rax
0x1400189fd  lea     rax, [rbp+57h+var_70]
0x140018a01  mov     [rsp+110h+var_D0], rax
0x140018a06  lea     rax, [rbp+57h+var_30]
0x140018a0a  mov     [rsp+110h+var_D8], rax
0x140018a0f  lea     rax, [rbp+57h+var_6C]
0x140018a13  mov     [rsp+110h+var_E0], rax
0x140018a18  lea     rax, [rbp+57h+var_28]
0x140018a1c  mov     [rsp+110h+var_E8], rax
0x140018a21  lea     rax, [rbp+57h+var_20]
0x140018a25  mov     [rsp+110h+var_F0], rax
0x140018a2a  lea     rdx, byte_14006D8C7
0x140018a31  mov     rcx, r9
0x140018a34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140018a39  jmp     loc_140018AE2
0x140018a3e  lea     rdx, [rbp+57h+SRWLock]
0x140018a42  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140018a47  mov     rax, [rbx+110h]
0x140018a4e  mov     dword ptr [rax], 2
0x140018a54  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140018a58  test    rcx, rcx
0x140018a5b  jz      short loc_140018A63
0x140018a5d  call    cs:__imp_ReleaseSRWLockExclusive
0x140018a63  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140018a68  mov     rdi, rax
0x140018a6b  mov     ecx, [rax]
0x140018a6d  cmp     ecx, 5
0x140018a70  jbe     short loc_140018AE2
0x140018a72  mov     rax, [rax+18h]
0x140018a76  mov     rcx, [rdi+10h]
0x140018a7a  mov     rdx, 400000000000h
0x140018a84  test    rdx, rcx
0x140018a87  jz      short loc_140018AE2
0x140018a89  mov     rcx, rax
0x140018a8c  and     rcx, rdx
0x140018a8f  cmp     rcx, rax
0x140018a92  jnz     short loc_140018AE2
0x140018a94  call    cs:__imp_GetCurrentThreadId
0x140018a9a  mov     dword ptr [rbp+57h+SRWLock], eax
0x140018a9d  mov     r8, [rbx+110h]
0x140018aa4  mov     eax, [r8+48h]
0x140018aa8  mov     [rbp+57h+arg_8], eax
0x140018aab  mov     [rbp+57h+arg_10], 0
0x140018ab3  add     r8, 8
0x140018ab7  lea     rax, [rbp+57h+SRWLock]
0x140018abb  mov     [rsp+110h+var_E0], rax
0x140018ac0  lea     rax, [rbp+57h+arg_8]
0x140018ac4  mov     [rsp+110h+var_E8], rax
0x140018ac9  lea     rax, [rbp+57h+arg_10]
0x140018acd  mov     [rsp+110h+var_F0], rax
0x140018ad2  lea     rdx, word_14006D5CE
0x140018ad9  mov     rcx, rdi
0x140018adc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140018ae1  nop
0x140018ae2  lea     rcx, [rbx+120h]; this
0x140018ae9  cmp     dword ptr [rcx+18h], 0
0x140018aed  jz      short loc_140018AF5
0x140018aef  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140018af4  nop
0x140018af5  add     rsp, 100h
0x140018afc  pop     rdi
0x140018afd  pop     rbx
0x140018afe  pop     rbp
0x140018aff  retn
```
