# FMIFS_MESSAGE::~FMIFS_MESSAGE(void)

- ea: `0x180003ee0`
- end: `0x180003efe`
- name: `??1FMIFS_MESSAGE@@UEAA@XZ`
- size: `30`
- prototype: `void __fastcall(FMIFS_MESSAGE *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800048c0`
- `0x180004ca0`
- `0x180005240`
- `0x1800058a0`
- `0x180007270`
- `0x180007610`
- `0x180008ac0`
- `0x180008ba0`

## import_xrefs

- `ulib!??1MESSAGE@@UEAA@XZ` at `0x180003ef7`

## pseudocode

```c
void __fastcall FMIFS_MESSAGE::~FMIFS_MESSAGE(FMIFS_MESSAGE *this)
{
  *(_QWORD *)this = &FMIFS_MESSAGE::`vftable';
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  MESSAGE::~MESSAGE((MESSAGE *)this);
}

```

## disassembly

```asm
0x180003ee0  lea     rax, ??_7FMIFS_MESSAGE@@6B@; const FMIFS_MESSAGE::`vftable'
0x180003ee7  mov     [rcx], rax
0x180003eea  xor     eax, eax
0x180003eec  mov     [rcx+68h], rax
0x180003ef0  mov     [rcx+70h], rax
0x180003ef4  mov     [rcx+78h], eax
0x180003ef7  jmp     cs:__imp_??1MESSAGE@@UEAA@XZ; MESSAGE::~MESSAGE(void)
```
