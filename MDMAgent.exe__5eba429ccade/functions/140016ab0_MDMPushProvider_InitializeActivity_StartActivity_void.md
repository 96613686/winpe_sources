# MDMPushProvider::InitializeActivity::StartActivity(void)

- ea: `0x140016ab0`
- end: `0x140016b3f`
- name: `?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140015d98`

## callees

- `0x140001628`
- `0x140015b74`
- `0x1400163d8`
- `0x140016ab0`
- `0x1400173d4`
- `0x14001750c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016ad1`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StartActivity(MDMPushProvider::InitializeActivity *this)
{
  __int64 v2; // rcx
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = MDMPushProvider::Provider(v2);
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v3,
      (__int64)&unk_14001F1E8,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140016ab0  mov     [rsp+arg_10], rbx
0x140016ab5  push    rdi
0x140016ab6  sub     rsp, 30h
0x140016aba  mov     rbx, rcx
0x140016abd  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140016ac2  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016ac7  mov     rdi, rax
0x140016aca  mov     edx, [rax]
0x140016acc  cmp     edx, 5
0x140016acf  jbe     short loc_140016B2B
0x140016ad1  call    cs:__imp_GetCurrentThreadId
0x140016ad7  mov     [rsp+38h+arg_0], eax
0x140016adb  mov     [rsp+38h+arg_8], 0
0x140016ae4  mov     r8, [rbx+110h]
0x140016aeb  cmp     byte ptr [r8+4], 0
0x140016af0  jz      short loc_140016AFF
0x140016af2  lea     rcx, [r8+18h]; struct _GUID *
0x140016af6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140016afb  test    al, al
0x140016afd  jz      short loc_140016B01
0x140016aff  xor     ecx, ecx
0x140016b01  add     r8, 8
0x140016b05  lea     rax, [rsp+38h+arg_0]
0x140016b0a  mov     [rsp+38h+var_10], rax
0x140016b0f  lea     rax, [rsp+38h+arg_8]
0x140016b14  mov     [rsp+38h+var_18], rax
0x140016b19  mov     r9, rcx
0x140016b1c  lea     rdx, unk_14001F1E8
0x140016b23  mov     rcx, rdi
0x140016b26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140016b2b  mov     rcx, rbx
0x140016b2e  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140016b33  nop
0x140016b34  mov     rbx, [rsp+38h+arg_10]
0x140016b39  add     rsp, 30h
0x140016b3d  pop     rdi
0x140016b3e  retn
```
