# CDeviceTreeElement::`scalar deleting destructor'(uint)

- ea: `0x18000c840`
- end: `0x18000c88c`
- name: `??_GCDeviceTreeElement@@QEAAPEAXI@Z`
- size: `76`
- prototype: `CDeviceTreeElement *__fastcall(CDeviceTreeElement *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002ef0`

## callees

- `0x18000c840`
- `0x18001b410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c870`

## pseudocode

```c
CDeviceTreeElement *__fastcall CDeviceTreeElement::`scalar deleting destructor'(CDeviceTreeElement *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    CoTaskMemFree(v4);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c840  push    rbx
0x18000c842  sub     rsp, 20h
0x18000c846  mov     rbx, rcx
0x18000c849  mov     rcx, [rcx+18h]; pv
0x18000c84d  test    rcx, rcx
0x18000c850  jz      short loc_18000C858
0x18000c852  call    cs:__imp_CoTaskMemFree
0x18000c858  mov     rcx, [rbx+10h]; pv
0x18000c85c  test    rcx, rcx
0x18000c85f  jz      short loc_18000C867
0x18000c861  call    cs:__imp_CoTaskMemFree
0x18000c867  mov     rcx, [rbx+8]; pv
0x18000c86b  test    rcx, rcx
0x18000c86e  jz      short loc_18000C876
0x18000c870  call    cs:__imp_CoTaskMemFree
0x18000c876  mov     edx, 28h ; '('
0x18000c87b  mov     rcx, rbx; Block
0x18000c87e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c883  mov     rax, rbx
0x18000c886  add     rsp, 20h
0x18000c88a  pop     rbx
0x18000c88b  retn
```
