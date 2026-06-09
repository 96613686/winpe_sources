# MDMPushProvider::RenewActivity::StopActivity(void)

- ea: `0x1400185d0`
- end: `0x140018860`
- name: `?StopActivity@RenewActivity@MDMPushProvider@@MEAAXXZ`
- size: `656`
- prototype: `void __fastcall(MDMPushProvider::RenewActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000117c`
- `0x140001744`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400185d0`
- `0x140018b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001862a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400187bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001862a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400187bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400187f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400187f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MDMPushProvider::RenewActivity::StopActivity(MDMPushProvider::RenewActivity *this)
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
          (__int64)&unk_14006DA70,
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
          (__int64)byte_14006D879,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((MDMPushProvider::RenewActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400185d0  push    rbp
0x1400185d2  push    rbx
0x1400185d3  push    rdi
0x1400185d4  lea     rbp, [rsp-47h]
0x1400185d9  sub     rsp, 100h
0x1400185e0  mov     rbx, rcx
0x1400185e3  mov     rdi, [rcx+110h]
0x1400185ea  mov     eax, [rdi+48h]
0x1400185ed  test    eax, eax
0x1400185ef  jns     loc_14001879E
0x1400185f5  add     rdi, 50h ; 'P'
0x1400185f9  cmp     eax, [rdi+8]
0x1400185fc  jnz     loc_14001879E
0x140018602  test    rdi, rdi
0x140018605  jz      loc_14001879E
0x14001860b  lea     rdx, [rbp+57h+SRWLock]
0x14001860f  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140018614  mov     rax, [rbx+110h]
0x14001861b  mov     dword ptr [rax], 2
0x140018621  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140018625  test    rcx, rcx
0x140018628  jz      short loc_140018630
0x14001862a  call    cs:__imp_ReleaseSRWLockExclusive
0x140018630  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140018635  mov     r9, rax
0x140018638  mov     ecx, [rax]
0x14001863a  cmp     ecx, 5
0x14001863d  jbe     loc_140018842
0x140018643  mov     rax, [rax+18h]
0x140018647  mov     rcx, [r9+10h]
0x14001864b  mov     rdx, 400000000000h
0x140018655  test    rdx, rcx
0x140018658  jz      loc_140018842
0x14001865e  mov     rcx, rax
0x140018661  and     rcx, rdx
0x140018664  cmp     rcx, rax
0x140018667  jnz     loc_140018842
0x14001866d  mov     rax, [rdi+78h]
0x140018671  mov     [rbp+57h+var_68], rax
0x140018675  mov     rax, [rdi+70h]
0x140018679  mov     [rbp+57h+var_60], rax
0x14001867d  mov     eax, [rdi+68h]
0x140018680  mov     dword ptr [rbp+57h+SRWLock], eax
0x140018683  mov     rax, [rdi+60h]
0x140018687  mov     [rbp+57h+var_58], rax
0x14001868b  mov     rax, [rdi+58h]
0x14001868f  mov     [rbp+57h+var_50], rax
0x140018693  mov     eax, [rdi+50h]
0x140018696  mov     [rbp+57h+arg_8], eax
0x140018699  mov     rax, [rdi+48h]
0x14001869d  mov     [rbp+57h+var_48], rax
0x1400186a1  mov     eax, [rdi+20h]
0x1400186a4  mov     dword ptr [rbp+57h+arg_10], eax
0x1400186a7  mov     rax, [rdi+18h]
0x1400186ab  mov     [rbp+57h+var_40], rax
0x1400186af  mov     eax, [rdi]
0x1400186b1  mov     [rbp+57h+arg_18], eax
0x1400186b4  mov     rax, [rdi+80h]
0x1400186bb  mov     [rbp+57h+var_38], rax
0x1400186bf  mov     eax, [rdi+40h]
0x1400186c2  mov     [rbp+57h+var_70], eax
0x1400186c5  mov     rax, [rdi+38h]
0x1400186c9  mov     [rbp+57h+var_30], rax
0x1400186cd  mov     eax, [rdi+8]
0x1400186d0  mov     [rbp+57h+var_6C], eax
0x1400186d3  mov     [rbp+57h+var_28], 1000000h
0x1400186db  mov     [rbp+57h+var_20], 0
0x1400186e3  mov     r8, [rbx+110h]
0x1400186ea  add     r8, 8
0x1400186ee  lea     rax, [rbp+57h+var_68]
0x1400186f2  mov     [rsp+110h+var_78], rax
0x1400186fa  lea     rax, [rbp+57h+var_60]
0x1400186fe  mov     [rsp+110h+var_80], rax
0x140018706  lea     rax, [rbp+57h+SRWLock]
0x14001870a  mov     [rsp+110h+var_88], rax
0x140018712  lea     rax, [rbp+57h+var_58]
0x140018716  mov     [rsp+110h+var_90], rax
0x14001871e  lea     rax, [rbp+57h+var_50]
0x140018722  mov     [rsp+110h+var_98], rax
0x140018727  lea     rax, [rbp+57h+arg_8]
0x14001872b  mov     [rsp+110h+var_A0], rax
0x140018730  lea     rax, [rbp+57h+var_48]
0x140018734  mov     [rsp+110h+var_A8], rax
0x140018739  lea     rax, [rbp+57h+arg_10]
0x14001873d  mov     [rsp+110h+var_B0], rax
0x140018742  lea     rax, [rbp+57h+var_40]
0x140018746  mov     [rsp+110h+var_B8], rax
0x14001874b  lea     rax, [rbp+57h+arg_18]
0x14001874f  mov     [rsp+110h+var_C0], rax
0x140018754  lea     rax, [rbp+57h+var_38]
0x140018758  mov     [rsp+110h+var_C8], rax
0x14001875d  lea     rax, [rbp+57h+var_70]
0x140018761  mov     [rsp+110h+var_D0], rax
0x140018766  lea     rax, [rbp+57h+var_30]
0x14001876a  mov     [rsp+110h+var_D8], rax
0x14001876f  lea     rax, [rbp+57h+var_6C]
0x140018773  mov     [rsp+110h+var_E0], rax
0x140018778  lea     rax, [rbp+57h+var_28]
0x14001877c  mov     [rsp+110h+var_E8], rax
0x140018781  lea     rax, [rbp+57h+var_20]
0x140018785  mov     [rsp+110h+var_F0], rax
0x14001878a  lea     rdx, unk_14006DA70
0x140018791  mov     rcx, r9
0x140018794  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140018799  jmp     loc_140018842
0x14001879e  lea     rdx, [rbp+57h+SRWLock]
0x1400187a2  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400187a7  mov     rax, [rbx+110h]
0x1400187ae  mov     dword ptr [rax], 2
0x1400187b4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400187b8  test    rcx, rcx
0x1400187bb  jz      short loc_1400187C3
0x1400187bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1400187c3  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400187c8  mov     rdi, rax
0x1400187cb  mov     ecx, [rax]
0x1400187cd  cmp     ecx, 5
0x1400187d0  jbe     short loc_140018842
0x1400187d2  mov     rax, [rax+18h]
0x1400187d6  mov     rcx, [rdi+10h]
0x1400187da  mov     rdx, 400000000000h
0x1400187e4  test    rdx, rcx
0x1400187e7  jz      short loc_140018842
0x1400187e9  mov     rcx, rax
0x1400187ec  and     rcx, rdx
0x1400187ef  cmp     rcx, rax
0x1400187f2  jnz     short loc_140018842
0x1400187f4  call    cs:__imp_GetCurrentThreadId
0x1400187fa  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400187fd  mov     r8, [rbx+110h]
0x140018804  mov     eax, [r8+48h]
0x140018808  mov     [rbp+57h+arg_8], eax
0x14001880b  mov     [rbp+57h+arg_10], 0
0x140018813  add     r8, 8
0x140018817  lea     rax, [rbp+57h+SRWLock]
0x14001881b  mov     [rsp+110h+var_E0], rax
0x140018820  lea     rax, [rbp+57h+arg_8]
0x140018824  mov     [rsp+110h+var_E8], rax
0x140018829  lea     rax, [rbp+57h+arg_10]
0x14001882d  mov     [rsp+110h+var_F0], rax
0x140018832  lea     rdx, byte_14006D879
0x140018839  mov     rcx, rdi
0x14001883c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140018841  nop
0x140018842  lea     rcx, [rbx+120h]; this
0x140018849  cmp     dword ptr [rcx+18h], 0
0x14001884d  jz      short loc_140018855
0x14001884f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140018854  nop
0x140018855  add     rsp, 100h
0x14001885c  pop     rdi
0x14001885d  pop     rbx
0x14001885e  pop     rbp
0x14001885f  retn
```
