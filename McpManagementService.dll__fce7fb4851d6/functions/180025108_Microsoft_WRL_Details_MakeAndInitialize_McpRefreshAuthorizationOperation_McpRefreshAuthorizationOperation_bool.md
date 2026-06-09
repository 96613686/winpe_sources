# Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationOperation,McpRefreshAuthorizationOperation,bool,McpService *>(McpRefreshAuthorizationOperation * *,bool &&,McpService * &&)

- ea: `0x180025108`
- end: `0x1800251c8`
- name: `??$MakeAndInitialize@VMcpRefreshAuthorizationOperation@@V1@_NPEAVMcpService@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpRefreshAuthorizationOperation@@$$QEA_N$$QEAPEAVMcpService@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(McpRefreshAuthorizationOperation **, char *, struct McpService **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026630`

## callees

- `0x180003ae4`
- `0x180006f0c`
- `0x180009fc0`
- `0x180024ca0`
- `0x180025108`
- `0x180025540`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationOperation,McpRefreshAuthorizationOperation,bool,McpService *>(
        McpRefreshAuthorizationOperation **a1,
        char *a2,
        struct McpService **a3)
{
  McpRefreshAuthorizationOperation *v6; // rax
  int v7; // edi
  McpRefreshAuthorizationOperation *refreshed; // rbx
  McpRefreshAuthorizationOperation *v10; // [rsp+50h] [rbp+8h] BYREF
  McpRefreshAuthorizationOperation *v11; // [rsp+68h] [rbp+20h] BYREF

  *a1 = 0;
  v6 = (McpRefreshAuthorizationOperation *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v6;
  v10 = v6;
  if ( v6 )
  {
    refreshed = McpRefreshAuthorizationOperation::McpRefreshAuthorizationOperation(v6);
    v10 = refreshed;
    v11 = 0;
    v7 = McpRefreshAuthorizationOperation::RuntimeClassInitialize(refreshed, *a2, *a3);
    if ( v7 >= 0 )
    {
      if ( refreshed )
        (*(void (__fastcall **)(McpRefreshAuthorizationOperation *))(*(_QWORD *)refreshed + 8LL))(refreshed);
      *a1 = refreshed;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
      v7 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025108  mov     [rsp+arg_8], rbx
0x18002510d  push    rsi
0x18002510e  push    rdi
0x18002510f  push    r14
0x180025111  sub     rsp, 30h
0x180025115  mov     rdi, r8
0x180025118  mov     r14, rdx
0x18002511b  mov     rsi, rcx
0x18002511e  mov     qword ptr [rcx], 0
0x180025125  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002512c  mov     ecx, 0B8h; unsigned __int64
0x180025131  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025136  mov     [rsp+48h+arg_18], rax
0x18002513b  mov     [rsp+48h+arg_0], rax
0x180025140  test    rax, rax
0x180025143  jnz     short loc_18002514C
0x180025145  mov     edi, 8007000Eh
0x18002514a  jmp     short loc_1800251AE
0x18002514c  mov     [rsp+48h+var_28], rax
0x180025151  mov     rcx, rax; this
0x180025154  call    ??0McpRefreshAuthorizationOperation@@QEAA@XZ; McpRefreshAuthorizationOperation::McpRefreshAuthorizationOperation(void)
0x180025159  mov     rbx, rax
0x18002515c  mov     [rsp+48h+arg_0], rax
0x180025161  mov     [rsp+48h+arg_18], 0
0x18002516a  mov     r8, [rdi]; struct McpService *
0x18002516d  mov     dl, [r14]; bool
0x180025170  mov     rcx, rax; this
0x180025173  call    ?RuntimeClassInitialize@McpRefreshAuthorizationOperation@@QEAAJ_NPEAVMcpService@@@Z; McpRefreshAuthorizationOperation::RuntimeClassInitialize(bool,McpService *)
0x180025178  mov     edi, eax
0x18002517a  test    eax, eax
0x18002517c  jns     short loc_18002518A
0x18002517e  lea     rcx, [rsp+48h+arg_0]
0x180025183  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025188  jmp     short loc_1800251AE
0x18002518a  test    rbx, rbx
0x18002518d  jz      short loc_18002519F
0x18002518f  mov     rax, [rbx]
0x180025192  mov     rcx, rbx
0x180025195  mov     rax, [rax+8]
0x180025199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002519e  nop
0x18002519f  mov     [rsi], rbx
0x1800251a2  lea     rcx, [rsp+48h+arg_0]
0x1800251a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800251ac  xor     edi, edi
0x1800251ae  lea     rcx, [rsp+48h+arg_18]
0x1800251b3  call    ??1?$MakeAllocator@VMcpManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(void)
0x1800251b8  mov     eax, edi
0x1800251ba  mov     rbx, [rsp+48h+arg_8]
0x1800251bf  add     rsp, 30h
0x1800251c3  pop     r14
0x1800251c5  pop     rdi
0x1800251c6  pop     rsi
0x1800251c7  retn
```
