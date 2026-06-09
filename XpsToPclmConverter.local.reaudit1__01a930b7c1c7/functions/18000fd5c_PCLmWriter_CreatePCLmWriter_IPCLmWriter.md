# PCLmWriter::CreatePCLmWriter(IPCLmWriter * *)

- ea: `0x18000fd5c`
- end: `0x18000fddf`
- name: `?CreatePCLmWriter@PCLmWriter@@YAJPEAPEAUIPCLmWriter@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(PCLmWriter *__hidden this, struct IPCLmWriter **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dca0`

## callees

- `0x180001acc`
- `0x18000d9fc`
- `0x18000df30`
- `0x18000f460`
- `0x18000fd5c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCLmWriter::CreatePCLmWriter(PCLmWriter *this, struct IPCLmWriter **a2)
{
  PCLmWriter *v3; // rbx
  PCLmWriter::PCLmWriter *v4; // rax
  unsigned int v5; // ebx
  PCLmWriter::PCLmWriter *v7; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v4 = (PCLmWriter::PCLmWriter *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v4;
  if ( v4 )
  {
    v3 = PCLmWriter::PCLmWriter::PCLmWriter(v4);
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>::~MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>(&v7);
  v7 = v3;
  if ( v3 )
  {
    (*(void (__fastcall **)(PCLmWriter *))(*(_QWORD *)v3 + 8LL))(v3);
    *(_QWORD *)this = v3;
    v5 = 0;
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease((__int64 *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18000fd5c  mov     [rsp+arg_0], rbx
0x18000fd61  push    rdi
0x18000fd62  sub     rsp, 20h
0x18000fd66  mov     rdi, rcx
0x18000fd69  xor     ebx, ebx
0x18000fd6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fd72  lea     ecx, [rbx+58h]; unsigned __int64
0x18000fd75  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fd7a  mov     [rsp+28h+arg_8], rax
0x18000fd7f  test    rax, rax
0x18000fd82  jz      short loc_18000FD98
0x18000fd84  mov     rcx, rax; this
0x18000fd87  call    ??0PCLmWriter@0@QEAA@XZ; PCLmWriter::PCLmWriter::PCLmWriter(void)
0x18000fd8c  mov     rbx, rax
0x18000fd8f  mov     [rsp+28h+arg_8], 0
0x18000fd98  lea     rcx, [rsp+28h+arg_8]
0x18000fd9d  call    ??1?$MakeAllocator@VXpsToPclmConverter@1@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>::~MakeAllocator<XpsToPclmConverter::XpsToPclmConverter>(void)
0x18000fda2  mov     [rsp+28h+arg_8], rbx
0x18000fda7  test    rbx, rbx
0x18000fdaa  jnz     short loc_18000FDB3
0x18000fdac  mov     ebx, 8007000Eh
0x18000fdb1  jmp     short loc_18000FDC8
0x18000fdb3  mov     rax, [rbx]
0x18000fdb6  mov     rcx, rbx
0x18000fdb9  mov     rax, [rax+8]
0x18000fdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc2  nop
0x18000fdc3  mov     [rdi], rbx
0x18000fdc6  xor     ebx, ebx
0x18000fdc8  lea     rcx, [rsp+28h+arg_8]
0x18000fdcd  call    ?InternalRelease@?$ComPtr@UIPCLmWriter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(void)
0x18000fdd2  mov     eax, ebx
0x18000fdd4  mov     rbx, [rsp+28h+arg_0]
0x18000fdd9  add     rsp, 20h
0x18000fddd  pop     rdi
0x18000fdde  retn
```
