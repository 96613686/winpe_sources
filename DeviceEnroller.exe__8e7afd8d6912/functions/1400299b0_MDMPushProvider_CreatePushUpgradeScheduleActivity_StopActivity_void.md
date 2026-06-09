# MDMPushProvider::CreatePushUpgradeScheduleActivity::StopActivity(void)

- ea: `0x1400299b0`
- end: `0x140029c2c`
- name: `?StopActivity@CreatePushUpgradeScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x140018b08`
- `0x1400299b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029a0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029bab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029a0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140029bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029bc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029bc0`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
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
        (__int64)&byte_14006E3D7,
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
        (__int64)byte_14006EF45,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::CreatePushUpgradeScheduleActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400299b0  push    rbp
0x1400299b2  push    rbx
0x1400299b3  push    rdi
0x1400299b4  lea     rbp, [rsp+10h]
0x1400299b9  sub     rsp, 130h
0x1400299c0  mov     rbx, rcx
0x1400299c3  mov     rdi, [rcx+110h]
0x1400299ca  mov     eax, [rdi+48h]
0x1400299cd  test    eax, eax
0x1400299cf  jns     loc_140029B8C
0x1400299d5  add     rdi, 50h ; 'P'
0x1400299d9  cmp     eax, [rdi+8]
0x1400299dc  jnz     loc_140029B8C
0x1400299e2  test    rdi, rdi
0x1400299e5  jz      loc_140029B8C
0x1400299eb  lea     rdx, [rbp+SRWLock]
0x1400299ef  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400299f4  mov     rax, [rbx+110h]
0x1400299fb  mov     dword ptr [rax], 2
0x140029a01  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029a05  test    rcx, rcx
0x140029a08  jz      short loc_140029A10
0x140029a0a  call    cs:__imp_ReleaseSRWLockExclusive
0x140029a10  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029a15  mov     r9, rax
0x140029a18  mov     ecx, [rax]
0x140029a1a  cmp     ecx, 5
0x140029a1d  jbe     loc_140029C0E
0x140029a23  mov     rcx, [rdi+30h]
0x140029a27  mov     [rbp+var_70], rcx
0x140029a2b  mov     ecx, [rdi+44h]
0x140029a2e  mov     dword ptr [rbp+SRWLock], ecx
0x140029a31  mov     ecx, [rdi+10h]
0x140029a34  mov     [rbp+arg_8], ecx
0x140029a37  mov     rcx, [rdi+78h]
0x140029a3b  mov     [rbp+var_68], rcx
0x140029a3f  mov     rax, [rdi+70h]
0x140029a43  mov     [rbp+var_60], rax
0x140029a47  mov     eax, [rdi+68h]
0x140029a4a  mov     dword ptr [rbp+arg_10], eax
0x140029a4d  mov     rax, [rdi+60h]
0x140029a51  mov     [rbp+var_58], rax
0x140029a55  mov     rax, [rdi+58h]
0x140029a59  mov     [rbp+var_50], rax
0x140029a5d  mov     eax, [rdi+50h]
0x140029a60  mov     [rbp+arg_18], eax
0x140029a63  mov     rax, [rdi+48h]
0x140029a67  mov     [rbp+var_48], rax
0x140029a6b  mov     eax, [rdi+20h]
0x140029a6e  mov     [rbp+var_80], eax
0x140029a71  mov     rax, [rdi+18h]
0x140029a75  mov     [rbp+var_40], rax
0x140029a79  mov     eax, [rdi]
0x140029a7b  mov     [rbp+var_7C], eax
0x140029a7e  mov     rax, [rdi+80h]
0x140029a85  mov     [rbp+var_38], rax
0x140029a89  mov     eax, [rdi+40h]
0x140029a8c  mov     [rbp+var_78], eax
0x140029a8f  mov     rax, [rdi+38h]
0x140029a93  mov     [rbp+var_30], rax
0x140029a97  mov     eax, [rdi+8]
0x140029a9a  mov     [rbp+var_74], eax
0x140029a9d  mov     [rbp+var_28], 1000000h
0x140029aa5  mov     [rbp+var_20], 0
0x140029aad  mov     r8, [rbx+110h]
0x140029ab4  add     r8, 8
0x140029ab8  lea     rax, [rbp+var_70]
0x140029abc  mov     [rsp+140h+var_90], rax
0x140029ac4  lea     rax, [rbp+SRWLock]
0x140029ac8  mov     [rsp+140h+var_98], rax
0x140029ad0  lea     rax, [rbp+arg_8]
0x140029ad4  mov     [rsp+140h+var_A0], rax
0x140029adc  lea     rax, [rbp+var_68]
0x140029ae0  mov     [rsp+140h+var_A8], rax
0x140029ae8  lea     rax, [rbp+var_60]
0x140029aec  mov     [rsp+140h+var_B0], rax
0x140029af4  lea     rax, [rbp+arg_10]
0x140029af8  mov     [rsp+140h+var_B8], rax
0x140029b00  lea     rax, [rbp+var_58]
0x140029b04  mov     [rsp+140h+var_C0], rax
0x140029b0c  lea     rax, [rbp+var_50]
0x140029b10  mov     [rsp+140h+var_C8], rax
0x140029b15  lea     rax, [rbp+arg_18]
0x140029b19  mov     [rsp+140h+var_D0], rax
0x140029b1e  lea     rax, [rbp+var_48]
0x140029b22  mov     [rsp+140h+var_D8], rax
0x140029b27  lea     rax, [rbp+var_80]
0x140029b2b  mov     [rsp+140h+var_E0], rax
0x140029b30  lea     rax, [rbp+var_40]
0x140029b34  mov     [rsp+140h+var_E8], rax
0x140029b39  lea     rax, [rbp+var_7C]
0x140029b3d  mov     [rsp+140h+var_F0], rax
0x140029b42  lea     rax, [rbp+var_38]
0x140029b46  mov     [rsp+140h+var_F8], rax
0x140029b4b  lea     rax, [rbp+var_78]
0x140029b4f  mov     [rsp+140h+var_100], rax
0x140029b54  lea     rax, [rbp+var_30]
0x140029b58  mov     [rsp+140h+var_108], rax
0x140029b5d  lea     rax, [rbp+var_74]
0x140029b61  mov     [rsp+140h+var_110], rax
0x140029b66  lea     rax, [rbp+var_28]
0x140029b6a  mov     [rsp+140h+var_118], rax
0x140029b6f  lea     rax, [rbp+var_20]
0x140029b73  mov     [rsp+140h+var_120], rax
0x140029b78  lea     rdx, byte_14006E3D7
0x140029b7f  mov     rcx, r9
0x140029b82  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140029b87  jmp     loc_140029C0E
0x140029b8c  lea     rdx, [rbp+SRWLock]
0x140029b90  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029b95  mov     rax, [rbx+110h]
0x140029b9c  mov     dword ptr [rax], 2
0x140029ba2  mov     rcx, [rbp+SRWLock]; SRWLock
0x140029ba6  test    rcx, rcx
0x140029ba9  jz      short loc_140029BB1
0x140029bab  call    cs:__imp_ReleaseSRWLockExclusive
0x140029bb1  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140029bb6  mov     rdi, rax
0x140029bb9  mov     ecx, [rax]
0x140029bbb  cmp     ecx, 5
0x140029bbe  jbe     short loc_140029C0E
0x140029bc0  call    cs:__imp_GetCurrentThreadId
0x140029bc6  mov     dword ptr [rbp+SRWLock], eax
0x140029bc9  mov     r8, [rbx+110h]
0x140029bd0  mov     ecx, [r8+48h]
0x140029bd4  mov     [rbp+arg_8], ecx
0x140029bd7  mov     [rbp+arg_10], 0
0x140029bdf  add     r8, 8
0x140029be3  lea     rax, [rbp+SRWLock]
0x140029be7  mov     [rsp+140h+var_110], rax
0x140029bec  lea     rax, [rbp+arg_8]
0x140029bf0  mov     [rsp+140h+var_118], rax
0x140029bf5  lea     rax, [rbp+arg_10]
0x140029bf9  mov     [rsp+140h+var_120], rax
0x140029bfe  lea     rdx, byte_14006EF45
0x140029c05  mov     rcx, rdi
0x140029c08  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140029c0d  nop
0x140029c0e  lea     rcx, [rbx+120h]; this
0x140029c15  cmp     dword ptr [rcx+18h], 0
0x140029c19  jz      short loc_140029C21
0x140029c1b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140029c20  nop
0x140029c21  add     rsp, 130h
0x140029c28  pop     rdi
0x140029c29  pop     rbx
0x140029c2a  pop     rbp
0x140029c2b  retn
```
