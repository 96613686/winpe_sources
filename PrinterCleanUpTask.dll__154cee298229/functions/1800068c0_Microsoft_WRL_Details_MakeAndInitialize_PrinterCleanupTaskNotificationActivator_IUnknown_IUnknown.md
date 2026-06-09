# Microsoft::WRL::Details::MakeAndInitialize<PrinterCleanupTaskNotificationActivator,IUnknown,>(IUnknown * *)

- ea: `0x1800068c0`
- end: `0x180006979`
- name: `??$MakeAndInitialize@VPrinterCleanupTaskNotificationActivator@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x18000246c`
- `0x1800068c0`
- `0x1800069cc`
- `0x180006aa8`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<PrinterCleanupTaskNotificationActivator,IUnknown,>(
        _QWORD *a1)
{
  void *v2; // rax
  void *v3; // rbx
  unsigned int v4; // edi
  void *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v6 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(v2);
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INotificationActivationCallback>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &PrinterCleanupTaskNotificationActivator::`vftable';
    v6 = 0;
    v4 = ((__int64 (__fastcall *)(void *, GUID *, _QWORD *))PrinterCleanupTaskNotificationActivator::`vftable')(
           v3,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(&v6);
  return v4;
}

```

## disassembly

```asm
0x1800068c0  mov     [rsp+arg_8], rbx
0x1800068c5  push    rdi
0x1800068c6  sub     rsp, 20h
0x1800068ca  mov     rdi, rcx
0x1800068cd  mov     qword ptr [rcx], 0
0x1800068d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800068db  mov     ecx, 10h; unsigned __int64
0x1800068e0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800068e5  mov     rbx, rax
0x1800068e8  mov     [rsp+28h+arg_0], rax
0x1800068ed  test    rax, rax
0x1800068f0  jnz     short loc_1800068F9
0x1800068f2  mov     edi, 8007000Eh
0x1800068f7  jmp     short loc_180006962
0x1800068f9  mov     rcx, rbx
0x1800068fc  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$0A@$0A@$0A@UIClassFactory@@VNil@Details@23@V5623@V5623@V5623@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x180006901  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINotificationActivationCallback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,INotificationActivationCallback>::`vftable'
0x180006908  mov     [rbx], rcx
0x18000690b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006912  test    rcx, rcx
0x180006915  jz      short loc_180006924
0x180006917  mov     rax, [rcx]
0x18000691a  mov     rax, [rax+8]
0x18000691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006923  nop
0x180006924  lea     rax, ??_7PrinterCleanupTaskNotificationActivator@@6B@; const PrinterCleanupTaskNotificationActivator::`vftable'
0x18000692b  mov     [rbx], rax
0x18000692e  mov     [rsp+28h+arg_0], 0
0x180006937  mov     r8, rdi
0x18000693a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006941  mov     rcx, rbx
0x180006944  mov     rax, cs:??_7PrinterCleanupTaskNotificationActivator@@6B@; const PrinterCleanupTaskNotificationActivator::`vftable'
0x18000694b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006950  mov     edi, eax
0x180006952  mov     rcx, [rbx]
0x180006955  mov     rax, [rcx+10h]
0x180006959  mov     rcx, rbx
0x18000695c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006961  nop
0x180006962  lea     rcx, [rsp+28h+arg_0]
0x180006967  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>>(void)
0x18000696c  mov     eax, edi
0x18000696e  mov     rbx, [rsp+28h+arg_8]
0x180006973  add     rsp, 20h
0x180006977  pop     rdi
0x180006978  retn
```
