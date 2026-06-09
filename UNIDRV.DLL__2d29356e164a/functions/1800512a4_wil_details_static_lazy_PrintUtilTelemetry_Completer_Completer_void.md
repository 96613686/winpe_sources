# wil::details::static_lazy<PrintUtilTelemetry>::Completer::~Completer(void)

- ea: `0x1800512a4`
- end: `0x1800512fa`
- name: `??1Completer@?$static_lazy@VPrintUtilTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005665c`

## callees

- `0x1800512a4`
- `0x1800543c4`
- `0x180075010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800512f3`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PrintUtilTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = PrintUtilLogging::Provider();
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
0x1800512a4  mov     [rsp+arg_0], rbx
0x1800512a9  push    rdi
0x1800512aa  sub     rsp, 20h
0x1800512ae  cmp     dword ptr [rcx+8], 0
0x1800512b2  mov     rdi, rcx
0x1800512b5  jnz     short loc_1800512DF
0x1800512b7  mov     rbx, [rcx]
0x1800512ba  call    ?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ; PrintUtilLogging::Provider(void)
0x1800512bf  mov     [rbx+10h], rax
0x1800512c3  lea     rcx, [rbx+8]
0x1800512c7  mov     rax, [rbx+8]
0x1800512cb  mov     byte ptr [rbx+18h], 0
0x1800512cf  mov     dword ptr [rbx+1Ch], 1
0x1800512d6  mov     rax, [rax+8]
0x1800512da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512df  mov     rcx, [rdi]
0x1800512e2  mov     edx, [rdi+8]
0x1800512e5  lea     r8, [rcx+8]
0x1800512e9  mov     rbx, [rsp+28h+arg_0]
0x1800512ee  add     rsp, 20h
0x1800512f2  pop     rdi
0x1800512f3  jmp     cs:__imp_InitOnceComplete
```
