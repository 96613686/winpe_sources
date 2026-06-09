# AutoDeleteFileStream::`vector deleting destructor'(uint)

- ea: `0x1800104c0`
- end: `0x1800104f0`
- name: `??_EAutoDeleteFileStream@@UEAAPEAXI@Z`
- size: `48`
- prototype: `AutoDeleteFileStream *__fastcall(AutoDeleteFileStream *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800103d0`
- `0x1800104c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800104dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800104dc`

## pseudocode

```c
AutoDeleteFileStream *__fastcall AutoDeleteFileStream::`vector deleting destructor'(
        AutoDeleteFileStream *this,
        char a2)
{
  AutoDeleteFileStream::~AutoDeleteFileStream(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_0], rbx
0x1800104c5  push    rdi
0x1800104c6  sub     rsp, 20h
0x1800104ca  mov     ebx, edx
0x1800104cc  mov     rdi, rcx
0x1800104cf  call    ??1AutoDeleteFileStream@@UEAA@XZ; AutoDeleteFileStream::~AutoDeleteFileStream(void)
0x1800104d4  test    bl, 1
0x1800104d7  jz      short loc_1800104E2
0x1800104d9  mov     rcx, rdi
0x1800104dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800104e2  mov     rbx, [rsp+28h+arg_0]
0x1800104e7  mov     rax, rdi
0x1800104ea  add     rsp, 20h
0x1800104ee  pop     rdi
0x1800104ef  retn
```
