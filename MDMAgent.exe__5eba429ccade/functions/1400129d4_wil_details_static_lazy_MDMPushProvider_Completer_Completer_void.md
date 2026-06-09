# wil::details::static_lazy<MDMPushProvider>::Completer::~Completer(void)

- ea: `0x1400129d4`
- end: `0x140012a2e`
- name: `??1Completer@?$static_lazy@VMDMPushProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400173f4`

## callees

- `0x140001dc0`
- `0x1400129d4`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140012a27`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MDMPushProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1400129d4  mov     [rsp+arg_0], rbx
0x1400129d9  push    rdi
0x1400129da  sub     rsp, 20h
0x1400129de  cmp     dword ptr [rcx+8], 0
0x1400129e2  mov     rdi, rcx
0x1400129e5  jnz     short loc_140012A13
0x1400129e7  mov     rbx, [rcx]
0x1400129ea  mov     rcx, [rbx+20h]; CallbackContext
0x1400129ee  mov     [rbx+10h], rcx
0x1400129f2  mov     byte ptr [rbx+18h], 1
0x1400129f6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1400129fb  mov     rax, [rbx+8]
0x1400129ff  lea     rcx, [rbx+8]
0x140012a03  mov     dword ptr [rbx+1Ch], 1
0x140012a0a  mov     rax, [rax+8]
0x140012a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a13  mov     rcx, [rdi]
0x140012a16  mov     edx, [rdi+8]
0x140012a19  lea     r8, [rcx+8]
0x140012a1d  mov     rbx, [rsp+28h+arg_0]
0x140012a22  add     rsp, 20h
0x140012a26  pop     rdi
0x140012a27  jmp     cs:__imp_InitOnceComplete
```
