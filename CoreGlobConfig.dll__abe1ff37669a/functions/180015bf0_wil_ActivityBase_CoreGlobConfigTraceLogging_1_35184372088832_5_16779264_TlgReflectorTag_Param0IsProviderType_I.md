# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180015bf0`
- end: `0x180015c0f`
- name: `?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019f30`
- `0x18001a010`
- `0x18001a240`
- `0x18001a470`
- `0x18001a6a0`
- `0x18001a8d0`
- `0x18001ab00`
- `0x18001ad30`

## callees

- `0x180015bf0`
- `0x180015d64`
- `0x18001af5c`

## pseudocode

```c
void __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x180015bf0  sub     rsp, 28h
0x180015bf4  add     rcx, 120h; this
0x180015bfb  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x180015c00  test    al, al
0x180015c02  jz      short loc_180015C0A
0x180015c04  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180015c09  nop
0x180015c0a  add     rsp, 28h
0x180015c0e  retn
```
