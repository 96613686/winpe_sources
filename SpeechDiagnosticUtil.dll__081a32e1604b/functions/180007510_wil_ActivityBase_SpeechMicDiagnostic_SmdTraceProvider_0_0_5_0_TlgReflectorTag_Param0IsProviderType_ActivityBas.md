# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180007510`
- end: `0x180007581`
- name: `??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007828`
- `0x180007854`
- `0x180007880`
- `0x1800078ac`
- `0x1800078d8`
- `0x180007918`
- `0x180007944`
- `0x180007970`
- `0x180007e38`
- `0x180008040`
- `0x180008190`
- `0x1800082d0`
- `0x1800084a0`
- `0x180008d10`
- `0x180008fe0`
- `0x180009330`
- `0x18000d2a0`

## callees

- `0x180002ce0`
- `0x180007510`
- `0x180007588`
- `0x180007a10`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
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
        wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180007510  mov     [rsp+arg_0], rbx
0x180007515  push    rdi
0x180007516  sub     rsp, 20h
0x18000751a  mov     rbx, rcx
0x18000751d  add     rcx, 120h; this
0x180007524  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180007529  mov     rcx, [rbx+118h]
0x180007530  test    rcx, rcx
0x180007533  jz      short loc_18000756E
0x180007535  or      eax, 0FFFFFFFFh
0x180007538  lock xadd [rcx], eax
0x18000753c  cmp     eax, 1
0x18000753f  jnz     short loc_180007563
0x180007541  mov     rdi, [rbx+118h]
0x180007548  test    rdi, rdi
0x18000754b  jz      short loc_180007563
0x18000754d  lea     rcx, [rdi+8]
0x180007551  call    ??1?$ActivityData@VSmdTraceProvider@SpeechMicDiagnostic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180007556  mov     edx, 110h; unsigned __int64
0x18000755b  mov     rcx, rdi; void *
0x18000755e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007563  mov     qword ptr [rbx+118h], 0
0x18000756e  lea     rcx, [rbx+8]
0x180007572  mov     rbx, [rsp+28h+arg_0]
0x180007577  add     rsp, 20h
0x18000757b  pop     rdi
0x18000757c  jmp     ??1?$ActivityData@VSmdTraceProvider@SpeechMicDiagnostic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SpeechMicDiagnostic::SmdTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
```
