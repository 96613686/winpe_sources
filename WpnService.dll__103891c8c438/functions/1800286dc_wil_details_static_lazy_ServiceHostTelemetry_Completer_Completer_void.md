# wil::details::static_lazy<ServiceHostTelemetry>::Completer::~Completer(void)

- ea: `0x1800286dc`
- end: `0x180028732`
- name: `??1Completer@?$static_lazy@VServiceHostTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014fcc`

## callees

- `0x1800172bc`
- `0x1800286dc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002872b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ServiceHostTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = ServiceHostLogging::Provider();
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
0x1800286dc  mov     [rsp+arg_0], rbx
0x1800286e1  push    rdi
0x1800286e2  sub     rsp, 20h
0x1800286e6  cmp     dword ptr [rcx+8], 0
0x1800286ea  mov     rdi, rcx
0x1800286ed  jnz     short loc_180028717
0x1800286ef  mov     rbx, [rcx]
0x1800286f2  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x1800286f7  mov     [rbx+10h], rax
0x1800286fb  lea     rcx, [rbx+8]
0x1800286ff  mov     rax, [rbx+8]
0x180028703  mov     byte ptr [rbx+18h], 0
0x180028707  mov     dword ptr [rbx+1Ch], 1
0x18002870e  mov     rax, [rax+8]
0x180028712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028717  mov     rcx, [rdi]
0x18002871a  mov     edx, [rdi+8]
0x18002871d  lea     r8, [rcx+8]
0x180028721  mov     rbx, [rsp+28h+arg_0]
0x180028726  add     rsp, 20h
0x18002872a  pop     rdi
0x18002872b  jmp     cs:__imp_InitOnceComplete
```
