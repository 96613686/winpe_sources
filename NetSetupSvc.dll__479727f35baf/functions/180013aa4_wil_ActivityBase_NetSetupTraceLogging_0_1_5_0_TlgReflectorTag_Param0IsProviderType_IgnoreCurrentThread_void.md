# wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180013aa4`
- end: `0x180013ac3`
- name: `?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `13`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180014dd4`
- `0x180014ec0`
- `0x180015120`
- `0x180015380`
- `0x1800155e0`
- `0x180015840`
- `0x180015aa0`
- `0x180015d00`
- `0x180015f60`
- `0x1800161c0`
- `0x180016420`
- `0x180016680`
- `0x1800168e0`

## callees

- `0x180013aa4`
- `0x180013c14`
- `0x180016b38`

## pseudocode

```c
void __fastcall wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x180013aa4  sub     rsp, 28h
0x180013aa8  add     rcx, 120h; this
0x180013aaf  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x180013ab4  test    al, al
0x180013ab6  jz      short loc_180013ABE
0x180013ab8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180013abd  nop
0x180013abe  add     rsp, 28h
0x180013ac2  retn
```
