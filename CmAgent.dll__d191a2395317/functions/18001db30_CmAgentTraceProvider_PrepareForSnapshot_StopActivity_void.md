# CmAgentTraceProvider::PrepareForSnapshot::StopActivity(void)

- ea: `0x18001db30`
- end: `0x18001ddd4`
- name: `?StopActivity@PrepareForSnapshot@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::PrepareForSnapshot *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001db30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dd60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dd60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001db8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001db8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd22`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::PrepareForSnapshot::StopActivity(CmAgentTraceProvider::PrepareForSnapshot *this)
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
        (__int64)&byte_180043DFF,
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
        (__int64)&byte_180043A27,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::PrepareForSnapshot *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001db30  push    rbp
0x18001db32  push    rbx
0x18001db33  push    rdi
0x18001db34  lea     rbp, [rsp-47h]
0x18001db39  sub     rsp, 100h
0x18001db40  mov     rbx, rcx
0x18001db43  mov     rdi, [rcx+110h]
0x18001db4a  mov     eax, [rdi+48h]
0x18001db4d  test    eax, eax
0x18001db4f  jns     loc_18001DD03
0x18001db55  add     rdi, 50h ; 'P'
0x18001db59  cmp     eax, [rdi+8]
0x18001db5c  jnz     loc_18001DD03
0x18001db62  test    rdi, rdi
0x18001db65  jz      loc_18001DD03
0x18001db6b  lea     rdx, [rbp+57h+SRWLock]
0x18001db6f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001db74  mov     rax, [rbx+110h]
0x18001db7b  mov     dword ptr [rax], 2
0x18001db81  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001db85  test    rcx, rcx
0x18001db88  jz      short loc_18001DB96
0x18001db8a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001db91  nop     dword ptr [rax+rax+00h]
0x18001db96  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001db9b  mov     r9, [rax+8]
0x18001db9f  mov     eax, [r9]
0x18001dba2  cmp     eax, 5
0x18001dba5  jbe     loc_18001DDB5
0x18001dbab  mov     rdx, [r9+18h]
0x18001dbaf  mov     rax, [r9+10h]
0x18001dbb3  mov     rcx, 400000000000h
0x18001dbbd  test    rcx, rax
0x18001dbc0  jz      loc_18001DDB5
0x18001dbc6  mov     rax, rdx
0x18001dbc9  and     rax, rcx
0x18001dbcc  cmp     rax, rdx
0x18001dbcf  jnz     loc_18001DDB5
0x18001dbd5  mov     rax, [rdi+78h]
0x18001dbd9  mov     [rbp+57h+var_68], rax
0x18001dbdd  mov     rax, [rdi+70h]
0x18001dbe1  mov     [rbp+57h+var_60], rax
0x18001dbe5  mov     eax, [rdi+68h]
0x18001dbe8  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001dbeb  mov     rax, [rdi+60h]
0x18001dbef  mov     [rbp+57h+var_58], rax
0x18001dbf3  mov     rax, [rdi+58h]
0x18001dbf7  mov     [rbp+57h+var_50], rax
0x18001dbfb  mov     eax, [rdi+50h]
0x18001dbfe  mov     [rbp+57h+arg_8], eax
0x18001dc01  mov     rax, [rdi+48h]
0x18001dc05  mov     [rbp+57h+var_48], rax
0x18001dc09  mov     eax, [rdi+20h]
0x18001dc0c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001dc0f  mov     rax, [rdi+18h]
0x18001dc13  mov     [rbp+57h+var_40], rax
0x18001dc17  mov     eax, [rdi]
0x18001dc19  mov     [rbp+57h+arg_18], eax
0x18001dc1c  mov     rax, [rdi+80h]
0x18001dc23  mov     [rbp+57h+var_38], rax
0x18001dc27  mov     eax, [rdi+40h]
0x18001dc2a  mov     [rbp+57h+var_70], eax
0x18001dc2d  mov     rax, [rdi+38h]
0x18001dc31  mov     [rbp+57h+var_30], rax
0x18001dc35  mov     eax, [rdi+8]
0x18001dc38  mov     [rbp+57h+var_6C], eax
0x18001dc3b  mov     eax, 1000000h
0x18001dc40  mov     [rbp+57h+var_28], rax
0x18001dc44  mov     [rbp+57h+var_20], rax
0x18001dc48  mov     r8, [rbx+110h]
0x18001dc4f  add     r8, 8
0x18001dc53  lea     rax, [rbp+57h+var_68]
0x18001dc57  mov     [rsp+110h+var_78], rax
0x18001dc5f  lea     rax, [rbp+57h+var_60]
0x18001dc63  mov     [rsp+110h+var_80], rax
0x18001dc6b  lea     rax, [rbp+57h+SRWLock]
0x18001dc6f  mov     [rsp+110h+var_88], rax
0x18001dc77  lea     rax, [rbp+57h+var_58]
0x18001dc7b  mov     [rsp+110h+var_90], rax
0x18001dc83  lea     rax, [rbp+57h+var_50]
0x18001dc87  mov     [rsp+110h+var_98], rax
0x18001dc8c  lea     rax, [rbp+57h+arg_8]
0x18001dc90  mov     [rsp+110h+var_A0], rax
0x18001dc95  lea     rax, [rbp+57h+var_48]
0x18001dc99  mov     [rsp+110h+var_A8], rax
0x18001dc9e  lea     rax, [rbp+57h+arg_10]
0x18001dca2  mov     [rsp+110h+var_B0], rax
0x18001dca7  lea     rax, [rbp+57h+var_40]
0x18001dcab  mov     [rsp+110h+var_B8], rax
0x18001dcb0  lea     rax, [rbp+57h+arg_18]
0x18001dcb4  mov     [rsp+110h+var_C0], rax
0x18001dcb9  lea     rax, [rbp+57h+var_38]
0x18001dcbd  mov     [rsp+110h+var_C8], rax
0x18001dcc2  lea     rax, [rbp+57h+var_70]
0x18001dcc6  mov     [rsp+110h+var_D0], rax
0x18001dccb  lea     rax, [rbp+57h+var_30]
0x18001dccf  mov     [rsp+110h+var_D8], rax
0x18001dcd4  lea     rax, [rbp+57h+var_6C]
0x18001dcd8  mov     [rsp+110h+var_E0], rax
0x18001dcdd  lea     rax, [rbp+57h+var_28]
0x18001dce1  mov     [rsp+110h+var_E8], rax
0x18001dce6  lea     rax, [rbp+57h+var_20]
0x18001dcea  mov     [rsp+110h+var_F0], rax
0x18001dcef  lea     rdx, byte_180043DFF
0x18001dcf6  mov     rcx, r9
0x18001dcf9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001dcfe  jmp     loc_18001DDB5
0x18001dd03  lea     rdx, [rbp+57h+SRWLock]
0x18001dd07  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001dd0c  mov     rax, [rbx+110h]
0x18001dd13  mov     dword ptr [rax], 2
0x18001dd19  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001dd1d  test    rcx, rcx
0x18001dd20  jz      short loc_18001DD2E
0x18001dd22  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dd29  nop     dword ptr [rax+rax+00h]
0x18001dd2e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001dd33  mov     rdi, [rax+8]
0x18001dd37  mov     eax, [rdi]
0x18001dd39  cmp     eax, 5
0x18001dd3c  jbe     short loc_18001DDB5
0x18001dd3e  mov     rdx, [rdi+18h]
0x18001dd42  mov     rax, [rdi+10h]
0x18001dd46  mov     rcx, 400000000000h
0x18001dd50  test    rcx, rax
0x18001dd53  jz      short loc_18001DDB5
0x18001dd55  mov     rax, rdx
0x18001dd58  and     rax, rcx
0x18001dd5b  cmp     rax, rdx
0x18001dd5e  jnz     short loc_18001DDB5
0x18001dd60  call    cs:__imp_GetCurrentThreadId
0x18001dd67  nop     dword ptr [rax+rax+00h]
0x18001dd6c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001dd6f  mov     r8, [rbx+110h]
0x18001dd76  mov     eax, [r8+48h]
0x18001dd7a  mov     [rbp+57h+arg_8], eax
0x18001dd7d  mov     eax, 1000000h
0x18001dd82  mov     [rbp+57h+arg_10], rax
0x18001dd86  add     r8, 8
0x18001dd8a  lea     rax, [rbp+57h+SRWLock]
0x18001dd8e  mov     [rsp+110h+var_E0], rax
0x18001dd93  lea     rax, [rbp+57h+arg_8]
0x18001dd97  mov     [rsp+110h+var_E8], rax
0x18001dd9c  lea     rax, [rbp+57h+arg_10]
0x18001dda0  mov     [rsp+110h+var_F0], rax
0x18001dda5  lea     rdx, byte_180043A27
0x18001ddac  mov     rcx, rdi
0x18001ddaf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ddb4  nop
0x18001ddb5  lea     rcx, [rbx+120h]; this
0x18001ddbc  cmp     dword ptr [rcx+18h], 0
0x18001ddc0  jz      short loc_18001DDC8
0x18001ddc2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001ddc7  nop
0x18001ddc8  add     rsp, 100h
0x18001ddcf  pop     rdi
0x18001ddd0  pop     rbx
0x18001ddd1  pop     rbp
0x18001ddd2  retn
```
