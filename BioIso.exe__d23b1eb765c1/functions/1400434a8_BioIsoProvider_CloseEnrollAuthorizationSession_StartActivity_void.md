# BioIsoProvider::CloseEnrollAuthorizationSession::StartActivity(void)

- ea: `0x1400434a8`
- end: `0x140043548`
- name: `?StartActivity@CloseEnrollAuthorizationSession@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::CloseEnrollAuthorizationSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140054a80`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x1400434a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400434ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400434ca`

## pseudocode

```c
void __fastcall BioIsoProvider::CloseEnrollAuthorizationSession::StartActivity(
        BioIsoProvider::CloseEnrollAuthorizationSession *this)
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
      (__int64)&dword_1400964DC,
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
0x1400434a8  mov     [rsp+arg_10], rbx
0x1400434ad  push    rdi
0x1400434ae  sub     rsp, 30h
0x1400434b2  mov     rbx, rcx
0x1400434b5  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1400434ba  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400434bf  mov     rdi, [rax+8]
0x1400434c3  mov     eax, [rdi]
0x1400434c5  cmp     eax, 5
0x1400434c8  jbe     short loc_140043533
0x1400434ca  call    cs:__imp_GetCurrentThreadId
0x1400434d1  nop     dword ptr [rax+rax+00h]
0x1400434d6  mov     [rsp+38h+arg_0], eax
0x1400434da  xor     eax, eax
0x1400434dc  mov     [rsp+38h+arg_8], rax
0x1400434e1  mov     r8, [rbx+110h]
0x1400434e8  cmp     [r8+4], al
0x1400434ec  jz      short loc_140043509
0x1400434ee  lea     r9, [r8+18h]
0x1400434f2  cmp     [r9], eax
0x1400434f5  jnz     short loc_14004350C
0x1400434f7  cmp     [r9+4], eax
0x1400434fb  jnz     short loc_14004350C
0x1400434fd  cmp     [r9+8], eax
0x140043501  jnz     short loc_14004350C
0x140043503  cmp     [r9+0Ch], eax
0x140043507  jnz     short loc_14004350C
0x140043509  mov     r9, rax
0x14004350c  add     r8, 8
0x140043510  lea     rax, [rsp+38h+arg_0]
0x140043515  mov     [rsp+38h+var_10], rax
0x14004351a  lea     rax, [rsp+38h+arg_8]
0x14004351f  mov     [rsp+38h+var_18], rax
0x140043524  lea     rdx, dword_1400964DC
0x14004352b  mov     rcx, rdi
0x14004352e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140043533  mov     rcx, rbx
0x140043536  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14004353b  nop
0x14004353c  mov     rbx, [rsp+38h+arg_10]
0x140043541  add     rsp, 30h
0x140043545  pop     rdi
0x140043546  retn
```
