# MDMPushProvider::InitializeActivity::StopActivity(void)

- ea: `0x14002a160`
- end: `0x14002a3dc`
- name: `?StopActivity@InitializeActivity@MDMPushProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x14002a160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a35b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a35b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a370`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StopActivity(MDMPushProvider::InitializeActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const OLECHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const OLECHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const OLECHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

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
    if ( *(_DWORD *)v5 > 5u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const OLECHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const OLECHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const OLECHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&byte_14006E5DF,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
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
    v6 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)byte_14006E533,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::InitializeActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14002a160  push    rbp
0x14002a162  push    rbx
0x14002a163  push    rdi
0x14002a164  lea     rbp, [rsp+10h]
0x14002a169  sub     rsp, 130h
0x14002a170  mov     rbx, rcx
0x14002a173  mov     rdi, [rcx+110h]
0x14002a17a  mov     eax, [rdi+48h]
0x14002a17d  test    eax, eax
0x14002a17f  jns     loc_14002A33C
0x14002a185  add     rdi, 50h ; 'P'
0x14002a189  cmp     eax, [rdi+8]
0x14002a18c  jnz     loc_14002A33C
0x14002a192  test    rdi, rdi
0x14002a195  jz      loc_14002A33C
0x14002a19b  lea     rdx, [rbp+SRWLock]
0x14002a19f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002a1a4  mov     rax, [rbx+110h]
0x14002a1ab  mov     dword ptr [rax], 2
0x14002a1b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x14002a1b5  test    rcx, rcx
0x14002a1b8  jz      short loc_14002A1C0
0x14002a1ba  call    cs:__imp_ReleaseSRWLockExclusive
0x14002a1c0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14002a1c5  mov     r9, rax
0x14002a1c8  mov     ecx, [rax]
0x14002a1ca  cmp     ecx, 5
0x14002a1cd  jbe     loc_14002A3BE
0x14002a1d3  mov     rcx, [rdi+30h]
0x14002a1d7  mov     [rbp+var_70], rcx
0x14002a1db  mov     ecx, [rdi+44h]
0x14002a1de  mov     dword ptr [rbp+SRWLock], ecx
0x14002a1e1  mov     ecx, [rdi+10h]
0x14002a1e4  mov     [rbp+arg_8], ecx
0x14002a1e7  mov     rcx, [rdi+78h]
0x14002a1eb  mov     [rbp+var_68], rcx
0x14002a1ef  mov     rax, [rdi+70h]
0x14002a1f3  mov     [rbp+var_60], rax
0x14002a1f7  mov     eax, [rdi+68h]
0x14002a1fa  mov     dword ptr [rbp+arg_10], eax
0x14002a1fd  mov     rax, [rdi+60h]
0x14002a201  mov     [rbp+var_58], rax
0x14002a205  mov     rax, [rdi+58h]
0x14002a209  mov     [rbp+var_50], rax
0x14002a20d  mov     eax, [rdi+50h]
0x14002a210  mov     [rbp+arg_18], eax
0x14002a213  mov     rax, [rdi+48h]
0x14002a217  mov     [rbp+var_48], rax
0x14002a21b  mov     eax, [rdi+20h]
0x14002a21e  mov     [rbp+var_80], eax
0x14002a221  mov     rax, [rdi+18h]
0x14002a225  mov     [rbp+var_40], rax
0x14002a229  mov     eax, [rdi]
0x14002a22b  mov     [rbp+var_7C], eax
0x14002a22e  mov     rax, [rdi+80h]
0x14002a235  mov     [rbp+var_38], rax
0x14002a239  mov     eax, [rdi+40h]
0x14002a23c  mov     [rbp+var_78], eax
0x14002a23f  mov     rax, [rdi+38h]
0x14002a243  mov     [rbp+var_30], rax
0x14002a247  mov     eax, [rdi+8]
0x14002a24a  mov     [rbp+var_74], eax
0x14002a24d  mov     [rbp+var_28], 1000000h
0x14002a255  mov     [rbp+var_20], 0
0x14002a25d  mov     r8, [rbx+110h]
0x14002a264  add     r8, 8
0x14002a268  lea     rax, [rbp+var_70]
0x14002a26c  mov     [rsp+140h+var_90], rax
0x14002a274  lea     rax, [rbp+SRWLock]
0x14002a278  mov     [rsp+140h+var_98], rax
0x14002a280  lea     rax, [rbp+arg_8]
0x14002a284  mov     [rsp+140h+var_A0], rax
0x14002a28c  lea     rax, [rbp+var_68]
0x14002a290  mov     [rsp+140h+var_A8], rax
0x14002a298  lea     rax, [rbp+var_60]
0x14002a29c  mov     [rsp+140h+var_B0], rax
0x14002a2a4  lea     rax, [rbp+arg_10]
0x14002a2a8  mov     [rsp+140h+var_B8], rax
0x14002a2b0  lea     rax, [rbp+var_58]
0x14002a2b4  mov     [rsp+140h+var_C0], rax
0x14002a2bc  lea     rax, [rbp+var_50]
0x14002a2c0  mov     [rsp+140h+var_C8], rax
0x14002a2c5  lea     rax, [rbp+arg_18]
0x14002a2c9  mov     [rsp+140h+var_D0], rax
0x14002a2ce  lea     rax, [rbp+var_48]
0x14002a2d2  mov     [rsp+140h+var_D8], rax
0x14002a2d7  lea     rax, [rbp+var_80]
0x14002a2db  mov     [rsp+140h+var_E0], rax
0x14002a2e0  lea     rax, [rbp+var_40]
0x14002a2e4  mov     [rsp+140h+var_E8], rax
0x14002a2e9  lea     rax, [rbp+var_7C]
0x14002a2ed  mov     [rsp+140h+var_F0], rax
0x14002a2f2  lea     rax, [rbp+var_38]
0x14002a2f6  mov     [rsp+140h+var_F8], rax
0x14002a2fb  lea     rax, [rbp+var_78]
0x14002a2ff  mov     [rsp+140h+var_100], rax
0x14002a304  lea     rax, [rbp+var_30]
0x14002a308  mov     [rsp+140h+var_108], rax
0x14002a30d  lea     rax, [rbp+var_74]
0x14002a311  mov     [rsp+140h+var_110], rax
0x14002a316  lea     rax, [rbp+var_28]
0x14002a31a  mov     [rsp+140h+var_118], rax
0x14002a31f  lea     rax, [rbp+var_20]
0x14002a323  mov     [rsp+140h+var_120], rax
0x14002a328  lea     rdx, byte_14006E5DF
0x14002a32f  mov     rcx, r9
0x14002a332  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002a337  jmp     loc_14002A3BE
0x14002a33c  lea     rdx, [rbp+SRWLock]
0x14002a340  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002a345  mov     rax, [rbx+110h]
0x14002a34c  mov     dword ptr [rax], 2
0x14002a352  mov     rcx, [rbp+SRWLock]; SRWLock
0x14002a356  test    rcx, rcx
0x14002a359  jz      short loc_14002A361
0x14002a35b  call    cs:__imp_ReleaseSRWLockExclusive
0x14002a361  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14002a366  mov     rdi, rax
0x14002a369  mov     ecx, [rax]
0x14002a36b  cmp     ecx, 5
0x14002a36e  jbe     short loc_14002A3BE
0x14002a370  call    cs:__imp_GetCurrentThreadId
0x14002a376  mov     dword ptr [rbp+SRWLock], eax
0x14002a379  mov     r8, [rbx+110h]
0x14002a380  mov     ecx, [r8+48h]
0x14002a384  mov     [rbp+arg_8], ecx
0x14002a387  mov     [rbp+arg_10], 0
0x14002a38f  add     r8, 8
0x14002a393  lea     rax, [rbp+SRWLock]
0x14002a397  mov     [rsp+140h+var_110], rax
0x14002a39c  lea     rax, [rbp+arg_8]
0x14002a3a0  mov     [rsp+140h+var_118], rax
0x14002a3a5  lea     rax, [rbp+arg_10]
0x14002a3a9  mov     [rsp+140h+var_120], rax
0x14002a3ae  lea     rdx, byte_14006E533
0x14002a3b5  mov     rcx, rdi
0x14002a3b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002a3bd  nop
0x14002a3be  lea     rcx, [rbx+120h]; this
0x14002a3c5  cmp     dword ptr [rcx+18h], 0
0x14002a3c9  jz      short loc_14002A3D1
0x14002a3cb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14002a3d0  nop
0x14002a3d1  add     rsp, 130h
0x14002a3d8  pop     rdi
0x14002a3d9  pop     rbx
0x14002a3da  pop     rbp
0x14002a3db  retn
```
