# std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::~unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>(void)

- ea: `0x14000c2e0`
- end: `0x14000c301`
- name: `??1?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ed4a`
- `0x14000ed8c`
- `0x14000eee0`

## callees

- `0x14000c2e0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::~unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 128LL))(v1);
  return result;
}

```

## disassembly

```asm
0x14000c2e0  sub     rsp, 28h
0x14000c2e4  mov     rcx, [rcx]
0x14000c2e7  test    rcx, rcx
0x14000c2ea  jz      short loc_14000C2FC
0x14000c2ec  mov     rax, [rcx]
0x14000c2ef  mov     rax, [rax+80h]
0x14000c2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2fb  nop
0x14000c2fc  add     rsp, 28h
0x14000c300  retn
```
