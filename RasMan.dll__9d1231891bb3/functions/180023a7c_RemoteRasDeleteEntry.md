# RemoteRasDeleteEntry

- ea: `0x180023a7c`
- end: `0x180023a97`
- name: `RemoteRasDeleteEntry`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022d10`

## callees

- `0x180022f80`
- `0x180023a7c`

## pseudocode

```c
__int64 __fastcall RemoteRasDeleteEntry(_QWORD *a1)
{
  return (unsigned int)RasRpcDeleteEntry(*a1);
}

```

## disassembly

```asm
0x180023a7c  sub     rsp, 38h
0x180023a80  mov     rcx, [rcx]
0x180023a83  call    RasRpcDeleteEntry
0x180023a88  mov     [rsp+38h+var_18], eax
0x180023a8c  mov     eax, [rsp+38h+var_18]
0x180023a90  jmp     short $+2
0x180023a92  add     rsp, 38h
0x180023a96  retn
0x180026806  push    rbp
0x180026808  sub     rsp, 20h
0x18002680c  mov     rbp, rdx
0x18002680f  mov     rax, [rcx]
0x180026812  mov     ecx, [rax]
0x180026814  mov     [rbp+20h], ecx
0x180026817  mov     ecx, [rbp+20h]; ExceptionCode
0x18002681a  call    cs:__imp_I_RpcExceptionFilter
0x180026820  nop
0x180026821  add     rsp, 20h
0x180026825  pop     rbp
0x180026826  retn
```
