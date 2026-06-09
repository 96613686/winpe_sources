# PluginAction

- ea: `0x140009900`
- end: `0x140009911`
- name: `PluginAction`
- size: `17`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140007f3c`

## pseudocode

```c
__int64 __fastcall PluginAction(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4)
{
  return ExecuteAction(a2, a3, a4);
}

```

## disassembly

```asm
0x140009900  mov     rax, r8
0x140009903  mov     rcx, rdx; unsigned __int16 *
0x140009906  mov     rdx, rax; unsigned __int16 *
0x140009909  mov     r8, r9; unsigned __int8 *
0x14000990c  jmp     ?ExecuteAction@@YAJPEBG0PEAE@Z; ExecuteAction(ushort const *,ushort const *,uchar *)
```
