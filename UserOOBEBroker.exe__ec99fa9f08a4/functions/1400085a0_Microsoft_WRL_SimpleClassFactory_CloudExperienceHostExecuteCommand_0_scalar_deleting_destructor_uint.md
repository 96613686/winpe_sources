# Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::`scalar deleting destructor'(uint)

- ea: `0x1400085a0`
- end: `0x1400085c4`
- name: `??_G?$SimpleClassFactory@VCloudExperienceHostExecuteCommand@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400085a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400085b5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400085b5`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1400085a0  push    rbx
0x1400085a2  sub     rsp, 20h
0x1400085a6  mov     dword ptr [rcx+0Ch], 0C0000001h
0x1400085ad  mov     rbx, rcx
0x1400085b0  test    dl, 1
0x1400085b3  jz      short loc_1400085BB
0x1400085b5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400085bb  mov     rax, rbx
0x1400085be  add     rsp, 20h
0x1400085c2  pop     rbx
0x1400085c3  retn
```
