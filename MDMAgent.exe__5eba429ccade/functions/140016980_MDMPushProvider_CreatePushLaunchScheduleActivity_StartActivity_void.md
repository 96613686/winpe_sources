# MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(void)

- ea: `0x140016980`
- end: `0x140016a0f`
- name: `?StartActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012bd0`

## callees

- `0x140001628`
- `0x140015b74`
- `0x1400163d8`
- `0x140016980`
- `0x1400173d4`
- `0x14001750c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400169a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400169a1`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
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
      (__int64)&byte_14001FADF,
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
0x140016980  mov     [rsp+arg_10], rbx
0x140016985  push    rdi
0x140016986  sub     rsp, 30h
0x14001698a  mov     rbx, rcx
0x14001698d  call    ?zInternalStart@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140016992  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016997  mov     rdi, rax
0x14001699a  mov     edx, [rax]
0x14001699c  cmp     edx, 5
0x14001699f  jbe     short loc_1400169FB
0x1400169a1  call    cs:__imp_GetCurrentThreadId
0x1400169a7  mov     [rsp+38h+arg_0], eax
0x1400169ab  mov     [rsp+38h+arg_8], 0
0x1400169b4  mov     r8, [rbx+110h]
0x1400169bb  cmp     byte ptr [r8+4], 0
0x1400169c0  jz      short loc_1400169CF
0x1400169c2  lea     rcx, [r8+18h]; struct _GUID *
0x1400169c6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400169cb  test    al, al
0x1400169cd  jz      short loc_1400169D1
0x1400169cf  xor     ecx, ecx
0x1400169d1  add     r8, 8
0x1400169d5  lea     rax, [rsp+38h+arg_0]
0x1400169da  mov     [rsp+38h+var_10], rax
0x1400169df  lea     rax, [rsp+38h+arg_8]
0x1400169e4  mov     [rsp+38h+var_18], rax
0x1400169e9  mov     r9, rcx
0x1400169ec  lea     rdx, byte_14001FADF
0x1400169f3  mov     rcx, rdi
0x1400169f6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400169fb  mov     rcx, rbx
0x1400169fe  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x140016a03  nop
0x140016a04  mov     rbx, [rsp+38h+arg_10]
0x140016a09  add     rsp, 30h
0x140016a0d  pop     rdi
0x140016a0e  retn
```
