# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000a1b4`
- end: `0x18000a1d0`
- name: `?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000baa4`
- `0x18000bb90`

## callees

- `0x180006c74`
- `0x18000a1b4`

## pseudocode

```c
void __fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  v1 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( *((_DWORD *)v1 + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x18000a1b4  sub     rsp, 28h
0x18000a1b8  add     rcx, 120h; this
0x18000a1bf  cmp     dword ptr [rcx+18h], 0
0x18000a1c3  jz      short loc_18000A1CB
0x18000a1c5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000a1ca  nop
0x18000a1cb  add     rsp, 28h
0x18000a1cf  retn
```
