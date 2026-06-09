# BioIsoProvider::EngineControlUnitPrivileged::StartActivity(void)

- ea: `0x140043da0`
- end: `0x140043e40`
- name: `?StartActivity@EngineControlUnitPrivileged@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::EngineControlUnitPrivileged *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140015420`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140043da0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043dc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043dc2`

## pseudocode

```c
void __fastcall BioIsoProvider::EngineControlUnitPrivileged::StartActivity(
        BioIsoProvider::EngineControlUnitPrivileged *this)
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
      (__int64)word_1400973DA,
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
0x140043da0  mov     [rsp+arg_10], rbx
0x140043da5  push    rdi
0x140043da6  sub     rsp, 30h
0x140043daa  mov     rbx, rcx
0x140043dad  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140043db2  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140043db7  mov     rdi, [rax+8]
0x140043dbb  mov     eax, [rdi]
0x140043dbd  cmp     eax, 5
0x140043dc0  jbe     short loc_140043E2B
0x140043dc2  call    cs:__imp_GetCurrentThreadId
0x140043dc9  nop     dword ptr [rax+rax+00h]
0x140043dce  mov     [rsp+38h+arg_0], eax
0x140043dd2  xor     eax, eax
0x140043dd4  mov     [rsp+38h+arg_8], rax
0x140043dd9  mov     r8, [rbx+110h]
0x140043de0  cmp     [r8+4], al
0x140043de4  jz      short loc_140043E01
0x140043de6  lea     r9, [r8+18h]
0x140043dea  cmp     [r9], eax
0x140043ded  jnz     short loc_140043E04
0x140043def  cmp     [r9+4], eax
0x140043df3  jnz     short loc_140043E04
0x140043df5  cmp     [r9+8], eax
0x140043df9  jnz     short loc_140043E04
0x140043dfb  cmp     [r9+0Ch], eax
0x140043dff  jnz     short loc_140043E04
0x140043e01  mov     r9, rax
0x140043e04  add     r8, 8
0x140043e08  lea     rax, [rsp+38h+arg_0]
0x140043e0d  mov     [rsp+38h+var_10], rax
0x140043e12  lea     rax, [rsp+38h+arg_8]
0x140043e17  mov     [rsp+38h+var_18], rax
0x140043e1c  lea     rdx, word_1400973DA
0x140043e23  mov     rcx, rdi
0x140043e26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140043e2b  mov     rcx, rbx
0x140043e2e  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140043e33  nop
0x140043e34  mov     rbx, [rsp+38h+arg_10]
0x140043e39  add     rsp, 30h
0x140043e3d  pop     rdi
0x140043e3e  retn
```
