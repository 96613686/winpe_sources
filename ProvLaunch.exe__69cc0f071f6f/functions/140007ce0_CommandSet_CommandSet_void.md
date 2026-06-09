# CommandSet::~CommandSet(void)

- ea: `0x140007ce0`
- end: `0x140007d1a`
- name: `??1CommandSet@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CommandSet *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003560`
- `0x1400090ec`
- `0x14000ad7b`
- `0x14000add6`

## callees

- `0x140007c70`
- `0x140007ce0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007cf4`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007cf4`

## pseudocode

```c
void __fastcall CommandSet::~CommandSet(CommandSet *this)
{
  if ( *((_QWORD *)this + 6) >= 8u )
    operator delete(*((void **)this + 3));
  *((_QWORD *)this + 6) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 12) = 0;
  std::list<Command>::~list<Command>((void ***)this + 1);
}

```

## disassembly

```asm
0x140007ce0  push    rbx
0x140007ce2  sub     rsp, 20h
0x140007ce6  cmp     qword ptr [rcx+30h], 8
0x140007ceb  mov     rbx, rcx
0x140007cee  jb      short loc_140007CFA
0x140007cf0  mov     rcx, [rcx+18h]
0x140007cf4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007cfa  xor     eax, eax
0x140007cfc  mov     qword ptr [rbx+30h], 7
0x140007d04  mov     [rbx+28h], rax
0x140007d08  lea     rcx, [rbx+8]; void *
0x140007d0c  mov     [rbx+18h], ax
0x140007d10  add     rsp, 20h
0x140007d14  pop     rbx
0x140007d15  jmp     ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; std::list<Command>::~list<Command>(void)
```
