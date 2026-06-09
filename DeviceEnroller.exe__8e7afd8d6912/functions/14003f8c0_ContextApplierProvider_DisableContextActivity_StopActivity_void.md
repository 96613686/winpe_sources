# ContextApplierProvider::DisableContextActivity::StopActivity(void)

- ea: `0x14003f8c0`
- end: `0x14003fb50`
- name: `?StopActivity@DisableContextActivity@ContextApplierProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(ContextApplierProvider::DisableContextActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x140018b08`
- `0x14003abc4`
- `0x14003f8c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f91a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003faad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003f91a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003faad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fae4`

## pseudocode

```c
void __fastcall ContextApplierProvider::DisableContextActivity::StopActivity(
        ContextApplierProvider::DisableContextActivity *this)
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
          (__int64)byte_140070C35,
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
          (__int64)byte_140070D63,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContextApplierProvider::DisableContextActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003f8c0  push    rbp
0x14003f8c2  push    rbx
0x14003f8c3  push    rdi
0x14003f8c4  lea     rbp, [rsp-47h]
0x14003f8c9  sub     rsp, 100h
0x14003f8d0  mov     rbx, rcx
0x14003f8d3  mov     rdi, [rcx+110h]
0x14003f8da  mov     eax, [rdi+48h]
0x14003f8dd  test    eax, eax
0x14003f8df  jns     loc_14003FA8E
0x14003f8e5  add     rdi, 50h ; 'P'
0x14003f8e9  cmp     eax, [rdi+8]
0x14003f8ec  jnz     loc_14003FA8E
0x14003f8f2  test    rdi, rdi
0x14003f8f5  jz      loc_14003FA8E
0x14003f8fb  lea     rdx, [rbp+57h+SRWLock]
0x14003f8ff  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003f904  mov     rax, [rbx+110h]
0x14003f90b  mov     dword ptr [rax], 2
0x14003f911  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003f915  test    rcx, rcx
0x14003f918  jz      short loc_14003F920
0x14003f91a  call    cs:__imp_ReleaseSRWLockExclusive
0x14003f920  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003f925  mov     r9, rax
0x14003f928  mov     ecx, [rax]
0x14003f92a  cmp     ecx, 5
0x14003f92d  jbe     loc_14003FB32
0x14003f933  mov     rax, [rax+18h]
0x14003f937  mov     rcx, [r9+10h]
0x14003f93b  mov     rdx, 400000000000h
0x14003f945  test    rdx, rcx
0x14003f948  jz      loc_14003FB32
0x14003f94e  mov     rcx, rax
0x14003f951  and     rcx, rdx
0x14003f954  cmp     rcx, rax
0x14003f957  jnz     loc_14003FB32
0x14003f95d  mov     rax, [rdi+78h]
0x14003f961  mov     [rbp+57h+var_68], rax
0x14003f965  mov     rax, [rdi+70h]
0x14003f969  mov     [rbp+57h+var_60], rax
0x14003f96d  mov     eax, [rdi+68h]
0x14003f970  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003f973  mov     rax, [rdi+60h]
0x14003f977  mov     [rbp+57h+var_58], rax
0x14003f97b  mov     rax, [rdi+58h]
0x14003f97f  mov     [rbp+57h+var_50], rax
0x14003f983  mov     eax, [rdi+50h]
0x14003f986  mov     [rbp+57h+arg_8], eax
0x14003f989  mov     rax, [rdi+48h]
0x14003f98d  mov     [rbp+57h+var_48], rax
0x14003f991  mov     eax, [rdi+20h]
0x14003f994  mov     dword ptr [rbp+57h+arg_10], eax
0x14003f997  mov     rax, [rdi+18h]
0x14003f99b  mov     [rbp+57h+var_40], rax
0x14003f99f  mov     eax, [rdi]
0x14003f9a1  mov     [rbp+57h+arg_18], eax
0x14003f9a4  mov     rax, [rdi+80h]
0x14003f9ab  mov     [rbp+57h+var_38], rax
0x14003f9af  mov     eax, [rdi+40h]
0x14003f9b2  mov     [rbp+57h+var_70], eax
0x14003f9b5  mov     rax, [rdi+38h]
0x14003f9b9  mov     [rbp+57h+var_30], rax
0x14003f9bd  mov     eax, [rdi+8]
0x14003f9c0  mov     [rbp+57h+var_6C], eax
0x14003f9c3  mov     [rbp+57h+var_28], 1000000h
0x14003f9cb  mov     [rbp+57h+var_20], 0
0x14003f9d3  mov     r8, [rbx+110h]
0x14003f9da  add     r8, 8
0x14003f9de  lea     rax, [rbp+57h+var_68]
0x14003f9e2  mov     [rsp+110h+var_78], rax
0x14003f9ea  lea     rax, [rbp+57h+var_60]
0x14003f9ee  mov     [rsp+110h+var_80], rax
0x14003f9f6  lea     rax, [rbp+57h+SRWLock]
0x14003f9fa  mov     [rsp+110h+var_88], rax
0x14003fa02  lea     rax, [rbp+57h+var_58]
0x14003fa06  mov     [rsp+110h+var_90], rax
0x14003fa0e  lea     rax, [rbp+57h+var_50]
0x14003fa12  mov     [rsp+110h+var_98], rax
0x14003fa17  lea     rax, [rbp+57h+arg_8]
0x14003fa1b  mov     [rsp+110h+var_A0], rax
0x14003fa20  lea     rax, [rbp+57h+var_48]
0x14003fa24  mov     [rsp+110h+var_A8], rax
0x14003fa29  lea     rax, [rbp+57h+arg_10]
0x14003fa2d  mov     [rsp+110h+var_B0], rax
0x14003fa32  lea     rax, [rbp+57h+var_40]
0x14003fa36  mov     [rsp+110h+var_B8], rax
0x14003fa3b  lea     rax, [rbp+57h+arg_18]
0x14003fa3f  mov     [rsp+110h+var_C0], rax
0x14003fa44  lea     rax, [rbp+57h+var_38]
0x14003fa48  mov     [rsp+110h+var_C8], rax
0x14003fa4d  lea     rax, [rbp+57h+var_70]
0x14003fa51  mov     [rsp+110h+var_D0], rax
0x14003fa56  lea     rax, [rbp+57h+var_30]
0x14003fa5a  mov     [rsp+110h+var_D8], rax
0x14003fa5f  lea     rax, [rbp+57h+var_6C]
0x14003fa63  mov     [rsp+110h+var_E0], rax
0x14003fa68  lea     rax, [rbp+57h+var_28]
0x14003fa6c  mov     [rsp+110h+var_E8], rax
0x14003fa71  lea     rax, [rbp+57h+var_20]
0x14003fa75  mov     [rsp+110h+var_F0], rax
0x14003fa7a  lea     rdx, byte_140070C35
0x14003fa81  mov     rcx, r9
0x14003fa84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14003fa89  jmp     loc_14003FB32
0x14003fa8e  lea     rdx, [rbp+57h+SRWLock]
0x14003fa92  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003fa97  mov     rax, [rbx+110h]
0x14003fa9e  mov     dword ptr [rax], 2
0x14003faa4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003faa8  test    rcx, rcx
0x14003faab  jz      short loc_14003FAB3
0x14003faad  call    cs:__imp_ReleaseSRWLockExclusive
0x14003fab3  call    ?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ; DynamoProvider::Provider(void)
0x14003fab8  mov     rdi, rax
0x14003fabb  mov     ecx, [rax]
0x14003fabd  cmp     ecx, 5
0x14003fac0  jbe     short loc_14003FB32
0x14003fac2  mov     rax, [rax+18h]
0x14003fac6  mov     rcx, [rdi+10h]
0x14003faca  mov     rdx, 400000000000h
0x14003fad4  test    rdx, rcx
0x14003fad7  jz      short loc_14003FB32
0x14003fad9  mov     rcx, rax
0x14003fadc  and     rcx, rdx
0x14003fadf  cmp     rcx, rax
0x14003fae2  jnz     short loc_14003FB32
0x14003fae4  call    cs:__imp_GetCurrentThreadId
0x14003faea  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003faed  mov     r8, [rbx+110h]
0x14003faf4  mov     eax, [r8+48h]
0x14003faf8  mov     [rbp+57h+arg_8], eax
0x14003fafb  mov     [rbp+57h+arg_10], 0
0x14003fb03  add     r8, 8
0x14003fb07  lea     rax, [rbp+57h+SRWLock]
0x14003fb0b  mov     [rsp+110h+var_E0], rax
0x14003fb10  lea     rax, [rbp+57h+arg_8]
0x14003fb14  mov     [rsp+110h+var_E8], rax
0x14003fb19  lea     rax, [rbp+57h+arg_10]
0x14003fb1d  mov     [rsp+110h+var_F0], rax
0x14003fb22  lea     rdx, byte_140070D63
0x14003fb29  mov     rcx, rdi
0x14003fb2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003fb31  nop
0x14003fb32  lea     rcx, [rbx+120h]; this
0x14003fb39  cmp     dword ptr [rcx+18h], 0
0x14003fb3d  jz      short loc_14003FB45
0x14003fb3f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003fb44  nop
0x14003fb45  add     rsp, 100h
0x14003fb4c  pop     rdi
0x14003fb4d  pop     rbx
0x14003fb4e  pop     rbp
0x14003fb4f  retn
```
