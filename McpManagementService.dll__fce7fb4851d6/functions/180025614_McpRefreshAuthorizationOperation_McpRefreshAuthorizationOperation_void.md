# McpRefreshAuthorizationOperation::~McpRefreshAuthorizationOperation(void)

- ea: `0x180025614`
- end: `0x180025665`
- name: `??1McpRefreshAuthorizationOperation@@UEAA@XZ`
- size: `81`
- prototype: `void __fastcall(McpRefreshAuthorizationOperation *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025670`

## callees

- `0x180009fc0`
- `0x1800219f8`
- `0x180021a20`
- `0x180025614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025640`

## pseudocode

```c
void __fastcall McpRefreshAuthorizationOperation::~McpRefreshAuthorizationOperation(
        McpRefreshAuthorizationOperation *this)
{
  void *v2; // rcx

  McpManagement::SvcHostServerReference::~SvcHostServerReference((McpRefreshAuthorizationOperation *)((char *)this + 136));
  v2 = (void *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  McpOperationHandler::~McpOperationHandler((McpRefreshAuthorizationOperation *)((char *)this + 48));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 40);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180025614  push    rbx
0x180025616  sub     rsp, 20h
0x18002561a  mov     rbx, rcx
0x18002561d  add     rcx, 88h; this
0x180025624  call    ??1SvcHostServerReference@McpManagement@@QEAA@XZ; McpManagement::SvcHostServerReference::~SvcHostServerReference(void)
0x180025629  mov     rcx, [rbx+80h]; pv
0x180025630  mov     qword ptr [rbx+80h], 0
0x18002563b  test    rcx, rcx
0x18002563e  jz      short loc_180025646
0x180025640  call    cs:__imp_CoTaskMemFree
0x180025646  lea     rcx, [rbx+30h]; this
0x18002564a  call    ??1McpOperationHandler@@QEAA@XZ; McpOperationHandler::~McpOperationHandler(void)
0x18002564f  lea     rcx, [rbx+28h]
0x180025653  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025658  mov     dword ptr [rbx+14h], 0C0000001h
0x18002565f  add     rsp, 20h
0x180025663  pop     rbx
0x180025664  retn
```
