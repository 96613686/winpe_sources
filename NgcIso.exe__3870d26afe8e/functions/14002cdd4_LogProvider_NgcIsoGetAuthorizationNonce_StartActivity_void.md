# LogProvider::NgcIsoGetAuthorizationNonce::StartActivity(void)

- ea: `0x14002cdd4`
- end: `0x14002ce63`
- name: `?StartActivity@NgcIsoGetAuthorizationNonce@LogProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(LogProvider::NgcIsoGetAuthorizationNonce *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140026780`

## callees

- `0x1400030b4`
- `0x14000c558`
- `0x140016428`
- `0x1400173a0`
- `0x14002cdd4`
- `0x14003b088`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002cdf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002cdf5`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetAuthorizationNonce::StartActivity(LogProvider::NgcIsoGetAuthorizationNonce *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LogProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)word_140084182,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x14002cdd4  mov     [rsp+arg_10], rbx
0x14002cdd9  push    rdi
0x14002cdda  sub     rsp, 30h
0x14002cdde  mov     rbx, rcx
0x14002cde1  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14002cde6  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002cdeb  mov     rdi, rax
0x14002cdee  mov     edx, [rax]
0x14002cdf0  cmp     edx, 4
0x14002cdf3  jbe     short loc_14002CE4F
0x14002cdf5  call    cs:__imp_GetCurrentThreadId
0x14002cdfb  mov     [rsp+38h+arg_0], eax
0x14002cdff  mov     [rsp+38h+arg_8], 0
0x14002ce08  mov     r8, [rbx+110h]
0x14002ce0f  cmp     byte ptr [r8+4], 0
0x14002ce14  jz      short loc_14002CE23
0x14002ce16  lea     rcx, [r8+18h]; struct _GUID *
0x14002ce1a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14002ce1f  test    al, al
0x14002ce21  jz      short loc_14002CE25
0x14002ce23  xor     ecx, ecx
0x14002ce25  add     r8, 8
0x14002ce29  lea     rax, [rsp+38h+arg_0]
0x14002ce2e  mov     [rsp+38h+var_10], rax
0x14002ce33  lea     rax, [rsp+38h+arg_8]
0x14002ce38  mov     [rsp+38h+var_18], rax
0x14002ce3d  mov     r9, rcx
0x14002ce40  lea     rdx, word_140084182
0x14002ce47  mov     rcx, rdi
0x14002ce4a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14002ce4f  mov     rcx, rbx
0x14002ce52  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14002ce57  nop
0x14002ce58  mov     rbx, [rsp+38h+arg_10]
0x14002ce5d  add     rsp, 30h
0x14002ce61  pop     rdi
0x14002ce62  retn
```
