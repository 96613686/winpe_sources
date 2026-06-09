# LUATelemetry::RegistrySyncActivity::StartActivity(void)

- ea: `0x180040ca0`
- end: `0x180040d48`
- name: `?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ`
- size: `168`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180040730`

## callees

- `0x18000cb30`
- `0x18000d7f0`
- `0x1800187ec`
- `0x18001ef50`
- `0x18001fd94`
- `0x180023064`
- `0x180040ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cd6`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::StartActivity(LUATelemetry::RegistrySyncActivity *this)
{
  struct LUATelemetry *v2; // rax
  _DWORD *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // ecx
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Instance();
  v3 = (_DWORD *)*((_QWORD *)v2 + 1);
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v2 + 1), 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 50331648;
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v3,
      (unsigned int)&unk_18005395B,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180040ca0  mov     [rsp+arg_10], rbx
0x180040ca5  push    rdi
0x180040ca6  sub     rsp, 30h
0x180040caa  mov     rbx, rcx
0x180040cad  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040cb2  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040cb7  mov     rdi, [rax+8]
0x180040cbb  cmp     dword ptr [rdi], 5
0x180040cbe  jbe     short loc_180040D36
0x180040cc0  mov     rdx, 400000000000h
0x180040cca  mov     rcx, rdi
0x180040ccd  call    _tlgKeywordOn
0x180040cd2  test    al, al
0x180040cd4  jz      short loc_180040D36
0x180040cd6  call    cs:__imp_GetCurrentThreadId
0x180040cdd  nop     dword ptr [rax+rax+00h]
0x180040ce2  mov     r8, [rbx+110h]
0x180040ce9  mov     [rsp+38h+arg_0], eax
0x180040ced  mov     [rsp+38h+arg_8], 3000000h
0x180040cf6  cmp     byte ptr [r8+4], 0
0x180040cfb  jz      short loc_180040D0A
0x180040cfd  lea     rcx, [r8+18h]; struct _GUID *
0x180040d01  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180040d06  test    al, al
0x180040d08  jz      short loc_180040D0C
0x180040d0a  xor     ecx, ecx
0x180040d0c  lea     rax, [rsp+38h+arg_0]
0x180040d11  mov     r9, rcx
0x180040d14  mov     [rsp+38h+var_10], rax
0x180040d19  lea     rdx, unk_18005395B
0x180040d20  lea     rax, [rsp+38h+arg_8]
0x180040d25  add     r8, 8
0x180040d29  mov     rcx, rdi
0x180040d2c  mov     [rsp+38h+var_18], rax
0x180040d31  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180040d36  mov     rcx, rbx
0x180040d39  mov     rbx, [rsp+38h+arg_10]
0x180040d3e  add     rsp, 30h
0x180040d42  pop     rdi
0x180040d43  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
