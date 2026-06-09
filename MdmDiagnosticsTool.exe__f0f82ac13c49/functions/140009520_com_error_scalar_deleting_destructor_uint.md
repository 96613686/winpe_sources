# _com_error::`scalar deleting destructor'(uint)

- ea: `0x140009520`
- end: `0x140009550`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400094d0`
- `0x140009520`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000953c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000953c`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009520  mov     [rsp+arg_0], rbx
0x140009525  push    rdi
0x140009526  sub     rsp, 20h
0x14000952a  mov     ebx, edx
0x14000952c  mov     rdi, rcx
0x14000952f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x140009534  test    bl, 1
0x140009537  jz      short loc_140009542
0x140009539  mov     rcx, rdi
0x14000953c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009542  mov     rbx, [rsp+28h+arg_0]
0x140009547  mov     rax, rdi
0x14000954a  add     rsp, 20h
0x14000954e  pop     rdi
0x14000954f  retn
```
