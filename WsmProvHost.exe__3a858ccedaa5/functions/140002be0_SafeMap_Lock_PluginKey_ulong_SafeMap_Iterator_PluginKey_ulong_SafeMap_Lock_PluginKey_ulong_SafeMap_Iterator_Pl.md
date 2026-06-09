# SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>::~SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>(void)

- ea: `0x140002be0`
- end: `0x140002bff`
- name: `??1?$SafeMap_Lock@UPluginKey@@KV?$SafeMap_Iterator@UPluginKey@@K@@@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(_BYTE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400044f6`
- `0x140004508`

## callees

- `0x140002be0`
- `0x140005010`

## pseudocode

```c
__int64 __fastcall SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>::~SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>(
        _BYTE *a1)
{
  __int64 result; // rax

  if ( a1[8] )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 24LL))(*(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x140002be0  sub     rsp, 28h; public: SafeMap_Lock<class CListenerOperation *, struct Empty, class SafeMap_Iterator<class CListenerOperation *, struct Empty>>::~SafeMap_Lock<class CListenerOperation *, struct Empty, class SafeMap_Iterator<class CListenerOperation *, struct Empty>>(void)
0x140002be4  cmp     byte ptr [rcx+8], 0
0x140002be8  jz      short loc_140002BFA
0x140002bea  mov     rcx, [rcx]
0x140002bed  mov     rax, [rcx]
0x140002bf0  mov     rax, [rax+18h]
0x140002bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bf9  nop
0x140002bfa  add     rsp, 28h
0x140002bfe  retn
```
