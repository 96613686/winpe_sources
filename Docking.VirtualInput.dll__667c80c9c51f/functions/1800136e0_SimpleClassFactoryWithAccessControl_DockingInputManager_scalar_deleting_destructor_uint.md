# SimpleClassFactoryWithAccessControl<DockingInputManager>::`scalar deleting destructor'(uint)

- ea: `0x1800136e0`
- end: `0x18001371c`
- name: `??_G?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@UEAAPEAXI@Z`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003a70`
- `0x1800134fc`
- `0x1800136e0`

## pseudocode

```c
void *__fastcall SimpleClassFactoryWithAccessControl<DockingInputManager>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  SimpleClassFactoryWithAccessControl<DockingInputManager>::~SimpleClassFactoryWithAccessControl<DockingInputManager>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800136e0  mov     [rsp+arg_8], edx
0x1800136e4  mov     [rsp+arg_0], rcx
0x1800136e9  sub     rsp, 28h
0x1800136ed  mov     rcx, [rsp+28h+arg_0]
0x1800136f2  call    ??1?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@UEAA@XZ; SimpleClassFactoryWithAccessControl<DockingInputManager>::~SimpleClassFactoryWithAccessControl<DockingInputManager>(void)
0x1800136f7  mov     eax, [rsp+28h+arg_8]
0x1800136fb  and     eax, 1
0x1800136fe  test    eax, eax
0x180013700  jz      short loc_180013712
0x180013702  mov     edx, 18h; unsigned __int64
0x180013707  mov     rcx, [rsp+28h+arg_0]; void *
0x18001370c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013711  nop
0x180013712  mov     rax, [rsp+28h+arg_0]
0x180013717  add     rsp, 28h
0x18001371b  retn
```
