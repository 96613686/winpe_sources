# Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(void)

- ea: `0x18000df0c`
- end: `0x18000df2a`
- name: `?InternalAddRef@?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000da7c`
- `0x18000f924`
- `0x180010a9c`
- `0x18001a17c`
- `0x18001ae80`
- `0x18001afe4`

## callees

- `0x18000df0c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(__int64 *a1)
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
0x18000df0c  sub     rsp, 28h
0x18000df10  mov     rcx, [rcx]
0x18000df13  test    rcx, rcx
0x18000df16  jz      short loc_18000DF25
0x18000df18  mov     rax, [rcx]
0x18000df1b  mov     rax, [rax+8]
0x18000df1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df24  nop
0x18000df25  add     rsp, 28h
0x18000df29  retn
```
