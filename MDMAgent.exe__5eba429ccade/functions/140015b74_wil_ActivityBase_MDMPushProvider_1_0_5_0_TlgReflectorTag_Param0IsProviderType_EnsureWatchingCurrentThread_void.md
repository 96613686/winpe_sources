# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x140015b74`
- end: `0x140015b92`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140016980`
- `0x140016a18`
- `0x140016ab0`

## callees

- `0x140015b74`
- `0x140015f60`
- `0x140016b48`

## pseudocode

```c
void __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x140015b74  sub     rsp, 28h
0x140015b78  add     rcx, 120h; this
0x140015b7f  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x140015b84  test    al, al
0x140015b86  jnz     short loc_140015B8D
0x140015b88  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140015b8d  add     rsp, 28h
0x140015b91  retn
```
