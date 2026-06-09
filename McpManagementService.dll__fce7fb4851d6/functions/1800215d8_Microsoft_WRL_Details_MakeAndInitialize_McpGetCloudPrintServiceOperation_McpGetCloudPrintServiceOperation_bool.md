# Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceOperation,McpGetCloudPrintServiceOperation,bool &,bool &,bool &>(McpGetCloudPrintServiceOperation * *,bool &,bool &,bool &)

- ea: `0x1800215d8`
- end: `0x1800216aa`
- name: `??$MakeAndInitialize@VMcpGetCloudPrintServiceOperation@@V1@AEA_NAEA_NAEA_N@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetCloudPrintServiceOperation@@AEA_N11@Z`
- size: `210`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceOperation **, char *, char *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021d44`

## callees

- `0x180003ae4`
- `0x180006f0c`
- `0x180009fc0`
- `0x1800215d8`
- `0x1800217bc`
- `0x180022580`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceOperation,McpGetCloudPrintServiceOperation,bool &,bool &,bool &>(
        McpGetCloudPrintServiceOperation **a1,
        char *a2,
        char *a3,
        char *a4)
{
  McpGetCloudPrintServiceOperation *v8; // rax
  int v9; // edi
  McpGetCloudPrintServiceOperation *CloudPrintServiceOperation; // rbx
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  McpGetCloudPrintServiceOperation *v13; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v8 = (McpGetCloudPrintServiceOperation *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
  v12[0] = v8;
  v13 = v8;
  if ( v8 )
  {
    v12[1] = v8;
    CloudPrintServiceOperation = McpGetCloudPrintServiceOperation::McpGetCloudPrintServiceOperation(v8);
    v13 = CloudPrintServiceOperation;
    v12[0] = 0;
    v9 = McpGetCloudPrintServiceOperation::RuntimeClassInitialize(CloudPrintServiceOperation, *a2, *a3, *a4);
    if ( v9 >= 0 )
    {
      if ( CloudPrintServiceOperation )
        (*(void (__fastcall **)(McpGetCloudPrintServiceOperation *))(*(_QWORD *)CloudPrintServiceOperation + 8LL))(CloudPrintServiceOperation);
      *a1 = CloudPrintServiceOperation;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      v9 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800215d8  mov     [rsp+arg_8], rbx
0x1800215dd  mov     [rsp+arg_10], rsi
0x1800215e2  push    rdi
0x1800215e3  push    r14
0x1800215e5  push    r15
0x1800215e7  sub     rsp, 30h
0x1800215eb  mov     rdi, r9
0x1800215ee  mov     r14, r8
0x1800215f1  mov     r15, rdx
0x1800215f4  mov     rsi, rcx
0x1800215f7  mov     qword ptr [rcx], 0
0x1800215fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021605  mov     ecx, 0D0h; unsigned __int64
0x18002160a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002160f  mov     [rsp+48h+var_28], rax
0x180021614  mov     [rsp+48h+arg_0], rax
0x180021619  test    rax, rax
0x18002161c  jnz     short loc_180021625
0x18002161e  mov     edi, 8007000Eh
0x180021623  jmp     short loc_18002168A
0x180021625  mov     [rsp+48h+var_20], rax
0x18002162a  mov     rcx, rax; this
0x18002162d  call    ??0McpGetCloudPrintServiceOperation@@QEAA@XZ; McpGetCloudPrintServiceOperation::McpGetCloudPrintServiceOperation(void)
0x180021632  mov     rbx, rax
0x180021635  mov     [rsp+48h+arg_0], rax
0x18002163a  mov     [rsp+48h+var_28], 0
0x180021643  mov     r9b, [rdi]; bool
0x180021646  mov     r8b, [r14]; bool
0x180021649  mov     dl, [r15]; bool
0x18002164c  mov     rcx, rax; this
0x18002164f  call    ?RuntimeClassInitialize@McpGetCloudPrintServiceOperation@@QEAAJ_N00@Z; McpGetCloudPrintServiceOperation::RuntimeClassInitialize(bool,bool,bool)
0x180021654  mov     edi, eax
0x180021656  test    eax, eax
0x180021658  jns     short loc_180021666
0x18002165a  lea     rcx, [rsp+48h+arg_0]
0x18002165f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021664  jmp     short loc_18002168A
0x180021666  test    rbx, rbx
0x180021669  jz      short loc_18002167B
0x18002166b  mov     rax, [rbx]
0x18002166e  mov     rcx, rbx
0x180021671  mov     rax, [rax+8]
0x180021675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002167a  nop
0x18002167b  mov     [rsi], rbx
0x18002167e  lea     rcx, [rsp+48h+arg_0]
0x180021683  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021688  xor     edi, edi
0x18002168a  lea     rcx, [rsp+48h+var_28]
0x18002168f  call    ??1?$MakeAllocator@VMcpManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(void)
0x180021694  mov     eax, edi
0x180021696  mov     rbx, [rsp+48h+arg_8]
0x18002169b  mov     rsi, [rsp+48h+arg_10]
0x1800216a0  add     rsp, 30h
0x1800216a4  pop     r15
0x1800216a6  pop     r14
0x1800216a8  pop     rdi
0x1800216a9  retn
```
