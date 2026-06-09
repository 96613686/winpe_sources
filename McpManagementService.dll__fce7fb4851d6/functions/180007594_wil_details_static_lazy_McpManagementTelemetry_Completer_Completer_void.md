# wil::details::static_lazy<McpManagementTelemetry>::Completer::~Completer(void)

- ea: `0x180007594`
- end: `0x1800075ea`
- name: `??1Completer@?$static_lazy@VMcpManagementTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e534`

## callees

- `0x180007594`
- `0x18000b1c0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800075e3`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<McpManagementTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = McpManagementLogging::Provider();
    v3.Ptr = v2[1].Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180007594  mov     [rsp+arg_0], rbx
0x180007599  push    rdi
0x18000759a  sub     rsp, 20h
0x18000759e  cmp     dword ptr [rcx+8], 0
0x1800075a2  mov     rdi, rcx
0x1800075a5  jnz     short loc_1800075CF
0x1800075a7  mov     rbx, [rcx]
0x1800075aa  call    ?Provider@McpManagementLogging@@SAPEBU_tlgProvider_t@@XZ; McpManagementLogging::Provider(void)
0x1800075af  mov     [rbx+10h], rax
0x1800075b3  lea     rcx, [rbx+8]
0x1800075b7  mov     rax, [rbx+8]
0x1800075bb  mov     byte ptr [rbx+18h], 0
0x1800075bf  mov     dword ptr [rbx+1Ch], 1
0x1800075c6  mov     rax, [rax+8]
0x1800075ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075cf  mov     rcx, [rdi]
0x1800075d2  mov     edx, [rdi+8]
0x1800075d5  lea     r8, [rcx+8]
0x1800075d9  mov     rbx, [rsp+28h+arg_0]
0x1800075de  add     rsp, 20h
0x1800075e2  pop     rdi
0x1800075e3  jmp     cs:__imp_InitOnceComplete
```
