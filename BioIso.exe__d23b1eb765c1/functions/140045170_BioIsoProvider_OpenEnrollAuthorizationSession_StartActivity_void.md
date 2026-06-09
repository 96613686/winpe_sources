# BioIsoProvider::OpenEnrollAuthorizationSession::StartActivity(void)

- ea: `0x140045170`
- end: `0x140045210`
- name: `?StartActivity@OpenEnrollAuthorizationSession@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::OpenEnrollAuthorizationSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140054fd0`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140045170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140045192`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140045192`

## pseudocode

```c
void __fastcall BioIsoProvider::OpenEnrollAuthorizationSession::StartActivity(
        BioIsoProvider::OpenEnrollAuthorizationSession *this)
{
  _DWORD *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = (_DWORD *)*((_QWORD *)BioIsoProvider::Instance() + 1);
  if ( *v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)&word_14009657E,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140045170  mov     [rsp+arg_10], rbx
0x140045175  push    rdi
0x140045176  sub     rsp, 30h
0x14004517a  mov     rbx, rcx
0x14004517d  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140045182  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140045187  mov     rdi, [rax+8]
0x14004518b  mov     eax, [rdi]
0x14004518d  cmp     eax, 5
0x140045190  jbe     short loc_1400451FB
0x140045192  call    cs:__imp_GetCurrentThreadId
0x140045199  nop     dword ptr [rax+rax+00h]
0x14004519e  mov     [rsp+38h+arg_0], eax
0x1400451a2  xor     eax, eax
0x1400451a4  mov     [rsp+38h+arg_8], rax
0x1400451a9  mov     r8, [rbx+110h]
0x1400451b0  cmp     [r8+4], al
0x1400451b4  jz      short loc_1400451D1
0x1400451b6  lea     r9, [r8+18h]
0x1400451ba  cmp     [r9], eax
0x1400451bd  jnz     short loc_1400451D4
0x1400451bf  cmp     [r9+4], eax
0x1400451c3  jnz     short loc_1400451D4
0x1400451c5  cmp     [r9+8], eax
0x1400451c9  jnz     short loc_1400451D4
0x1400451cb  cmp     [r9+0Ch], eax
0x1400451cf  jnz     short loc_1400451D4
0x1400451d1  mov     r9, rax
0x1400451d4  add     r8, 8
0x1400451d8  lea     rax, [rsp+38h+arg_0]
0x1400451dd  mov     [rsp+38h+var_10], rax
0x1400451e2  lea     rax, [rsp+38h+arg_8]
0x1400451e7  mov     [rsp+38h+var_18], rax
0x1400451ec  lea     rdx, word_14009657E
0x1400451f3  mov     rcx, rdi
0x1400451f6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400451fb  mov     rcx, rbx
0x1400451fe  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140045203  nop
0x140045204  mov     rbx, [rsp+38h+arg_10]
0x140045209  add     rsp, 30h
0x14004520d  pop     rdi
0x14004520e  retn
```
