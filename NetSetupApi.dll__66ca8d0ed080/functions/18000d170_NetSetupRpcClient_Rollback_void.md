# NetSetupRpcClient::Rollback(void)

- ea: `0x18000d170`
- end: `0x18000d175`
- name: `?Rollback@NetSetupRpcClient@@UEAAXXZ`
- size: `5`
- prototype: `void __fastcall(NetSetupRpcClient *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180006068`

## pseudocode

```c
// attributes: thunk
void __fastcall NetSetupRpcClient::Rollback(NetSetupRpcClient *this)
{
  NetSetupExecuteInRpc__lambda_9806d347daf136e94f1ae8d6593d4887_(this);
}

```

## disassembly

```asm
0x18000d170  jmp     NetSetupExecuteInRpc__lambda_9806d347daf136e94f1ae8d6593d4887___; NetSetupExecuteInRpc__lambda_9806d347daf136e94f1ae8d6593d4887_
```
