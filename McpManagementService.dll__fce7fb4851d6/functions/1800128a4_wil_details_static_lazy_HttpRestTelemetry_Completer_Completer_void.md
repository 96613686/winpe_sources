# wil::details::static_lazy<HttpRestTelemetry>::Completer::~Completer(void)

- ea: `0x1800128a4`
- end: `0x1800128fa`
- name: `??1Completer@?$static_lazy@VHttpRestTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e1f0`

## callees

- `0x1800128a4`
- `0x18001a65c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800128f3`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<HttpRestTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = HttpRestLogging::Provider();
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
0x1800128a4  mov     [rsp+arg_0], rbx
0x1800128a9  push    rdi
0x1800128aa  sub     rsp, 20h
0x1800128ae  cmp     dword ptr [rcx+8], 0
0x1800128b2  mov     rdi, rcx
0x1800128b5  jnz     short loc_1800128DF
0x1800128b7  mov     rbx, [rcx]
0x1800128ba  call    ?Provider@HttpRestLogging@@SAPEBU_tlgProvider_t@@XZ; HttpRestLogging::Provider(void)
0x1800128bf  mov     [rbx+10h], rax
0x1800128c3  lea     rcx, [rbx+8]
0x1800128c7  mov     rax, [rbx+8]
0x1800128cb  mov     byte ptr [rbx+18h], 0
0x1800128cf  mov     dword ptr [rbx+1Ch], 1
0x1800128d6  mov     rax, [rax+8]
0x1800128da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128df  mov     rcx, [rdi]
0x1800128e2  mov     edx, [rdi+8]
0x1800128e5  lea     r8, [rcx+8]
0x1800128e9  mov     rbx, [rsp+28h+arg_0]
0x1800128ee  add     rsp, 20h
0x1800128f2  pop     rdi
0x1800128f3  jmp     cs:__imp_InitOnceComplete
```
