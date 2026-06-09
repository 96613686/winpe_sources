# BioIsoProvider::CloseKeyAuthorizationSession::StartActivity(void)

- ea: `0x140043550`
- end: `0x1400435f0`
- name: `?StartActivity@CloseKeyAuthorizationSession@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::CloseKeyAuthorizationSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140054b50`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140043550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043572`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043572`

## pseudocode

```c
void __fastcall BioIsoProvider::CloseKeyAuthorizationSession::StartActivity(
        BioIsoProvider::CloseKeyAuthorizationSession *this)
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
      (__int64)&unk_140096350,
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
0x140043550  mov     [rsp+arg_10], rbx
0x140043555  push    rdi
0x140043556  sub     rsp, 30h
0x14004355a  mov     rbx, rcx
0x14004355d  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140043562  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140043567  mov     rdi, [rax+8]
0x14004356b  mov     eax, [rdi]
0x14004356d  cmp     eax, 5
0x140043570  jbe     short loc_1400435DB
0x140043572  call    cs:__imp_GetCurrentThreadId
0x140043579  nop     dword ptr [rax+rax+00h]
0x14004357e  mov     [rsp+38h+arg_0], eax
0x140043582  xor     eax, eax
0x140043584  mov     [rsp+38h+arg_8], rax
0x140043589  mov     r8, [rbx+110h]
0x140043590  cmp     [r8+4], al
0x140043594  jz      short loc_1400435B1
0x140043596  lea     r9, [r8+18h]
0x14004359a  cmp     [r9], eax
0x14004359d  jnz     short loc_1400435B4
0x14004359f  cmp     [r9+4], eax
0x1400435a3  jnz     short loc_1400435B4
0x1400435a5  cmp     [r9+8], eax
0x1400435a9  jnz     short loc_1400435B4
0x1400435ab  cmp     [r9+0Ch], eax
0x1400435af  jnz     short loc_1400435B4
0x1400435b1  mov     r9, rax
0x1400435b4  add     r8, 8
0x1400435b8  lea     rax, [rsp+38h+arg_0]
0x1400435bd  mov     [rsp+38h+var_10], rax
0x1400435c2  lea     rax, [rsp+38h+arg_8]
0x1400435c7  mov     [rsp+38h+var_18], rax
0x1400435cc  lea     rdx, unk_140096350
0x1400435d3  mov     rcx, rdi
0x1400435d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400435db  mov     rcx, rbx
0x1400435de  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1400435e3  nop
0x1400435e4  mov     rbx, [rsp+38h+arg_10]
0x1400435e9  add     rsp, 30h
0x1400435ed  pop     rdi
0x1400435ee  retn
```
