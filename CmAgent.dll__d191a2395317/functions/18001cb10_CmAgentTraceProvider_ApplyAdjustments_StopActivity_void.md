# CmAgentTraceProvider::ApplyAdjustments::StopActivity(void)

- ea: `0x18001cb10`
- end: `0x18001cdb4`
- name: `?StopActivity@ApplyAdjustments@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::ApplyAdjustments *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001cb10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cd40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cd40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cb6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cd02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cb6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cd02`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::ApplyAdjustments::StopActivity(CmAgentTraceProvider::ApplyAdjustments *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+A0h] [rbp-19h] BYREF
  int v10; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v11; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v13; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v17; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v11 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_180043C3D,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v10,
        &v18,
        (__int64)&v9,
        &v17,
        (__int64)&v24,
        &v16,
        (__int64)&v23,
        &v15,
        (__int64)&v22,
        &v14,
        &v13,
        (__int64)&SRWLock,
        &v12,
        &v11);
    }
  }
  else
  {
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)qword_180043700,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::ApplyAdjustments *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001cb10  push    rbp
0x18001cb12  push    rbx
0x18001cb13  push    rdi
0x18001cb14  lea     rbp, [rsp-47h]
0x18001cb19  sub     rsp, 100h
0x18001cb20  mov     rbx, rcx
0x18001cb23  mov     rdi, [rcx+110h]
0x18001cb2a  mov     eax, [rdi+48h]
0x18001cb2d  test    eax, eax
0x18001cb2f  jns     loc_18001CCE3
0x18001cb35  add     rdi, 50h ; 'P'
0x18001cb39  cmp     eax, [rdi+8]
0x18001cb3c  jnz     loc_18001CCE3
0x18001cb42  test    rdi, rdi
0x18001cb45  jz      loc_18001CCE3
0x18001cb4b  lea     rdx, [rbp+57h+SRWLock]
0x18001cb4f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001cb54  mov     rax, [rbx+110h]
0x18001cb5b  mov     dword ptr [rax], 2
0x18001cb61  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001cb65  test    rcx, rcx
0x18001cb68  jz      short loc_18001CB76
0x18001cb6a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cb71  nop     dword ptr [rax+rax+00h]
0x18001cb76  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001cb7b  mov     r9, [rax+8]
0x18001cb7f  mov     eax, [r9]
0x18001cb82  cmp     eax, 5
0x18001cb85  jbe     loc_18001CD95
0x18001cb8b  mov     rdx, [r9+18h]
0x18001cb8f  mov     rax, [r9+10h]
0x18001cb93  mov     rcx, 400000000000h
0x18001cb9d  test    rcx, rax
0x18001cba0  jz      loc_18001CD95
0x18001cba6  mov     rax, rdx
0x18001cba9  and     rax, rcx
0x18001cbac  cmp     rax, rdx
0x18001cbaf  jnz     loc_18001CD95
0x18001cbb5  mov     rax, [rdi+78h]
0x18001cbb9  mov     [rbp+57h+var_68], rax
0x18001cbbd  mov     rax, [rdi+70h]
0x18001cbc1  mov     [rbp+57h+var_60], rax
0x18001cbc5  mov     eax, [rdi+68h]
0x18001cbc8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001cbcb  mov     rax, [rdi+60h]
0x18001cbcf  mov     [rbp+57h+var_58], rax
0x18001cbd3  mov     rax, [rdi+58h]
0x18001cbd7  mov     [rbp+57h+var_50], rax
0x18001cbdb  mov     eax, [rdi+50h]
0x18001cbde  mov     [rbp+57h+arg_8], eax
0x18001cbe1  mov     rax, [rdi+48h]
0x18001cbe5  mov     [rbp+57h+var_48], rax
0x18001cbe9  mov     eax, [rdi+20h]
0x18001cbec  mov     dword ptr [rbp+57h+arg_10], eax
0x18001cbef  mov     rax, [rdi+18h]
0x18001cbf3  mov     [rbp+57h+var_40], rax
0x18001cbf7  mov     eax, [rdi]
0x18001cbf9  mov     [rbp+57h+arg_18], eax
0x18001cbfc  mov     rax, [rdi+80h]
0x18001cc03  mov     [rbp+57h+var_38], rax
0x18001cc07  mov     eax, [rdi+40h]
0x18001cc0a  mov     [rbp+57h+var_70], eax
0x18001cc0d  mov     rax, [rdi+38h]
0x18001cc11  mov     [rbp+57h+var_30], rax
0x18001cc15  mov     eax, [rdi+8]
0x18001cc18  mov     [rbp+57h+var_6C], eax
0x18001cc1b  mov     eax, 1000000h
0x18001cc20  mov     [rbp+57h+var_28], rax
0x18001cc24  mov     [rbp+57h+var_20], rax
0x18001cc28  mov     r8, [rbx+110h]
0x18001cc2f  add     r8, 8
0x18001cc33  lea     rax, [rbp+57h+var_68]
0x18001cc37  mov     [rsp+110h+var_78], rax
0x18001cc3f  lea     rax, [rbp+57h+var_60]
0x18001cc43  mov     [rsp+110h+var_80], rax
0x18001cc4b  lea     rax, [rbp+57h+SRWLock]
0x18001cc4f  mov     [rsp+110h+var_88], rax
0x18001cc57  lea     rax, [rbp+57h+var_58]
0x18001cc5b  mov     [rsp+110h+var_90], rax
0x18001cc63  lea     rax, [rbp+57h+var_50]
0x18001cc67  mov     [rsp+110h+var_98], rax
0x18001cc6c  lea     rax, [rbp+57h+arg_8]
0x18001cc70  mov     [rsp+110h+var_A0], rax
0x18001cc75  lea     rax, [rbp+57h+var_48]
0x18001cc79  mov     [rsp+110h+var_A8], rax
0x18001cc7e  lea     rax, [rbp+57h+arg_10]
0x18001cc82  mov     [rsp+110h+var_B0], rax
0x18001cc87  lea     rax, [rbp+57h+var_40]
0x18001cc8b  mov     [rsp+110h+var_B8], rax
0x18001cc90  lea     rax, [rbp+57h+arg_18]
0x18001cc94  mov     [rsp+110h+var_C0], rax
0x18001cc99  lea     rax, [rbp+57h+var_38]
0x18001cc9d  mov     [rsp+110h+var_C8], rax
0x18001cca2  lea     rax, [rbp+57h+var_70]
0x18001cca6  mov     [rsp+110h+var_D0], rax
0x18001ccab  lea     rax, [rbp+57h+var_30]
0x18001ccaf  mov     [rsp+110h+var_D8], rax
0x18001ccb4  lea     rax, [rbp+57h+var_6C]
0x18001ccb8  mov     [rsp+110h+var_E0], rax
0x18001ccbd  lea     rax, [rbp+57h+var_28]
0x18001ccc1  mov     [rsp+110h+var_E8], rax
0x18001ccc6  lea     rax, [rbp+57h+var_20]
0x18001ccca  mov     [rsp+110h+var_F0], rax
0x18001cccf  lea     rdx, byte_180043C3D
0x18001ccd6  mov     rcx, r9
0x18001ccd9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001ccde  jmp     loc_18001CD95
0x18001cce3  lea     rdx, [rbp+57h+SRWLock]
0x18001cce7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ccec  mov     rax, [rbx+110h]
0x18001ccf3  mov     dword ptr [rax], 2
0x18001ccf9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ccfd  test    rcx, rcx
0x18001cd00  jz      short loc_18001CD0E
0x18001cd02  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cd09  nop     dword ptr [rax+rax+00h]
0x18001cd0e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001cd13  mov     rdi, [rax+8]
0x18001cd17  mov     eax, [rdi]
0x18001cd19  cmp     eax, 5
0x18001cd1c  jbe     short loc_18001CD95
0x18001cd1e  mov     rdx, [rdi+18h]
0x18001cd22  mov     rax, [rdi+10h]
0x18001cd26  mov     rcx, 400000000000h
0x18001cd30  test    rcx, rax
0x18001cd33  jz      short loc_18001CD95
0x18001cd35  mov     rax, rdx
0x18001cd38  and     rax, rcx
0x18001cd3b  cmp     rax, rdx
0x18001cd3e  jnz     short loc_18001CD95
0x18001cd40  call    cs:__imp_GetCurrentThreadId
0x18001cd47  nop     dword ptr [rax+rax+00h]
0x18001cd4c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001cd4f  mov     r8, [rbx+110h]
0x18001cd56  mov     eax, [r8+48h]
0x18001cd5a  mov     [rbp+57h+arg_8], eax
0x18001cd5d  mov     eax, 1000000h
0x18001cd62  mov     [rbp+57h+arg_10], rax
0x18001cd66  add     r8, 8
0x18001cd6a  lea     rax, [rbp+57h+SRWLock]
0x18001cd6e  mov     [rsp+110h+var_E0], rax
0x18001cd73  lea     rax, [rbp+57h+arg_8]
0x18001cd77  mov     [rsp+110h+var_E8], rax
0x18001cd7c  lea     rax, [rbp+57h+arg_10]
0x18001cd80  mov     [rsp+110h+var_F0], rax
0x18001cd85  lea     rdx, qword_180043700
0x18001cd8c  mov     rcx, rdi
0x18001cd8f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001cd94  nop
0x18001cd95  lea     rcx, [rbx+120h]; this
0x18001cd9c  cmp     dword ptr [rcx+18h], 0
0x18001cda0  jz      short loc_18001CDA8
0x18001cda2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001cda7  nop
0x18001cda8  add     rsp, 100h
0x18001cdaf  pop     rdi
0x18001cdb0  pop     rbx
0x18001cdb1  pop     rbp
0x18001cdb2  retn
```
