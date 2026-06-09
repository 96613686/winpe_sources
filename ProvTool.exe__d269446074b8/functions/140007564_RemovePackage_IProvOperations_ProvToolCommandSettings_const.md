# RemovePackage(IProvOperations *,_ProvToolCommandSettings const &)

- ea: `0x140007564`
- end: `0x140007584`
- name: `?RemovePackage@@YAJPEAUIProvOperations@@AEBU_ProvToolCommandSettings@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(struct IProvOperations *, const struct _ProvToolCommandSettings *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x140007564`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall RemovePackage(struct IProvOperations *a1, const struct _ProvToolCommandSettings *a2)
{
  __int64 result; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    result = (*(__int64 (__fastcall **)(struct IProvOperations *))(*(_QWORD *)a1 + 32LL))(a1);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB0,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x140007564  sub     rsp, 28h
0x140007568  mov     rax, [rcx]
0x14000756b  mov     rdx, [rdx+30h]
0x14000756f  mov     rax, [rax+20h]
0x140007573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007578  jmp     short loc_14000757E
0x14000757a  mov     eax, [rsp+28h+arg_0]
0x14000757e  add     rsp, 28h
0x140007582  retn
```
