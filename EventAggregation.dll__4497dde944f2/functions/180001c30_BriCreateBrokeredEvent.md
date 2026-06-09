# BriCreateBrokeredEvent

- ea: `0x180001c30`
- end: `0x180001c79`
- name: `BriCreateBrokeredEvent`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800022b0`

## pseudocode

```c
__int64 __fastcall BriCreateBrokeredEvent(
        UUID *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        _QWORD *a7,
        _OWORD *a8)
{
  return BriCreateBrokeredEventEx(a1, a2, a3, a4, a5, a6, a7, a8, 0);
}

```

## disassembly

```asm
0x180001c30  sub     rsp, 58h
0x180001c34  mov     rax, [rsp+58h+arg_38]
0x180001c3c  mov     [rsp+58h+var_18], 0; __int64
0x180001c45  mov     [rsp+58h+var_20], rax; __int64
0x180001c4a  mov     rax, [rsp+58h+arg_30]
0x180001c52  mov     [rsp+58h+var_28], rax; __int64
0x180001c57  mov     rax, [rsp+58h+arg_28]
0x180001c5f  mov     [rsp+58h+var_30], rax; __int64
0x180001c64  mov     eax, [rsp+58h+arg_20]
0x180001c6b  mov     [rsp+58h+var_38], eax; int
0x180001c6f  call    BriCreateBrokeredEventEx
0x180001c74  add     rsp, 58h
0x180001c78  retn
```
