# std::logic_error::~logic_error(void)

- ea: `0x14000d350`
- end: `0x14000d380`
- name: `??1logic_error@std@@UEAA@XZ`
- size: `48`
- prototype: `void __fastcall(std::logic_error *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d338`
- `0x14000d388`
- `0x14000d420`
- `0x14000d460`
- `0x14000d4a0`

## callees

- `0x14000f998`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x14000d379`

## pseudocode

```c
void __fastcall std::logic_error::~logic_error(std::logic_error *this)
{
  *(_QWORD *)this = &std::logic_error::`vftable';
  std::string::_Tidy((__int64)this + 24, 1, 0);
  exception::~exception(this);
}

```

## disassembly

```asm
0x14000d350  push    rbx
0x14000d352  sub     rsp, 20h
0x14000d356  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x14000d35d  mov     rbx, rcx
0x14000d360  mov     [rcx], rax
0x14000d363  xor     r8d, r8d
0x14000d366  add     rcx, 18h
0x14000d36a  mov     dl, 1
0x14000d36c  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000d371  mov     rcx, rbx
0x14000d374  add     rsp, 20h
0x14000d378  pop     rbx
0x14000d379  jmp     cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
```
