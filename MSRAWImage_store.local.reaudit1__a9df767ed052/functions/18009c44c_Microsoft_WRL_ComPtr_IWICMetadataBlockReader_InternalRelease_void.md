# Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)

- ea: `0x18009c44c`
- end: `0x18009c47c`
- name: `?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ`
- size: `48`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800975d0`
- `0x1800976ac`
- `0x180097808`
- `0x1800985c0`
- `0x180098684`
- `0x1800989fc`
- `0x1800990d4`
- `0x18009a000`
- `0x18009a900`
- `0x18009c7f0`
- `0x18009c940`
- `0x1800a17a0`
- `0x1800a4024`
- `0x1800a42c0`
- `0x1800a52e4`
- `0x1800a5344`
- `0x1800a555c`
- `0x1800a55bc`
- `0x1800a7520`
- `0x1800a7b28`
- `0x1800a7f98`
- `0x1800a81cc`
- `0x1800a8588`
- `0x1800a8df0`
- `0x1800a98c0`
- `0x1800abf54`
- `0x1800ad600`

## callees

- `0x18009c44c`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(__int64 *a1)
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
0x18009c44c  sub     rsp, 38h
0x18009c450  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18009c459  mov     rdx, rcx
0x18009c45c  xor     eax, eax
0x18009c45e  mov     rcx, [rcx]
0x18009c461  test    rcx, rcx
0x18009c464  jz      short loc_18009C476
0x18009c466  mov     [rdx], rax
0x18009c469  mov     rax, [rcx]
0x18009c46c  mov     rax, [rax+10h]
0x18009c470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c475  nop
0x18009c476  add     rsp, 38h
0x18009c47a  retn
```
