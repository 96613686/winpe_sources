# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`scalar deleting destructor'(uint)

- ea: `0x14000c8c0`
- end: `0x14000c8e8`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140003644`
- `0x14000c8c0`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`scalar deleting destructor'(
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
0x14000c8c0  push    rbx
0x14000c8c2  sub     rsp, 20h
0x14000c8c6  mov     dword ptr [rcx+0Ch], 0C0000001h
0x14000c8cd  mov     rbx, rcx
0x14000c8d0  test    dl, 1
0x14000c8d3  jz      short loc_14000C8DF
0x14000c8d5  mov     edx, 10h; unsigned __int64
0x14000c8da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c8df  mov     rax, rbx
0x14000c8e2  add     rsp, 20h
0x14000c8e6  pop     rbx
0x14000c8e7  retn
```
