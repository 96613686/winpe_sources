# Microsoft::WRL::ComPtr<IUnknown>::ReleaseAndGetAddressOf(void)

- ea: `0x1800108d4`
- end: `0x1800108f1`
- name: `?ReleaseAndGetAddressOf@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAPEAPEAUIUnknown@@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cd68`

## callees

- `0x18000601c`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<IUnknown>::ReleaseAndGetAddressOf(__int64 *a1)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  return a1;
}

```

## disassembly

```asm
0x1800108d4  mov     [rsp+arg_0], rcx
0x1800108d9  sub     rsp, 28h
0x1800108dd  mov     rcx, [rsp+28h+arg_0]
0x1800108e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800108e7  mov     rax, [rsp+28h+arg_0]
0x1800108ec  add     rsp, 28h
0x1800108f0  retn
```
