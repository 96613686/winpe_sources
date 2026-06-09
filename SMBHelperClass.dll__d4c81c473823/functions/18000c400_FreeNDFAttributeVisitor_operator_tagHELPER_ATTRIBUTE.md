# FreeNDFAttributeVisitor::operator()(tagHELPER_ATTRIBUTE * &)

- ea: `0x18000c400`
- end: `0x18000c43d`
- name: `??RFreeNDFAttributeVisitor@@UEAAHAEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c42c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c42c`

## pseudocode

```c
__int64 __fastcall FreeNDFAttributeVisitor::operator()(__int64 a1, void ***a2)
{
  void *v3; // rcx
  void *v4; // rcx

  v3 = **a2;
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *((_DWORD *)*a2 + 2) == 10 )
  {
    v4 = (*a2)[2];
    if ( v4 )
      CoTaskMemFree(v4);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c400  push    rbx
0x18000c402  sub     rsp, 20h
0x18000c406  mov     rax, [rdx]
0x18000c409  mov     rbx, rdx
0x18000c40c  mov     rcx, [rax]; pv
0x18000c40f  test    rcx, rcx
0x18000c412  jz      short loc_18000C41A
0x18000c414  call    cs:__imp_CoTaskMemFree
0x18000c41a  mov     rcx, [rbx]
0x18000c41d  cmp     dword ptr [rcx+8], 0Ah
0x18000c421  jnz     short loc_18000C432
0x18000c423  mov     rcx, [rcx+10h]; pv
0x18000c427  test    rcx, rcx
0x18000c42a  jz      short loc_18000C432
0x18000c42c  call    cs:__imp_CoTaskMemFree
0x18000c432  mov     eax, 1
0x18000c437  add     rsp, 20h
0x18000c43b  pop     rbx
0x18000c43c  retn
```
