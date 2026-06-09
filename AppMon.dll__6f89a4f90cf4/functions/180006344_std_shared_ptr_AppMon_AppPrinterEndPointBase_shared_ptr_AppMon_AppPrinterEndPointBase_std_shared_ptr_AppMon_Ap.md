# std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)

- ea: `0x180006344`
- end: `0x180006372`
- name: `??0?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006bb0`
- `0x180008990`
- `0x18000a7f8`
- `0x18000aefc`
- `0x18000af98`
- `0x18000c0cc`

## callees

- `0x180006344`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<AppMon::AppPrinterEndPointBase>::shared_ptr<AppMon::AppPrinterEndPointBase>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x180006344  mov     qword ptr [rcx], 0
0x18000634b  mov     qword ptr [rcx+8], 0
0x180006353  mov     rax, [rdx+8]
0x180006357  test    rax, rax
0x18000635a  jz      short loc_180006360
0x18000635c  lock inc dword ptr [rax+8]
0x180006360  mov     rax, [rdx]
0x180006363  mov     [rcx], rax
0x180006366  mov     rax, [rdx+8]
0x18000636a  mov     [rcx+8], rax
0x18000636e  mov     rax, rcx
0x180006371  retn
```
