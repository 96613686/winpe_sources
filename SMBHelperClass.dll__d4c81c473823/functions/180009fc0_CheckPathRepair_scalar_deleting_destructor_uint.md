# CheckPathRepair::`scalar deleting destructor'(uint)

- ea: `0x180009fc0`
- end: `0x180009ff0`
- name: `??_GCheckPathRepair@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CheckPathRepair *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180009fc0`
- `0x18000f9d8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009fdc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009fdc`

## pseudocode

```c
CheckPathRepair *__fastcall CheckPathRepair::`scalar deleting destructor'(CheckPathRepair *this, char a2)
{
  Repair::~Repair(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009fc0  mov     [rsp+arg_0], rbx
0x180009fc5  push    rdi
0x180009fc6  sub     rsp, 20h
0x180009fca  mov     ebx, edx
0x180009fcc  mov     rdi, rcx
0x180009fcf  call    ??1Repair@@UEAA@XZ; Repair::~Repair(void)
0x180009fd4  test    bl, 1
0x180009fd7  jz      short loc_180009FE2
0x180009fd9  mov     rcx, rdi
0x180009fdc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009fe2  mov     rbx, [rsp+28h+arg_0]
0x180009fe7  mov     rax, rdi
0x180009fea  add     rsp, 20h
0x180009fee  pop     rdi
0x180009fef  retn
```
