# CmAgentTraceProvider::SetupViewOfMappedStorage::StopActivity(void)

- ea: `0x18001dde0`
- end: `0x18001e084`
- name: `?StopActivity@SetupViewOfMappedStorage@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::SetupViewOfMappedStorage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001dde0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001de3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dfd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001de3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dfd2`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::SetupViewOfMappedStorage::StopActivity(
        CmAgentTraceProvider::SetupViewOfMappedStorage *this)
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
        (__int64)&byte_18004492F,
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
        (__int64)&unk_1800434D8,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::SetupViewOfMappedStorage *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001dde0  push    rbp
0x18001dde2  push    rbx
0x18001dde3  push    rdi
0x18001dde4  lea     rbp, [rsp-47h]
0x18001dde9  sub     rsp, 100h
0x18001ddf0  mov     rbx, rcx
0x18001ddf3  mov     rdi, [rcx+110h]
0x18001ddfa  mov     eax, [rdi+48h]
0x18001ddfd  test    eax, eax
0x18001ddff  jns     loc_18001DFB3
0x18001de05  add     rdi, 50h ; 'P'
0x18001de09  cmp     eax, [rdi+8]
0x18001de0c  jnz     loc_18001DFB3
0x18001de12  test    rdi, rdi
0x18001de15  jz      loc_18001DFB3
0x18001de1b  lea     rdx, [rbp+57h+SRWLock]
0x18001de1f  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001de24  mov     rax, [rbx+110h]
0x18001de2b  mov     dword ptr [rax], 2
0x18001de31  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001de35  test    rcx, rcx
0x18001de38  jz      short loc_18001DE46
0x18001de3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001de41  nop     dword ptr [rax+rax+00h]
0x18001de46  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001de4b  mov     r9, [rax+8]
0x18001de4f  mov     eax, [r9]
0x18001de52  cmp     eax, 5
0x18001de55  jbe     loc_18001E065
0x18001de5b  mov     rdx, [r9+18h]
0x18001de5f  mov     rax, [r9+10h]
0x18001de63  mov     rcx, 400000000000h
0x18001de6d  test    rcx, rax
0x18001de70  jz      loc_18001E065
0x18001de76  mov     rax, rdx
0x18001de79  and     rax, rcx
0x18001de7c  cmp     rax, rdx
0x18001de7f  jnz     loc_18001E065
0x18001de85  mov     rax, [rdi+78h]
0x18001de89  mov     [rbp+57h+var_68], rax
0x18001de8d  mov     rax, [rdi+70h]
0x18001de91  mov     [rbp+57h+var_60], rax
0x18001de95  mov     eax, [rdi+68h]
0x18001de98  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001de9b  mov     rax, [rdi+60h]
0x18001de9f  mov     [rbp+57h+var_58], rax
0x18001dea3  mov     rax, [rdi+58h]
0x18001dea7  mov     [rbp+57h+var_50], rax
0x18001deab  mov     eax, [rdi+50h]
0x18001deae  mov     [rbp+57h+arg_8], eax
0x18001deb1  mov     rax, [rdi+48h]
0x18001deb5  mov     [rbp+57h+var_48], rax
0x18001deb9  mov     eax, [rdi+20h]
0x18001debc  mov     dword ptr [rbp+57h+arg_10], eax
0x18001debf  mov     rax, [rdi+18h]
0x18001dec3  mov     [rbp+57h+var_40], rax
0x18001dec7  mov     eax, [rdi]
0x18001dec9  mov     [rbp+57h+arg_18], eax
0x18001decc  mov     rax, [rdi+80h]
0x18001ded3  mov     [rbp+57h+var_38], rax
0x18001ded7  mov     eax, [rdi+40h]
0x18001deda  mov     [rbp+57h+var_70], eax
0x18001dedd  mov     rax, [rdi+38h]
0x18001dee1  mov     [rbp+57h+var_30], rax
0x18001dee5  mov     eax, [rdi+8]
0x18001dee8  mov     [rbp+57h+var_6C], eax
0x18001deeb  mov     eax, 1000000h
0x18001def0  mov     [rbp+57h+var_28], rax
0x18001def4  mov     [rbp+57h+var_20], rax
0x18001def8  mov     r8, [rbx+110h]
0x18001deff  add     r8, 8
0x18001df03  lea     rax, [rbp+57h+var_68]
0x18001df07  mov     [rsp+110h+var_78], rax
0x18001df0f  lea     rax, [rbp+57h+var_60]
0x18001df13  mov     [rsp+110h+var_80], rax
0x18001df1b  lea     rax, [rbp+57h+SRWLock]
0x18001df1f  mov     [rsp+110h+var_88], rax
0x18001df27  lea     rax, [rbp+57h+var_58]
0x18001df2b  mov     [rsp+110h+var_90], rax
0x18001df33  lea     rax, [rbp+57h+var_50]
0x18001df37  mov     [rsp+110h+var_98], rax
0x18001df3c  lea     rax, [rbp+57h+arg_8]
0x18001df40  mov     [rsp+110h+var_A0], rax
0x18001df45  lea     rax, [rbp+57h+var_48]
0x18001df49  mov     [rsp+110h+var_A8], rax
0x18001df4e  lea     rax, [rbp+57h+arg_10]
0x18001df52  mov     [rsp+110h+var_B0], rax
0x18001df57  lea     rax, [rbp+57h+var_40]
0x18001df5b  mov     [rsp+110h+var_B8], rax
0x18001df60  lea     rax, [rbp+57h+arg_18]
0x18001df64  mov     [rsp+110h+var_C0], rax
0x18001df69  lea     rax, [rbp+57h+var_38]
0x18001df6d  mov     [rsp+110h+var_C8], rax
0x18001df72  lea     rax, [rbp+57h+var_70]
0x18001df76  mov     [rsp+110h+var_D0], rax
0x18001df7b  lea     rax, [rbp+57h+var_30]
0x18001df7f  mov     [rsp+110h+var_D8], rax
0x18001df84  lea     rax, [rbp+57h+var_6C]
0x18001df88  mov     [rsp+110h+var_E0], rax
0x18001df8d  lea     rax, [rbp+57h+var_28]
0x18001df91  mov     [rsp+110h+var_E8], rax
0x18001df96  lea     rax, [rbp+57h+var_20]
0x18001df9a  mov     [rsp+110h+var_F0], rax
0x18001df9f  lea     rdx, byte_18004492F
0x18001dfa6  mov     rcx, r9
0x18001dfa9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001dfae  jmp     loc_18001E065
0x18001dfb3  lea     rdx, [rbp+57h+SRWLock]
0x18001dfb7  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001dfbc  mov     rax, [rbx+110h]
0x18001dfc3  mov     dword ptr [rax], 2
0x18001dfc9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001dfcd  test    rcx, rcx
0x18001dfd0  jz      short loc_18001DFDE
0x18001dfd2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dfd9  nop     dword ptr [rax+rax+00h]
0x18001dfde  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001dfe3  mov     rdi, [rax+8]
0x18001dfe7  mov     eax, [rdi]
0x18001dfe9  cmp     eax, 5
0x18001dfec  jbe     short loc_18001E065
0x18001dfee  mov     rdx, [rdi+18h]
0x18001dff2  mov     rax, [rdi+10h]
0x18001dff6  mov     rcx, 400000000000h
0x18001e000  test    rcx, rax
0x18001e003  jz      short loc_18001E065
0x18001e005  mov     rax, rdx
0x18001e008  and     rax, rcx
0x18001e00b  cmp     rax, rdx
0x18001e00e  jnz     short loc_18001E065
0x18001e010  call    cs:__imp_GetCurrentThreadId
0x18001e017  nop     dword ptr [rax+rax+00h]
0x18001e01c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e01f  mov     r8, [rbx+110h]
0x18001e026  mov     eax, [r8+48h]
0x18001e02a  mov     [rbp+57h+arg_8], eax
0x18001e02d  mov     eax, 1000000h
0x18001e032  mov     [rbp+57h+arg_10], rax
0x18001e036  add     r8, 8
0x18001e03a  lea     rax, [rbp+57h+SRWLock]
0x18001e03e  mov     [rsp+110h+var_E0], rax
0x18001e043  lea     rax, [rbp+57h+arg_8]
0x18001e047  mov     [rsp+110h+var_E8], rax
0x18001e04c  lea     rax, [rbp+57h+arg_10]
0x18001e050  mov     [rsp+110h+var_F0], rax
0x18001e055  lea     rdx, unk_1800434D8
0x18001e05c  mov     rcx, rdi
0x18001e05f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e064  nop
0x18001e065  lea     rcx, [rbx+120h]; this
0x18001e06c  cmp     dword ptr [rcx+18h], 0
0x18001e070  jz      short loc_18001E078
0x18001e072  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001e077  nop
0x18001e078  add     rsp, 100h
0x18001e07f  pop     rdi
0x18001e080  pop     rbx
0x18001e081  pop     rbp
0x18001e082  retn
```
