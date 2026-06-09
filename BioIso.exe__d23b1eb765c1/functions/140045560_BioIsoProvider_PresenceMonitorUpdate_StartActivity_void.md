# BioIsoProvider::PresenceMonitorUpdate::StartActivity(void)

- ea: `0x140045560`
- end: `0x140045600`
- name: `?StartActivity@PresenceMonitorUpdate@BioIsoProvider@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(BioIsoProvider::PresenceMonitorUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140014720`

## callees

- `0x1400020dc`
- `0x14000d990`
- `0x14000e3f4`
- `0x140013784`
- `0x140045560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140045582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140045582`

## pseudocode

```c
void __fastcall BioIsoProvider::PresenceMonitorUpdate::StartActivity(BioIsoProvider::PresenceMonitorUpdate *this)
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
      (__int64)&byte_14009671F,
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
0x140045560  mov     [rsp+arg_10], rbx
0x140045565  push    rdi
0x140045566  sub     rsp, 30h
0x14004556a  mov     rbx, rcx
0x14004556d  call    ?zInternalStart@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140045572  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140045577  mov     rdi, [rax+8]
0x14004557b  mov     eax, [rdi]
0x14004557d  cmp     eax, 5
0x140045580  jbe     short loc_1400455EB
0x140045582  call    cs:__imp_GetCurrentThreadId
0x140045589  nop     dword ptr [rax+rax+00h]
0x14004558e  mov     [rsp+38h+arg_0], eax
0x140045592  xor     eax, eax
0x140045594  mov     [rsp+38h+arg_8], rax
0x140045599  mov     r8, [rbx+110h]
0x1400455a0  cmp     [r8+4], al
0x1400455a4  jz      short loc_1400455C1
0x1400455a6  lea     r9, [r8+18h]
0x1400455aa  cmp     [r9], eax
0x1400455ad  jnz     short loc_1400455C4
0x1400455af  cmp     [r9+4], eax
0x1400455b3  jnz     short loc_1400455C4
0x1400455b5  cmp     [r9+8], eax
0x1400455b9  jnz     short loc_1400455C4
0x1400455bb  cmp     [r9+0Ch], eax
0x1400455bf  jnz     short loc_1400455C4
0x1400455c1  mov     r9, rax
0x1400455c4  add     r8, 8
0x1400455c8  lea     rax, [rsp+38h+arg_0]
0x1400455cd  mov     [rsp+38h+var_10], rax
0x1400455d2  lea     rax, [rsp+38h+arg_8]
0x1400455d7  mov     [rsp+38h+var_18], rax
0x1400455dc  lea     rdx, byte_14009671F
0x1400455e3  mov     rcx, rdi
0x1400455e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400455eb  mov     rcx, rbx
0x1400455ee  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1400455f3  nop
0x1400455f4  mov     rbx, [rsp+38h+arg_10]
0x1400455f9  add     rsp, 30h
0x1400455fd  pop     rdi
0x1400455fe  retn
```
