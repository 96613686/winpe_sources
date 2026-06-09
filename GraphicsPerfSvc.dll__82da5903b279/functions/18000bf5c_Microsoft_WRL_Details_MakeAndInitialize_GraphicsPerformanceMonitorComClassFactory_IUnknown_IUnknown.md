# Microsoft::WRL::Details::MakeAndInitialize<GraphicsPerformanceMonitorComClassFactory,IUnknown,>(IUnknown * *)

- ea: `0x18000bf5c`
- end: `0x18000bfe7`
- name: `??$MakeAndInitialize@VGraphicsPerformanceMonitorComClassFactory@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d908`

## callees

- `0x180003f00`
- `0x18000bf5c`
- `0x18000c430`
- `0x18000c4fc`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<GraphicsPerformanceMonitorComClassFactory,IUnknown,>(
        _QWORD *a1)
{
  GraphicsPerformanceMonitorComClassFactory *v2; // rax
  unsigned int v3; // edi
  GraphicsPerformanceMonitorComClassFactory *v4; // rbx
  GraphicsPerformanceMonitorComClassFactory *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = (GraphicsPerformanceMonitorComClassFactory *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v2;
  if ( v2 )
  {
    v4 = GraphicsPerformanceMonitorComClassFactory::GraphicsPerformanceMonitorComClassFactory(v2);
    v6 = 0;
    v3 = (**(__int64 (__fastcall ***)(GraphicsPerformanceMonitorComClassFactory *, GUID *, _QWORD *))v4)(
           v4,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(GraphicsPerformanceMonitorComClassFactory *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<GraphicsPerformanceMonitorApiFactory>::~MakeAllocator<GraphicsPerformanceMonitorApiFactory>(&v6);
  return v3;
}

```

## disassembly

```asm
0x18000bf5c  mov     [rsp+arg_8], rbx
0x18000bf61  push    rdi
0x18000bf62  sub     rsp, 20h
0x18000bf66  mov     rdi, rcx
0x18000bf69  mov     qword ptr [rcx], 0
0x18000bf70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf77  mov     ecx, 18h; unsigned __int64
0x18000bf7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bf81  mov     [rsp+28h+arg_0], rax
0x18000bf86  test    rax, rax
0x18000bf89  jnz     short loc_18000BF92
0x18000bf8b  mov     edi, 8007000Eh
0x18000bf90  jmp     short loc_18000BFD0
0x18000bf92  mov     rcx, rax; this
0x18000bf95  call    ??0GraphicsPerformanceMonitorComClassFactory@@QEAA@XZ; GraphicsPerformanceMonitorComClassFactory::GraphicsPerformanceMonitorComClassFactory(void)
0x18000bf9a  mov     rbx, rax
0x18000bf9d  mov     [rsp+28h+arg_0], 0
0x18000bfa6  mov     rcx, [rax]
0x18000bfa9  mov     rax, [rcx]
0x18000bfac  mov     r8, rdi
0x18000bfaf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000bfb6  mov     rcx, rbx
0x18000bfb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfbe  mov     edi, eax
0x18000bfc0  mov     rcx, [rbx]
0x18000bfc3  mov     rax, [rcx+10h]
0x18000bfc7  mov     rcx, rbx
0x18000bfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfcf  nop
0x18000bfd0  lea     rcx, [rsp+28h+arg_0]
0x18000bfd5  call    ??1?$MakeAllocator@VGraphicsPerformanceMonitorApiFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<GraphicsPerformanceMonitorApiFactory>::~MakeAllocator<GraphicsPerformanceMonitorApiFactory>(void)
0x18000bfda  mov     eax, edi
0x18000bfdc  mov     rbx, [rsp+28h+arg_8]
0x18000bfe1  add     rsp, 20h
0x18000bfe5  pop     rdi
0x18000bfe6  retn
```
