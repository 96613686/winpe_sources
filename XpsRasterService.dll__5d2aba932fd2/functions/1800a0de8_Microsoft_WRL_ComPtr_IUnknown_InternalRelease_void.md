# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x1800a0de8`
- end: `0x1800a0e0e`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a06dc`
- `0x1800a08d0`
- `0x1800a0a50`
- `0x1800a2740`
- `0x1800a2804`
- `0x1800a28c8`
- `0x1800a29a0`
- `0x1800a2d1c`
- `0x1800a2d90`
- `0x1800a2e04`
- `0x1800a2ee0`
- `0x1800a30f0`
- `0x1800a5560`

## callees

- `0x1800a0de8`
- `0x1800c3010`

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
0x1800a0de8  sub     rsp, 28h
0x1800a0dec  mov     rdx, rcx
0x1800a0def  xor     eax, eax
0x1800a0df1  mov     rcx, [rcx]
0x1800a0df4  test    rcx, rcx
0x1800a0df7  jz      short loc_1800A0E09
0x1800a0df9  mov     [rdx], rax
0x1800a0dfc  mov     rax, [rcx]
0x1800a0dff  mov     rax, [rax+10h]
0x1800a0e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0e08  nop
0x1800a0e09  add     rsp, 28h
0x1800a0e0d  retn
```
