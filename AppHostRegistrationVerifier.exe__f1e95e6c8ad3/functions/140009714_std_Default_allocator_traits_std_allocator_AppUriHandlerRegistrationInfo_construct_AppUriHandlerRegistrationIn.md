# std::_Default_allocator_traits<std::allocator<AppUriHandlerRegistrationInfo>>::construct<AppUriHandlerRegistrationInfo,AppUriHandlerRegistrationInfo>(std::allocator<AppUriHandlerRegistrationInfo> &,AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo &&)

- ea: `0x140009714`
- end: `0x140009732`
- name: `??$construct@UAppUriHandlerRegistrationInfo@@U1@@?$_Default_allocator_traits@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@SAXAEAV?$allocator@UAppUriHandlerRegistrationInfo@@@1@QEAUAppUriHandlerRegistrationInfo@@$$QEAU3@@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092cc`

## pseudocode

```c
__int64 __fastcall std::_Default_allocator_traits<std::allocator<AppUriHandlerRegistrationInfo>>::construct<AppUriHandlerRegistrationInfo,AppUriHandlerRegistrationInfo>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 result; // rax

  *a2 = *a3;
  result = a3[1];
  *a3 = 0;
  a2[1] = result;
  a3[1] = 0;
  return result;
}

```

## disassembly

```asm
0x140009714  mov     rax, [r8]
0x140009717  mov     [rdx], rax
0x14000971a  mov     rax, [r8+8]
0x14000971e  mov     qword ptr [r8], 0
0x140009725  mov     [rdx+8], rax
0x140009729  mov     qword ptr [r8+8], 0
0x140009731  retn
```
