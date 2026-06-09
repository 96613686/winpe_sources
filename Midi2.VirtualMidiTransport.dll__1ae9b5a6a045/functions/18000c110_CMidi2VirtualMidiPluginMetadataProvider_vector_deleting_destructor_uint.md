# CMidi2VirtualMidiPluginMetadataProvider::`vector deleting destructor'(uint)

- ea: `0x18000c110`
- end: `0x18000c138`
- name: `??_ECMidi2VirtualMidiPluginMetadataProvider@@UEAAPEAXI@Z`
- size: `40`
- prototype: `void *__fastcall(CMidi2VirtualMidiPluginMetadataProvider *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180003914`
- `0x18000c110`

## pseudocode

```c
CMidi2VirtualMidiPluginMetadataProvider *__fastcall CMidi2VirtualMidiPluginMetadataProvider::`vector deleting destructor'(
        CMidi2VirtualMidiPluginMetadataProvider *this,
        char a2)
{
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c110  push    rbx
0x18000c112  sub     rsp, 20h
0x18000c116  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000c11d  mov     rbx, rcx
0x18000c120  test    dl, 1
0x18000c123  jz      short loc_18000C12F
0x18000c125  mov     edx, 20h ; ' '
0x18000c12a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c12f  mov     rax, rbx
0x18000c132  add     rsp, 20h
0x18000c136  pop     rbx
0x18000c137  retn
```
