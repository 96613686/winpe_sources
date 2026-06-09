# CmAgentTraceProvider::UpdateHotPatches::StopActivity(void)

- ea: `0x18001e090`
- end: `0x18001e334`
- name: `?StopActivity@UpdateHotPatches@CmAgentTraceProvider@@MEAAXXZ`
- size: `676`
- prototype: `void __fastcall(CmAgentTraceProvider::UpdateHotPatches *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x1800012bc`
- `0x180006fcc`
- `0x180007088`
- `0x18000907c`
- `0x18001e090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e2c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e2c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e282`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e282`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::UpdateHotPatches::StopActivity(CmAgentTraceProvider::UpdateHotPatches *this)
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
        (__int64)&word_18004414E,
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
        (__int64)&dword_180043BEC,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CmAgentTraceProvider::UpdateHotPatches *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001e090  push    rbp
0x18001e092  push    rbx
0x18001e093  push    rdi
0x18001e094  lea     rbp, [rsp-47h]
0x18001e099  sub     rsp, 100h
0x18001e0a0  mov     rbx, rcx
0x18001e0a3  mov     rdi, [rcx+110h]
0x18001e0aa  mov     eax, [rdi+48h]
0x18001e0ad  test    eax, eax
0x18001e0af  jns     loc_18001E263
0x18001e0b5  add     rdi, 50h ; 'P'
0x18001e0b9  cmp     eax, [rdi+8]
0x18001e0bc  jnz     loc_18001E263
0x18001e0c2  test    rdi, rdi
0x18001e0c5  jz      loc_18001E263
0x18001e0cb  lea     rdx, [rbp+57h+SRWLock]
0x18001e0cf  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e0d4  mov     rax, [rbx+110h]
0x18001e0db  mov     dword ptr [rax], 2
0x18001e0e1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e0e5  test    rcx, rcx
0x18001e0e8  jz      short loc_18001E0F6
0x18001e0ea  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e0f1  nop     dword ptr [rax+rax+00h]
0x18001e0f6  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e0fb  mov     r9, [rax+8]
0x18001e0ff  mov     eax, [r9]
0x18001e102  cmp     eax, 5
0x18001e105  jbe     loc_18001E315
0x18001e10b  mov     rdx, [r9+18h]
0x18001e10f  mov     rax, [r9+10h]
0x18001e113  mov     rcx, 400000000000h
0x18001e11d  test    rcx, rax
0x18001e120  jz      loc_18001E315
0x18001e126  mov     rax, rdx
0x18001e129  and     rax, rcx
0x18001e12c  cmp     rax, rdx
0x18001e12f  jnz     loc_18001E315
0x18001e135  mov     rax, [rdi+78h]
0x18001e139  mov     [rbp+57h+var_68], rax
0x18001e13d  mov     rax, [rdi+70h]
0x18001e141  mov     [rbp+57h+var_60], rax
0x18001e145  mov     eax, [rdi+68h]
0x18001e148  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e14b  mov     rax, [rdi+60h]
0x18001e14f  mov     [rbp+57h+var_58], rax
0x18001e153  mov     rax, [rdi+58h]
0x18001e157  mov     [rbp+57h+var_50], rax
0x18001e15b  mov     eax, [rdi+50h]
0x18001e15e  mov     [rbp+57h+arg_8], eax
0x18001e161  mov     rax, [rdi+48h]
0x18001e165  mov     [rbp+57h+var_48], rax
0x18001e169  mov     eax, [rdi+20h]
0x18001e16c  mov     dword ptr [rbp+57h+arg_10], eax
0x18001e16f  mov     rax, [rdi+18h]
0x18001e173  mov     [rbp+57h+var_40], rax
0x18001e177  mov     eax, [rdi]
0x18001e179  mov     [rbp+57h+arg_18], eax
0x18001e17c  mov     rax, [rdi+80h]
0x18001e183  mov     [rbp+57h+var_38], rax
0x18001e187  mov     eax, [rdi+40h]
0x18001e18a  mov     [rbp+57h+var_70], eax
0x18001e18d  mov     rax, [rdi+38h]
0x18001e191  mov     [rbp+57h+var_30], rax
0x18001e195  mov     eax, [rdi+8]
0x18001e198  mov     [rbp+57h+var_6C], eax
0x18001e19b  mov     eax, 1000000h
0x18001e1a0  mov     [rbp+57h+var_28], rax
0x18001e1a4  mov     [rbp+57h+var_20], rax
0x18001e1a8  mov     r8, [rbx+110h]
0x18001e1af  add     r8, 8
0x18001e1b3  lea     rax, [rbp+57h+var_68]
0x18001e1b7  mov     [rsp+110h+var_78], rax
0x18001e1bf  lea     rax, [rbp+57h+var_60]
0x18001e1c3  mov     [rsp+110h+var_80], rax
0x18001e1cb  lea     rax, [rbp+57h+SRWLock]
0x18001e1cf  mov     [rsp+110h+var_88], rax
0x18001e1d7  lea     rax, [rbp+57h+var_58]
0x18001e1db  mov     [rsp+110h+var_90], rax
0x18001e1e3  lea     rax, [rbp+57h+var_50]
0x18001e1e7  mov     [rsp+110h+var_98], rax
0x18001e1ec  lea     rax, [rbp+57h+arg_8]
0x18001e1f0  mov     [rsp+110h+var_A0], rax
0x18001e1f5  lea     rax, [rbp+57h+var_48]
0x18001e1f9  mov     [rsp+110h+var_A8], rax
0x18001e1fe  lea     rax, [rbp+57h+arg_10]
0x18001e202  mov     [rsp+110h+var_B0], rax
0x18001e207  lea     rax, [rbp+57h+var_40]
0x18001e20b  mov     [rsp+110h+var_B8], rax
0x18001e210  lea     rax, [rbp+57h+arg_18]
0x18001e214  mov     [rsp+110h+var_C0], rax
0x18001e219  lea     rax, [rbp+57h+var_38]
0x18001e21d  mov     [rsp+110h+var_C8], rax
0x18001e222  lea     rax, [rbp+57h+var_70]
0x18001e226  mov     [rsp+110h+var_D0], rax
0x18001e22b  lea     rax, [rbp+57h+var_30]
0x18001e22f  mov     [rsp+110h+var_D8], rax
0x18001e234  lea     rax, [rbp+57h+var_6C]
0x18001e238  mov     [rsp+110h+var_E0], rax
0x18001e23d  lea     rax, [rbp+57h+var_28]
0x18001e241  mov     [rsp+110h+var_E8], rax
0x18001e246  lea     rax, [rbp+57h+var_20]
0x18001e24a  mov     [rsp+110h+var_F0], rax
0x18001e24f  lea     rdx, word_18004414E
0x18001e256  mov     rcx, r9
0x18001e259  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001e25e  jmp     loc_18001E315
0x18001e263  lea     rdx, [rbp+57h+SRWLock]
0x18001e267  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001e26c  mov     rax, [rbx+110h]
0x18001e273  mov     dword ptr [rax], 2
0x18001e279  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001e27d  test    rcx, rcx
0x18001e280  jz      short loc_18001E28E
0x18001e282  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e289  nop     dword ptr [rax+rax+00h]
0x18001e28e  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001e293  mov     rdi, [rax+8]
0x18001e297  mov     eax, [rdi]
0x18001e299  cmp     eax, 5
0x18001e29c  jbe     short loc_18001E315
0x18001e29e  mov     rdx, [rdi+18h]
0x18001e2a2  mov     rax, [rdi+10h]
0x18001e2a6  mov     rcx, 400000000000h
0x18001e2b0  test    rcx, rax
0x18001e2b3  jz      short loc_18001E315
0x18001e2b5  mov     rax, rdx
0x18001e2b8  and     rax, rcx
0x18001e2bb  cmp     rax, rdx
0x18001e2be  jnz     short loc_18001E315
0x18001e2c0  call    cs:__imp_GetCurrentThreadId
0x18001e2c7  nop     dword ptr [rax+rax+00h]
0x18001e2cc  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001e2cf  mov     r8, [rbx+110h]
0x18001e2d6  mov     eax, [r8+48h]
0x18001e2da  mov     [rbp+57h+arg_8], eax
0x18001e2dd  mov     eax, 1000000h
0x18001e2e2  mov     [rbp+57h+arg_10], rax
0x18001e2e6  add     r8, 8
0x18001e2ea  lea     rax, [rbp+57h+SRWLock]
0x18001e2ee  mov     [rsp+110h+var_E0], rax
0x18001e2f3  lea     rax, [rbp+57h+arg_8]
0x18001e2f7  mov     [rsp+110h+var_E8], rax
0x18001e2fc  lea     rax, [rbp+57h+arg_10]
0x18001e300  mov     [rsp+110h+var_F0], rax
0x18001e305  lea     rdx, dword_180043BEC
0x18001e30c  mov     rcx, rdi
0x18001e30f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e314  nop
0x18001e315  lea     rcx, [rbx+120h]; this
0x18001e31c  cmp     dword ptr [rcx+18h], 0
0x18001e320  jz      short loc_18001E328
0x18001e322  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001e327  nop
0x18001e328  add     rsp, 100h
0x18001e32f  pop     rdi
0x18001e330  pop     rbx
0x18001e331  pop     rbp
0x18001e332  retn
```
