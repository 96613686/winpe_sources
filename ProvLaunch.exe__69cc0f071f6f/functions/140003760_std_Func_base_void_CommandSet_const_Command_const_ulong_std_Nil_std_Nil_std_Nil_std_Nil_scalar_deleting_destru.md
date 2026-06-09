# std::_Func_base<void,CommandSet const &,Command const &,ulong,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`scalar deleting destructor'(uint)

- ea: `0x140003760`
- end: `0x140003787`
- name: `??_G?$_Func_base@XAEBUCommandSet@@AEBUCommand@@KU_Nil@std@@U34@U34@U34@@std@@UEAAPEAXI@Z`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003760`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003778`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003778`

## pseudocode

```c
_QWORD *__fastcall std::_Func_base<void,CommandSet const &,Command const &,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Func_base<void,CommandSet const &,Command const &,unsigned long,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003760  push    rbx
0x140003762  sub     rsp, 20h
0x140003766  lea     rax, ??_7?$_Func_base@XAEBUCommandSet@@AEBUCommand@@KU_Nil@std@@U34@U34@U34@@std@@6B@; const std::_Func_base<void,CommandSet const &,Command const &,ulong,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14000376d  mov     rbx, rcx
0x140003770  mov     [rcx], rax
0x140003773  test    dl, 1
0x140003776  jz      short loc_14000377E
0x140003778  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000377e  mov     rax, rbx
0x140003781  add     rsp, 20h
0x140003785  pop     rbx
0x140003786  retn
```
