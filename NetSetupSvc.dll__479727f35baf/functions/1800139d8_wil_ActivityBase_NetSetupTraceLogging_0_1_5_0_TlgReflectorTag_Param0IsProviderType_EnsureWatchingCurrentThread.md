# wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x1800139d8`
- end: `0x1800139f6`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180014400`
- `0x1800144c8`
- `0x180014590`
- `0x180014658`
- `0x180014720`
- `0x1800147e8`
- `0x1800148b0`
- `0x180014978`
- `0x180014a40`
- `0x180014b08`
- `0x180014bd0`
- `0x180014c98`

## callees

- `0x1800139d8`
- `0x180013c14`
- `0x180014d60`

## pseudocode

```c
void __fastcall wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x1800139d8  sub     rsp, 28h
0x1800139dc  add     rcx, 120h; this
0x1800139e3  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x1800139e8  test    al, al
0x1800139ea  jnz     short loc_1800139F1
0x1800139ec  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800139f1  add     rsp, 28h
0x1800139f5  retn
```
