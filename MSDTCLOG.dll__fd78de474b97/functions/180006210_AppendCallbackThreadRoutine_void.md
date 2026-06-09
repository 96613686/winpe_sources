# AppendCallbackThreadRoutine(void *)

- ea: `0x180006210`
- end: `0x180006241`
- name: `?AppendCallbackThreadRoutine@@YAKPEAX@Z`
- size: `49`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x180006210`
- `0x18000db58`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall AppendCallbackThreadRoutine(_QWORD *Parameter)
{
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*Parameter + 8LL))(
    *Parameter,
    *((unsigned int *)Parameter + 2),
    Parameter[2]);
  operator delete(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180006210  push    rbx
0x180006212  sub     rsp, 20h
0x180006216  mov     rbx, rcx
0x180006219  mov     rcx, [rcx]
0x18000621c  mov     rax, [rcx]
0x18000621f  mov     r8, [rbx+10h]
0x180006223  mov     edx, [rbx+8]
0x180006226  mov     rax, [rax+8]
0x18000622a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622f  mov     rcx, rbx; Block
0x180006232  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006237  jmp     short $+2
0x180006239  xor     eax, eax
0x18000623b  add     rsp, 20h
0x18000623f  pop     rbx
0x180006240  retn
0x18001347e  push    rbp
0x180013480  sub     rsp, 20h
0x180013484  mov     rbp, rdx
0x180013487  call    ?DtcExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@H@Z; DtcExceptionFilter(_EXCEPTION_POINTERS *,int)
0x18001348c  nop
0x18001348d  add     rsp, 20h
0x180013491  pop     rbp
0x180013492  retn
```
