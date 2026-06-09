# AddStackTraceToException<UnBCL::PathTooLongException>(UnBCL::PathTooLongException *,char const *)

- ea: `0x18000d02c`
- end: `0x18000d04b`
- name: `??$AddStackTraceToException@VPathTooLongException@UnBCL@@@@YAPEAVPathTooLongException@UnBCL@@PEAV01@PEBD@Z`
- size: `31`
- prototype: `UnBCL::Exception *__fastcall(UnBCL::Exception *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180013dd8`

## import_xrefs

- `unbcl!?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z` at `0x18000d03c`
- `unbcl!?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z` at `0x18000d03c`

## string_xrefs

- `0x18000d032`: `void __cdecl pCheckPathTooLong(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
UnBCL::Exception *__fastcall AddStackTraceToException<UnBCL::PathTooLongException>(UnBCL::Exception *a1)
{
  UnBCL::Exception::AddStackTrace(a1, "void __cdecl pCheckPathTooLong(const class UnBCL::String *)");
  return a1;
}

```

## disassembly

```asm
0x18000d02c  push    rbx
0x18000d02e  sub     rsp, 20h
0x18000d032  lea     rdx, aVoidCdeclPchec; "void __cdecl pCheckPathTooLong(const cl"...
0x18000d039  mov     rbx, rcx
0x18000d03c  call    cs:__imp_?AddStackTrace@Exception@UnBCL@@QEAAXPEBD@Z; UnBCL::Exception::AddStackTrace(char const *)
0x18000d042  mov     rax, rbx
0x18000d045  add     rsp, 20h
0x18000d049  pop     rbx
0x18000d04a  retn
```
