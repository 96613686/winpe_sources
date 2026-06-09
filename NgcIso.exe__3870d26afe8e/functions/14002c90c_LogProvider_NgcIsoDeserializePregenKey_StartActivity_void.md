# LogProvider::NgcIsoDeserializePregenKey::StartActivity(void)

- ea: `0x14002c90c`
- end: `0x14002c99b`
- name: `?StartActivity@NgcIsoDeserializePregenKey@LogProvider@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(LogProvider::NgcIsoDeserializePregenKey *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400259e0`

## callees

- `0x1400030b4`
- `0x14000c558`
- `0x140016428`
- `0x1400173a0`
- `0x14002c90c`
- `0x14003b088`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c92d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c92d`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoDeserializePregenKey::StartActivity(LogProvider::NgcIsoDeserializePregenKey *this)
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
      (unsigned int)&byte_140084927,
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
0x14002c90c  mov     [rsp+arg_10], rbx
0x14002c911  push    rdi
0x14002c912  sub     rsp, 30h
0x14002c916  mov     rbx, rcx
0x14002c919  call    ?zInternalStart@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14002c91e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002c923  mov     rdi, rax
0x14002c926  mov     edx, [rax]
0x14002c928  cmp     edx, 4
0x14002c92b  jbe     short loc_14002C987
0x14002c92d  call    cs:__imp_GetCurrentThreadId
0x14002c933  mov     [rsp+38h+arg_0], eax
0x14002c937  mov     [rsp+38h+arg_8], 0
0x14002c940  mov     r8, [rbx+110h]
0x14002c947  cmp     byte ptr [r8+4], 0
0x14002c94c  jz      short loc_14002C95B
0x14002c94e  lea     rcx, [r8+18h]; struct _GUID *
0x14002c952  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14002c957  test    al, al
0x14002c959  jz      short loc_14002C95D
0x14002c95b  xor     ecx, ecx
0x14002c95d  add     r8, 8
0x14002c961  lea     rax, [rsp+38h+arg_0]
0x14002c966  mov     [rsp+38h+var_10], rax
0x14002c96b  lea     rax, [rsp+38h+arg_8]
0x14002c970  mov     [rsp+38h+var_18], rax
0x14002c975  mov     r9, rcx
0x14002c978  lea     rdx, byte_140084927
0x14002c97f  mov     rcx, rdi
0x14002c982  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14002c987  mov     rcx, rbx
0x14002c98a  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14002c98f  nop
0x14002c990  mov     rbx, [rsp+38h+arg_10]
0x14002c995  add     rsp, 30h
0x14002c999  pop     rdi
0x14002c99a  retn
```
