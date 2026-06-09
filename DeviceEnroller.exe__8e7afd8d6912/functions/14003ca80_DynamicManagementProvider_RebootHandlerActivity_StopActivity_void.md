# DynamicManagementProvider::RebootHandlerActivity::StopActivity(void)

- ea: `0x14003ca80`
- end: `0x14003cd10`
- name: `?StopActivity@RebootHandlerActivity@DynamicManagementProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(DynamicManagementProvider::RebootHandlerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14003abc4`
- `0x14003ca80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cada`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cc6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cada`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cc6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cca4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cca4`

## pseudocode

```c
void __fastcall DynamicManagementProvider::RebootHandlerActivity::StopActivity(
        DynamicManagementProvider::RebootHandlerActivity *this)
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
          (__int64)byte_14007084B,
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
          (__int64)byte_1400707F5,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((DynamicManagementProvider::RebootHandlerActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003ca80  push    rbp
0x14003ca82  push    rbx
0x14003ca83  push    rdi
0x14003ca84  lea     rbp, [rsp-47h]
0x14003ca89  sub     rsp, 100h
0x14003ca90  mov     rbx, rcx
0x14003ca93  mov     rdi, [rcx+110h]
0x14003ca9a  mov     eax, [rdi+48h]
0x14003ca9d  test    eax, eax
0x14003ca9f  jns     loc_14003CC4E
0x14003caa5  add     rdi, 50h ; 'P'
0x14003caa9  cmp     eax, [rdi+8]
0x14003caac  jnz     loc_14003CC4E
0x14003cab2  test    rdi, rdi
0x14003cab5  jz      loc_14003CC4E
0x14003cabb  lea     rdx, [rbp+57h+SRWLock]
0x14003cabf  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003cac4  mov     rax, [rbx+110h]
0x14003cacb  mov     dword ptr [rax], 2
0x14003cad1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003cad5  test    rcx, rcx
0x14003cad8  jz      short loc_14003CAE0
0x14003cada  call    cs:__imp_ReleaseSRWLockExclusive
0x14003cae0  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003cae5  mov     r9, rax
0x14003cae8  mov     ecx, [rax]
0x14003caea  cmp     ecx, 5
0x14003caed  jbe     loc_14003CCF2
0x14003caf3  mov     rax, [rax+18h]
0x14003caf7  mov     rcx, [r9+10h]
0x14003cafb  mov     rdx, 400000000000h
0x14003cb05  test    rdx, rcx
0x14003cb08  jz      loc_14003CCF2
0x14003cb0e  mov     rcx, rax
0x14003cb11  and     rcx, rdx
0x14003cb14  cmp     rcx, rax
0x14003cb17  jnz     loc_14003CCF2
0x14003cb1d  mov     rax, [rdi+78h]
0x14003cb21  mov     [rbp+57h+var_68], rax
0x14003cb25  mov     rax, [rdi+70h]
0x14003cb29  mov     [rbp+57h+var_60], rax
0x14003cb2d  mov     eax, [rdi+68h]
0x14003cb30  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003cb33  mov     rax, [rdi+60h]
0x14003cb37  mov     [rbp+57h+var_58], rax
0x14003cb3b  mov     rax, [rdi+58h]
0x14003cb3f  mov     [rbp+57h+var_50], rax
0x14003cb43  mov     eax, [rdi+50h]
0x14003cb46  mov     [rbp+57h+arg_8], eax
0x14003cb49  mov     rax, [rdi+48h]
0x14003cb4d  mov     [rbp+57h+var_48], rax
0x14003cb51  mov     eax, [rdi+20h]
0x14003cb54  mov     dword ptr [rbp+57h+arg_10], eax
0x14003cb57  mov     rax, [rdi+18h]
0x14003cb5b  mov     [rbp+57h+var_40], rax
0x14003cb5f  mov     eax, [rdi]
0x14003cb61  mov     [rbp+57h+arg_18], eax
0x14003cb64  mov     rax, [rdi+80h]
0x14003cb6b  mov     [rbp+57h+var_38], rax
0x14003cb6f  mov     eax, [rdi+40h]
0x14003cb72  mov     [rbp+57h+var_70], eax
0x14003cb75  mov     rax, [rdi+38h]
0x14003cb79  mov     [rbp+57h+var_30], rax
0x14003cb7d  mov     eax, [rdi+8]
0x14003cb80  mov     [rbp+57h+var_6C], eax
0x14003cb83  mov     [rbp+57h+var_28], 1000000h
0x14003cb8b  mov     [rbp+57h+var_20], 0
0x14003cb93  mov     r8, [rbx+110h]
0x14003cb9a  add     r8, 8
0x14003cb9e  lea     rax, [rbp+57h+var_68]
0x14003cba2  mov     [rsp+110h+var_78], rax
0x14003cbaa  lea     rax, [rbp+57h+var_60]
0x14003cbae  mov     [rsp+110h+var_80], rax
0x14003cbb6  lea     rax, [rbp+57h+SRWLock]
0x14003cbba  mov     [rsp+110h+var_88], rax
0x14003cbc2  lea     rax, [rbp+57h+var_58]
0x14003cbc6  mov     [rsp+110h+var_90], rax
0x14003cbce  lea     rax, [rbp+57h+var_50]
0x14003cbd2  mov     [rsp+110h+var_98], rax
0x14003cbd7  lea     rax, [rbp+57h+arg_8]
0x14003cbdb  mov     [rsp+110h+var_A0], rax
0x14003cbe0  lea     rax, [rbp+57h+var_48]
0x14003cbe4  mov     [rsp+110h+var_A8], rax
0x14003cbe9  lea     rax, [rbp+57h+arg_10]
0x14003cbed  mov     [rsp+110h+var_B0], rax
0x14003cbf2  lea     rax, [rbp+57h+var_40]
0x14003cbf6  mov     [rsp+110h+var_B8], rax
0x14003cbfb  lea     rax, [rbp+57h+arg_18]
0x14003cbff  mov     [rsp+110h+var_C0], rax
0x14003cc04  lea     rax, [rbp+57h+var_38]
0x14003cc08  mov     [rsp+110h+var_C8], rax
0x14003cc0d  lea     rax, [rbp+57h+var_70]
0x14003cc11  mov     [rsp+110h+var_D0], rax
0x14003cc16  lea     rax, [rbp+57h+var_30]
0x14003cc1a  mov     [rsp+110h+var_D8], rax
0x14003cc1f  lea     rax, [rbp+57h+var_6C]
0x14003cc23  mov     [rsp+110h+var_E0], rax
0x14003cc28  lea     rax, [rbp+57h+var_28]
0x14003cc2c  mov     [rsp+110h+var_E8], rax
0x14003cc31  lea     rax, [rbp+57h+var_20]
0x14003cc35  mov     [rsp+110h+var_F0], rax
0x14003cc3a  lea     rdx, byte_14007084B
0x14003cc41  mov     rcx, r9
0x14003cc44  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14003cc49  jmp     loc_14003CCF2
0x14003cc4e  lea     rdx, [rbp+57h+SRWLock]
0x14003cc52  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003cc57  mov     rax, [rbx+110h]
0x14003cc5e  mov     dword ptr [rax], 2
0x14003cc64  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003cc68  test    rcx, rcx
0x14003cc6b  jz      short loc_14003CC73
0x14003cc6d  call    cs:__imp_ReleaseSRWLockExclusive
0x14003cc73  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003cc78  mov     rdi, rax
0x14003cc7b  mov     ecx, [rax]
0x14003cc7d  cmp     ecx, 5
0x14003cc80  jbe     short loc_14003CCF2
0x14003cc82  mov     rax, [rax+18h]
0x14003cc86  mov     rcx, [rdi+10h]
0x14003cc8a  mov     rdx, 400000000000h
0x14003cc94  test    rdx, rcx
0x14003cc97  jz      short loc_14003CCF2
0x14003cc99  mov     rcx, rax
0x14003cc9c  and     rcx, rdx
0x14003cc9f  cmp     rcx, rax
0x14003cca2  jnz     short loc_14003CCF2
0x14003cca4  call    cs:__imp_GetCurrentThreadId
0x14003ccaa  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003ccad  mov     r8, [rbx+110h]
0x14003ccb4  mov     eax, [r8+48h]
0x14003ccb8  mov     [rbp+57h+arg_8], eax
0x14003ccbb  mov     [rbp+57h+arg_10], 0
0x14003ccc3  add     r8, 8
0x14003ccc7  lea     rax, [rbp+57h+SRWLock]
0x14003cccb  mov     [rsp+110h+var_E0], rax
0x14003ccd0  lea     rax, [rbp+57h+arg_8]
0x14003ccd4  mov     [rsp+110h+var_E8], rax
0x14003ccd9  lea     rax, [rbp+57h+arg_10]
0x14003ccdd  mov     [rsp+110h+var_F0], rax
0x14003cce2  lea     rdx, byte_1400707F5
0x14003cce9  mov     rcx, rdi
0x14003ccec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003ccf1  nop
0x14003ccf2  lea     rcx, [rbx+120h]; this
0x14003ccf9  cmp     dword ptr [rcx+18h], 0
0x14003ccfd  jz      short loc_14003CD05
0x14003ccff  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003cd04  nop
0x14003cd05  add     rsp, 100h
0x14003cd0c  pop     rdi
0x14003cd0d  pop     rbx
0x14003cd0e  pop     rbp
0x14003cd0f  retn
```
