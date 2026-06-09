# EtwApiEnd

- ea: `0x1800016d0`
- end: `0x18000171e`
- name: `EtwApiEnd`
- size: `78`
- prototype: `__int64 *__fastcall(__int64, int, char)`
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001520`
- `0x180001600`
- `0x180006710`
- `0x180006880`
- `0x18000f690`
- `0x18000f900`
- `0x18000fa50`

## callees

- `0x1800016d0`
- `0x18000f608`
- `0x180015010`

## pseudocode

```c
__int64 *__fastcall EtwApiEnd(__int64 a1, int a2, char a3)
{
  __int64 *result; // rax

  if ( a1 )
    result = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  else
    result = qword_18001D4A0;
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    return (__int64 *)McTemplateU0jqd_EventWriteTransfer(a1, a2, (_DWORD)result, a2, a3);
  return result;
}

```

## disassembly

```asm
0x1800016d0  mov     [rsp+arg_0], rbx
0x1800016d5  push    rdi
0x1800016d6  sub     rsp, 30h
0x1800016da  mov     ebx, r8d
0x1800016dd  mov     edi, edx
0x1800016df  test    rcx, rcx
0x1800016e2  jz      short loc_180001704
0x1800016e4  mov     rax, [rcx]
0x1800016e7  mov     rax, [rax+8]
0x1800016eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016f0  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x1800016f7  jnz     short loc_18000170D
0x1800016f9  mov     rbx, [rsp+38h+arg_0]
0x1800016fe  add     rsp, 30h
0x180001702  pop     rdi
0x180001703  retn
0x180001704  lea     rax, qword_18001D4A0
0x18000170b  jmp     short loc_1800016F0
0x18000170d  mov     r9d, edi
0x180001710  mov     [rsp+38h+var_18], ebx
0x180001714  mov     r8, rax
0x180001717  call    McTemplateU0jqd_EventWriteTransfer
0x18000171c  jmp     short loc_1800016F9
```
