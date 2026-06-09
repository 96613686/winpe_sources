# MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(void)

- ea: `0x140017628`
- end: `0x1400176be`
- name: `?StartActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001351c`

## callees

- `0x14000162c`
- `0x1400167e0`
- `0x140017078`
- `0x140017628`
- `0x140018098`
- `0x1400181d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017649`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  int v4; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = MDMPushProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4) || _tlgGuidIsZero((const struct _GUID *)(v3 + 24)) )
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v2,
      (unsigned int)&byte_140020ADF,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x140017628  mov     [rsp+arg_10], rbx
0x14001762d  push    rdi
0x14001762e  sub     rsp, 30h
0x140017632  mov     rbx, rcx
0x140017635  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14001763a  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14001763f  mov     rdi, rax
0x140017642  mov     edx, [rax]
0x140017644  cmp     edx, 5
0x140017647  jbe     short loc_1400176A9
0x140017649  call    cs:__imp_GetCurrentThreadId
0x140017650  nop     dword ptr [rax+rax+00h]
0x140017655  mov     [rsp+38h+arg_0], eax
0x140017659  mov     [rsp+38h+arg_8], 0
0x140017662  mov     r8, [rbx+110h]
0x140017669  cmp     byte ptr [r8+4], 0
0x14001766e  jz      short loc_14001767D
0x140017670  lea     rcx, [r8+18h]; struct _GUID *
0x140017674  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140017679  test    al, al
0x14001767b  jz      short loc_14001767F
0x14001767d  xor     ecx, ecx
0x14001767f  add     r8, 8
0x140017683  lea     rax, [rsp+38h+arg_0]
0x140017688  mov     [rsp+38h+var_10], rax
0x14001768d  lea     rax, [rsp+38h+arg_8]
0x140017692  mov     [rsp+38h+var_18], rax
0x140017697  mov     r9, rcx
0x14001769a  lea     rdx, byte_140020ADF
0x1400176a1  mov     rcx, rdi
0x1400176a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400176a9  mov     rcx, rbx
0x1400176ac  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1400176b1  nop
0x1400176b2  mov     rbx, [rsp+38h+arg_10]
0x1400176b7  add     rsp, 30h
0x1400176bb  pop     rdi
0x1400176bc  retn
```
