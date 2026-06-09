# MpConfigUtils::CSimpleMpConfig::`scalar deleting destructor'(uint)

- ea: `0x180006130`
- end: `0x180006160`
- name: `??_GCSimpleMpConfig@MpConfigUtils@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(MpConfigUtils::CSimpleMpConfig *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180006020`
- `0x180006130`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000614c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000614c`

## pseudocode

```c
MpConfigUtils::CSimpleMpConfig *__fastcall MpConfigUtils::CSimpleMpConfig::`scalar deleting destructor'(
        MpConfigUtils::CSimpleMpConfig *this,
        char a2)
{
  MpConfigUtils::CSimpleMpConfig::~CSimpleMpConfig(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006130  mov     [rsp+arg_0], rbx
0x180006135  push    rdi
0x180006136  sub     rsp, 20h
0x18000613a  mov     ebx, edx
0x18000613c  mov     rdi, rcx
0x18000613f  call    ??1CSimpleMpConfig@MpConfigUtils@@UEAA@XZ; MpConfigUtils::CSimpleMpConfig::~CSimpleMpConfig(void)
0x180006144  test    bl, 1
0x180006147  jz      short loc_180006152
0x180006149  mov     rcx, rdi
0x18000614c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006152  mov     rbx, [rsp+28h+arg_0]
0x180006157  mov     rax, rdi
0x18000615a  add     rsp, 20h
0x18000615e  pop     rdi
0x18000615f  retn
```
