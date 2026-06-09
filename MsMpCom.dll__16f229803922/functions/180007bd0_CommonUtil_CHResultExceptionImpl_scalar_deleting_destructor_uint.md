# CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(uint)

- ea: `0x180007bd0`
- end: `0x180007c0a`
- name: `??_GCHResultExceptionImpl@CommonUtil@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(CommonUtil::CHResultExceptionImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001ca8`
- `0x180007bd0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007bf6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bf6`

## pseudocode

```c
CommonUtil::CHResultExceptionImpl *__fastcall CommonUtil::CHResultExceptionImpl::`scalar deleting destructor'(
        CommonUtil::CHResultExceptionImpl *this,
        char a2)
{
  *(_QWORD *)this = &CommonUtil::CHResultException::`vftable';
  exception::~exception(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007bd0  mov     [rsp+arg_0], rbx
0x180007bd5  push    rdi
0x180007bd6  sub     rsp, 20h
0x180007bda  lea     rax, ??_7CHResultException@CommonUtil@@6B@; const CommonUtil::CHResultException::`vftable'
0x180007be1  mov     ebx, edx
0x180007be3  mov     [rcx], rax
0x180007be6  mov     rdi, rcx
0x180007be9  call    ??1exception@@UEAA@XZ_0; exception::~exception(void)
0x180007bee  test    bl, 1
0x180007bf1  jz      short loc_180007BFC
0x180007bf3  mov     rcx, rdi
0x180007bf6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007bfc  mov     rbx, [rsp+28h+arg_0]
0x180007c01  mov     rax, rdi
0x180007c04  add     rsp, 20h
0x180007c08  pop     rdi
0x180007c09  retn
```
