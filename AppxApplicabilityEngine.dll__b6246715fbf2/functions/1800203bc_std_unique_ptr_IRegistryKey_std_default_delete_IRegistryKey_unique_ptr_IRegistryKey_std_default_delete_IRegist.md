# std::unique_ptr<IRegistryKey,std::default_delete<IRegistryKey>>::~unique_ptr<IRegistryKey,std::default_delete<IRegistryKey>>(void)

- ea: `0x1800203bc`
- end: `0x1800203de`
- name: `??1?$unique_ptr@VIRegistryKey@@U?$default_delete@VIRegistryKey@@@std@@@std@@QEAA@XZ`
- size: `34`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800245ec`
- `0x1800248df`
- `0x180024af5`

## callees

- `0x1800203bc`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IRegistryKey>::~unique_ptr<IRegistryKey>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 96LL))(v1, 1);
  return result;
}

```

## disassembly

```asm
0x1800203bc  sub     rsp, 28h
0x1800203c0  mov     rcx, [rcx]
0x1800203c3  test    rcx, rcx
0x1800203c6  jz      short loc_1800203D9
0x1800203c8  mov     rax, [rcx]
0x1800203cb  mov     edx, 1
0x1800203d0  mov     rax, [rax+60h]
0x1800203d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203d9  add     rsp, 28h
0x1800203dd  retn
```
