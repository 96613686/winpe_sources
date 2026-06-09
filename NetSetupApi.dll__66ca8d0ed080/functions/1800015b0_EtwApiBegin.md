# EtwApiBegin

- ea: `0x1800015b0`
- end: `0x1800015ee`
- name: `EtwApiBegin`
- size: `62`
- prototype: `__int64 *__fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001520`
- `0x180006710`
- `0x180006880`
- `0x18000f690`
- `0x18000f900`
- `0x18000fa50`

## callees

- `0x1800015b0`
- `0x18000f5a0`
- `0x180015010`

## pseudocode

```c
__int64 *__fastcall EtwApiBegin(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 *result; // rax

  v2 = a2;
  if ( a1 )
    result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  else
    result = qword_18001D4A0;
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    return (__int64 *)McTemplateU0jq_EventWriteTransfer(a1, a2, result, v2);
  return result;
}

```

## disassembly

```asm
0x1800015b0  push    rbx
0x1800015b2  sub     rsp, 20h
0x1800015b6  mov     ebx, edx
0x1800015b8  test    rcx, rcx
0x1800015bb  jz      short loc_1800015D8
0x1800015bd  mov     rax, [rcx]
0x1800015c0  mov     rax, [rax+8]
0x1800015c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015c9  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x1800015d0  jnz     short loc_1800015E1
0x1800015d2  add     rsp, 20h
0x1800015d6  pop     rbx
0x1800015d7  retn
0x1800015d8  lea     rax, qword_18001D4A0
0x1800015df  jmp     short loc_1800015C9
0x1800015e1  mov     r9d, ebx
0x1800015e4  mov     r8, rax
0x1800015e7  call    McTemplateU0jq_EventWriteTransfer
0x1800015ec  jmp     short loc_1800015D2
```
