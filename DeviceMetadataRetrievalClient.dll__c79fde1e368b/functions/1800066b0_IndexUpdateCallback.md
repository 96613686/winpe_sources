# IndexUpdateCallback

- ea: `0x1800066b0`
- end: `0x18000670d`
- name: `IndexUpdateCallback`
- size: `93`
- prototype: `__int64 __fastcall(__int64, __int64, wchar_t *String2, wchar_t *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800066b0`
- `0x18000b96c`
- `0x1800135cc`

## pseudocode

```c
__int64 __fastcall IndexUpdateCallback(__int64 a1, __int64 a2, wchar_t *String2, wchar_t *a4, __int64 a5, _QWORD *a6)
{
  int v8; // ebp
  int v9; // r14d

  v8 = a2;
  v9 = a1;
  if ( !*a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  return UpdateEntry(*a6, a6[1], v9, v8, String2, a4, a5);
}

```

## disassembly

```asm
0x1800066b0  push    rbx
0x1800066b2  push    rbp
0x1800066b3  push    rsi
0x1800066b4  push    rdi
0x1800066b5  push    r14
0x1800066b7  sub     rsp, 40h
0x1800066bb  mov     rbx, [rsp+68h+arg_28]
0x1800066c3  mov     rdi, r9
0x1800066c6  mov     rsi, r8
0x1800066c9  mov     ebp, edx
0x1800066cb  mov     r14, rcx
0x1800066ce  cmp     qword ptr [rbx], 0
0x1800066d2  jnz     short loc_1800066D9
0x1800066d4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800066d9  mov     rax, [rsp+68h+arg_20]
0x1800066e1  mov     r9d, ebp; int
0x1800066e4  mov     rdx, [rbx+8]; int
0x1800066e8  mov     r8, r14; int
0x1800066eb  mov     rcx, [rbx]; int
0x1800066ee  mov     [rsp+68h+var_38], rax; __int64
0x1800066f3  mov     [rsp+68h+var_40], rdi; wchar_t *
0x1800066f8  mov     [rsp+68h+String2], rsi; String2
0x1800066fd  call    UpdateEntry
0x180006702  add     rsp, 40h
0x180006706  pop     r14
0x180006708  pop     rdi
0x180006709  pop     rsi
0x18000670a  pop     rbp
0x18000670b  pop     rbx
0x18000670c  retn
```
