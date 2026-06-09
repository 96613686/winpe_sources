# CSingleSideReducer::`vector deleting destructor'(uint)

- ea: `0x100437140`
- end: `0x100437174`
- name: `??_ECSingleSideReducer@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CSingleSideReducer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x100437140`
- `0x100437180`
- `0x100468a54`

## pseudocode

```c
CSingleSideReducer *__fastcall CSingleSideReducer::`vector deleting destructor'(CSingleSideReducer *this, char a2)
{
  CSingleSideReducer::~CSingleSideReducer(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x100437140  mov     [rsp+arg_0], rbx
0x100437145  push    rdi
0x100437146  sub     rsp, 20h
0x10043714a  mov     ebx, edx
0x10043714c  mov     rdi, rcx
0x10043714f  call    ??1CSingleSideReducer@@UEAA@XZ
0x100437154  test    bl, 1
0x100437157  jz      short loc_100437166
0x100437159  mov     edx, 0C8h; unsigned __int64
0x10043715e  mov     rcx, rdi; void *
0x100437161  call    ??3@YAXPEAX_K@Z
0x100437166  mov     rbx, [rsp+28h+arg_0]
0x10043716b  mov     rax, rdi
0x10043716e  add     rsp, 20h
0x100437172  pop     rdi
0x100437173  retn
```
