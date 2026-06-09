# DynamicManagementProvider::GetAlertDataActivity::StopActivity(void)

- ea: `0x14003c560`
- end: `0x14003c7dc`
- name: `?StopActivity@GetAlertDataActivity@DynamicManagementProvider@@MEAAXXZ`
- size: `636`
- prototype: `void __fastcall(DynamicManagementProvider::GetAlertDataActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001430`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14003abc4`
- `0x14003c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c5ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c75b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c5ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c75b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003c770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003c770`

## pseudocode

```c
void __fastcall DynamicManagementProvider::GetAlertDataActivity::StopActivity(
        DynamicManagementProvider::GetAlertDataActivity *this)
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
    v5 = DynamoProvider::Provider();
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
        (__int64)&unk_140070978,
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
    v6 = DynamoProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&dword_140070184,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((DynamicManagementProvider::GetAlertDataActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003c560  push    rbp
0x14003c562  push    rbx
0x14003c563  push    rdi
0x14003c564  lea     rbp, [rsp+10h]
0x14003c569  sub     rsp, 130h
0x14003c570  mov     rbx, rcx
0x14003c573  mov     rdi, [rcx+110h]
0x14003c57a  mov     eax, [rdi+48h]
0x14003c57d  test    eax, eax
0x14003c57f  jns     loc_14003C73C
0x14003c585  add     rdi, 50h ; 'P'
0x14003c589  cmp     eax, [rdi+8]
0x14003c58c  jnz     loc_14003C73C
0x14003c592  test    rdi, rdi
0x14003c595  jz      loc_14003C73C
0x14003c59b  lea     rdx, [rbp+SRWLock]
0x14003c59f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003c5a4  mov     rax, [rbx+110h]
0x14003c5ab  mov     dword ptr [rax], 2
0x14003c5b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x14003c5b5  test    rcx, rcx
0x14003c5b8  jz      short loc_14003C5C0
0x14003c5ba  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c5c0  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003c5c5  mov     r9, rax
0x14003c5c8  mov     ecx, [rax]
0x14003c5ca  cmp     ecx, 5
0x14003c5cd  jbe     loc_14003C7BE
0x14003c5d3  mov     rcx, [rdi+30h]
0x14003c5d7  mov     [rbp+var_70], rcx
0x14003c5db  mov     ecx, [rdi+44h]
0x14003c5de  mov     dword ptr [rbp+SRWLock], ecx
0x14003c5e1  mov     ecx, [rdi+10h]
0x14003c5e4  mov     [rbp+arg_8], ecx
0x14003c5e7  mov     rcx, [rdi+78h]
0x14003c5eb  mov     [rbp+var_68], rcx
0x14003c5ef  mov     rax, [rdi+70h]
0x14003c5f3  mov     [rbp+var_60], rax
0x14003c5f7  mov     eax, [rdi+68h]
0x14003c5fa  mov     dword ptr [rbp+arg_10], eax
0x14003c5fd  mov     rax, [rdi+60h]
0x14003c601  mov     [rbp+var_58], rax
0x14003c605  mov     rax, [rdi+58h]
0x14003c609  mov     [rbp+var_50], rax
0x14003c60d  mov     eax, [rdi+50h]
0x14003c610  mov     [rbp+arg_18], eax
0x14003c613  mov     rax, [rdi+48h]
0x14003c617  mov     [rbp+var_48], rax
0x14003c61b  mov     eax, [rdi+20h]
0x14003c61e  mov     [rbp+var_80], eax
0x14003c621  mov     rax, [rdi+18h]
0x14003c625  mov     [rbp+var_40], rax
0x14003c629  mov     eax, [rdi]
0x14003c62b  mov     [rbp+var_7C], eax
0x14003c62e  mov     rax, [rdi+80h]
0x14003c635  mov     [rbp+var_38], rax
0x14003c639  mov     eax, [rdi+40h]
0x14003c63c  mov     [rbp+var_78], eax
0x14003c63f  mov     rax, [rdi+38h]
0x14003c643  mov     [rbp+var_30], rax
0x14003c647  mov     eax, [rdi+8]
0x14003c64a  mov     [rbp+var_74], eax
0x14003c64d  mov     [rbp+var_28], 1000000h
0x14003c655  mov     [rbp+var_20], 0
0x14003c65d  mov     r8, [rbx+110h]
0x14003c664  add     r8, 8
0x14003c668  lea     rax, [rbp+var_70]
0x14003c66c  mov     [rsp+140h+var_90], rax
0x14003c674  lea     rax, [rbp+SRWLock]
0x14003c678  mov     [rsp+140h+var_98], rax
0x14003c680  lea     rax, [rbp+arg_8]
0x14003c684  mov     [rsp+140h+var_A0], rax
0x14003c68c  lea     rax, [rbp+var_68]
0x14003c690  mov     [rsp+140h+var_A8], rax
0x14003c698  lea     rax, [rbp+var_60]
0x14003c69c  mov     [rsp+140h+var_B0], rax
0x14003c6a4  lea     rax, [rbp+arg_10]
0x14003c6a8  mov     [rsp+140h+var_B8], rax
0x14003c6b0  lea     rax, [rbp+var_58]
0x14003c6b4  mov     [rsp+140h+var_C0], rax
0x14003c6bc  lea     rax, [rbp+var_50]
0x14003c6c0  mov     [rsp+140h+var_C8], rax
0x14003c6c5  lea     rax, [rbp+arg_18]
0x14003c6c9  mov     [rsp+140h+var_D0], rax
0x14003c6ce  lea     rax, [rbp+var_48]
0x14003c6d2  mov     [rsp+140h+var_D8], rax
0x14003c6d7  lea     rax, [rbp+var_80]
0x14003c6db  mov     [rsp+140h+var_E0], rax
0x14003c6e0  lea     rax, [rbp+var_40]
0x14003c6e4  mov     [rsp+140h+var_E8], rax
0x14003c6e9  lea     rax, [rbp+var_7C]
0x14003c6ed  mov     [rsp+140h+var_F0], rax
0x14003c6f2  lea     rax, [rbp+var_38]
0x14003c6f6  mov     [rsp+140h+var_F8], rax
0x14003c6fb  lea     rax, [rbp+var_78]
0x14003c6ff  mov     [rsp+140h+var_100], rax
0x14003c704  lea     rax, [rbp+var_30]
0x14003c708  mov     [rsp+140h+var_108], rax
0x14003c70d  lea     rax, [rbp+var_74]
0x14003c711  mov     [rsp+140h+var_110], rax
0x14003c716  lea     rax, [rbp+var_28]
0x14003c71a  mov     [rsp+140h+var_118], rax
0x14003c71f  lea     rax, [rbp+var_20]
0x14003c723  mov     [rsp+140h+var_120], rax
0x14003c728  lea     rdx, unk_140070978
0x14003c72f  mov     rcx, r9
0x14003c732  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003c737  jmp     loc_14003C7BE
0x14003c73c  lea     rdx, [rbp+SRWLock]
0x14003c740  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003c745  mov     rax, [rbx+110h]
0x14003c74c  mov     dword ptr [rax], 2
0x14003c752  mov     rcx, [rbp+SRWLock]; SRWLock
0x14003c756  test    rcx, rcx
0x14003c759  jz      short loc_14003C761
0x14003c75b  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c761  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003c766  mov     rdi, rax
0x14003c769  mov     ecx, [rax]
0x14003c76b  cmp     ecx, 5
0x14003c76e  jbe     short loc_14003C7BE
0x14003c770  call    cs:__imp_GetCurrentThreadId
0x14003c776  mov     dword ptr [rbp+SRWLock], eax
0x14003c779  mov     r8, [rbx+110h]
0x14003c780  mov     ecx, [r8+48h]
0x14003c784  mov     [rbp+arg_8], ecx
0x14003c787  mov     [rbp+arg_10], 0
0x14003c78f  add     r8, 8
0x14003c793  lea     rax, [rbp+SRWLock]
0x14003c797  mov     [rsp+140h+var_110], rax
0x14003c79c  lea     rax, [rbp+arg_8]
0x14003c7a0  mov     [rsp+140h+var_118], rax
0x14003c7a5  lea     rax, [rbp+arg_10]
0x14003c7a9  mov     [rsp+140h+var_120], rax
0x14003c7ae  lea     rdx, dword_140070184
0x14003c7b5  mov     rcx, rdi
0x14003c7b8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003c7bd  nop
0x14003c7be  lea     rcx, [rbx+120h]; this
0x14003c7c5  cmp     dword ptr [rcx+18h], 0
0x14003c7c9  jz      short loc_14003C7D1
0x14003c7cb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003c7d0  nop
0x14003c7d1  add     rsp, 130h
0x14003c7d8  pop     rdi
0x14003c7d9  pop     rbx
0x14003c7da  pop     rbp
0x14003c7db  retn
```
