# wil::details::static_lazy<VirtualPrintDEHTelemetry>::Completer::~Completer(void)

- ea: `0x180036208`
- end: `0x18003625e`
- name: `??1Completer@?$static_lazy@VVirtualPrintDEHTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800382dc`

## callees

- `0x180036208`
- `0x1800371f0`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180036257`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall wil::details::static_lazy<VirtualPrintDEHTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = VirtualPrintDEHLogging::Provider();
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
0x180036208  mov     [rsp+arg_0], rbx
0x18003620d  push    rdi
0x18003620e  sub     rsp, 20h
0x180036212  cmp     dword ptr [rcx+8], 0
0x180036216  mov     rdi, rcx
0x180036219  jnz     short loc_180036243
0x18003621b  mov     rbx, [rcx]
0x18003621e  call    ?Provider@VirtualPrintDEHLogging@@SAPEBU_tlgProvider_t@@XZ; VirtualPrintDEHLogging::Provider(void)
0x180036223  mov     [rbx+10h], rax
0x180036227  lea     rcx, [rbx+8]
0x18003622b  mov     rax, [rbx+8]
0x18003622f  mov     byte ptr [rbx+18h], 0
0x180036233  mov     dword ptr [rbx+1Ch], 1
0x18003623a  mov     rax, [rax+8]
0x18003623e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036243  mov     rcx, [rdi]
0x180036246  mov     edx, [rdi+8]
0x180036249  lea     r8, [rcx+8]
0x18003624d  mov     rbx, [rsp+28h+arg_0]
0x180036252  add     rsp, 20h
0x180036256  pop     rdi
0x180036257  jmp     cs:__imp_InitOnceComplete
```
