# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vector deleting destructor'(uint)

- ea: `0x140007f30`
- end: `0x140007f58`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000175c`
- `0x140007f30`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vector deleting destructor'(
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
0x140007f30  push    rbx
0x140007f32  sub     rsp, 20h
0x140007f36  mov     dword ptr [rcx+0Ch], 0C0000001h
0x140007f3d  mov     rbx, rcx
0x140007f40  test    dl, 1
0x140007f43  jz      short loc_140007F4F
0x140007f45  mov     edx, 10h
0x140007f4a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007f4f  mov     rax, rbx
0x140007f52  add     rsp, 20h
0x140007f56  pop     rbx
0x140007f57  retn
```
