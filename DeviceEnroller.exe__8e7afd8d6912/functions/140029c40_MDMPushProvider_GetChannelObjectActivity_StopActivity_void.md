# MDMPushProvider::GetChannelObjectActivity::StopActivity(void)

- ea: `0x140029c40`
- end: `0x140029ebc`
- name: `?StopActivity@GetChannelObjectActivity@MDMPushProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(MDMPushProvider::GetChannelObjectActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x140029c40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029e3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029c9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029e50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029e50`

## pseudocode

```c
void __fastcall MDMPushProvider::GetChannelObjectActivity::StopActivity(
        MDMPushProvider::GetChannelObjectActivity *this)
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
        (__int64)&dword_14006E284,
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
        (__int64)&byte_14006EFA7,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::GetChannelObjectActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140029c40  push    rbp
0x140029c42  push    rbx
0x140029c43  push    rdi
0x140029c44  lea     rbp, [rsp+10h]
0x140029c49  sub     rsp, 130h
0x140029c50  mov     rbx, rcx
0x140029c53  mov     rdi, [rcx+110h]
0x140029c5a  mov     eax, [rdi+48h]
0x140029c5d  test    eax, eax
0x140029c5f  jns     loc_140029E1C
0x140029c65  add     rdi, 50h ; 'P'
0x140029c69  cmp     eax, [rdi+8]
0x140029c6c  jnz     loc_140029E1C
0x140029c72  test    rdi, rdi
0x140029c75  jz      loc_140029E1C
0x140029c7b  lea     rdx, [rbp+SRWLock]
0x140029c7f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029c84  mov     rax, [rbx+110h]
0x140029c8b  mov     dword ptr [rax], 2
0x140029c91  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029c95  test    rcx, rcx
0x140029c98  jz      short loc_140029CA0
0x140029c9a  call    cs:__imp_ReleaseSRWLockExclusive
0x140029ca0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029ca5  mov     r9, rax
0x140029ca8  mov     ecx, [rax]
0x140029caa  cmp     ecx, 5
0x140029cad  jbe     loc_140029E9E
0x140029cb3  mov     rcx, [rdi+30h]
0x140029cb7  mov     [rbp+var_70], rcx
0x140029cbb  mov     ecx, [rdi+44h]
0x140029cbe  mov     dword ptr [rbp+SRWLock], ecx
0x140029cc1  mov     ecx, [rdi+10h]
0x140029cc4  mov     [rbp+arg_8], ecx
0x140029cc7  mov     rcx, [rdi+78h]
0x140029ccb  mov     [rbp+var_68], rcx
0x140029ccf  mov     rax, [rdi+70h]
0x140029cd3  mov     [rbp+var_60], rax
0x140029cd7  mov     eax, [rdi+68h]
0x140029cda  mov     dword ptr [rbp+arg_10], eax
0x140029cdd  mov     rax, [rdi+60h]
0x140029ce1  mov     [rbp+var_58], rax
0x140029ce5  mov     rax, [rdi+58h]
0x140029ce9  mov     [rbp+var_50], rax
0x140029ced  mov     eax, [rdi+50h]
0x140029cf0  mov     [rbp+arg_18], eax
0x140029cf3  mov     rax, [rdi+48h]
0x140029cf7  mov     [rbp+var_48], rax
0x140029cfb  mov     eax, [rdi+20h]
0x140029cfe  mov     [rbp+var_80], eax
0x140029d01  mov     rax, [rdi+18h]
0x140029d05  mov     [rbp+var_40], rax
0x140029d09  mov     eax, [rdi]
0x140029d0b  mov     [rbp+var_7C], eax
0x140029d0e  mov     rax, [rdi+80h]
0x140029d15  mov     [rbp+var_38], rax
0x140029d19  mov     eax, [rdi+40h]
0x140029d1c  mov     [rbp+var_78], eax
0x140029d1f  mov     rax, [rdi+38h]
0x140029d23  mov     [rbp+var_30], rax
0x140029d27  mov     eax, [rdi+8]
0x140029d2a  mov     [rbp+var_74], eax
0x140029d2d  mov     [rbp+var_28], 1000000h
0x140029d35  mov     [rbp+var_20], 0
0x140029d3d  mov     r8, [rbx+110h]
0x140029d44  add     r8, 8
0x140029d48  lea     rax, [rbp+var_70]
0x140029d4c  mov     [rsp+140h+var_90], rax
0x140029d54  lea     rax, [rbp+SRWLock]
0x140029d58  mov     [rsp+140h+var_98], rax
0x140029d60  lea     rax, [rbp+arg_8]
0x140029d64  mov     [rsp+140h+var_A0], rax
0x140029d6c  lea     rax, [rbp+var_68]
0x140029d70  mov     [rsp+140h+var_A8], rax
0x140029d78  lea     rax, [rbp+var_60]
0x140029d7c  mov     [rsp+140h+var_B0], rax
0x140029d84  lea     rax, [rbp+arg_10]
0x140029d88  mov     [rsp+140h+var_B8], rax
0x140029d90  lea     rax, [rbp+var_58]
0x140029d94  mov     [rsp+140h+var_C0], rax
0x140029d9c  lea     rax, [rbp+var_50]
0x140029da0  mov     [rsp+140h+var_C8], rax
0x140029da5  lea     rax, [rbp+arg_18]
0x140029da9  mov     [rsp+140h+var_D0], rax
0x140029dae  lea     rax, [rbp+var_48]
0x140029db2  mov     [rsp+140h+var_D8], rax
0x140029db7  lea     rax, [rbp+var_80]
0x140029dbb  mov     [rsp+140h+var_E0], rax
0x140029dc0  lea     rax, [rbp+var_40]
0x140029dc4  mov     [rsp+140h+var_E8], rax
0x140029dc9  lea     rax, [rbp+var_7C]
0x140029dcd  mov     [rsp+140h+var_F0], rax
0x140029dd2  lea     rax, [rbp+var_38]
0x140029dd6  mov     [rsp+140h+var_F8], rax
0x140029ddb  lea     rax, [rbp+var_78]
0x140029ddf  mov     [rsp+140h+var_100], rax
0x140029de4  lea     rax, [rbp+var_30]
0x140029de8  mov     [rsp+140h+var_108], rax
0x140029ded  lea     rax, [rbp+var_74]
0x140029df1  mov     [rsp+140h+var_110], rax
0x140029df6  lea     rax, [rbp+var_28]
0x140029dfa  mov     [rsp+140h+var_118], rax
0x140029dff  lea     rax, [rbp+var_20]
0x140029e03  mov     [rsp+140h+var_120], rax
0x140029e08  lea     rdx, dword_14006E284
0x140029e0f  mov     rcx, r9
0x140029e12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140029e17  jmp     loc_140029E9E
0x140029e1c  lea     rdx, [rbp+SRWLock]
0x140029e20  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029e25  mov     rax, [rbx+110h]
0x140029e2c  mov     dword ptr [rax], 2
0x140029e32  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029e36  test    rcx, rcx
0x140029e39  jz      short loc_140029E41
0x140029e3b  call    cs:__imp_ReleaseSRWLockExclusive
0x140029e41  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029e46  mov     rdi, rax
0x140029e49  mov     ecx, [rax]
0x140029e4b  cmp     ecx, 5
0x140029e4e  jbe     short loc_140029E9E
0x140029e50  call    cs:__imp_GetCurrentThreadId
0x140029e56  mov     dword ptr [rbp+SRWLock], eax
0x140029e59  mov     r8, [rbx+110h]
0x140029e60  mov     ecx, [r8+48h]
0x140029e64  mov     [rbp+arg_8], ecx
0x140029e67  mov     [rbp+arg_10], 0
0x140029e6f  add     r8, 8
0x140029e73  lea     rax, [rbp+SRWLock]
0x140029e77  mov     [rsp+140h+var_110], rax
0x140029e7c  lea     rax, [rbp+arg_8]
0x140029e80  mov     [rsp+140h+var_118], rax
0x140029e85  lea     rax, [rbp+arg_10]
0x140029e89  mov     [rsp+140h+var_120], rax
0x140029e8e  lea     rdx, byte_14006EFA7
0x140029e95  mov     rcx, rdi
0x140029e98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140029e9d  nop
0x140029e9e  lea     rcx, [rbx+120h]; this
0x140029ea5  cmp     dword ptr [rcx+18h], 0
0x140029ea9  jz      short loc_140029EB1
0x140029eab  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140029eb0  nop
0x140029eb1  add     rsp, 130h
0x140029eb8  pop     rdi
0x140029eb9  pop     rbx
0x140029eba  pop     rbp
0x140029ebb  retn
```
