# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180010a40`
- end: `0x180010a6f`
- name: `??1?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800118c0`
- `0x180011a6c`
- `0x180011a98`
- `0x180011b4c`
- `0x180011b78`
- `0x180011ba4`
- `0x180011c64`

## callees

- `0x180010a78`
- `0x180011bd0`
- `0x18001eb74`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  wil::details::shared_object<wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(a1 + 280);
  return wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180010a40  push    rbx
0x180010a42  sub     rsp, 20h
0x180010a46  mov     rbx, rcx
0x180010a49  add     rcx, 120h; this
0x180010a50  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180010a55  lea     rcx, [rbx+118h]
0x180010a5c  call    ?reset@?$shared_object@V?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180010a61  lea     rcx, [rbx+8]
0x180010a65  add     rsp, 20h
0x180010a69  pop     rbx
0x180010a6a  jmp     ??1?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
```
