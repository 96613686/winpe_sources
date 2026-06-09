# MSAClientTraceTelemetry::DisconnectAccountOobe::StartActivity(void)

- ea: `0x180017d10`
- end: `0x180017dc9`
- name: `?StartActivity@DisconnectAccountOobe@MSAClientTraceTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(MSAClientTraceTelemetry::DisconnectAccountOobe *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180013e54`

## callees

- `0x180001d58`
- `0x180001f90`
- `0x1800145e0`
- `0x18001610c`
- `0x180017d10`
- `0x18001b9f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d4b`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::DisconnectAccountOobe::StartActivity(
        MSAClientTraceTelemetry::DisconnectAccountOobe *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = MSAClientTraceTelemetry::Provider();
  v4 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL, v3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0x2000000;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)byte_1800462C3,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180017d10  mov     [rsp+arg_10], rbx
0x180017d15  push    rdi
0x180017d16  sub     rsp, 30h
0x180017d1a  mov     rbx, rcx
0x180017d1d  call    ?zInternalStart@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180017d22  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180017d27  mov     rdi, rax
0x180017d2a  mov     edx, [rax]
0x180017d2c  cmp     edx, 5
0x180017d2f  jbe     loc_180017DB5
0x180017d35  mov     rdx, 400000000000h
0x180017d3f  mov     rcx, rax
0x180017d42  call    _tlgKeywordOn
0x180017d47  test    al, al
0x180017d49  jz      short loc_180017DB5
0x180017d4b  call    cs:__imp_GetCurrentThreadId
0x180017d51  mov     [rsp+38h+arg_0], eax
0x180017d55  mov     [rsp+38h+arg_8], 2000000h
0x180017d5e  mov     r8, [rbx+110h]
0x180017d65  cmp     byte ptr [r8+4], 0
0x180017d6a  jz      short loc_180017D8B
0x180017d6c  lea     r9, [r8+18h]
0x180017d70  cmp     dword ptr [r9], 0
0x180017d74  jnz     short loc_180017D8E
0x180017d76  cmp     dword ptr [r9+4], 0
0x180017d7b  jnz     short loc_180017D8E
0x180017d7d  cmp     dword ptr [r9+8], 0
0x180017d82  jnz     short loc_180017D8E
0x180017d84  cmp     dword ptr [r9+0Ch], 0
0x180017d89  jnz     short loc_180017D8E
0x180017d8b  xor     r9d, r9d
0x180017d8e  add     r8, 8
0x180017d92  lea     rax, [rsp+38h+arg_0]
0x180017d97  mov     [rsp+38h+var_10], rax
0x180017d9c  lea     rax, [rsp+38h+arg_8]
0x180017da1  mov     [rsp+38h+var_18], rax
0x180017da6  lea     rdx, byte_1800462C3
0x180017dad  mov     rcx, rdi
0x180017db0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180017db5  mov     rcx, rbx
0x180017db8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180017dbd  nop
0x180017dbe  mov     rbx, [rsp+38h+arg_10]
0x180017dc3  add     rsp, 30h
0x180017dc7  pop     rdi
0x180017dc8  retn
```
