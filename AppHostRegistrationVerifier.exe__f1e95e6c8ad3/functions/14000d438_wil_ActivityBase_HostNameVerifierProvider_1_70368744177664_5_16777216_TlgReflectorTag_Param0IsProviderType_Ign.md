# wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14000d438`
- end: `0x14000d457`
- name: `?IgnoreCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e348`
- `0x14000e430`
- `0x14000e660`
- `0x14000e890`

## callees

- `0x14000d438`
- `0x14000d4f0`
- `0x14000eab8`

## pseudocode

```c
void __fastcall wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x14000d438  sub     rsp, 28h
0x14000d43c  add     rcx, 120h; this
0x14000d443  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x14000d448  test    al, al
0x14000d44a  jz      short loc_14000D452
0x14000d44c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14000d451  nop
0x14000d452  add     rsp, 28h
0x14000d456  retn
```
