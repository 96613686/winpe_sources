# RegistryFunctions::`vector deleting destructor'(uint)

- ea: `0x180008460`
- end: `0x18000848b`
- name: `??_ERegistryFunctions@@UEAAPEAXI@Z`
- size: `43`
- prototype: `RegistryFunctions *__fastcall(RegistryFunctions *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001cd4`
- `0x180008460`

## pseudocode

```c
RegistryFunctions *__fastcall RegistryFunctions::`vector deleting destructor'(RegistryFunctions *this, char a2)
{
  *(_QWORD *)this = &IRegistryFunctions::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008460  push    rbx
0x180008462  sub     rsp, 20h
0x180008466  lea     rax, ??_7IRegistryFunctions@@6B@; const IRegistryFunctions::`vftable'
0x18000846d  mov     rbx, rcx
0x180008470  mov     [rcx], rax
0x180008473  test    dl, 1
0x180008476  jz      short loc_180008482
0x180008478  mov     edx, 8; unsigned __int64
0x18000847d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008482  mov     rax, rbx
0x180008485  add     rsp, 20h
0x180008489  pop     rbx
0x18000848a  retn
```
