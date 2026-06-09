# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>,Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>,>(Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0> * *)

- ea: `0x180007f34`
- end: `0x180007fc4`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VCdsToInputTaskHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCdsToInputTaskHandler@@$0A@@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007b90`

## callees

- `0x18000396c`
- `0x180007f34`
- `0x180008334`
- `0x180008408`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>,Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>,>(
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
    v4 = Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>::SimpleClassFactory<CdsToInputTaskHandler,0>(v2);
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
0x180007f34  mov     [rsp+arg_8], rbx
0x180007f39  push    rdi
0x180007f3a  sub     rsp, 20h
0x180007f3e  mov     rdi, rcx
0x180007f41  mov     qword ptr [rcx], 0
0x180007f48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007f4f  mov     ecx, 18h; unsigned __int64
0x180007f54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007f59  mov     [rsp+28h+arg_0], rax
0x180007f5e  test    rax, rax
0x180007f61  jnz     short loc_180007F6A
0x180007f63  mov     ebx, 8007000Eh
0x180007f68  jmp     short loc_180007FAD
0x180007f6a  mov     rcx, rax
0x180007f6d  call    ??0?$SimpleClassFactory@VCdsToInputTaskHandler@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<CdsToInputTaskHandler,0>::SimpleClassFactory<CdsToInputTaskHandler,0>(void)
0x180007f72  mov     rbx, rax
0x180007f75  mov     [rsp+28h+arg_0], 0
0x180007f7e  test    rax, rax
0x180007f81  jz      short loc_180007F93
0x180007f83  mov     rcx, [rax]
0x180007f86  mov     rax, [rcx+8]
0x180007f8a  mov     rcx, rbx
0x180007f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f92  nop
0x180007f93  mov     [rdi], rbx
0x180007f96  test    rbx, rbx
0x180007f99  jz      short loc_180007FAB
0x180007f9b  mov     rax, [rbx]
0x180007f9e  mov     rcx, rbx
0x180007fa1  mov     rax, [rax+10h]
0x180007fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007faa  nop
0x180007fab  xor     ebx, ebx
0x180007fad  lea     rcx, [rsp+28h+arg_0]
0x180007fb2  call    ??1?$MakeAllocator@VCdsToInputTaskHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CdsToInputTaskHandler>::~MakeAllocator<CdsToInputTaskHandler>(void)
0x180007fb7  mov     eax, ebx
0x180007fb9  mov     rbx, [rsp+28h+arg_8]
0x180007fbe  add     rsp, 20h
0x180007fc2  pop     rdi
0x180007fc3  retn
```
