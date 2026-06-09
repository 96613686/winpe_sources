# Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>(void)

- ea: `0x1800069e0`
- end: `0x1800069fb`
- name: `??0?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@QEAA@XZ`
- size: `27`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006828`

## callees

- `0x180006980`

## pseudocode

```c
_QWORD *Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>()
{
  _QWORD *v0; // rcx
  _QWORD *result; // rax

  Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>();
  result = v0;
  *v0 = &Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800069e0  sub     rsp, 28h
0x1800069e4  call    ??0?$ClassFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>(void)
0x1800069e9  lea     r9, ??_7?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::`vftable'
0x1800069f0  mov     rax, rcx
0x1800069f3  mov     [rcx], r9
0x1800069f6  add     rsp, 28h
0x1800069fa  retn
```
