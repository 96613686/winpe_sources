# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vector deleting destructor'(uint)

- ea: `0x1400085d0`
- end: `0x1400085f4`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIObjectWithSelection@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400085d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400085e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400085e5`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IObjectWithSelection>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1400085d0  push    rbx
0x1400085d2  sub     rsp, 20h
0x1400085d6  mov     dword ptr [rcx+14h], 0C0000001h
0x1400085dd  mov     rbx, rcx
0x1400085e0  test    dl, 1
0x1400085e3  jz      short loc_1400085EB
0x1400085e5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400085eb  mov     rax, rbx
0x1400085ee  add     rsp, 20h
0x1400085f2  pop     rbx
0x1400085f3  retn
```
