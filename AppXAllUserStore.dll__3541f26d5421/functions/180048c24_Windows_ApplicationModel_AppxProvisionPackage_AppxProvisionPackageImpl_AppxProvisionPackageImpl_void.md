# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionPackageImpl::~AppxProvisionPackageImpl(void)

- ea: `0x180048c24`
- end: `0x180048c58`
- name: `??1AppxProvisionPackageImpl@AppxProvisionPackage@ApplicationModel@Windows@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048c60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c45`

## pseudocode

```c
void __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionPackageImpl::~AppxProvisionPackageImpl(
        LPVOID *this)
{
  *this = &Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionPackageImpl::`vftable';
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[2]);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180048c24  push    rbx
0x180048c26  sub     rsp, 20h
0x180048c2a  lea     rax, ??_7AppxProvisionPackageImpl@AppxProvisionPackage@ApplicationModel@Windows@@6B@
0x180048c31  mov     rbx, rcx
0x180048c34  mov     [rcx], rax
0x180048c37  mov     rcx, [rcx+18h]; pv
0x180048c3b  call    cs:__imp_CoTaskMemFree
0x180048c41  mov     rcx, [rbx+10h]; pv
0x180048c45  call    cs:__imp_CoTaskMemFree
0x180048c4b  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180048c52  add     rsp, 20h
0x180048c56  pop     rbx
0x180048c57  retn
```
