# wil::details::static_lazy<PrintScanBrokerTelemetry>::Completer::~Completer(void)

- ea: `0x18000833c`
- end: `0x180008392`
- name: `??1Completer@?$static_lazy@VPrintScanBrokerTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800100a4`

## callees

- `0x18000833c`
- `0x18000c55c`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000838b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall wil::details::static_lazy<PrintScanBrokerTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = PrintScanBrokerLogging::Provider();
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
0x18000833c  mov     [rsp+arg_0], rbx
0x180008341  push    rdi
0x180008342  sub     rsp, 20h
0x180008346  cmp     dword ptr [rcx+8], 0
0x18000834a  mov     rdi, rcx
0x18000834d  jnz     short loc_180008377
0x18000834f  mov     rbx, [rcx]
0x180008352  call    ?Provider@PrintScanBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; PrintScanBrokerLogging::Provider(void)
0x180008357  mov     [rbx+10h], rax
0x18000835b  lea     rcx, [rbx+8]
0x18000835f  mov     rax, [rbx+8]
0x180008363  mov     byte ptr [rbx+18h], 0
0x180008367  mov     dword ptr [rbx+1Ch], 1
0x18000836e  mov     rax, [rax+8]
0x180008372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008377  mov     rcx, [rdi]
0x18000837a  mov     edx, [rdi+8]
0x18000837d  lea     r8, [rcx+8]
0x180008381  mov     rbx, [rsp+28h+arg_0]
0x180008386  add     rsp, 20h
0x18000838a  pop     rdi
0x18000838b  jmp     cs:__imp_InitOnceComplete
```
