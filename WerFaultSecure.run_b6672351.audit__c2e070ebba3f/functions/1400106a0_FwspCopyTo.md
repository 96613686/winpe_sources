# FwspCopyTo

- ea: `0x1400106a0`
- end: `0x1400106c3`
- name: `FwspCopyTo`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400106a0`

## pseudocode

```c
__int64 __fastcall FwspCopyTo(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x1400106a0  test    r9, r9
0x1400106a3  jz      short loc_1400106AC
0x1400106a5  mov     qword ptr [r9], 0
0x1400106ac  mov     rax, [rsp+arg_20]
0x1400106b1  test    rax, rax
0x1400106b4  jz      short loc_1400106BD
0x1400106b6  mov     qword ptr [rax], 0
0x1400106bd  mov     eax, 80004001h
0x1400106c2  retn
```
