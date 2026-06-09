# wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14000e620`
- end: `0x14000e63e`
- name: `?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014ac8`
- `0x140014bb0`
- `0x140014eb0`
- `0x1400151b0`
- `0x14001544c`
- `0x1400156b0`
- `0x1400158e0`
- `0x140015b10`
- `0x140015d40`
- `0x140015f70`

## callees

- `0x14000e620`
- `0x14000ea9c`
- `0x14001619c`

## pseudocode

```c
void __fastcall wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x14000e620  sub     rsp, 28h
0x14000e624  add     rcx, 120h; this
0x14000e62b  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x14000e630  test    al, al
0x14000e632  jz      short loc_14000E639
0x14000e634  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14000e639  add     rsp, 28h
0x14000e63d  retn
```
