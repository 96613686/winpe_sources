# WuSmartPtr::XPtrBaseWithArrayAllocation<char,WuSmartPtr::Policies::CoPolicy<char>>::~XPtrBaseWithArrayAllocation<char,WuSmartPtr::Policies::CoPolicy<char>>(void)

- ea: `0x140011378`
- end: `0x14001139c`
- name: `??1?$XPtrBaseWithArrayAllocation@DU?$CoPolicy@D@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004e0c4`
- `0x14004f3a5`
- `0x14004fc6a`
- `0x14004fca0`
- `0x14004fce8`
- `0x1400503d3`

## callees

- `0x140011378`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011389`

## pseudocode

```c
void __fastcall WuSmartPtr::XPtrBaseWithArrayAllocation<char,WuSmartPtr::Policies::CoPolicy<char>>::~XPtrBaseWithArrayAllocation<char,WuSmartPtr::Policies::CoPolicy<char>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140011378  push    rbx
0x14001137a  sub     rsp, 20h
0x14001137e  mov     rbx, rcx
0x140011381  mov     rcx, [rcx]; pv
0x140011384  test    rcx, rcx
0x140011387  jz      short loc_140011396
0x140011389  call    cs:__imp_CoTaskMemFree
0x14001138f  mov     qword ptr [rbx], 0
0x140011396  add     rsp, 20h
0x14001139a  pop     rbx
0x14001139b  retn
```
