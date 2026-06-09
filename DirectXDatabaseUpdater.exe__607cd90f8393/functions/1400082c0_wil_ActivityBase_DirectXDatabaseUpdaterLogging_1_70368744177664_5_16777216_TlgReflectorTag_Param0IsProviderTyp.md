# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1400082c0`
- end: `0x1400082df`
- name: `?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000b5fc`
- `0x14000b6e4`
- `0x14000b93c`
- `0x14000bb94`
- `0x14000be40`
- `0x14000c070`
- `0x14000c2a0`
- `0x14000c4d0`
- `0x14000c700`
- `0x14000c930`

## callees

- `0x1400082c0`
- `0x14000839c`
- `0x14000cb58`

## pseudocode

```c
void __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x1400082c0  sub     rsp, 28h
0x1400082c4  add     rcx, 120h; this
0x1400082cb  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x1400082d0  test    al, al
0x1400082d2  jz      short loc_1400082DA
0x1400082d4  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400082d9  nop
0x1400082da  add     rsp, 28h
0x1400082de  retn
```
