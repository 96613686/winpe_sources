# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x1800145ec`
- end: `0x18001460a`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001997c`
- `0x180019a3c`
- `0x180019afc`
- `0x180019bbc`
- `0x180019c7c`
- `0x180019d3c`
- `0x180019dfc`

## callees

- `0x1800145ec`
- `0x180015d64`
- `0x180019ebc`

## pseudocode

```c
void __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x1800145ec  sub     rsp, 28h
0x1800145f0  add     rcx, 120h; this
0x1800145f7  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x1800145fc  test    al, al
0x1800145fe  jnz     short loc_180014605
0x180014600  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180014605  add     rsp, 28h
0x180014609  retn
```
