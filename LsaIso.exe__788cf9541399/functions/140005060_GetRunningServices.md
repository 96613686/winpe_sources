# GetRunningServices

- ea: `0x140005060`
- end: `0x14000507b`
- name: `GetRunningServices`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140005060`

## pseudocode

```c
__int64 GetRunningServices()
{
  __int64 result; // rax

  result = 0;
  if ( g_fKeyGuardEnabled )
    result = 2;
  if ( g_fCredGuardEnabled )
    return (unsigned int)result | 1;
  return result;
}

```

## disassembly

```asm
0x140005060  xor     eax, eax
0x140005062  cmp     cs:?g_fKeyGuardEnabled@@3HA, eax; int g_fKeyGuardEnabled
0x140005068  lea     ecx, [rax+2]
0x14000506b  cmovnz  eax, ecx
0x14000506e  cmp     cs:?g_fCredGuardEnabled@@3HA, 0; int g_fCredGuardEnabled
0x140005075  jz      short locret_14000507A
0x140005077  or      eax, 1
0x14000507a  retn
```
