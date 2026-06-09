# SmAllocUninstallStringData

- ea: `0x140001044`
- end: `0x14000105f`
- name: `SmAllocUninstallStringData`
- size: `27`
- prototype: `__int64 (*())(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007e00`

## callees

- `0x140001044`
- `0x140001860`

## pseudocode

```c
__int64 (*SmAllocUninstallStringData())(void)
{
  __int64 (*result)(void); // rax

  result = qword_140004080;
  if ( qword_140004080 )
    return (__int64 (*)(void))qword_140004080();
  return result;
}

```

## disassembly

```asm
0x140001044  sub     rsp, 28h
0x140001048  mov     rax, cs:qword_140004080
0x14000104f  test    rax, rax
0x140001052  jz      short loc_140001059
0x140001054  call    _guard_dispatch_icall
0x140001059  add     rsp, 28h
0x14000105d  retn
```
