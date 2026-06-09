# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerCustomConsent,IHandlerAccessChange>::`vector deleting destructor'(uint)

- ea: `0x1800020e0`
- end: `0x180002108`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800020e0`
- `0x180005070`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IHandlerCustomConsent,IHandlerAccessChange>::`vector deleting destructor'(
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
0x1800020e0  push    rbx
0x1800020e2  sub     rsp, 20h
0x1800020e6  mov     dword ptr [rcx+14h], 0C0000001h
0x1800020ed  mov     rbx, rcx
0x1800020f0  test    dl, 1
0x1800020f3  jz      short loc_1800020FF
0x1800020f5  mov     edx, 18h
0x1800020fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800020ff  mov     rax, rbx
0x180002102  add     rsp, 20h
0x180002106  pop     rbx
0x180002107  retn
```
