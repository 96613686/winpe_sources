# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000dcdc`
- end: `0x18000dd4d`
- name: `??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000de74`
- `0x18000dea0`
- `0x18000e9e8`
- `0x18000edbc`
- `0x180010444`

## callees

- `0x180002f90`
- `0x18000dcdc`
- `0x18000dd54`
- `0x18000def8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
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
        wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3, 0x110u);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x18000dcdc  mov     [rsp+arg_0], rbx
0x18000dce1  push    rdi
0x18000dce2  sub     rsp, 20h
0x18000dce6  mov     rbx, rcx
0x18000dce9  add     rcx, 120h; this
0x18000dcf0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000dcf5  mov     rcx, [rbx+118h]
0x18000dcfc  test    rcx, rcx
0x18000dcff  jz      short loc_18000DD3A
0x18000dd01  or      eax, 0FFFFFFFFh
0x18000dd04  lock xadd [rcx], eax
0x18000dd08  cmp     eax, 1
0x18000dd0b  jnz     short loc_18000DD2F
0x18000dd0d  mov     rdi, [rbx+118h]
0x18000dd14  test    rdi, rdi
0x18000dd17  jz      short loc_18000DD2F
0x18000dd19  lea     rcx, [rdi+8]
0x18000dd1d  call    ??1?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000dd22  mov     edx, 110h; unsigned __int64
0x18000dd27  mov     rcx, rdi; void *
0x18000dd2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dd2f  mov     qword ptr [rbx+118h], 0
0x18000dd3a  lea     rcx, [rbx+8]
0x18000dd3e  mov     rbx, [rsp+28h+arg_0]
0x18000dd43  add     rsp, 20h
0x18000dd47  pop     rdi
0x18000dd48  jmp     ??1?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(void)
```
