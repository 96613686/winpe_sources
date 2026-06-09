# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(void)

- ea: `0x180006aa8`
- end: `0x180006abe`
- name: `??1?$MakeAllocator@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006828`
- `0x1800068c0`

## callees

- `0x180002560`
- `0x180006aa8`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180006aa8  sub     rsp, 28h
0x180006aac  mov     rcx, [rcx]; Block
0x180006aaf  test    rcx, rcx
0x180006ab2  jz      short loc_180006AB9
0x180006ab4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ab9  add     rsp, 28h
0x180006abd  retn
```
