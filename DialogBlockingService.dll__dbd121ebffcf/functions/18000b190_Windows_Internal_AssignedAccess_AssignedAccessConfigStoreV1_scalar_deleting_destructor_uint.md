# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`scalar deleting destructor'(uint)

- ea: `0x18000b190`
- end: `0x18000b1ec`
- name: `??_GAssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@UEAAPEAXI@Z`
- size: `92`
- prototype: `Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001c90`
- `0x18000b190`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1a8`

## pseudocode

```c
Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::`scalar deleting destructor'(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 1) = 0;
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b190  mov     [rsp+arg_0], rbx
0x18000b195  push    rdi
0x18000b196  sub     rsp, 20h
0x18000b19a  mov     rbx, rcx
0x18000b19d  mov     edi, edx
0x18000b19f  mov     rcx, [rcx+8]; pv
0x18000b1a3  test    rcx, rcx
0x18000b1a6  jz      short loc_18000B1B6
0x18000b1a8  call    cs:__imp_CoTaskMemFree
0x18000b1ae  mov     qword ptr [rbx+8], 0
0x18000b1b6  mov     qword ptr [rbx+10h], 0
0x18000b1be  lea     rax, ??_7AssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase::`vftable'
0x18000b1c5  mov     qword ptr [rbx+18h], 0
0x18000b1cd  mov     [rbx], rax
0x18000b1d0  test    dil, 1
0x18000b1d4  jz      short loc_18000B1DE
0x18000b1d6  mov     rcx, rbx; Block
0x18000b1d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b1de  mov     rax, rbx
0x18000b1e1  mov     rbx, [rsp+28h+arg_0]
0x18000b1e6  add     rsp, 20h
0x18000b1ea  pop     rdi
0x18000b1eb  retn
```
