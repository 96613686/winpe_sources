# XinputHid::XinputHidInterface::WorkerThreadThunk(void *)

- ea: `0x180010750`
- end: `0x180010760`
- name: `?WorkerThreadThunk@XinputHidInterface@XinputHid@@CAKPEAX@Z`
- size: `16`
- prototype: `__int64 __fastcall(XinputHid::XinputHidInterface *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f5d4`

## pseudocode

```c
__int64 __fastcall XinputHid::XinputHidInterface::WorkerThreadThunk(XinputHid::XinputHidInterface *Parameter)
{
  XinputHid::XinputHidInterface::DriverManagementWorkerThread(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180010750  sub     rsp, 28h
0x180010754  call    ?DriverManagementWorkerThread@XinputHidInterface@XinputHid@@AEAAXXZ; XinputHid::XinputHidInterface::DriverManagementWorkerThread(void)
0x180010759  xor     eax, eax
0x18001075b  add     rsp, 28h
0x18001075f  retn
```
