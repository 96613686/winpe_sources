# Microsoft::WRL::ComPtr<DockingInputManager>::~ComPtr<DockingInputManager>(void)

- ea: `0x180013450`
- end: `0x180013469`
- name: `??1?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800130c8`

## callees

- `0x180013d68`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<DockingInputManager>::~ComPtr<DockingInputManager>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<DockingInputManager>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180013450  mov     [rsp+arg_0], rcx
0x180013455  sub     rsp, 28h
0x180013459  mov     rcx, [rsp+28h+arg_0]
0x18001345e  call    ?InternalRelease@?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DockingInputManager>::InternalRelease(void)
0x180013463  nop
0x180013464  add     rsp, 28h
0x180013468  retn
```
