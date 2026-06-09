# SspiSrvCallBegin

- ea: `0x1800026a0`
- end: `0x1800026bc`
- name: `SspiSrvCallBegin`
- size: `28`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800028b0`
- `0x180002980`
- `0x1800029d0`
- `0x180002a30`
- `0x180002a80`
- `0x180002b90`
- `0x180002c70`
- `0x180002e70`

## callees

- `0x1800026a0`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800026b1`
- `ntdll!EtwEventActivityIdControl` at `0x1800026b1`

## pseudocode

```c
__int64 __fastcall SspiSrvCallBegin(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return EtwEventActivityIdControl(2, a1);
  return result;
}

```

## disassembly

```asm
0x1800026a0  sub     rsp, 28h
0x1800026a4  test    rcx, rcx
0x1800026a7  jz      short loc_1800026B7
0x1800026a9  mov     rdx, rcx
0x1800026ac  mov     ecx, 2
0x1800026b1  call    cs:__imp_EtwEventActivityIdControl
0x1800026b7  add     rsp, 28h
0x1800026bb  retn
```
