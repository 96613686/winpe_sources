# WnsCPLog::WnsSinkUnadviseCP::StartActivity(void)

- ea: `0x1800337e0`
- end: `0x18003386f`
- name: `?StartActivity@WnsSinkUnadviseCP@WnsCPLog@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(WnsCPLog::WnsSinkUnadviseCP *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180033f38`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180014d80`
- `0x180023dc4`
- `0x1800337e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033801`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkUnadviseCP::StartActivity(WnsCPLog::WnsSinkUnadviseCP *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  const GUID *v4; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4) || _tlgGuidIsZero((const struct _GUID *)(v3 + 24)) )
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (unsigned __int8 *)&dword_180041C5C,
      (const GUID *)(v3 + 8),
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800337e0  mov     [rsp+arg_10], rbx
0x1800337e5  push    rdi
0x1800337e6  sub     rsp, 30h
0x1800337ea  mov     rbx, rcx
0x1800337ed  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800337f2  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800337f7  mov     rdi, rax
0x1800337fa  mov     edx, [rax]
0x1800337fc  cmp     edx, 5
0x1800337ff  jbe     short loc_18003385B
0x180033801  call    cs:__imp_GetCurrentThreadId
0x180033807  mov     [rsp+38h+arg_0], eax
0x18003380b  mov     [rsp+38h+arg_8], 0
0x180033814  mov     r8, [rbx+110h]
0x18003381b  cmp     byte ptr [r8+4], 0
0x180033820  jz      short loc_18003382F
0x180033822  lea     rcx, [r8+18h]; struct _GUID *
0x180033826  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003382b  test    al, al
0x18003382d  jz      short loc_180033831
0x18003382f  xor     ecx, ecx
0x180033831  add     r8, 8
0x180033835  lea     rax, [rsp+38h+arg_0]
0x18003383a  mov     [rsp+38h+var_10], rax
0x18003383f  lea     rax, [rsp+38h+arg_8]
0x180033844  mov     [rsp+38h+var_18], rax
0x180033849  mov     r9, rcx
0x18003384c  lea     rdx, dword_180041C5C
0x180033853  mov     rcx, rdi
0x180033856  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003385b  mov     rcx, rbx
0x18003385e  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180033863  nop
0x180033864  mov     rbx, [rsp+38h+arg_10]
0x180033869  add     rsp, 30h
0x18003386d  pop     rdi
0x18003386e  retn
```
