# CMidi2VirtualMidiConfigurationManager::`vector deleting destructor'(uint)

- ea: `0x18001ab00`
- end: `0x18001ab4d`
- name: `??_ECMidi2VirtualMidiConfigurationManager@@UEAAPEAXI@Z`
- size: `77`
- prototype: `void *__fastcall(CMidi2VirtualMidiConfigurationManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180003914`
- `0x18001ab00`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMidi2VirtualMidiConfigurationManager *__fastcall CMidi2VirtualMidiConfigurationManager::`vector deleting destructor'(
        CMidi2VirtualMidiConfigurationManager *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ab00  mov     [rsp+arg_0], rbx
0x18001ab05  push    rdi
0x18001ab06  sub     rsp, 20h
0x18001ab0a  mov     edi, edx
0x18001ab0c  mov     rbx, rcx
0x18001ab0f  mov     rcx, [rcx+10h]
0x18001ab13  test    rcx, rcx
0x18001ab16  jz      short loc_18001AB25
0x18001ab18  mov     rax, [rcx]
0x18001ab1b  mov     rax, [rax+10h]
0x18001ab1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab24  nop
0x18001ab25  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18001ab2c  test    dil, 1
0x18001ab30  jz      short loc_18001AB3F
0x18001ab32  mov     edx, 28h ; '('
0x18001ab37  mov     rcx, rbx; Block
0x18001ab3a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ab3f  mov     rax, rbx
0x18001ab42  mov     rbx, [rsp+28h+arg_0]
0x18001ab47  add     rsp, 20h
0x18001ab4b  pop     rdi
0x18001ab4c  retn
```
