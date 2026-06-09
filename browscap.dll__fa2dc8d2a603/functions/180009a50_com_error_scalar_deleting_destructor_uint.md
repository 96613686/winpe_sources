# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180009a50`
- end: `0x180009aab`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `91`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009a50`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180009a97`
- `msvcrt!free` at `0x180009a97`
- `KERNEL32!LocalFree` at `0x180009a87`
- `KERNEL32!LocalFree` at `0x180009a87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x180009a50  mov     [rsp+arg_0], rbx
0x180009a55  push    rdi
0x180009a56  sub     rsp, 20h
0x180009a5a  mov     edi, edx
0x180009a5c  mov     rbx, rcx
0x180009a5f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180009a66  mov     [rcx], rax
0x180009a69  mov     rcx, [rcx+10h]
0x180009a6d  test    rcx, rcx
0x180009a70  jz      short loc_180009A7E
0x180009a72  mov     rax, [rcx]
0x180009a75  mov     rax, [rax+10h]
0x180009a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7e  mov     rcx, [rbx+18h]; hMem
0x180009a82  test    rcx, rcx
0x180009a85  jz      short loc_180009A8E
0x180009a87  call    cs:__imp_LocalFree
0x180009a8d  nop
0x180009a8e  test    dil, 1
0x180009a92  jz      short loc_180009A9D
0x180009a94  mov     rcx, rbx; Block
0x180009a97  call    cs:__imp_free
0x180009a9d  mov     rax, rbx
0x180009aa0  mov     rbx, [rsp+28h+arg_0]
0x180009aa5  add     rsp, 20h
0x180009aa9  pop     rdi
0x180009aaa  retn
```
