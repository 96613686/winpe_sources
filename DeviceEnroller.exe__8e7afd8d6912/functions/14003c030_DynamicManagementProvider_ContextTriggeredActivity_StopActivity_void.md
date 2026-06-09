# DynamicManagementProvider::ContextTriggeredActivity::StopActivity(void)

- ea: `0x14003c030`
- end: `0x14003c2c0`
- name: `?StopActivity@ContextTriggeredActivity@DynamicManagementProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(DynamicManagementProvider::ContextTriggeredActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14003abc4`
- `0x14003c030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c21d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c21d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003c254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003c254`

## pseudocode

```c
void __fastcall DynamicManagementProvider::ContextTriggeredActivity::StopActivity(
        DynamicManagementProvider::ContextTriggeredActivity *this)
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
          (__int64)&unk_14006F948,
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
          (__int64)&unk_14006FA78,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((DynamicManagementProvider::ContextTriggeredActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003c030  push    rbp
0x14003c032  push    rbx
0x14003c033  push    rdi
0x14003c034  lea     rbp, [rsp-47h]
0x14003c039  sub     rsp, 100h
0x14003c040  mov     rbx, rcx
0x14003c043  mov     rdi, [rcx+110h]
0x14003c04a  mov     eax, [rdi+48h]
0x14003c04d  test    eax, eax
0x14003c04f  jns     loc_14003C1FE
0x14003c055  add     rdi, 50h ; 'P'
0x14003c059  cmp     eax, [rdi+8]
0x14003c05c  jnz     loc_14003C1FE
0x14003c062  test    rdi, rdi
0x14003c065  jz      loc_14003C1FE
0x14003c06b  lea     rdx, [rbp+57h+SRWLock]
0x14003c06f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003c074  mov     rax, [rbx+110h]
0x14003c07b  mov     dword ptr [rax], 2
0x14003c081  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003c085  test    rcx, rcx
0x14003c088  jz      short loc_14003C090
0x14003c08a  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c090  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003c095  mov     r9, rax
0x14003c098  mov     ecx, [rax]
0x14003c09a  cmp     ecx, 5
0x14003c09d  jbe     loc_14003C2A2
0x14003c0a3  mov     rax, [rax+18h]
0x14003c0a7  mov     rcx, [r9+10h]
0x14003c0ab  mov     rdx, 400000000000h
0x14003c0b5  test    rdx, rcx
0x14003c0b8  jz      loc_14003C2A2
0x14003c0be  mov     rcx, rax
0x14003c0c1  and     rcx, rdx
0x14003c0c4  cmp     rcx, rax
0x14003c0c7  jnz     loc_14003C2A2
0x14003c0cd  mov     rax, [rdi+78h]
0x14003c0d1  mov     [rbp+57h+var_68], rax
0x14003c0d5  mov     rax, [rdi+70h]
0x14003c0d9  mov     [rbp+57h+var_60], rax
0x14003c0dd  mov     eax, [rdi+68h]
0x14003c0e0  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003c0e3  mov     rax, [rdi+60h]
0x14003c0e7  mov     [rbp+57h+var_58], rax
0x14003c0eb  mov     rax, [rdi+58h]
0x14003c0ef  mov     [rbp+57h+var_50], rax
0x14003c0f3  mov     eax, [rdi+50h]
0x14003c0f6  mov     [rbp+57h+arg_8], eax
0x14003c0f9  mov     rax, [rdi+48h]
0x14003c0fd  mov     [rbp+57h+var_48], rax
0x14003c101  mov     eax, [rdi+20h]
0x14003c104  mov     dword ptr [rbp+57h+arg_10], eax
0x14003c107  mov     rax, [rdi+18h]
0x14003c10b  mov     [rbp+57h+var_40], rax
0x14003c10f  mov     eax, [rdi]
0x14003c111  mov     [rbp+57h+arg_18], eax
0x14003c114  mov     rax, [rdi+80h]
0x14003c11b  mov     [rbp+57h+var_38], rax
0x14003c11f  mov     eax, [rdi+40h]
0x14003c122  mov     [rbp+57h+var_70], eax
0x14003c125  mov     rax, [rdi+38h]
0x14003c129  mov     [rbp+57h+var_30], rax
0x14003c12d  mov     eax, [rdi+8]
0x14003c130  mov     [rbp+57h+var_6C], eax
0x14003c133  mov     [rbp+57h+var_28], 1000000h
0x14003c13b  mov     [rbp+57h+var_20], 0
0x14003c143  mov     r8, [rbx+110h]
0x14003c14a  add     r8, 8
0x14003c14e  lea     rax, [rbp+57h+var_68]
0x14003c152  mov     [rsp+110h+var_78], rax
0x14003c15a  lea     rax, [rbp+57h+var_60]
0x14003c15e  mov     [rsp+110h+var_80], rax
0x14003c166  lea     rax, [rbp+57h+SRWLock]
0x14003c16a  mov     [rsp+110h+var_88], rax
0x14003c172  lea     rax, [rbp+57h+var_58]
0x14003c176  mov     [rsp+110h+var_90], rax
0x14003c17e  lea     rax, [rbp+57h+var_50]
0x14003c182  mov     [rsp+110h+var_98], rax
0x14003c187  lea     rax, [rbp+57h+arg_8]
0x14003c18b  mov     [rsp+110h+var_A0], rax
0x14003c190  lea     rax, [rbp+57h+var_48]
0x14003c194  mov     [rsp+110h+var_A8], rax
0x14003c199  lea     rax, [rbp+57h+arg_10]
0x14003c19d  mov     [rsp+110h+var_B0], rax
0x14003c1a2  lea     rax, [rbp+57h+var_40]
0x14003c1a6  mov     [rsp+110h+var_B8], rax
0x14003c1ab  lea     rax, [rbp+57h+arg_18]
0x14003c1af  mov     [rsp+110h+var_C0], rax
0x14003c1b4  lea     rax, [rbp+57h+var_38]
0x14003c1b8  mov     [rsp+110h+var_C8], rax
0x14003c1bd  lea     rax, [rbp+57h+var_70]
0x14003c1c1  mov     [rsp+110h+var_D0], rax
0x14003c1c6  lea     rax, [rbp+57h+var_30]
0x14003c1ca  mov     [rsp+110h+var_D8], rax
0x14003c1cf  lea     rax, [rbp+57h+var_6C]
0x14003c1d3  mov     [rsp+110h+var_E0], rax
0x14003c1d8  lea     rax, [rbp+57h+var_28]
0x14003c1dc  mov     [rsp+110h+var_E8], rax
0x14003c1e1  lea     rax, [rbp+57h+var_20]
0x14003c1e5  mov     [rsp+110h+var_F0], rax
0x14003c1ea  lea     rdx, unk_14006F948
0x14003c1f1  mov     rcx, r9
0x14003c1f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14003c1f9  jmp     loc_14003C2A2
0x14003c1fe  lea     rdx, [rbp+57h+SRWLock]
0x14003c202  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003c207  mov     rax, [rbx+110h]
0x14003c20e  mov     dword ptr [rax], 2
0x14003c214  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003c218  test    rcx, rcx
0x14003c21b  jz      short loc_14003C223
0x14003c21d  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c223  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003c228  mov     rdi, rax
0x14003c22b  mov     ecx, [rax]
0x14003c22d  cmp     ecx, 5
0x14003c230  jbe     short loc_14003C2A2
0x14003c232  mov     rax, [rax+18h]
0x14003c236  mov     rcx, [rdi+10h]
0x14003c23a  mov     rdx, 400000000000h
0x14003c244  test    rdx, rcx
0x14003c247  jz      short loc_14003C2A2
0x14003c249  mov     rcx, rax
0x14003c24c  and     rcx, rdx
0x14003c24f  cmp     rcx, rax
0x14003c252  jnz     short loc_14003C2A2
0x14003c254  call    cs:__imp_GetCurrentThreadId
0x14003c25a  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003c25d  mov     r8, [rbx+110h]
0x14003c264  mov     eax, [r8+48h]
0x14003c268  mov     [rbp+57h+arg_8], eax
0x14003c26b  mov     [rbp+57h+arg_10], 0
0x14003c273  add     r8, 8
0x14003c277  lea     rax, [rbp+57h+SRWLock]
0x14003c27b  mov     [rsp+110h+var_E0], rax
0x14003c280  lea     rax, [rbp+57h+arg_8]
0x14003c284  mov     [rsp+110h+var_E8], rax
0x14003c289  lea     rax, [rbp+57h+arg_10]
0x14003c28d  mov     [rsp+110h+var_F0], rax
0x14003c292  lea     rdx, unk_14006FA78
0x14003c299  mov     rcx, rdi
0x14003c29c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003c2a1  nop
0x14003c2a2  lea     rcx, [rbx+120h]; this
0x14003c2a9  cmp     dword ptr [rcx+18h], 0
0x14003c2ad  jz      short loc_14003C2B5
0x14003c2af  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003c2b4  nop
0x14003c2b5  add     rsp, 100h
0x14003c2bc  pop     rdi
0x14003c2bd  pop     rbx
0x14003c2be  pop     rbp
0x14003c2bf  retn
```
