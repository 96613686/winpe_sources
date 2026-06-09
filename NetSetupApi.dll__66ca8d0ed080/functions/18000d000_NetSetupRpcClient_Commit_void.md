# NetSetupRpcClient::Commit(void)

- ea: `0x18000d000`
- end: `0x18000d005`
- name: `?Commit@NetSetupRpcClient@@UEAAXXZ`
- size: `5`
- prototype: `void __fastcall(NetSetupRpcClient *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c60`

## pseudocode

```c
// attributes: thunk
void __fastcall NetSetupRpcClient::Commit(NetSetupRpcClient *this)
{
  NetSetupExecuteInRpc__lambda_9a6b294e1b703c5deea7d02723889380_(this);
}

```

## disassembly

```asm
0x18000d000  jmp     NetSetupExecuteInRpc__lambda_9a6b294e1b703c5deea7d02723889380___; NetSetupExecuteInRpc__lambda_9a6b294e1b703c5deea7d02723889380_
```
