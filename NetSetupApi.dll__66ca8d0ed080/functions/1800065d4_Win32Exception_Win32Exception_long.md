# Win32Exception::Win32Exception(long)

- ea: `0x1800065d4`
- end: `0x180006602`
- name: `??0Win32Exception@@QEAA@J@Z`
- size: `46`
- prototype: `Win32Exception *__fastcall(Win32Exception *this, signed int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f40`
- `0x180004120`
- `0x180005328`
- `0x18000536c`
- `0x1800079b4`
- `0x18000e0d8`
- `0x1800102e8`
- `0x18001044c`
- `0x180010548`
- `0x180010798`
- `0x180010bfc`
- `0x180010c9c`

## callees

- `0x1800065d4`
- `0x180006608`

## pseudocode

```c
Win32Exception *__fastcall Win32Exception::Win32Exception(Win32Exception *this, signed int a2)
{
  if ( a2 > 0 )
    a2 = (unsigned __int16)a2 | 0x80070000;
  HResultException::HResultException(this, a2);
  *(_QWORD *)this = &Win32Exception::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800065d4  push    rbx
0x1800065d6  sub     rsp, 20h
0x1800065da  mov     rbx, rcx
0x1800065dd  test    edx, edx
0x1800065df  jle     short loc_1800065EA
0x1800065e1  movzx   edx, dx
0x1800065e4  or      edx, 80070000h; int
0x1800065ea  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800065ef  lea     rax, ??_7Win32Exception@@6B@; const Win32Exception::`vftable'
0x1800065f6  mov     [rbx], rax
0x1800065f9  mov     rax, rbx
0x1800065fc  add     rsp, 20h
0x180006600  pop     rbx
0x180006601  retn
```
