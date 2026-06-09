# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,>(Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0> * *)

- ea: `0x180006828`
- end: `0x1800068b8`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006770`

## callees

- `0x18000246c`
- `0x180006828`
- `0x1800069e0`
- `0x180006aa8`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>,>(
        __int64 *a1)
{
  void *v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    v4 = Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>(v2);
    v5 = v4;
    v7 = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *a1 = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(&v7);
  return v3;
}

```

## disassembly

```asm
0x180006828  mov     [rsp+arg_8], rbx
0x18000682d  push    rdi
0x18000682e  sub     rsp, 20h
0x180006832  mov     rdi, rcx
0x180006835  mov     qword ptr [rcx], 0
0x18000683c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006843  mov     ecx, 18h; unsigned __int64
0x180006848  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000684d  mov     [rsp+28h+arg_0], rax
0x180006852  test    rax, rax
0x180006855  jnz     short loc_18000685E
0x180006857  mov     ebx, 8007000Eh
0x18000685c  jmp     short loc_1800068A1
0x18000685e  mov     rcx, rax
0x180006861  call    ??0?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>(void)
0x180006866  mov     rbx, rax
0x180006869  mov     [rsp+28h+arg_0], 0
0x180006872  test    rax, rax
0x180006875  jz      short loc_180006887
0x180006877  mov     rcx, [rax]
0x18000687a  mov     rax, [rcx+8]
0x18000687e  mov     rcx, rbx
0x180006881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006886  nop
0x180006887  mov     [rdi], rbx
0x18000688a  test    rbx, rbx
0x18000688d  jz      short loc_18000689F
0x18000688f  mov     rax, [rbx]
0x180006892  mov     rcx, rbx
0x180006895  mov     rax, [rax+10h]
0x180006899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000689e  nop
0x18000689f  xor     ebx, ebx
0x1800068a1  lea     rcx, [rsp+28h+arg_0]
0x1800068a6  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(void)
0x1800068ab  mov     eax, ebx
0x1800068ad  mov     rbx, [rsp+28h+arg_8]
0x1800068b2  add     rsp, 20h
0x1800068b6  pop     rdi
0x1800068b7  retn
```
