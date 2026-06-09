# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x140015d70`
- end: `0x140015d8f`
- name: `?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140016bbc`
- `0x140016c90`
- `0x140016ed0`
- `0x140017110`

## callees

- `0x140015d70`
- `0x140015f60`
- `0x140017344`

## pseudocode

```c
void __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x140015d70  sub     rsp, 28h
0x140015d74  add     rcx, 120h; this
0x140015d7b  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x140015d80  test    al, al
0x140015d82  jz      short loc_140015D8A
0x140015d84  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140015d89  nop
0x140015d8a  add     rsp, 28h
0x140015d8e  retn
```
