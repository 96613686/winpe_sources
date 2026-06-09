# Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)

- ea: `0x18009c41c`
- end: `0x18009c444`
- name: `?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ`
- size: `40`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009874c`
- `0x1800989fc`
- `0x18009b4b0`
- `0x18009b6f0`
- `0x1800a55bc`
- `0x1800a7b28`
- `0x1800a7f98`
- `0x1800aafe0`
- `0x1800ab470`
- `0x1800ab5b0`

## callees

- `0x18009c41c`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(__int64 *a1)
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
0x18009c41c  sub     rsp, 38h
0x18009c420  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18009c429  mov     rcx, [rcx]
0x18009c42c  test    rcx, rcx
0x18009c42f  jz      short loc_18009C43E
0x18009c431  mov     rax, [rcx]
0x18009c434  mov     rax, [rax+8]
0x18009c438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c43d  nop
0x18009c43e  add     rsp, 38h
0x18009c442  retn
```
