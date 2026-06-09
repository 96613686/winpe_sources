# std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>>::~unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>>(void)

- ea: `0x14000c308`
- end: `0x14000c329`
- name: `??1?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ed60`

## callees

- `0x14000c308`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager>::~unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x14000c308  sub     rsp, 28h
0x14000c30c  mov     rcx, [rcx]
0x14000c30f  test    rcx, rcx
0x14000c312  jz      short loc_14000C324
0x14000c314  mov     rax, [rcx]
0x14000c317  mov     edx, 1
0x14000c31c  mov     rax, [rax]
0x14000c31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c324  add     rsp, 28h
0x14000c328  retn
```
