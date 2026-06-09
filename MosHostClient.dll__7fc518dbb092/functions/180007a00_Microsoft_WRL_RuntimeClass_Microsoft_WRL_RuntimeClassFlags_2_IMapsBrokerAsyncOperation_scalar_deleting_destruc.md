# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::`scalar deleting destructor'(uint)

- ea: `0x180007a00`
- end: `0x180007a23`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMapsBrokerAsyncOperation@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002534`
- `0x180007a00`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::`scalar deleting destructor'(
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
0x180007a00  push    rbx
0x180007a02  sub     rsp, 20h
0x180007a06  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180007a0d  mov     rbx, rcx
0x180007a10  test    dl, 1
0x180007a13  jz      short loc_180007A1A
0x180007a15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007a1a  mov     rax, rbx
0x180007a1d  add     rsp, 20h
0x180007a21  pop     rbx
0x180007a22  retn
```
