# __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)

- ea: `0x140002d9c`
- end: `0x140002da4`
- name: `?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _s_FuncInfo *, struct _xDISPATCHER_CONTEXT *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1400027d0`
- `0x1400027fc`
- `0x140002860`
- `0x14000294c`
- `0x140004170`

## callees

- `0x140002da4`

## pseudocode

```c
__int64 __fastcall __FrameHandler3::StateFromControlPc(const struct _s_FuncInfo *a1, struct _xDISPATCHER_CONTEXT *a2)
{
  return __FrameHandler3::StateFromIp(a1, a2, a2->ControlPc);
}

```

## disassembly

```asm
0x140002d9c  mov     r8, [rdx]; unsigned __int64
0x140002d9f  jmp     $+5
```
