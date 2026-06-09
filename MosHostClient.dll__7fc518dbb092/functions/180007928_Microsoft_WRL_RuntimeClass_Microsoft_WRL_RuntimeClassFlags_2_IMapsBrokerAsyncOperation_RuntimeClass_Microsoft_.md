# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>(void)

- ea: `0x180007928`
- end: `0x180007930`
- name: `??1?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMapsBrokerAsyncOperation@@@WRL@Microsoft@@UEAA@XZ`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800111e7`

## pseudocode

```c
void __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 12) = -1073741823;
}

```

## disassembly

```asm
0x180007928  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000792f  retn
```
