# McpGetCloudPrintServiceOperation::~McpGetCloudPrintServiceOperation(void)

- ea: `0x180021990`
- end: `0x1800219ef`
- name: `??1McpGetCloudPrintServiceOperation@@UEAA@XZ`
- size: `95`
- prototype: `void __fastcall(McpGetCloudPrintServiceOperation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021ae0`

## callees

- `0x1800125e4`
- `0x18001c9a8`
- `0x180021990`
- `0x1800219f8`
- `0x180021a20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219bc`

## pseudocode

```c
void __fastcall McpGetCloudPrintServiceOperation::~McpGetCloudPrintServiceOperation(
        McpGetCloudPrintServiceOperation *this)
{
  void *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  McpManagement::SvcHostServerReference::~SvcHostServerReference((McpGetCloudPrintServiceOperation *)((char *)this + 160));
  v2 = (void *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  McpOperationHandler::~McpOperationHandler((McpGetCloudPrintServiceOperation *)((char *)this + 72));
  std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>((__int64)this + 56);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180021990  push    rbx
0x180021992  sub     rsp, 20h
0x180021996  mov     rbx, rcx
0x180021999  add     rcx, 0A0h; this
0x1800219a0  call    ??1SvcHostServerReference@McpManagement@@QEAA@XZ; McpManagement::SvcHostServerReference::~SvcHostServerReference(void)
0x1800219a5  mov     rcx, [rbx+98h]; pv
0x1800219ac  mov     qword ptr [rbx+98h], 0
0x1800219b7  test    rcx, rcx
0x1800219ba  jz      short loc_1800219C2
0x1800219bc  call    cs:__imp_CoTaskMemFree
0x1800219c2  lea     rcx, [rbx+48h]; this
0x1800219c6  call    ??1McpOperationHandler@@QEAA@XZ; McpOperationHandler::~McpOperationHandler(void)
0x1800219cb  lea     rcx, [rbx+38h]
0x1800219cf  call    ??1?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAA@XZ; std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(void)
0x1800219d4  mov     rcx, [rbx+30h]; this
0x1800219d8  test    rcx, rcx
0x1800219db  jz      short loc_1800219E2
0x1800219dd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800219e2  mov     dword ptr [rbx+14h], 0C0000001h
0x1800219e9  add     rsp, 20h
0x1800219ed  pop     rbx
0x1800219ee  retn
```
