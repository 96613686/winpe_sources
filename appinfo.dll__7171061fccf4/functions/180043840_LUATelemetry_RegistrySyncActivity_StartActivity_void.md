# LUATelemetry::RegistrySyncActivity::StartActivity(void)

- ea: `0x180043840`
- end: `0x1800438e3`
- name: `?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ`
- size: `163`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800432a0`

## callees

- `0x18000cc00`
- `0x180011fd0`
- `0x18001a35c`
- `0x18001b23c`
- `0x18001ca6c`
- `0x180026b2c`
- `0x180043840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043877`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::StartActivity(LUATelemetry::RegistrySyncActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  const GUID *v6; // rcx
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 50331648;
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned __int8 *)&dword_1800575BC,
      (const GUID *)(v5 + 8),
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180043840  mov     [rsp+arg_10], rbx
0x180043845  push    rdi
0x180043846  sub     rsp, 30h
0x18004384a  mov     rbx, rcx
0x18004384d  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180043852  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180043857  mov     rdi, rax
0x18004385a  mov     edx, [rax]
0x18004385c  cmp     edx, 5
0x18004385f  jbe     short loc_1800438D1
0x180043861  mov     rdx, 400000000000h
0x18004386b  mov     rcx, rax
0x18004386e  call    _tlgKeywordOn
0x180043873  test    al, al
0x180043875  jz      short loc_1800438D1
0x180043877  call    cs:__imp_GetCurrentThreadId
0x18004387d  mov     r8, [rbx+110h]
0x180043884  mov     [rsp+38h+arg_0], eax
0x180043888  mov     [rsp+38h+arg_8], 3000000h
0x180043891  cmp     byte ptr [r8+4], 0
0x180043896  jz      short loc_1800438A5
0x180043898  lea     rcx, [r8+18h]; struct _GUID *
0x18004389c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800438a1  test    al, al
0x1800438a3  jz      short loc_1800438A7
0x1800438a5  xor     ecx, ecx
0x1800438a7  lea     rax, [rsp+38h+arg_0]
0x1800438ac  mov     r9, rcx
0x1800438af  mov     [rsp+38h+var_10], rax
0x1800438b4  lea     rdx, dword_1800575BC
0x1800438bb  lea     rax, [rsp+38h+arg_8]
0x1800438c0  add     r8, 8
0x1800438c4  mov     rcx, rdi
0x1800438c7  mov     [rsp+38h+var_18], rax
0x1800438cc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800438d1  mov     rcx, rbx
0x1800438d4  mov     rbx, [rsp+38h+arg_10]
0x1800438d9  add     rsp, 30h
0x1800438dd  pop     rdi
0x1800438de  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
