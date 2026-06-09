# Microsoft::WRL::ComPtr<TimeUpdate>::~ComPtr<TimeUpdate>(void)

- ea: `0x1800053c4`
- end: `0x1800053c9`
- name: `??1?$ComPtr@VTimeUpdate@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800111ee`

## callees

- `0x180007a30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<TimeUpdate>::~ComPtr<TimeUpdate>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800053c4  jmp     ?InternalRelease@?$ComPtr@VTimeUpdate@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease(void)
```
