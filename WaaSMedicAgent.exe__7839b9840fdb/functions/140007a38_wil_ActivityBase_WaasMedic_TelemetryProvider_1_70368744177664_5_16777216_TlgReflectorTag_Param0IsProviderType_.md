# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x140007a38`
- end: `0x140007aa9`
- name: `??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140007c7c`
- `0x140007f3c`
- `0x1400093c0`
- `0x14000a8f0`

## callees

- `0x140002dd8`
- `0x140007a38`
- `0x140007ab0`
- `0x140007ca8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
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
        wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x140007a38  mov     [rsp+arg_0], rbx
0x140007a3d  push    rdi
0x140007a3e  sub     rsp, 20h
0x140007a42  mov     rbx, rcx
0x140007a45  add     rcx, 120h; this
0x140007a4c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140007a51  mov     rcx, [rbx+118h]
0x140007a58  test    rcx, rcx
0x140007a5b  jz      short loc_140007A96
0x140007a5d  or      eax, 0FFFFFFFFh
0x140007a60  lock xadd [rcx], eax
0x140007a64  cmp     eax, 1
0x140007a67  jnz     short loc_140007A8B
0x140007a69  mov     rdi, [rbx+118h]
0x140007a70  test    rdi, rdi
0x140007a73  jz      short loc_140007A8B
0x140007a75  lea     rcx, [rdi+8]
0x140007a79  call    ??1?$ActivityData@VTelemetryProvider@WaasMedic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x140007a7e  mov     edx, 110h
0x140007a83  mov     rcx, rdi; Block
0x140007a86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007a8b  mov     qword ptr [rbx+118h], 0
0x140007a96  lea     rcx, [rbx+8]
0x140007a9a  mov     rbx, [rsp+28h+arg_0]
0x140007a9f  add     rsp, 20h
0x140007aa3  pop     rdi
0x140007aa4  jmp     ??1?$ActivityData@VTelemetryProvider@WaasMedic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
```
