# wil::details::static_lazy<AccountsTelemetry>::Completer::~Completer(void)

- ea: `0x180019d80`
- end: `0x180019dd6`
- name: `??1Completer@?$static_lazy@VAccountsTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a590`
- `0x18001e13c`

## callees

- `0x18000e00c`
- `0x180019d80`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019dcf`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<AccountsTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = SharedPCAccountManagerLogging::Provider();
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
0x180019d80  mov     [rsp+arg_0], rbx
0x180019d85  push    rdi
0x180019d86  sub     rsp, 20h
0x180019d8a  cmp     dword ptr [rcx+8], 0
0x180019d8e  mov     rdi, rcx
0x180019d91  jnz     short loc_180019DBB
0x180019d93  mov     rbx, [rcx]
0x180019d96  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180019d9b  mov     [rbx+10h], rax
0x180019d9f  lea     rcx, [rbx+8]
0x180019da3  mov     rax, [rbx+8]
0x180019da7  mov     byte ptr [rbx+18h], 0
0x180019dab  mov     dword ptr [rbx+1Ch], 1
0x180019db2  mov     rax, [rax+8]
0x180019db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dbb  mov     rcx, [rdi]
0x180019dbe  mov     edx, [rdi+8]
0x180019dc1  lea     r8, [rcx+8]
0x180019dc5  mov     rbx, [rsp+28h+arg_0]
0x180019dca  add     rsp, 20h
0x180019dce  pop     rdi
0x180019dcf  jmp     cs:__imp_InitOnceComplete
```
