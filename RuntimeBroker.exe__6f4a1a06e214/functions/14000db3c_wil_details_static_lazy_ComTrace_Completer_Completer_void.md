# wil::details::static_lazy<ComTrace>::Completer::~Completer(void)

- ea: `0x14000db3c`
- end: `0x14000db96`
- name: `??1Completer@?$static_lazy@VComTrace@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e98c`

## callees

- `0x1400017bc`
- `0x14000db3c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000db8f`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ComTrace>::Completer::~Completer(_DWORD *a1)
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
0x14000db3c  mov     [rsp+arg_0], rbx
0x14000db41  push    rdi
0x14000db42  sub     rsp, 20h
0x14000db46  cmp     dword ptr [rcx+8], 0
0x14000db4a  mov     rdi, rcx
0x14000db4d  jnz     short loc_14000DB7B
0x14000db4f  mov     rbx, [rcx]
0x14000db52  mov     rcx, [rbx+20h]
0x14000db56  mov     [rbx+10h], rcx
0x14000db5a  mov     byte ptr [rbx+18h], 1
0x14000db5e  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x14000db63  mov     rax, [rbx+8]
0x14000db67  lea     rcx, [rbx+8]
0x14000db6b  mov     dword ptr [rbx+1Ch], 1
0x14000db72  mov     rax, [rax+8]
0x14000db76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db7b  mov     rcx, [rdi]
0x14000db7e  mov     edx, [rdi+8]
0x14000db81  lea     r8, [rcx+8]
0x14000db85  mov     rbx, [rsp+28h+arg_0]
0x14000db8a  add     rsp, 20h
0x14000db8e  pop     rdi
0x14000db8f  jmp     cs:__imp_InitOnceComplete
```
