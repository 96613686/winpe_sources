# wil::details::static_lazy<CertPolEngProvider>::Completer::~Completer(void)

- ea: `0x1800174cc`
- end: `0x180017526`
- name: `??1Completer@?$static_lazy@VCertPolEngProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008200`
- `0x180008790`

## callees

- `0x180001760`
- `0x1800174cc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001751f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CertPolEngProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1800174cc  mov     [rsp+arg_0], rbx
0x1800174d1  push    rdi
0x1800174d2  sub     rsp, 20h
0x1800174d6  cmp     dword ptr [rcx+8], 0
0x1800174da  mov     rdi, rcx
0x1800174dd  jnz     short loc_18001750B
0x1800174df  mov     rbx, [rcx]
0x1800174e2  mov     rcx, [rbx+20h]
0x1800174e6  mov     [rbx+10h], rcx
0x1800174ea  mov     byte ptr [rbx+18h], 1
0x1800174ee  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x1800174f3  mov     rax, [rbx+8]
0x1800174f7  lea     rcx, [rbx+8]
0x1800174fb  mov     dword ptr [rbx+1Ch], 1
0x180017502  mov     rax, [rax+8]
0x180017506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001750b  mov     rcx, [rdi]
0x18001750e  mov     edx, [rdi+8]
0x180017511  lea     r8, [rcx+8]
0x180017515  mov     rbx, [rsp+28h+arg_0]
0x18001751a  add     rsp, 20h
0x18001751e  pop     rdi
0x18001751f  jmp     cs:__imp_InitOnceComplete
```
