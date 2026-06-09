# wil::details::static_lazy<McpEvtSrcTelemetry>::Completer::~Completer(void)

- ea: `0x180012900`
- end: `0x180012956`
- name: `??1Completer@?$static_lazy@VMcpEvtSrcTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e364`

## callees

- `0x180012900`
- `0x18001a67c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001294f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<McpEvtSrcTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = McpEvtSrcLogging::Provider();
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
0x180012900  mov     [rsp+arg_0], rbx
0x180012905  push    rdi
0x180012906  sub     rsp, 20h
0x18001290a  cmp     dword ptr [rcx+8], 0
0x18001290e  mov     rdi, rcx
0x180012911  jnz     short loc_18001293B
0x180012913  mov     rbx, [rcx]
0x180012916  call    ?Provider@McpEvtSrcLogging@@SAPEBU_tlgProvider_t@@XZ; McpEvtSrcLogging::Provider(void)
0x18001291b  mov     [rbx+10h], rax
0x18001291f  lea     rcx, [rbx+8]
0x180012923  mov     rax, [rbx+8]
0x180012927  mov     byte ptr [rbx+18h], 0
0x18001292b  mov     dword ptr [rbx+1Ch], 1
0x180012932  mov     rax, [rax+8]
0x180012936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001293b  mov     rcx, [rdi]
0x18001293e  mov     edx, [rdi+8]
0x180012941  lea     r8, [rcx+8]
0x180012945  mov     rbx, [rsp+28h+arg_0]
0x18001294a  add     rsp, 20h
0x18001294e  pop     rdi
0x18001294f  jmp     cs:__imp_InitOnceComplete
```
