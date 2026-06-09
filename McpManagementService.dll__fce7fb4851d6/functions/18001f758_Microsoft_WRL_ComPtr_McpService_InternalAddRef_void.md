# Microsoft::WRL::ComPtr<McpService>::InternalAddRef(void)

- ea: `0x18001f758`
- end: `0x18001f776`
- name: `?InternalAddRef@?$ComPtr@VMcpService@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f554`
- `0x18001f9a4`
- `0x1800237f0`
- `0x180024ca0`

## callees

- `0x18001f758`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<McpService>::InternalAddRef(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001f758  sub     rsp, 28h
0x18001f75c  mov     rcx, [rcx]
0x18001f75f  test    rcx, rcx
0x18001f762  jz      short loc_18001F771
0x18001f764  mov     rax, [rcx]
0x18001f767  mov     rax, [rax+8]
0x18001f76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f770  nop
0x18001f771  add     rsp, 28h
0x18001f775  retn
```
