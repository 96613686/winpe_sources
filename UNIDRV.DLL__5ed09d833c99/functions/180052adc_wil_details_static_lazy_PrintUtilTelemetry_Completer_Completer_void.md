# wil::details::static_lazy<PrintUtilTelemetry>::Completer::~Completer(void)

- ea: `0x180052adc`
- end: `0x180052b37`
- name: `??1Completer@?$static_lazy@VPrintUtilTelemetry@@@details@wil@@QEAA@XZ`
- size: `91`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800580ac`

## callees

- `0x180052adc`
- `0x180055ee4`
- `0x180077010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180052b2b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PrintUtilTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = PrintUtilLogging::Provider(a1);
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
0x180052adc  mov     [rsp+arg_0], rbx
0x180052ae1  push    rdi
0x180052ae2  sub     rsp, 20h
0x180052ae6  cmp     dword ptr [rcx+8], 0
0x180052aea  mov     rdi, rcx
0x180052aed  jnz     short loc_180052B17
0x180052aef  mov     rbx, [rcx]
0x180052af2  call    ?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ; PrintUtilLogging::Provider(void)
0x180052af7  mov     [rbx+10h], rax
0x180052afb  lea     rcx, [rbx+8]
0x180052aff  mov     rax, [rbx+8]
0x180052b03  mov     byte ptr [rbx+18h], 0
0x180052b07  mov     dword ptr [rbx+1Ch], 1
0x180052b0e  mov     rax, [rax+8]
0x180052b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b17  mov     rcx, [rdi]
0x180052b1a  mov     edx, [rdi+8]
0x180052b1d  lea     r8, [rcx+8]
0x180052b21  mov     rbx, [rsp+28h+arg_0]
0x180052b26  add     rsp, 20h
0x180052b2a  pop     rdi
0x180052b2b  jmp     cs:__imp_InitOnceComplete
```
