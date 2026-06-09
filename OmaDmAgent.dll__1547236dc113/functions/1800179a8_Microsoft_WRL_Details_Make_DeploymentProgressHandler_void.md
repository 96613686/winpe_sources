# Microsoft::WRL::Details::Make<DeploymentProgressHandler,>(void)

- ea: `0x1800179a8`
- end: `0x180017a32`
- name: `??$Make@VDeploymentProgressHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDeploymentProgressHandler@@@12@XZ`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017b58`

## callees

- `0x180002138`
- `0x1800179a8`
- `0x180017a7c`
- `0x18001d580`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
DeploymentProgressHandler **__fastcall Microsoft::WRL::Details::Make<DeploymentProgressHandler,>(
        DeploymentProgressHandler **a1)
{
  DeploymentProgressHandler *v2; // rax
  DeploymentProgressHandler *v3; // rdi
  DeploymentProgressHandler *v5; // [rsp+58h] [rbp+10h] BYREF
  DeploymentProgressHandler *v6; // [rsp+60h] [rbp+18h]
  DeploymentProgressHandler *v7; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v2 = (DeploymentProgressHandler *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v2;
  v6 = v2;
  if ( v2 )
  {
    v7 = v2;
    v3 = DeploymentProgressHandler::DeploymentProgressHandler(v2);
    if ( *a1 )
      (*(void (__fastcall **)(DeploymentProgressHandler *))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
    v5 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<DeploymentProgressHandler>::~MakeAllocator<DeploymentProgressHandler>(&v5);
  return a1;
}

```

## disassembly

```asm
0x1800179a8  mov     [rsp+arg_0], rcx
0x1800179ad  push    rbx
0x1800179ae  push    rdi
0x1800179af  sub     rsp, 38h
0x1800179b3  mov     rbx, rcx
0x1800179b6  mov     [rsp+48h+var_28], 0
0x1800179be  mov     qword ptr [rcx], 0
0x1800179c5  mov     [rsp+48h+var_28], 1
0x1800179cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800179d4  mov     ecx, 0D0h; unsigned __int64
0x1800179d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800179de  mov     [rsp+48h+arg_8], rax
0x1800179e3  mov     [rsp+48h+arg_10], rax
0x1800179e8  test    rax, rax
0x1800179eb  jz      short loc_180017A1D
0x1800179ed  mov     [rsp+48h+arg_18], rax
0x1800179f2  mov     rcx, rax; this
0x1800179f5  call    ??0DeploymentProgressHandler@@QEAA@XZ; DeploymentProgressHandler::DeploymentProgressHandler(void)
0x1800179fa  mov     rdi, rax
0x1800179fd  mov     rcx, [rbx]
0x180017a00  test    rcx, rcx
0x180017a03  jz      short loc_180017A11
0x180017a05  mov     rdx, [rcx]
0x180017a08  mov     rax, [rdx+10h]
0x180017a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a11  mov     [rbx], rdi
0x180017a14  mov     [rsp+48h+arg_8], 0
0x180017a1d  lea     rcx, [rsp+48h+arg_8]
0x180017a22  call    ??1?$MakeAllocator@VDeploymentProgressHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DeploymentProgressHandler>::~MakeAllocator<DeploymentProgressHandler>(void)
0x180017a27  mov     rax, rbx
0x180017a2a  add     rsp, 38h
0x180017a2e  pop     rdi
0x180017a2f  pop     rbx
0x180017a30  retn
```
