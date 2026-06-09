# MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(void)

- ea: `0x140016a18`
- end: `0x140016aa7`
- name: `?StartActivity@CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001464c`

## callees

- `0x140001628`
- `0x140015b74`
- `0x1400163d8`
- `0x140016a18`
- `0x1400173d4`
- `0x14001750c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016a39`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
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
      (__int64)byte_14001F4CB,
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
0x140016a18  mov     [rsp+arg_10], rbx
0x140016a1d  push    rdi
0x140016a1e  sub     rsp, 30h
0x140016a22  mov     rbx, rcx
0x140016a25  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140016a2a  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016a2f  mov     rdi, rax
0x140016a32  mov     edx, [rax]
0x140016a34  cmp     edx, 5
0x140016a37  jbe     short loc_140016A93
0x140016a39  call    cs:__imp_GetCurrentThreadId
0x140016a3f  mov     [rsp+38h+arg_0], eax
0x140016a43  mov     [rsp+38h+arg_8], 0
0x140016a4c  mov     r8, [rbx+110h]
0x140016a53  cmp     byte ptr [r8+4], 0
0x140016a58  jz      short loc_140016A67
0x140016a5a  lea     rcx, [r8+18h]; struct _GUID *
0x140016a5e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140016a63  test    al, al
0x140016a65  jz      short loc_140016A69
0x140016a67  xor     ecx, ecx
0x140016a69  add     r8, 8
0x140016a6d  lea     rax, [rsp+38h+arg_0]
0x140016a72  mov     [rsp+38h+var_10], rax
0x140016a77  lea     rax, [rsp+38h+arg_8]
0x140016a7c  mov     [rsp+38h+var_18], rax
0x140016a81  mov     r9, rcx
0x140016a84  lea     rdx, byte_14001F4CB
0x140016a8b  mov     rcx, rdi
0x140016a8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140016a93  mov     rcx, rbx
0x140016a96  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140016a9b  nop
0x140016a9c  mov     rbx, [rsp+38h+arg_10]
0x140016aa1  add     rsp, 30h
0x140016aa5  pop     rdi
0x140016aa6  retn
```
