# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x18000768c`
- end: `0x1800076b2`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005944`
- `0x18000c5b8`
- `0x18000c63c`
- `0x18000c940`
- `0x18000c9d0`
- `0x18000d908`
- `0x18000e8e0`
- `0x180010880`
- `0x180011630`

## callees

- `0x18000768c`
- `0x180031010`

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
0x18000768c  sub     rsp, 28h
0x180007690  mov     rdx, rcx
0x180007693  xor     eax, eax
0x180007695  mov     rcx, [rcx]
0x180007698  test    rcx, rcx
0x18000769b  jz      short loc_1800076AD
0x18000769d  mov     [rdx], rax
0x1800076a0  mov     rax, [rcx]
0x1800076a3  mov     rax, [rax+10h]
0x1800076a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ac  nop
0x1800076ad  add     rsp, 28h
0x1800076b1  retn
```
