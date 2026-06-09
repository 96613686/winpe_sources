# std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::`vector deleting destructor'(uint)

- ea: `0x1800055a0`
- end: `0x1800055c7`
- name: `??_E?$_Ref_count_del@VSharedMemory@@U?$default_delete@VSharedMemory@@@std@@@std@@UEAAPEAXI@Z`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800055a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800055b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800055b8`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_del<SharedMemory,std::default_delete<SharedMemory>>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Ref_count_base::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800055a0  push    rbx
0x1800055a2  sub     rsp, 20h
0x1800055a6  lea     rax, ??_7_Ref_count_base@std@@6B@; const std::_Ref_count_base::`vftable'
0x1800055ad  mov     rbx, rcx
0x1800055b0  mov     [rcx], rax
0x1800055b3  test    dl, 1
0x1800055b6  jz      short loc_1800055BE
0x1800055b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800055be  mov     rax, rbx
0x1800055c1  add     rsp, 20h
0x1800055c5  pop     rbx
0x1800055c6  retn
```
