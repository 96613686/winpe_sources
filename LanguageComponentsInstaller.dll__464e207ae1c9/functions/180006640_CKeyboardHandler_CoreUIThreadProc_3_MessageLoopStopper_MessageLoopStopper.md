# _CKeyboardHandler::CoreUIThreadProc_::_3_::MessageLoopStopper::_MessageLoopStopper

- ea: `0x180006640`
- end: `0x18000665e`
- name: `_CKeyboardHandler::CoreUIThreadProc_::_3_::MessageLoopStopper::_MessageLoopStopper`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027fd8`

## callees

- `0x180006640`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CKeyboardHandler::CoreUIThreadProc_::_3_::MessageLoopStopper::_MessageLoopStopper(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180006640  sub     rsp, 28h
0x180006644  mov     rcx, [rcx]
0x180006647  test    rcx, rcx
0x18000664a  jz      short loc_180006659
0x18000664c  mov     rax, [rcx]
0x18000664f  mov     rax, [rax+10h]
0x180006653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006658  nop
0x180006659  add     rsp, 28h
0x18000665d  retn
```
