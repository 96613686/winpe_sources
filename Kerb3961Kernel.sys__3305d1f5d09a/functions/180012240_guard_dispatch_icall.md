# _guard_dispatch_icall

- ea: `0x180012240`
- end: `0x180012246`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `72`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800018e8`
- `0x180001900`
- `0x180001a00`
- `0x180001c40`
- `0x1800023e0`
- `0x1800025e0`
- `0x1800028d4`
- `0x180002cc4`
- `0x180003020`
- `0x180003240`
- `0x180003590`
- `0x180003b10`
- `0x180003dc0`
- `0x1800041a0`
- `0x180004390`
- `0x180004700`
- `0x180004a00`
- `0x180004ec0`
- `0x180004f80`
- `0x180005160`
- `0x1800051e0`
- `0x180005550`
- `0x1800055e0`
- `0x180005890`
- `0x1800058f0`
- `0x180005c30`
- `0x180005fb0`
- `0x1800060f0`
- `0x1800063f0`
- `0x1800064e0`
- `0x180006880`
- `0x1800068b0`
- `0x180006900`
- `0x180007338`
- `0x180007710`
- `0x180008308`
- `0x180008840`
- `0x180008c20`
- `0x180009040`
- `0x180009300`
- `0x1800097c0`
- `0x180009ad0`
- `0x18000a050`
- `0x18000b510`
- `0x18000bc30`
- `0x18000bcd0`
- `0x18000bdc0`
- `0x18000beb0`
- `0x18000c080`
- `0x18000c230`

## callees

- `0x180012270`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180012240  jmp     cs:__guard_dispatch_icall_fptr
```
