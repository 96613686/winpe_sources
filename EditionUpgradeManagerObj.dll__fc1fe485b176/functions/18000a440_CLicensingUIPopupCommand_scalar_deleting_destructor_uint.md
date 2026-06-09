# CLicensingUIPopupCommand::`scalar deleting destructor'(uint)

- ea: `0x18000a440`
- end: `0x18000a468`
- name: `??_GCLicensingUIPopupCommand@@UEAAPEAXI@Z`
- size: `40`
- prototype: `CLicensingUIPopupCommand *__fastcall(CLicensingUIPopupCommand *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000a440`

## pseudocode

```c
CLicensingUIPopupCommand *__fastcall CLicensingUIPopupCommand::`scalar deleting destructor'(
        CLicensingUIPopupCommand *this,
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
0x18000a440  push    rbx
0x18000a442  sub     rsp, 20h
0x18000a446  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000a44d  mov     rbx, rcx
0x18000a450  test    dl, 1
0x18000a453  jz      short loc_18000A45F
0x18000a455  mov     edx, 30h ; '0'; unsigned __int64
0x18000a45a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a45f  mov     rax, rbx
0x18000a462  add     rsp, 20h
0x18000a466  pop     rbx
0x18000a467  retn
```
