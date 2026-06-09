# std::unique_ptr<_GUID,std::default_delete<_GUID>>::~unique_ptr<_GUID,std::default_delete<_GUID>>(void)

- ea: `0x1800052e4`
- end: `0x1800052ff`
- name: `??1?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005494`
- `0x180005600`
- `0x180016d10`
- `0x180017468`
- `0x180017928`
- `0x180018b50`
- `0x180019418`
- `0x18002b063`
- `0x18002b075`
- `0x18002b087`
- `0x18002b0f8`
- `0x18002b10a`
- `0x18002b168`
- `0x18002b17a`

## callees

- `0x180002ea4`
- `0x1800052e4`

## pseudocode

```c
void __fastcall std::unique_ptr<_GUID>::~unique_ptr<_GUID>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, 0x10u);
}

```

## disassembly

```asm
0x1800052e4  sub     rsp, 28h
0x1800052e8  mov     rcx, [rcx]; void *
0x1800052eb  test    rcx, rcx
0x1800052ee  jz      short loc_1800052FA
0x1800052f0  mov     edx, 10h; unsigned __int64
0x1800052f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800052fa  add     rsp, 28h
0x1800052fe  retn
```
