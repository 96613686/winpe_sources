# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(void)

- ea: `0x140009460`
- end: `0x140009465`
- name: `?Provider@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005bd4`
- `0x14000ef38`

## callees

- `0x14000946c`

## pseudocode

```c
// attributes: thunk
const struct _tlgProvider_t *__fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(
        __int64 a1)
{
  return DirectXDatabaseUpdaterLogging::Provider(a1);
}

```

## disassembly

```asm
0x140009460  jmp     ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
```
