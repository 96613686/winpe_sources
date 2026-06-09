# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vector deleting destructor'(uint)

- ea: `0x18000b8a0`
- end: `0x18000b8c8`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiTransportConfigurationManager@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800033f4`
- `0x18000b8a0`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiTransportConfigurationManager>::`vector deleting destructor'(
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
0x18000b8a0  push    rbx
0x18000b8a2  sub     rsp, 20h
0x18000b8a6  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000b8ad  mov     rbx, rcx
0x18000b8b0  test    dl, 1
0x18000b8b3  jz      short loc_18000B8BF
0x18000b8b5  mov     edx, 10h
0x18000b8ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b8bf  mov     rax, rbx
0x18000b8c2  add     rsp, 20h
0x18000b8c6  pop     rbx
0x18000b8c7  retn
```
