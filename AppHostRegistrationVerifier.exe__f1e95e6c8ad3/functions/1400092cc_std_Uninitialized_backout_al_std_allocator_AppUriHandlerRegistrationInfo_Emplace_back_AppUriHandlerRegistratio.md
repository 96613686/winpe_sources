# std::_Uninitialized_backout_al<std::allocator<AppUriHandlerRegistrationInfo>>::_Emplace_back<AppUriHandlerRegistrationInfo>(AppUriHandlerRegistrationInfo &&)

- ea: `0x1400092cc`
- end: `0x1400092e6`
- name: `??$_Emplace_back@UAppUriHandlerRegistrationInfo@@@?$_Uninitialized_backout_al@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAAX$$QEAUAppUriHandlerRegistrationInfo@@@Z`
- size: `26`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000964c`

## callees

- `0x140009714`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_backout_al<std::allocator<AppUriHandlerRegistrationInfo>>::_Emplace_back<AppUriHandlerRegistrationInfo>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = std::_Default_allocator_traits<std::allocator<AppUriHandlerRegistrationInfo>>::construct<AppUriHandlerRegistrationInfo,AppUriHandlerRegistrationInfo>(
             a1,
             *(_QWORD *)(a1 + 8),
             a2);
  *(_QWORD *)(v3 + 8) += 16LL;
  return result;
}

```

## disassembly

```asm
0x1400092cc  sub     rsp, 28h
0x1400092d0  mov     r8, rdx
0x1400092d3  mov     rdx, [rcx+8]
0x1400092d7  call    ??$construct@UAppUriHandlerRegistrationInfo@@U1@@?$_Default_allocator_traits@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@SAXAEAV?$allocator@UAppUriHandlerRegistrationInfo@@@1@QEAUAppUriHandlerRegistrationInfo@@$$QEAU3@@Z; std::_Default_allocator_traits<std::allocator<AppUriHandlerRegistrationInfo>>::construct<AppUriHandlerRegistrationInfo,AppUriHandlerRegistrationInfo>(std::allocator<AppUriHandlerRegistrationInfo> &,AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo &&)
0x1400092dc  add     qword ptr [rcx+8], 10h
0x1400092e1  add     rsp, 28h
0x1400092e5  retn
```
