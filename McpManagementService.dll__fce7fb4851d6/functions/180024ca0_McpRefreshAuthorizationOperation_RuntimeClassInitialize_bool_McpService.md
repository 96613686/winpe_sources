# McpRefreshAuthorizationOperation::RuntimeClassInitialize(bool,McpService *)

- ea: `0x180024ca0`
- end: `0x180024dd2`
- name: `?RuntimeClassInitialize@McpRefreshAuthorizationOperation@@QEAAJ_NPEAVMcpService@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(McpRefreshAuthorizationOperation *this, char, struct McpService *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025108`

## callees

- `0x180004d1c`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000df30`
- `0x18001f758`
- `0x180022188`
- `0x180022294`
- `0x180023538`
- `0x180023e98`
- `0x180024ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d2a`

## pseudocode

```c
__int64 __fastcall McpRefreshAuthorizationOperation::RuntimeClassInitialize(
        McpRefreshAuthorizationOperation *this,
        char a2,
        struct McpService *a3)
{
  __int64 unique_cotaskmem; // rax
  char *v7; // rdi
  HWND *v8; // rdx
  void *v9; // rcx
  __int64 result; // rax
  const char *v11; // r9
  _QWORD v12[7]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v13; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  McpManagementTelemetry::WriteDbgTraceInfo(
    "McpRefreshAuthorizationOperation::RuntimeClassInitialize",
    L"Initializing McpRefreshAuthorizationOperation");
  *((_BYTE *)this + 24) = a2;
  if ( *((struct McpService **)this + 5) != a3 )
  {
    pv = a3;
    Microsoft::WRL::ComPtr<McpService>::InternalAddRef(&pv);
    pv = (LPVOID)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
  }
  unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(&pv);
  v7 = (char *)this + 128;
  wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    (char *)this + 128,
    unique_cotaskmem);
  v9 = pv;
  pv = 0;
  if ( v9 )
    CoTaskMemFree(v9);
  if ( *(_QWORD *)v7 )
  {
    try
    {
      **(_DWORD **)v7 = 3;
      *(_QWORD *)(*(_QWORD *)v7 + 8LL) = this;
      if ( a2
        || (result = McpManagement::GetCallerWindowHandle((McpRefreshAuthorizationOperation *)((char *)this + 32), v8),
            (int)result >= 0) )
      {
        v13 = 0;
        v12[0] = off_18002CB88;
        v12[1] = *(_QWORD *)_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(
                              &pv,
                              this);
        v13 = v12;
        result = McpOperationHandler::Initialize((char *)this + 48, v12);
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x35,
                             (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcprefreshauthorizationoperation.cpp",
                             v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcprefreshauthorizationoperation.cpp",
      (const char *)0x8007000ELL,
      v12[0]);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024ca0  mov     [rsp+arg_10], rbx
0x180024ca5  mov     [rsp+arg_18], rsi
0x180024caa  push    rdi
0x180024cab  sub     rsp, 60h
0x180024caf  mov     rdi, r8
0x180024cb2  mov     sil, dl
0x180024cb5  mov     rbx, rcx
0x180024cb8  lea     rdx, aInitializingMc_0; "Initializing McpRefreshAuthorizationOpe"...
0x180024cbf  lea     rcx, aMcprefreshauth_3; "McpRefreshAuthorizationOperation::Runti"...
0x180024cc6  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180024ccb  mov     [rbx+18h], sil
0x180024ccf  cmp     [rbx+28h], rdi
0x180024cd3  jz      short loc_180024CFB
0x180024cd5  mov     [rsp+68h+pv], rdi
0x180024cda  lea     rcx, [rsp+68h+pv]
0x180024cdf  call    ?InternalAddRef@?$ComPtr@VMcpService@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<McpService>::InternalAddRef(void)
0x180024ce4  mov     rax, [rbx+28h]
0x180024ce8  mov     [rsp+68h+pv], rax
0x180024ced  mov     [rbx+28h], rdi
0x180024cf1  lea     rcx, [rsp+68h+pv]
0x180024cf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024cfb  lea     rcx, [rsp+68h+pv]
0x180024d00  call    ??$make_unique_cotaskmem_nothrow@UMcpOperationHandlerThreadParams@@$$V@wil@@YA?AV?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(void)
0x180024d05  lea     rdi, [rbx+80h]
0x180024d0c  mov     rdx, rax
0x180024d0f  mov     rcx, rdi
0x180024d12  call    ??4?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180024d17  mov     rcx, [rsp+68h+pv]; pv
0x180024d1c  mov     [rsp+68h+pv], 0
0x180024d25  test    rcx, rcx
0x180024d28  jz      short loc_180024D30
0x180024d2a  call    cs:__imp_CoTaskMemFree
0x180024d30  mov     rax, [rdi]
0x180024d33  test    rax, rax
0x180024d36  jnz     short loc_180024D58
0x180024d38  mov     rcx, [rsp+68h]; this
0x180024d3d  mov     ebx, 8007000Eh
0x180024d42  mov     r9d, ebx; char *
0x180024d45  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180024d4c  lea     edx, [rax+17h]; void *
0x180024d4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d54  mov     eax, ebx
0x180024d56  jmp     short loc_180024DBF
0x180024d58  mov     dword ptr [rax], 3
0x180024d5e  mov     rax, [rdi]
0x180024d61  mov     [rax+8], rbx
0x180024d65  test    sil, sil
0x180024d68  jnz     short loc_180024D77
0x180024d6a  lea     rcx, [rbx+20h]; this
0x180024d6e  call    ?GetCallerWindowHandle@McpManagement@@YAJPEAPEAUHWND__@@@Z; McpManagement::GetCallerWindowHandle(HWND__ * *)
0x180024d73  test    eax, eax
0x180024d75  js      short loc_180024DBF
0x180024d77  mov     [rsp+68h+var_10], 0
0x180024d80  lea     rax, off_18002CB88
0x180024d87  mov     [rsp+68h+var_48], rax
0x180024d8c  mov     rdx, rbx
0x180024d8f  lea     rcx, [rsp+68h+pv]
0x180024d94  call    ??0_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@Z; _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *)
0x180024d99  mov     rcx, [rax]
0x180024d9c  mov     [rsp+68h+var_40], rcx
0x180024da1  lea     rax, [rsp+68h+var_48]
0x180024da6  mov     [rsp+68h+var_10], rax
0x180024dab  lea     rcx, [rbx+30h]
0x180024daf  lea     rdx, [rsp+68h+var_48]
0x180024db4  call    ?Initialize@McpOperationHandler@@QEAAJV?$function@$$A6AJXZ@std@@@Z; McpOperationHandler::Initialize(std::function<long (void)>)
0x180024db9  jmp     short loc_180024DBF
0x180024dbb  mov     eax, [rsp+68h+arg_8]
0x180024dbf  lea     r11, [rsp+68h+var_8]
0x180024dc4  mov     rbx, [r11+20h]
0x180024dc8  mov     rsi, [r11+28h]
0x180024dcc  mov     rsp, r11
0x180024dcf  pop     rdi
0x180024dd0  retn
```
