# FreeNDFRepairVisitor::operator()(tagRepairInfo * &)

- ea: `0x18000c450`
- end: `0x18000c4a0`
- name: `??RFreeNDFRepairVisitor@@UEAAHAEAPEAUtagRepairInfo@@@Z`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000c450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c477`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c48f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c477`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c48f`

## pseudocode

```c
__int64 __fastcall FreeNDFRepairVisitor::operator()(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v3 = *(void **)(*(_QWORD *)a2 + 16LL);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *(void **)(*(_QWORD *)a2 + 24LL);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( *(_DWORD *)(*(_QWORD *)a2 + 56LL) == 4 )
  {
    v5 = *(void **)(*(_QWORD *)a2 + 64LL);
    if ( v5 )
      CoTaskMemFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c450  push    rbx
0x18000c452  sub     rsp, 20h
0x18000c456  mov     rax, [rdx]
0x18000c459  mov     rbx, rdx
0x18000c45c  mov     rcx, [rax+10h]; pv
0x18000c460  test    rcx, rcx
0x18000c463  jz      short loc_18000C46B
0x18000c465  call    cs:__imp_CoTaskMemFree
0x18000c46b  mov     rax, [rbx]
0x18000c46e  mov     rcx, [rax+18h]; pv
0x18000c472  test    rcx, rcx
0x18000c475  jz      short loc_18000C47D
0x18000c477  call    cs:__imp_CoTaskMemFree
0x18000c47d  mov     rcx, [rbx]
0x18000c480  cmp     dword ptr [rcx+38h], 4
0x18000c484  jnz     short loc_18000C495
0x18000c486  mov     rcx, [rcx+40h]; pv
0x18000c48a  test    rcx, rcx
0x18000c48d  jz      short loc_18000C495
0x18000c48f  call    cs:__imp_CoTaskMemFree
0x18000c495  mov     eax, 1
0x18000c49a  add     rsp, 20h
0x18000c49e  pop     rbx
0x18000c49f  retn
```
