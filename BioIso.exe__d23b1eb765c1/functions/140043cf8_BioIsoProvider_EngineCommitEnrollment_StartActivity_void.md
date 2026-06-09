# BioIsoProvider::EngineCommitEnrollment::StartActivity(void)

- ea: `0x140043cf8`
- end: `0x140043d98`
- name: `?StartActivity@EngineCommitEnrollment@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::EngineCommitEnrollment *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400098b0`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140043cf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043d1a`

## pseudocode

```c
void __fastcall BioIsoProvider::EngineCommitEnrollment::StartActivity(BioIsoProvider::EngineCommitEnrollment *this)
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
      (__int64)&dword_14009747C,
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
0x140043cf8  mov     [rsp+arg_10], rbx
0x140043cfd  push    rdi
0x140043cfe  sub     rsp, 30h
0x140043d02  mov     rbx, rcx
0x140043d05  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140043d0a  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140043d0f  mov     rdi, [rax+8]
0x140043d13  mov     eax, [rdi]
0x140043d15  cmp     eax, 5
0x140043d18  jbe     short loc_140043D83
0x140043d1a  call    cs:__imp_GetCurrentThreadId
0x140043d21  nop     dword ptr [rax+rax+00h]
0x140043d26  mov     [rsp+38h+arg_0], eax
0x140043d2a  xor     eax, eax
0x140043d2c  mov     [rsp+38h+arg_8], rax
0x140043d31  mov     r8, [rbx+110h]
0x140043d38  cmp     [r8+4], al
0x140043d3c  jz      short loc_140043D59
0x140043d3e  lea     r9, [r8+18h]
0x140043d42  cmp     [r9], eax
0x140043d45  jnz     short loc_140043D5C
0x140043d47  cmp     [r9+4], eax
0x140043d4b  jnz     short loc_140043D5C
0x140043d4d  cmp     [r9+8], eax
0x140043d51  jnz     short loc_140043D5C
0x140043d53  cmp     [r9+0Ch], eax
0x140043d57  jnz     short loc_140043D5C
0x140043d59  mov     r9, rax
0x140043d5c  add     r8, 8
0x140043d60  lea     rax, [rsp+38h+arg_0]
0x140043d65  mov     [rsp+38h+var_10], rax
0x140043d6a  lea     rax, [rsp+38h+arg_8]
0x140043d6f  mov     [rsp+38h+var_18], rax
0x140043d74  lea     rdx, dword_14009747C
0x140043d7b  mov     rcx, rdi
0x140043d7e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140043d83  mov     rcx, rbx
0x140043d86  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140043d8b  nop
0x140043d8c  mov     rbx, [rsp+38h+arg_10]
0x140043d91  add     rsp, 30h
0x140043d95  pop     rdi
0x140043d96  retn
```
