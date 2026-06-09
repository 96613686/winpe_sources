# wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000ea88`
- end: `0x18000eac4`
- name: `?IgnoreCurrentThread@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `60`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115ac`
- `0x1800117d0`
- `0x1800179c0`

## callees

- `0x18000ea88`
- `0x18000f10c`
- `0x180012358`

## pseudocode

```c
void __fastcall wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000ea88  mov     [rsp+arg_0], rcx
0x18000ea8d  sub     rsp, 28h
0x18000ea91  mov     rax, [rsp+28h+arg_0]
0x18000ea96  add     rax, 120h
0x18000ea9c  mov     rcx, rax; this
0x18000ea9f  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x18000eaa4  movzx   eax, al
0x18000eaa7  test    eax, eax
0x18000eaa9  jz      short loc_18000EABF
0x18000eaab  mov     rax, [rsp+28h+arg_0]
0x18000eab0  add     rax, 120h
0x18000eab6  mov     rcx, rax; this
0x18000eab9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000eabe  nop
0x18000eabf  add     rsp, 28h
0x18000eac3  retn
```
