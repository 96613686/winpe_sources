# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>,Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>,>(Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0> * *)

- ea: `0x180007fcc`
- end: `0x18000805c`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VInputToCdsTaskHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VInputToCdsTaskHandler@@$0A@@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007c50`

## callees

- `0x18000396c`
- `0x180007fcc`
- `0x180008358`
- `0x180008408`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>,Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>,>(
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
    v4 = Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>::SimpleClassFactory<InputToCdsTaskHandler,0>(v2);
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
  Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(&v7);
  return v3;
}

```

## disassembly

```asm
0x180007fcc  mov     [rsp+arg_8], rbx
0x180007fd1  push    rdi
0x180007fd2  sub     rsp, 20h
0x180007fd6  mov     rdi, rcx
0x180007fd9  mov     qword ptr [rcx], 0
0x180007fe0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007fe7  mov     ecx, 18h; unsigned __int64
0x180007fec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007ff1  mov     [rsp+28h+arg_0], rax
0x180007ff6  test    rax, rax
0x180007ff9  jnz     short loc_180008002
0x180007ffb  mov     ebx, 8007000Eh
0x180008000  jmp     short loc_180008045
0x180008002  mov     rcx, rax
0x180008005  call    ??0?$SimpleClassFactory@VInputToCdsTaskHandler@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<InputToCdsTaskHandler,0>::SimpleClassFactory<InputToCdsTaskHandler,0>(void)
0x18000800a  mov     rbx, rax
0x18000800d  mov     [rsp+28h+arg_0], 0
0x180008016  test    rax, rax
0x180008019  jz      short loc_18000802B
0x18000801b  mov     rcx, [rax]
0x18000801e  mov     rax, [rcx+8]
0x180008022  mov     rcx, rbx
0x180008025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802a  nop
0x18000802b  mov     [rdi], rbx
0x18000802e  test    rbx, rbx
0x180008031  jz      short loc_180008043
0x180008033  mov     rax, [rbx]
0x180008036  mov     rcx, rbx
0x180008039  mov     rax, [rax+10h]
0x18000803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008042  nop
0x180008043  xor     ebx, ebx
0x180008045  lea     rcx, [rsp+28h+arg_0]
0x18000804a  call    ??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)
0x18000804f  mov     eax, ebx
0x180008051  mov     rbx, [rsp+28h+arg_8]
0x180008056  add     rsp, 20h
0x18000805a  pop     rdi
0x18000805b  retn
```
