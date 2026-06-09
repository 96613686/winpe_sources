# _anonymous_namespace_::GuardedDecodeKey__TASK_SCHEDULE_

- ea: `0x18001e840`
- end: `0x18001e860`
- name: `_anonymous_namespace_::GuardedDecodeKey__TASK_SCHEDULE_`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001efc8`

## callees

- `0x18001dfc0`
- `0x18001e840`
- `0x18001e890`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::GuardedDecodeKey__TASK_SCHEDULE_(HKEY *a1, __int64 a2, void **a3)
{
  return anonymous_namespace_::DecodeKey__TASK_SCHEDULE_(a1, a2, a3);
}

```

## disassembly

```asm
0x18001e840  sub     rsp, 38h
0x18001e844  call    _anonymous_namespace___DecodeKey__TASK_SCHEDULE_
0x18001e849  mov     [rsp+38h+var_18], eax
0x18001e84d  jmp     short loc_18001E85B
0x18001e84f  test    eax, eax
0x18001e851  jle     short loc_18001E85B
0x18001e853  movzx   eax, ax
0x18001e856  or      eax, 80070000h
0x18001e85b  add     rsp, 38h
0x18001e85f  retn
0x1800214c8  push    rbp
0x1800214ca  sub     rsp, 20h
0x1800214ce  mov     rbp, rdx
0x1800214d1  mov     rax, [rcx]
0x1800214d4  cmp     dword ptr [rax], 6F7h
0x1800214da  jz      short loc_1800214E8
0x1800214dc  cmp     dword ptr [rax], 724h
0x1800214e2  jz      short loc_1800214E8
0x1800214e4  xor     eax, eax
0x1800214e6  jmp     short loc_1800214ED
0x1800214e8  mov     eax, 1
0x1800214ed  add     rsp, 20h
0x1800214f1  pop     rbp
0x1800214f2  retn
```
