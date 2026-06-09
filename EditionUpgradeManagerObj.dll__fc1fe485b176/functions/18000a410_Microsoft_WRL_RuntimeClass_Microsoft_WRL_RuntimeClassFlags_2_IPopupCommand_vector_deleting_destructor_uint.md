# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vector deleting destructor'(uint)

- ea: `0x18000a410`
- end: `0x18000a438`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000a410`

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
0x18000a410  push    rbx
0x18000a412  sub     rsp, 20h
0x18000a416  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000a41d  mov     rbx, rcx
0x18000a420  test    dl, 1
0x18000a423  jz      short loc_18000A42F
0x18000a425  mov     edx, 10h; unsigned __int64
0x18000a42a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a42f  mov     rax, rbx
0x18000a432  add     rsp, 20h
0x18000a436  pop     rbx
0x18000a437  retn
```
