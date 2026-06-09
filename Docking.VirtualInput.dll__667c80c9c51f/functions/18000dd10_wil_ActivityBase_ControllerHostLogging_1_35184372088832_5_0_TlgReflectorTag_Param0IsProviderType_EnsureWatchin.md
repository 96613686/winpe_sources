# wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18000dd10`
- end: `0x18000dd4c`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001139c`
- `0x180017884`

## callees

- `0x18000dd10`
- `0x18000f10c`
- `0x1800114d8`

## pseudocode

```c
void __fastcall wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  const struct wil::FailureInfo *v1; // rdx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v1);
}

```

## disassembly

```asm
0x18000dd10  mov     [rsp+arg_0], rcx
0x18000dd15  sub     rsp, 28h
0x18000dd19  mov     rax, [rsp+28h+arg_0]
0x18000dd1e  add     rax, 120h
0x18000dd24  mov     rcx, rax; this
0x18000dd27  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x18000dd2c  movzx   eax, al
0x18000dd2f  test    eax, eax
0x18000dd31  jnz     short loc_18000DD47
0x18000dd33  mov     rax, [rsp+28h+arg_0]
0x18000dd38  add     rax, 120h
0x18000dd3e  mov     rcx, rax; this
0x18000dd41  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000dd46  nop
0x18000dd47  add     rsp, 28h
0x18000dd4b  retn
```
