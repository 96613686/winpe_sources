# wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x14000b0f0`
- end: `0x14000b10e`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dfdc`
- `0x14000e0ec`
- `0x14000e1e0`

## callees

- `0x14000b0f0`
- `0x14000d4f0`
- `0x14000e2d4`

## pseudocode

```c
void __fastcall wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x14000b0f0  sub     rsp, 28h
0x14000b0f4  add     rcx, 120h; this
0x14000b0fb  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x14000b100  test    al, al
0x14000b102  jnz     short loc_14000B109
0x14000b104  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14000b109  add     rsp, 28h
0x14000b10d  retn
```
