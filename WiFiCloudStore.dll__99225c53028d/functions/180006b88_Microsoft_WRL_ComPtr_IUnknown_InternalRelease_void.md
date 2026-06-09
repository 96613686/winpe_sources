# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180006b88`
- end: `0x180006bae`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ce0`
- `0x180007190`
- `0x180011594`
- `0x180011d88`
- `0x180011db8`
- `0x180011f8c`
- `0x180012594`
- `0x1800143ec`
- `0x18001441c`
- `0x1800144c0`
- `0x180014d70`
- `0x180015624`
- `0x180015ea0`
- `0x18001b3c0`
- `0x180028144`
- `0x180028c24`
- `0x18002931c`

## callees

- `0x180006b88`
- `0x180041010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180006b88  sub     rsp, 28h
0x180006b8c  mov     rdx, rcx
0x180006b8f  xor     eax, eax
0x180006b91  mov     rcx, [rcx]
0x180006b94  test    rcx, rcx
0x180006b97  jz      short loc_180006BA9
0x180006b99  mov     [rdx], rax
0x180006b9c  mov     rax, [rcx]
0x180006b9f  mov     rax, [rax+10h]
0x180006ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba8  nop
0x180006ba9  add     rsp, 28h
0x180006bad  retn
```
