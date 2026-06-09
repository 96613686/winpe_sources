# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x140016a00`
- end: `0x140016a20`
- name: `?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140017878`
- `0x140017950`
- `0x140017b90`
- `0x140017dd0`

## callees

- `0x140016a00`
- `0x140016c04`
- `0x140018008`

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
0x140016a00  sub     rsp, 28h
0x140016a04  add     rcx, 120h; this
0x140016a0b  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x140016a10  test    al, al
0x140016a12  jz      short loc_140016A1A
0x140016a14  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140016a19  nop
0x140016a1a  add     rsp, 28h
0x140016a1e  retn
```
