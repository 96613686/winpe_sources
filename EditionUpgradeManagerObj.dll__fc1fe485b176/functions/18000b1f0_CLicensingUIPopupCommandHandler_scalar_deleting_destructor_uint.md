# CLicensingUIPopupCommandHandler::`scalar deleting destructor'(uint)

- ea: `0x18000b1f0`
- end: `0x18000b218`
- name: `??_GCLicensingUIPopupCommandHandler@@UEAAPEAXI@Z`
- size: `40`
- prototype: `CLicensingUIPopupCommandHandler *__fastcall(CLicensingUIPopupCommandHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000b1f0`

## pseudocode

```c
CLicensingUIPopupCommandHandler *__fastcall CLicensingUIPopupCommandHandler::`scalar deleting destructor'(
        CLicensingUIPopupCommandHandler *this,
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
0x18000b1f0  push    rbx
0x18000b1f2  sub     rsp, 20h
0x18000b1f6  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000b1fd  mov     rbx, rcx
0x18000b200  test    dl, 1
0x18000b203  jz      short loc_18000B20F
0x18000b205  mov     edx, 20h ; ' '; unsigned __int64
0x18000b20a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b20f  mov     rax, rbx
0x18000b212  add     rsp, 20h
0x18000b216  pop     rbx
0x18000b217  retn
```
