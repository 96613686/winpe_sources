# Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(void)

- ea: `0x140007fec`
- end: `0x14000800a`
- name: `?InternalAddRef@?$ComPtr@UITaskHandler@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140007158`
- `0x140008a10`

## callees

- `0x140007fec`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ITaskHandler>::InternalAddRef(__int64 *a1)
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
0x140007fec  sub     rsp, 28h
0x140007ff0  mov     rcx, [rcx]
0x140007ff3  test    rcx, rcx
0x140007ff6  jz      short loc_140008005
0x140007ff8  mov     rax, [rcx]
0x140007ffb  mov     rax, [rax+8]
0x140007fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008004  nop
0x140008005  add     rsp, 28h
0x140008009  retn
```
