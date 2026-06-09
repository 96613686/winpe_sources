# std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::allocator<std::shared_ptr<AppMon::AppPrinterEndPointBase>>>(void)

- ea: `0x180006378`
- end: `0x180006389`
- name: `??0?$vector@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@2@@std@@QEAA@XZ`
- size: `17`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011c0`
- `0x180006bb0`
- `0x18000b060`
- `0x18000c0cc`
- `0x18000e718`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x180006378  xor     eax, eax
0x18000637a  mov     [rcx], rax
0x18000637d  mov     [rcx+8], rax
0x180006381  mov     [rcx+10h], rax
0x180006385  mov     rax, rcx
0x180006388  retn
```
