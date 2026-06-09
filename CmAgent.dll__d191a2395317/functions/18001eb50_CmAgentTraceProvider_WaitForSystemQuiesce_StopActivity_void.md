# CmAgentTraceProvider::WaitForSystemQuiesce::StopActivity(void)

- ea: `0x18001eb50`
- end: `0x18001edf4`
- name: `?StopActivity@WaitForSystemQuiesce@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForSystemQuiesce *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001eb50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ed80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ebaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ebaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed42`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForSystemQuiesce::StopActivity(
        CmAgentTraceProvider::WaitForSystemQuiesce *this)
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
        (__int64)byte_18004430D,
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
        (__int64)byte_1800440A1,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::WaitForSystemQuiesce *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001eb50  push    rbp
0x18001eb52  push    rbx
0x18001eb53  push    rdi
0x18001eb54  lea     rbp, [rsp-47h]
0x18001eb59  sub     rsp, 100h
0x18001eb60  mov     rbx, rcx
0x18001eb63  mov     rdi, [rcx+110h]
0x18001eb6a  mov     eax, [rdi+48h]
0x18001eb6d  test    eax, eax
0x18001eb6f  jns     loc_18001ED23
0x18001eb75  add     rdi, 50h ; 'P'
0x18001eb79  cmp     eax, [rdi+8]
0x18001eb7c  jnz     loc_18001ED23
0x18001eb82  test    rdi, rdi
0x18001eb85  jz      loc_18001ED23
0x18001eb8b  lea     rdx, [rbp+57h+SRWLock]
0x18001eb8f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001eb94  mov     rax, [rbx+110h]
0x18001eb9b  mov     dword ptr [rax], 2
0x18001eba1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001eba5  test    rcx, rcx
0x18001eba8  jz      short loc_18001EBB6
0x18001ebaa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ebb1  nop     dword ptr [rax+rax+00h]
0x18001ebb6  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001ebbb  mov     r9, [rax+8]
0x18001ebbf  mov     eax, [r9]
0x18001ebc2  cmp     eax, 5
0x18001ebc5  jbe     loc_18001EDD5
0x18001ebcb  mov     rdx, [r9+18h]
0x18001ebcf  mov     rax, [r9+10h]
0x18001ebd3  mov     rcx, 400000000000h
0x18001ebdd  test    rcx, rax
0x18001ebe0  jz      loc_18001EDD5
0x18001ebe6  mov     rax, rdx
0x18001ebe9  and     rax, rcx
0x18001ebec  cmp     rax, rdx
0x18001ebef  jnz     loc_18001EDD5
0x18001ebf5  mov     rax, [rdi+78h]
0x18001ebf9  mov     [rbp+57h+var_68], rax
0x18001ebfd  mov     rax, [rdi+70h]
0x18001ec01  mov     [rbp+57h+var_60], rax
0x18001ec05  mov     eax, [rdi+68h]
0x18001ec08  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001ec0b  mov     rax, [rdi+60h]
0x18001ec0f  mov     [rbp+57h+var_58], rax
0x18001ec13  mov     rax, [rdi+58h]
0x18001ec17  mov     [rbp+57h+var_50], rax
0x18001ec1b  mov     eax, [rdi+50h]
0x18001ec1e  mov     [rbp+57h+arg_8], eax
0x18001ec21  mov     rax, [rdi+48h]
0x18001ec25  mov     [rbp+57h+var_48], rax
0x18001ec29  mov     eax, [rdi+20h]
0x18001ec2c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001ec2f  mov     rax, [rdi+18h]
0x18001ec33  mov     [rbp+57h+var_40], rax
0x18001ec37  mov     eax, [rdi]
0x18001ec39  mov     [rbp+57h+arg_18], eax
0x18001ec3c  mov     rax, [rdi+80h]
0x18001ec43  mov     [rbp+57h+var_38], rax
0x18001ec47  mov     eax, [rdi+40h]
0x18001ec4a  mov     [rbp+57h+var_70], eax
0x18001ec4d  mov     rax, [rdi+38h]
0x18001ec51  mov     [rbp+57h+var_30], rax
0x18001ec55  mov     eax, [rdi+8]
0x18001ec58  mov     [rbp+57h+var_6C], eax
0x18001ec5b  mov     eax, 1000000h
0x18001ec60  mov     [rbp+57h+var_28], rax
0x18001ec64  mov     [rbp+57h+var_20], rax
0x18001ec68  mov     r8, [rbx+110h]
0x18001ec6f  add     r8, 8
0x18001ec73  lea     rax, [rbp+57h+var_68]
0x18001ec77  mov     [rsp+110h+var_78], rax
0x18001ec7f  lea     rax, [rbp+57h+var_60]
0x18001ec83  mov     [rsp+110h+var_80], rax
0x18001ec8b  lea     rax, [rbp+57h+SRWLock]
0x18001ec8f  mov     [rsp+110h+var_88], rax
0x18001ec97  lea     rax, [rbp+57h+var_58]
0x18001ec9b  mov     [rsp+110h+var_90], rax
0x18001eca3  lea     rax, [rbp+57h+var_50]
0x18001eca7  mov     [rsp+110h+var_98], rax
0x18001ecac  lea     rax, [rbp+57h+arg_8]
0x18001ecb0  mov     [rsp+110h+var_A0], rax
0x18001ecb5  lea     rax, [rbp+57h+var_48]
0x18001ecb9  mov     [rsp+110h+var_A8], rax
0x18001ecbe  lea     rax, [rbp+57h+arg_10]
0x18001ecc2  mov     [rsp+110h+var_B0], rax
0x18001ecc7  lea     rax, [rbp+57h+var_40]
0x18001eccb  mov     [rsp+110h+var_B8], rax
0x18001ecd0  lea     rax, [rbp+57h+arg_18]
0x18001ecd4  mov     [rsp+110h+var_C0], rax
0x18001ecd9  lea     rax, [rbp+57h+var_38]
0x18001ecdd  mov     [rsp+110h+var_C8], rax
0x18001ece2  lea     rax, [rbp+57h+var_70]
0x18001ece6  mov     [rsp+110h+var_D0], rax
0x18001eceb  lea     rax, [rbp+57h+var_30]
0x18001ecef  mov     [rsp+110h+var_D8], rax
0x18001ecf4  lea     rax, [rbp+57h+var_6C]
0x18001ecf8  mov     [rsp+110h+var_E0], rax
0x18001ecfd  lea     rax, [rbp+57h+var_28]
0x18001ed01  mov     [rsp+110h+var_E8], rax
0x18001ed06  lea     rax, [rbp+57h+var_20]
0x18001ed0a  mov     [rsp+110h+var_F0], rax
0x18001ed0f  lea     rdx, byte_18004430D
0x18001ed16  mov     rcx, r9
0x18001ed19  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001ed1e  jmp     loc_18001EDD5
0x18001ed23  lea     rdx, [rbp+57h+SRWLock]
0x18001ed27  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001ed2c  mov     rax, [rbx+110h]
0x18001ed33  mov     dword ptr [rax], 2
0x18001ed39  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ed3d  test    rcx, rcx
0x18001ed40  jz      short loc_18001ED4E
0x18001ed42  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed49  nop     dword ptr [rax+rax+00h]
0x18001ed4e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001ed53  mov     rdi, [rax+8]
0x18001ed57  mov     eax, [rdi]
0x18001ed59  cmp     eax, 5
0x18001ed5c  jbe     short loc_18001EDD5
0x18001ed5e  mov     rdx, [rdi+18h]
0x18001ed62  mov     rax, [rdi+10h]
0x18001ed66  mov     rcx, 400000000000h
0x18001ed70  test    rcx, rax
0x18001ed73  jz      short loc_18001EDD5
0x18001ed75  mov     rax, rdx
0x18001ed78  and     rax, rcx
0x18001ed7b  cmp     rax, rdx
0x18001ed7e  jnz     short loc_18001EDD5
0x18001ed80  call    cs:__imp_GetCurrentThreadId
0x18001ed87  nop     dword ptr [rax+rax+00h]
0x18001ed8c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001ed8f  mov     r8, [rbx+110h]
0x18001ed96  mov     eax, [r8+48h]
0x18001ed9a  mov     [rbp+57h+arg_8], eax
0x18001ed9d  mov     eax, 1000000h
0x18001eda2  mov     [rbp+57h+arg_10], rax
0x18001eda6  add     r8, 8
0x18001edaa  lea     rax, [rbp+57h+SRWLock]
0x18001edae  mov     [rsp+110h+var_E0], rax
0x18001edb3  lea     rax, [rbp+57h+arg_8]
0x18001edb7  mov     [rsp+110h+var_E8], rax
0x18001edbc  lea     rax, [rbp+57h+arg_10]
0x18001edc0  mov     [rsp+110h+var_F0], rax
0x18001edc5  lea     rdx, byte_1800440A1
0x18001edcc  mov     rcx, rdi
0x18001edcf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001edd4  nop
0x18001edd5  lea     rcx, [rbx+120h]; this
0x18001eddc  cmp     dword ptr [rcx+18h], 0
0x18001ede0  jz      short loc_18001EDE8
0x18001ede2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001ede7  nop
0x18001ede8  add     rsp, 100h
0x18001edef  pop     rdi
0x18001edf0  pop     rbx
0x18001edf1  pop     rbp
0x18001edf2  retn
```
