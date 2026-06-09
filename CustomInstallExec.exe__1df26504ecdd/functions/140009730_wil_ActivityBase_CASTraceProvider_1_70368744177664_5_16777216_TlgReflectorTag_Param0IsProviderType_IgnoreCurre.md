# wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x140009730`
- end: `0x14000974f`
- name: `?IgnoreCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ad14`
- `0x14000afd4`
- `0x14000b2e0`
- `0x14000b510`

## callees

- `0x140009730`
- `0x140009908`
- `0x14000b738`

## pseudocode

```c
void __fastcall wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x140009730  sub     rsp, 28h
0x140009734  add     rcx, 120h; this
0x14000973b  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x140009740  test    al, al
0x140009742  jz      short loc_14000974A
0x140009744  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x140009749  nop
0x14000974a  add     rsp, 28h
0x14000974e  retn
```
