# Microsoft::WRL::ComPtr<IApplicationLicenseManager>::InternalRelease(void)

- ea: `0x18000154c`
- end: `0x180001572`
- name: `?InternalRelease@?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x18000154c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IApplicationLicenseManager>::InternalRelease(__int64 *a1)
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
0x18000154c  sub     rsp, 28h
0x180001550  mov     rdx, rcx
0x180001553  xor     eax, eax
0x180001555  mov     rcx, [rcx]
0x180001558  test    rcx, rcx
0x18000155b  jz      short loc_18000156D
0x18000155d  mov     [rdx], rax
0x180001560  mov     rax, [rcx]
0x180001563  mov     rax, [rax+10h]
0x180001567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156c  nop
0x18000156d  add     rsp, 28h
0x180001571  retn
```
