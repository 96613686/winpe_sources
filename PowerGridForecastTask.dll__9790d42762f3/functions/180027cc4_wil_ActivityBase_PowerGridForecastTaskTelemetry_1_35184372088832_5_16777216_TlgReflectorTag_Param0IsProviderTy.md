# wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180027cc4`
- end: `0x180027d31`
- name: `??1?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `109`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180028468`

## callees

- `0x180027cc4`
- `0x180027d38`
- `0x1800286d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027d0d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027d0d`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rcx
  char *v3; // rdi

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v2 = *(volatile signed __int32 **)(a1 + 280);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *(char **)(a1 + 280);
      if ( v3 )
      {
        wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180027cc4  mov     [rsp+arg_0], rbx
0x180027cc9  push    rdi
0x180027cca  sub     rsp, 20h
0x180027cce  mov     rbx, rcx
0x180027cd1  add     rcx, 120h; this
0x180027cd8  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180027cdd  mov     rcx, [rbx+118h]
0x180027ce4  test    rcx, rcx
0x180027ce7  jz      short loc_180027D1E
0x180027ce9  or      eax, 0FFFFFFFFh
0x180027cec  lock xadd [rcx], eax
0x180027cf0  cmp     eax, 1
0x180027cf3  jnz     short loc_180027D13
0x180027cf5  mov     rdi, [rbx+118h]
0x180027cfc  test    rdi, rdi
0x180027cff  jz      short loc_180027D13
0x180027d01  lea     rcx, [rdi+8]
0x180027d05  call    ??1?$ActivityData@VPowerGridForecastTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x180027d0a  mov     rcx, rdi
0x180027d0d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027d13  mov     qword ptr [rbx+118h], 0
0x180027d1e  lea     rcx, [rbx+8]
0x180027d22  mov     rbx, [rsp+28h+arg_0]
0x180027d27  add     rsp, 20h
0x180027d2b  pop     rdi
0x180027d2c  jmp     ??1?$ActivityData@VPowerGridForecastTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
```
