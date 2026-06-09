# CWMIBroker::`scalar deleting destructor'(uint)

- ea: `0x140002ff0`
- end: `0x140003020`
- name: `??_GCWMIBroker@@UEAAPEAXI@Z`
- size: `48`
- prototype: `unsigned __int16 **__fastcall(unsigned __int16 **this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002f04`
- `0x140002ff0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000300c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000300c`

## pseudocode

```c
unsigned __int16 **__fastcall CWMIBroker::`scalar deleting destructor'(unsigned __int16 **this, char a2)
{
  CWMIBroker::~CWMIBroker(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x140002ff0  mov     [rsp+arg_0], rbx
0x140002ff5  push    rdi
0x140002ff6  sub     rsp, 20h
0x140002ffa  mov     ebx, edx
0x140002ffc  mov     rdi, rcx
0x140002fff  call    ??1CWMIBroker@@UEAA@XZ; CWMIBroker::~CWMIBroker(void)
0x140003004  test    bl, 1
0x140003007  jz      short loc_140003012
0x140003009  mov     rcx, rdi
0x14000300c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140003012  mov     rax, rdi
0x140003015  mov     rbx, [rsp+28h+arg_0]
0x14000301a  add     rsp, 20h
0x14000301e  pop     rdi
0x14000301f  retn
```
