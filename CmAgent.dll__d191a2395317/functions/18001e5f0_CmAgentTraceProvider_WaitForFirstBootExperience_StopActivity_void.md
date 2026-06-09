# CmAgentTraceProvider::WaitForFirstBootExperience::StopActivity(void)

- ea: `0x18001e5f0`
- end: `0x18001e894`
- name: `?StopActivity@WaitForFirstBootExperience@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::WaitForFirstBootExperience *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001e5f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e820`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e64a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e64a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7e2`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::WaitForFirstBootExperience::StopActivity(
        CmAgentTraceProvider::WaitForFirstBootExperience *this)
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
        (__int64)word_180043A7A,
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
        (__int64)byte_180043751,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::WaitForFirstBootExperience *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001e5f0  push    rbp
0x18001e5f2  push    rbx
0x18001e5f3  push    rdi
0x18001e5f4  lea     rbp, [rsp-47h]
0x18001e5f9  sub     rsp, 100h
0x18001e600  mov     rbx, rcx
0x18001e603  mov     rdi, [rcx+110h]
0x18001e60a  mov     eax, [rdi+48h]
0x18001e60d  test    eax, eax
0x18001e60f  jns     loc_18001E7C3
0x18001e615  add     rdi, 50h ; 'P'
0x18001e619  cmp     eax, [rdi+8]
0x18001e61c  jnz     loc_18001E7C3
0x18001e622  test    rdi, rdi
0x18001e625  jz      loc_18001E7C3
0x18001e62b  lea     rdx, [rbp+57h+SRWLock]
0x18001e62f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e634  mov     rax, [rbx+110h]
0x18001e63b  mov     dword ptr [rax], 2
0x18001e641  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e645  test    rcx, rcx
0x18001e648  jz      short loc_18001E656
0x18001e64a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e651  nop     dword ptr [rax+rax+00h]
0x18001e656  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e65b  mov     r9, [rax+8]
0x18001e65f  mov     eax, [r9]
0x18001e662  cmp     eax, 5
0x18001e665  jbe     loc_18001E875
0x18001e66b  mov     rdx, [r9+18h]
0x18001e66f  mov     rax, [r9+10h]
0x18001e673  mov     rcx, 400000000000h
0x18001e67d  test    rcx, rax
0x18001e680  jz      loc_18001E875
0x18001e686  mov     rax, rdx
0x18001e689  and     rax, rcx
0x18001e68c  cmp     rax, rdx
0x18001e68f  jnz     loc_18001E875
0x18001e695  mov     rax, [rdi+78h]
0x18001e699  mov     [rbp+57h+var_68], rax
0x18001e69d  mov     rax, [rdi+70h]
0x18001e6a1  mov     [rbp+57h+var_60], rax
0x18001e6a5  mov     eax, [rdi+68h]
0x18001e6a8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e6ab  mov     rax, [rdi+60h]
0x18001e6af  mov     [rbp+57h+var_58], rax
0x18001e6b3  mov     rax, [rdi+58h]
0x18001e6b7  mov     [rbp+57h+var_50], rax
0x18001e6bb  mov     eax, [rdi+50h]
0x18001e6be  mov     [rbp+57h+arg_8], eax
0x18001e6c1  mov     rax, [rdi+48h]
0x18001e6c5  mov     [rbp+57h+var_48], rax
0x18001e6c9  mov     eax, [rdi+20h]
0x18001e6cc  mov     dword ptr [rbp+57h+arg_10], eax
0x18001e6cf  mov     rax, [rdi+18h]
0x18001e6d3  mov     [rbp+57h+var_40], rax
0x18001e6d7  mov     eax, [rdi]
0x18001e6d9  mov     [rbp+57h+arg_18], eax
0x18001e6dc  mov     rax, [rdi+80h]
0x18001e6e3  mov     [rbp+57h+var_38], rax
0x18001e6e7  mov     eax, [rdi+40h]
0x18001e6ea  mov     [rbp+57h+var_70], eax
0x18001e6ed  mov     rax, [rdi+38h]
0x18001e6f1  mov     [rbp+57h+var_30], rax
0x18001e6f5  mov     eax, [rdi+8]
0x18001e6f8  mov     [rbp+57h+var_6C], eax
0x18001e6fb  mov     eax, 1000000h
0x18001e700  mov     [rbp+57h+var_28], rax
0x18001e704  mov     [rbp+57h+var_20], rax
0x18001e708  mov     r8, [rbx+110h]
0x18001e70f  add     r8, 8
0x18001e713  lea     rax, [rbp+57h+var_68]
0x18001e717  mov     [rsp+110h+var_78], rax
0x18001e71f  lea     rax, [rbp+57h+var_60]
0x18001e723  mov     [rsp+110h+var_80], rax
0x18001e72b  lea     rax, [rbp+57h+SRWLock]
0x18001e72f  mov     [rsp+110h+var_88], rax
0x18001e737  lea     rax, [rbp+57h+var_58]
0x18001e73b  mov     [rsp+110h+var_90], rax
0x18001e743  lea     rax, [rbp+57h+var_50]
0x18001e747  mov     [rsp+110h+var_98], rax
0x18001e74c  lea     rax, [rbp+57h+arg_8]
0x18001e750  mov     [rsp+110h+var_A0], rax
0x18001e755  lea     rax, [rbp+57h+var_48]
0x18001e759  mov     [rsp+110h+var_A8], rax
0x18001e75e  lea     rax, [rbp+57h+arg_10]
0x18001e762  mov     [rsp+110h+var_B0], rax
0x18001e767  lea     rax, [rbp+57h+var_40]
0x18001e76b  mov     [rsp+110h+var_B8], rax
0x18001e770  lea     rax, [rbp+57h+arg_18]
0x18001e774  mov     [rsp+110h+var_C0], rax
0x18001e779  lea     rax, [rbp+57h+var_38]
0x18001e77d  mov     [rsp+110h+var_C8], rax
0x18001e782  lea     rax, [rbp+57h+var_70]
0x18001e786  mov     [rsp+110h+var_D0], rax
0x18001e78b  lea     rax, [rbp+57h+var_30]
0x18001e78f  mov     [rsp+110h+var_D8], rax
0x18001e794  lea     rax, [rbp+57h+var_6C]
0x18001e798  mov     [rsp+110h+var_E0], rax
0x18001e79d  lea     rax, [rbp+57h+var_28]
0x18001e7a1  mov     [rsp+110h+var_E8], rax
0x18001e7a6  lea     rax, [rbp+57h+var_20]
0x18001e7aa  mov     [rsp+110h+var_F0], rax
0x18001e7af  lea     rdx, word_180043A7A
0x18001e7b6  mov     rcx, r9
0x18001e7b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001e7be  jmp     loc_18001E875
0x18001e7c3  lea     rdx, [rbp+57h+SRWLock]
0x18001e7c7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e7cc  mov     rax, [rbx+110h]
0x18001e7d3  mov     dword ptr [rax], 2
0x18001e7d9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e7dd  test    rcx, rcx
0x18001e7e0  jz      short loc_18001E7EE
0x18001e7e2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e7e9  nop     dword ptr [rax+rax+00h]
0x18001e7ee  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e7f3  mov     rdi, [rax+8]
0x18001e7f7  mov     eax, [rdi]
0x18001e7f9  cmp     eax, 5
0x18001e7fc  jbe     short loc_18001E875
0x18001e7fe  mov     rdx, [rdi+18h]
0x18001e802  mov     rax, [rdi+10h]
0x18001e806  mov     rcx, 400000000000h
0x18001e810  test    rcx, rax
0x18001e813  jz      short loc_18001E875
0x18001e815  mov     rax, rdx
0x18001e818  and     rax, rcx
0x18001e81b  cmp     rax, rdx
0x18001e81e  jnz     short loc_18001E875
0x18001e820  call    cs:__imp_GetCurrentThreadId
0x18001e827  nop     dword ptr [rax+rax+00h]
0x18001e82c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e82f  mov     r8, [rbx+110h]
0x18001e836  mov     eax, [r8+48h]
0x18001e83a  mov     [rbp+57h+arg_8], eax
0x18001e83d  mov     eax, 1000000h
0x18001e842  mov     [rbp+57h+arg_10], rax
0x18001e846  add     r8, 8
0x18001e84a  lea     rax, [rbp+57h+SRWLock]
0x18001e84e  mov     [rsp+110h+var_E0], rax
0x18001e853  lea     rax, [rbp+57h+arg_8]
0x18001e857  mov     [rsp+110h+var_E8], rax
0x18001e85c  lea     rax, [rbp+57h+arg_10]
0x18001e860  mov     [rsp+110h+var_F0], rax
0x18001e865  lea     rdx, byte_180043751
0x18001e86c  mov     rcx, rdi
0x18001e86f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e874  nop
0x18001e875  lea     rcx, [rbx+120h]; this
0x18001e87c  cmp     dword ptr [rcx+18h], 0
0x18001e880  jz      short loc_18001E888
0x18001e882  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001e887  nop
0x18001e888  add     rsp, 100h
0x18001e88f  pop     rdi
0x18001e890  pop     rbx
0x18001e891  pop     rbp
0x18001e892  retn
```
