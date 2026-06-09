# UnBCL::PathTooLongException::`scalar deleting destructor'(uint)

- ea: `0x18000e400`
- end: `0x18000e431`
- name: `??_GPathTooLongException@UnBCL@@UEAAPEAXI@Z`
- size: `49`
- prototype: `UnBCL::PathTooLongException *__fastcall(UnBCL::PathTooLongException *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000e400`

## import_xrefs

- `unbcl!??1PathTooLongException@UnBCL@@UEAA@XZ` at `0x18000e40f`
- `unbcl!??1PathTooLongException@UnBCL@@UEAA@XZ` at `0x18000e40f`
- `unbcl!??3Object@UnBCL@@SAXPEAX@Z` at `0x18000e41d`
- `unbcl!??3Object@UnBCL@@SAXPEAX@Z` at `0x18000e41d`

## pseudocode

```c
UnBCL::PathTooLongException *__fastcall UnBCL::PathTooLongException::`scalar deleting destructor'(
        UnBCL::PathTooLongException *this,
        char a2)
{
  UnBCL::PathTooLongException::~PathTooLongException(this);
  if ( (a2 & 1) != 0 )
    UnBCL::Object::operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e400  mov     [rsp+arg_0], rbx
0x18000e405  push    rdi
0x18000e406  sub     rsp, 20h
0x18000e40a  mov     ebx, edx
0x18000e40c  mov     rdi, rcx
0x18000e40f  call    cs:__imp_??1PathTooLongException@UnBCL@@UEAA@XZ; UnBCL::PathTooLongException::~PathTooLongException(void)
0x18000e415  test    bl, 1
0x18000e418  jz      short loc_18000E423
0x18000e41a  mov     rcx, rdi
0x18000e41d  call    cs:__imp_??3Object@UnBCL@@SAXPEAX@Z; UnBCL::Object::operator delete(void *)
0x18000e423  mov     rbx, [rsp+28h+arg_0]
0x18000e428  mov     rax, rdi
0x18000e42b  add     rsp, 20h
0x18000e42f  pop     rdi
0x18000e430  retn
```
