# wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180002fd4`
- end: `0x180003040`
- name: `??1?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `108`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800032d8`

## callees

- `0x180001aa4`
- `0x180002fd4`
- `0x180003048`
- `0x180003460`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
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
        wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180002fd4  mov     [rsp+arg_0], rbx
0x180002fd9  push    rdi
0x180002fda  sub     rsp, 20h
0x180002fde  mov     rbx, rcx
0x180002fe1  add     rcx, 120h; this
0x180002fe8  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180002fed  mov     rcx, [rbx+118h]
0x180002ff4  test    rcx, rcx
0x180002ff7  jz      short loc_18000302D
0x180002ff9  or      eax, 0FFFFFFFFh
0x180002ffc  lock xadd [rcx], eax
0x180003000  cmp     eax, 1
0x180003003  jnz     short loc_180003022
0x180003005  mov     rdi, [rbx+118h]
0x18000300c  test    rdi, rdi
0x18000300f  jz      short loc_180003022
0x180003011  lea     rcx, [rdi+8]
0x180003015  call    ??1?$ActivityData@VEcoScoreTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000301a  mov     rcx, rdi; Block
0x18000301d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003022  mov     qword ptr [rbx+118h], 0
0x18000302d  lea     rcx, [rbx+8]
0x180003031  mov     rbx, [rsp+28h+arg_0]
0x180003036  add     rsp, 20h
0x18000303a  pop     rdi
0x18000303b  jmp     ??1?$ActivityData@VEcoScoreTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
```
