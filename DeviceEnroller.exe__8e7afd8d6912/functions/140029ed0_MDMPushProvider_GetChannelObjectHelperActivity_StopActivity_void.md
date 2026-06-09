# MDMPushProvider::GetChannelObjectHelperActivity::StopActivity(void)

- ea: `0x140029ed0`
- end: `0x14002a14c`
- name: `?StopActivity@GetChannelObjectHelperActivity@MDMPushProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(MDMPushProvider::GetChannelObjectHelperActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x140029ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a0cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002a0cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a0e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002a0e0`

## pseudocode

```c
void __fastcall MDMPushProvider::GetChannelObjectHelperActivity::StopActivity(
        MDMPushProvider::GetChannelObjectHelperActivity *this)
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
        (__int64)&dword_14006ED9C,
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
        (__int64)&word_14006E9D6,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::GetChannelObjectHelperActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x140029ed0  push    rbp
0x140029ed2  push    rbx
0x140029ed3  push    rdi
0x140029ed4  lea     rbp, [rsp+10h]
0x140029ed9  sub     rsp, 130h
0x140029ee0  mov     rbx, rcx
0x140029ee3  mov     rdi, [rcx+110h]
0x140029eea  mov     eax, [rdi+48h]
0x140029eed  test    eax, eax
0x140029eef  jns     loc_14002A0AC
0x140029ef5  add     rdi, 50h ; 'P'
0x140029ef9  cmp     eax, [rdi+8]
0x140029efc  jnz     loc_14002A0AC
0x140029f02  test    rdi, rdi
0x140029f05  jz      loc_14002A0AC
0x140029f0b  lea     rdx, [rbp+SRWLock]
0x140029f0f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029f14  mov     rax, [rbx+110h]
0x140029f1b  mov     dword ptr [rax], 2
0x140029f21  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029f25  test    rcx, rcx
0x140029f28  jz      short loc_140029F30
0x140029f2a  call    cs:__imp_ReleaseSRWLockExclusive
0x140029f30  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029f35  mov     r9, rax
0x140029f38  mov     ecx, [rax]
0x140029f3a  cmp     ecx, 5
0x140029f3d  jbe     loc_14002A12E
0x140029f43  mov     rcx, [rdi+30h]
0x140029f47  mov     [rbp+var_70], rcx
0x140029f4b  mov     ecx, [rdi+44h]
0x140029f4e  mov     dword ptr [rbp+SRWLock], ecx
0x140029f51  mov     ecx, [rdi+10h]
0x140029f54  mov     [rbp+arg_8], ecx
0x140029f57  mov     rcx, [rdi+78h]
0x140029f5b  mov     [rbp+var_68], rcx
0x140029f5f  mov     rax, [rdi+70h]
0x140029f63  mov     [rbp+var_60], rax
0x140029f67  mov     eax, [rdi+68h]
0x140029f6a  mov     dword ptr [rbp+arg_10], eax
0x140029f6d  mov     rax, [rdi+60h]
0x140029f71  mov     [rbp+var_58], rax
0x140029f75  mov     rax, [rdi+58h]
0x140029f79  mov     [rbp+var_50], rax
0x140029f7d  mov     eax, [rdi+50h]
0x140029f80  mov     [rbp+arg_18], eax
0x140029f83  mov     rax, [rdi+48h]
0x140029f87  mov     [rbp+var_48], rax
0x140029f8b  mov     eax, [rdi+20h]
0x140029f8e  mov     [rbp+var_80], eax
0x140029f91  mov     rax, [rdi+18h]
0x140029f95  mov     [rbp+var_40], rax
0x140029f99  mov     eax, [rdi]
0x140029f9b  mov     [rbp+var_7C], eax
0x140029f9e  mov     rax, [rdi+80h]
0x140029fa5  mov     [rbp+var_38], rax
0x140029fa9  mov     eax, [rdi+40h]
0x140029fac  mov     [rbp+var_78], eax
0x140029faf  mov     rax, [rdi+38h]
0x140029fb3  mov     [rbp+var_30], rax
0x140029fb7  mov     eax, [rdi+8]
0x140029fba  mov     [rbp+var_74], eax
0x140029fbd  mov     [rbp+var_28], 1000000h
0x140029fc5  mov     [rbp+var_20], 0
0x140029fcd  mov     r8, [rbx+110h]
0x140029fd4  add     r8, 8
0x140029fd8  lea     rax, [rbp+var_70]
0x140029fdc  mov     [rsp+140h+var_90], rax
0x140029fe4  lea     rax, [rbp+SRWLock]
0x140029fe8  mov     [rsp+140h+var_98], rax
0x140029ff0  lea     rax, [rbp+arg_8]
0x140029ff4  mov     [rsp+140h+var_A0], rax
0x140029ffc  lea     rax, [rbp+var_68]
0x14002a000  mov     [rsp+140h+var_A8], rax
0x14002a008  lea     rax, [rbp+var_60]
0x14002a00c  mov     [rsp+140h+var_B0], rax
0x14002a014  lea     rax, [rbp+arg_10]
0x14002a018  mov     [rsp+140h+var_B8], rax
0x14002a020  lea     rax, [rbp+var_58]
0x14002a024  mov     [rsp+140h+var_C0], rax
0x14002a02c  lea     rax, [rbp+var_50]
0x14002a030  mov     [rsp+140h+var_C8], rax
0x14002a035  lea     rax, [rbp+arg_18]
0x14002a039  mov     [rsp+140h+var_D0], rax
0x14002a03e  lea     rax, [rbp+var_48]
0x14002a042  mov     [rsp+140h+var_D8], rax
0x14002a047  lea     rax, [rbp+var_80]
0x14002a04b  mov     [rsp+140h+var_E0], rax
0x14002a050  lea     rax, [rbp+var_40]
0x14002a054  mov     [rsp+140h+var_E8], rax
0x14002a059  lea     rax, [rbp+var_7C]
0x14002a05d  mov     [rsp+140h+var_F0], rax
0x14002a062  lea     rax, [rbp+var_38]
0x14002a066  mov     [rsp+140h+var_F8], rax
0x14002a06b  lea     rax, [rbp+var_78]
0x14002a06f  mov     [rsp+140h+var_100], rax
0x14002a074  lea     rax, [rbp+var_30]
0x14002a078  mov     [rsp+140h+var_108], rax
0x14002a07d  lea     rax, [rbp+var_74]
0x14002a081  mov     [rsp+140h+var_110], rax
0x14002a086  lea     rax, [rbp+var_28]
0x14002a08a  mov     [rsp+140h+var_118], rax
0x14002a08f  lea     rax, [rbp+var_20]
0x14002a093  mov     [rsp+140h+var_120], rax
0x14002a098  lea     rdx, dword_14006ED9C
0x14002a09f  mov     rcx, r9
0x14002a0a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002a0a7  jmp     loc_14002A12E
0x14002a0ac  lea     rdx, [rbp+SRWLock]
0x14002a0b0  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002a0b5  mov     rax, [rbx+110h]
0x14002a0bc  mov     dword ptr [rax], 2
0x14002a0c2  mov     rcx, [rbp+SRWLock]; SRWLock
0x14002a0c6  test    rcx, rcx
0x14002a0c9  jz      short loc_14002A0D1
0x14002a0cb  call    cs:__imp_ReleaseSRWLockExclusive
0x14002a0d1  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14002a0d6  mov     rdi, rax
0x14002a0d9  mov     ecx, [rax]
0x14002a0db  cmp     ecx, 5
0x14002a0de  jbe     short loc_14002A12E
0x14002a0e0  call    cs:__imp_GetCurrentThreadId
0x14002a0e6  mov     dword ptr [rbp+SRWLock], eax
0x14002a0e9  mov     r8, [rbx+110h]
0x14002a0f0  mov     ecx, [r8+48h]
0x14002a0f4  mov     [rbp+arg_8], ecx
0x14002a0f7  mov     [rbp+arg_10], 0
0x14002a0ff  add     r8, 8
0x14002a103  lea     rax, [rbp+SRWLock]
0x14002a107  mov     [rsp+140h+var_110], rax
0x14002a10c  lea     rax, [rbp+arg_8]
0x14002a110  mov     [rsp+140h+var_118], rax
0x14002a115  lea     rax, [rbp+arg_10]
0x14002a119  mov     [rsp+140h+var_120], rax
0x14002a11e  lea     rdx, word_14006E9D6
0x14002a125  mov     rcx, rdi
0x14002a128  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002a12d  nop
0x14002a12e  lea     rcx, [rbx+120h]; this
0x14002a135  cmp     dword ptr [rcx+18h], 0
0x14002a139  jz      short loc_14002A141
0x14002a13b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14002a140  nop
0x14002a141  add     rsp, 130h
0x14002a148  pop     rdi
0x14002a149  pop     rbx
0x14002a14a  pop     rbp
0x14002a14b  retn
```
