# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180004874`
- end: `0x180004885`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003bfc`
- `0x180003ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000487e`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180004874  xor     r9d, r9d
0x180004877  xor     r8d, r8d
0x18000487a  lea     edx, [r9+1]
0x18000487e  jmp     cs:__imp_RaiseException
```
