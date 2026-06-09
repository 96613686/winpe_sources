# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>(void)

- ea: `0x140009d90`
- end: `0x140009da1`
- name: `??0?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a934`
- `0x14000b114`

## pseudocode

```c
_QWORD *__fastcall std::vector<AppUriHandlerRegistrationInfo>::vector<AppUriHandlerRegistrationInfo>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x140009d90  xor     eax, eax
0x140009d92  mov     [rcx], rax
0x140009d95  mov     [rcx+8], rax
0x140009d99  mov     [rcx+10h], rax
0x140009d9d  mov     rax, rcx
0x140009da0  retn
```
