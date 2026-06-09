# STRW::STRW(ushort *,ulong)

- ea: `0x1800092d4`
- end: `0x1800092f9`
- name: `??0STRW@@QEAA@PEAGK@Z`
- size: `37`
- prototype: `STRW *__fastcall(STRW *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009834`
- `0x18000a9f0`
- `0x18000b390`
- `0x18000b5e0`
- `0x18000e9b0`
- `0x18000f500`
- `0x18000f5c0`
- `0x18000f8e0`
- `0x180011fec`

## callees

- `0x18000929c`

## pseudocode

```c
STRW *__fastcall STRW::STRW(STRW *this, unsigned __int16 *a2, unsigned int a3)
{
  STRW *v3; // r11
  STRW *result; // rax

  BUFFER::BUFFER((STRW *)((char *)this + 8), a2, 2LL * a3);
  result = v3;
  *(_DWORD *)v3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800092d4  sub     rsp, 28h
0x1800092d8  mov     r8d, r8d
0x1800092db  mov     r11, rcx
0x1800092de  add     r8, r8; unsigned __int64
0x1800092e1  add     rcx, 8; this
0x1800092e5  call    ??0BUFFER@@QEAA@PEAX_K@Z; BUFFER::BUFFER(void *,unsigned __int64)
0x1800092ea  mov     rax, r11
0x1800092ed  mov     dword ptr [r11], 0
0x1800092f4  add     rsp, 28h
0x1800092f8  retn
```
