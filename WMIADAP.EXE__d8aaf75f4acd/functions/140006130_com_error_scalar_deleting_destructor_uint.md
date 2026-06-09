# _com_error::`scalar deleting destructor'(uint)

- ea: `0x140006130`
- end: `0x140006160`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `48`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400060e0`
- `0x140006130`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000614c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000614c`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x140006130  mov     [rsp+arg_0], rbx
0x140006135  push    rdi
0x140006136  sub     rsp, 20h
0x14000613a  mov     ebx, edx
0x14000613c  mov     rdi, rcx
0x14000613f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x140006144  test    bl, 1
0x140006147  jz      short loc_140006152
0x140006149  mov     rcx, rdi
0x14000614c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006152  mov     rbx, [rsp+28h+arg_0]
0x140006157  mov     rax, rdi
0x14000615a  add     rsp, 20h
0x14000615e  pop     rdi
0x14000615f  retn
```
