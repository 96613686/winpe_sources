# McpGetCloudPrintServiceOperation::WaitForCompletion(IMcpGetCloudPrintServiceResult * *)

- ea: `0x180022790`
- end: `0x1800228ad`
- name: `?WaitForCompletion@McpGetCloudPrintServiceOperation@@UEAAJPEAPEAUIMcpGetCloudPrintServiceResult@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceOperation *__hidden this, struct IMcpGetCloudPrintServiceResult **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18000df30`
- `0x18001b0e8`
- `0x180022000`
- `0x180022084`
- `0x180022790`
- `0x1800236e4`

## string_xrefs

- `0x1800227b7`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`
- `0x18002281b`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`
- `0x1800227d4`: `Waiting for McpGetCloudPrintServiceOperation to complete.`
- `0x1800227db`: `McpGetCloudPrintServiceOperation::WaitForCompletion`
- `0x18002287d`: `McpGetCloudPrintServiceOperation::WaitForCompletion`
- `0x18002280c`: `OperationHandler Failed to WaitForCompletion. hr=%#x`
- `0x180022876`: `Failed to MakeAndInitialize McpGetCloudPrintServiceResult. hr=%#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall McpGetCloudPrintServiceOperation::WaitForCompletion(
        McpGetCloudPrintServiceOperation *this,
        struct IMcpGetCloudPrintServiceResult **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  struct IMcpGetCloudPrintServiceResult *v9; // rcx
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-18h]
  char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v14; // [rsp+48h] [rbp+10h] BYREF
  McpGetCloudPrintServiceResult *v15; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetCloudPrintServiceOperation::WaitForCompletion",
      L"Waiting for McpGetCloudPrintServiceOperation to complete.");
    v14 = 0;
    v5 = McpOperationHandler::WaitForCompletion((McpGetCloudPrintServiceOperation *)((char *)this + 72), &v14);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      try
      {
        v7 = Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceResult,McpGetCloudPrintServiceResult,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>(
               &v15,
               (unsigned int *)&v14,
               (__int64)this + 40,
               (__int64)this + 56);
        v8 = v7;
        if ( v7 < 0 )
        {
          McpManagementTelemetry::WriteDbgTraceWarning(
            "McpGetCloudPrintServiceOperation::WaitForCompletion",
            L"Failed to MakeAndInitialize McpGetCloudPrintServiceResult. hr=%#x",
            (unsigned int)v7);
        }
        else
        {
          v9 = v15;
          v15 = 0;
          *a2 = v9;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        result = v8;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x6C,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserv"
                                             "iceoperation.cpp",
                               v10);
      }
    }
    else
    {
      LODWORD(v12) = v5;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
        (const char *)(unsigned int)v5,
        (int)"OperationHandler Failed to WaitForCompletion. hr=%#x",
        v12);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180022790  mov     [rsp+arg_0], rbx
0x180022795  mov     [rsp+arg_18], rsi
0x18002279a  push    rdi
0x18002279b  sub     rsp, 30h
0x18002279f  mov     rdi, rdx
0x1800227a2  mov     rsi, rcx
0x1800227a5  test    rdx, rdx
0x1800227a8  jnz     short loc_1800227CD
0x1800227aa  mov     rcx, [rsp+38h]; this
0x1800227af  mov     ebx, 80004003h
0x1800227b4  mov     r9d, ebx; char *
0x1800227b7  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800227be  lea     edx, [rdi+52h]; void *
0x1800227c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227c6  mov     eax, ebx
0x1800227c8  jmp     loc_18002289C
0x1800227cd  mov     qword ptr [rdx], 0
0x1800227d4  lea     rdx, aWaitingForMcpg_0; "Waiting for McpGetCloudPrintServiceOper"...
0x1800227db  lea     rcx, aMcpgetcloudpri_2; "McpGetCloudPrintServiceOperation::WaitF"...
0x1800227e2  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800227e7  mov     [rsp+38h+arg_8], 0
0x1800227ef  lea     rcx, [rsi+48h]; this
0x1800227f3  lea     rdx, [rsp+38h+arg_8]; int *
0x1800227f8  call    ?WaitForCompletion@McpOperationHandler@@QEAAJPEAJ@Z; McpOperationHandler::WaitForCompletion(long *)
0x1800227fd  mov     ebx, eax
0x1800227ff  test    eax, eax
0x180022801  jns     short loc_180022830
0x180022803  mov     rcx, [rsp+38h]; this
0x180022808  mov     dword ptr [rsp+38h+var_10], eax; char *
0x18002280c  lea     rax, aOperationhandl; "OperationHandler Failed to WaitForCompl"...
0x180022813  mov     qword ptr [rsp+38h+var_18], rax; int
0x180022818  mov     r9d, ebx; char *
0x18002281b  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180022822  mov     edx, 59h ; 'Y'; void *
0x180022827  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002282c  mov     eax, ebx
0x18002282e  jmp     short loc_18002289C
0x180022830  mov     [rsp+38h+arg_10], 0
0x180022839  lea     rcx, [rsp+38h+arg_10]
0x18002283e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022843  lea     r9, [rsi+38h]
0x180022847  lea     r8, [rsi+28h]
0x18002284b  lea     rdx, [rsp+38h+arg_8]
0x180022850  lea     rcx, [rsp+38h+arg_10]
0x180022855  call    ??$MakeAndInitialize@VMcpGetCloudPrintServiceResult@@V1@AEAJAEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetCloudPrintServiceResult@@AEAJAEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceResult,McpGetCloudPrintServiceResult,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>(McpGetCloudPrintServiceResult * *,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x18002285a  mov     ebx, eax
0x18002285c  test    eax, eax
0x18002285e  js      short loc_180022873
0x180022860  mov     rcx, [rsp+38h+arg_10]
0x180022865  mov     [rsp+38h+arg_10], 0
0x18002286e  mov     [rdi], rcx
0x180022871  jmp     short loc_18002288A
0x180022873  mov     r8d, ebx
0x180022876  lea     rdx, aFailedToMakean_0; "Failed to MakeAndInitialize McpGetCloud"...
0x18002287d  lea     rcx, aMcpgetcloudpri_2; "McpGetCloudPrintServiceOperation::WaitF"...
0x180022884  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180022889  nop
0x18002288a  lea     rcx, [rsp+38h+arg_10]
0x18002288f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022894  mov     eax, ebx
0x180022896  jmp     short loc_18002289C
0x180022898  mov     eax, [rsp+38h+arg_8]
0x18002289c  mov     rbx, [rsp+38h+arg_0]
0x1800228a1  mov     rsi, [rsp+38h+arg_18]
0x1800228a6  add     rsp, 30h
0x1800228aa  pop     rdi
0x1800228ab  retn
```
