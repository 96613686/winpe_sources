# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck>::`vector deleting destructor'(uint)

- ea: `0x180002840`
- end: `0x180002868`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerAccessCheck@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002840`
- `0x180005070`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerAccessCheck>::`vector deleting destructor'(
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
0x180002840  push    rbx
0x180002842  sub     rsp, 20h
0x180002846  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000284d  mov     rbx, rcx
0x180002850  test    dl, 1
0x180002853  jz      short loc_18000285F
0x180002855  mov     edx, 10h
0x18000285a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000285f  mov     rax, rbx
0x180002862  add     rsp, 20h
0x180002866  pop     rbx
0x180002867  retn
```
