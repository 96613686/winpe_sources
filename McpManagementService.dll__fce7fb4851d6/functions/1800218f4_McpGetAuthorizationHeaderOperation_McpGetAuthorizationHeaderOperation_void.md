# McpGetAuthorizationHeaderOperation::~McpGetAuthorizationHeaderOperation(void)

- ea: `0x1800218f4`
- end: `0x18002198a`
- name: `??1McpGetAuthorizationHeaderOperation@@UEAA@XZ`
- size: `150`
- prototype: `void __fastcall(McpGetAuthorizationHeaderOperation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021aa0`

## callees

- `0x18000e208`
- `0x1800125e4`
- `0x1800218f4`
- `0x1800219f8`
- `0x180021a20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021920`

## pseudocode

```c
void __fastcall McpGetAuthorizationHeaderOperation::~McpGetAuthorizationHeaderOperation(
        McpGetAuthorizationHeaderOperation *this)
{
  void *v2; // rcx

  McpManagement::SvcHostServerReference::~SvcHostServerReference((McpGetAuthorizationHeaderOperation *)((char *)this + 336));
  v2 = (void *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  McpOperationHandler::~McpOperationHandler((McpGetAuthorizationHeaderOperation *)((char *)this + 248));
  std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>((__int64)this + 232);
  std::wstring::_Tidy_deallocate((char *)this + 200);
  std::wstring::_Tidy_deallocate((char *)this + 168);
  std::wstring::_Tidy_deallocate((char *)this + 136);
  std::wstring::_Tidy_deallocate((char *)this + 104);
  std::wstring::_Tidy_deallocate((char *)this + 72);
  std::wstring::_Tidy_deallocate((char *)this + 40);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x1800218f4  push    rbx
0x1800218f6  sub     rsp, 20h
0x1800218fa  mov     rbx, rcx
0x1800218fd  add     rcx, 150h; this
0x180021904  call    ??1SvcHostServerReference@McpManagement@@QEAA@XZ; McpManagement::SvcHostServerReference::~SvcHostServerReference(void)
0x180021909  mov     rcx, [rbx+148h]; pv
0x180021910  mov     qword ptr [rbx+148h], 0
0x18002191b  test    rcx, rcx
0x18002191e  jz      short loc_180021926
0x180021920  call    cs:__imp_CoTaskMemFree
0x180021926  lea     rcx, [rbx+0F8h]; this
0x18002192d  call    ??1McpOperationHandler@@QEAA@XZ; McpOperationHandler::~McpOperationHandler(void)
0x180021932  lea     rcx, [rbx+0E8h]
0x180021939  call    ??1?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAA@XZ; std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(void)
0x18002193e  lea     rcx, [rbx+0C8h]
0x180021945  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002194a  lea     rcx, [rbx+0A8h]
0x180021951  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021956  lea     rcx, [rbx+88h]
0x18002195d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021962  lea     rcx, [rbx+68h]
0x180021966  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002196b  lea     rcx, [rbx+48h]
0x18002196f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021974  lea     rcx, [rbx+28h]
0x180021978  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002197d  mov     dword ptr [rbx+14h], 0C0000001h
0x180021984  add     rsp, 20h
0x180021988  pop     rbx
0x180021989  retn
```
