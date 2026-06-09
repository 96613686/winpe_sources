# McpService::RefreshAuthorizationAsync(int,IMcpRefreshAuthorizationOperation * *)

- ea: `0x180026630`
- end: `0x18002670c`
- name: `?RefreshAuthorizationAsync@McpService@@UEAAJHPEAPEAUIMcpRefreshAuthorizationOperation@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(McpService *__hidden this, int, struct IMcpRefreshAuthorizationOperation **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18001b060`
- `0x180022000`
- `0x18002341c`
- `0x180025108`
- `0x180026630`

## string_xrefs

- `0x18002664f`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x1800266e1`: `McpService::RefreshAuthorizationAsync`
- `0x1800266da`: `Failed to spawn RefreshAuth McpOperation worker thread. hr=%#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall McpService::RefreshAuthorizationAsync(
        McpService *this,
        int a2,
        struct IMcpRefreshAuthorizationOperation **a3)
{
  __int64 result; // rax
  __int64 Error; // rbx
  struct IMcpRefreshAuthorizationOperation *v6; // rax
  const char *v7; // r9
  struct McpService *v8; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+50h] [rbp+18h] BYREF
  unsigned int **v11; // [rsp+58h] [rbp+20h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    v11 = 0;
    v8 = this;
    LOBYTE(v10) = a2 == 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    try
    {
      LODWORD(Error) = Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationOperation,McpRefreshAuthorizationOperation,bool,McpService *>(
                         (McpRefreshAuthorizationOperation **)&v11,
                         (char *)&v10,
                         &v8);
      if ( (int)Error >= 0 )
      {
        if ( McpOperationHandler::CreateOperationThread(v11[16]) )
        {
          v6 = (struct IMcpRefreshAuthorizationOperation *)v11;
          v11 = 0;
          *a3 = v6;
        }
        else
        {
          Error = (unsigned int)ResultFromKnownLastError();
          McpManagementTelemetry::WriteDbgTraceWarning(
            "McpService::RefreshAuthorizationAsync",
            L"Failed to spawn RefreshAuth McpOperation worker thread. hr=%#x",
            Error);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      result = (unsigned int)Error;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xE0,
                             (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                             v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      (int)v8);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180026630  mov     [rsp+arg_0], rbx
0x180026635  push    rdi
0x180026636  sub     rsp, 30h
0x18002663a  mov     rdi, r8
0x18002663d  test    r8, r8
0x180026640  jnz     short loc_180026667
0x180026642  mov     rcx, [rsp+38h]; this
0x180026647  mov     ebx, 80004003h
0x18002664c  mov     r9d, ebx; char *
0x18002664f  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180026656  mov     edx, 0CCh; void *
0x18002665b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026660  mov     eax, ebx
0x180026662  jmp     loc_180026700
0x180026667  mov     qword ptr [r8], 0
0x18002666e  mov     [rsp+38h+arg_18], 0
0x180026677  mov     [rsp+38h+var_18], rcx
0x18002667c  cmp     edx, 1
0x18002667f  setz    byte ptr [rsp+38h+arg_10]
0x180026684  lea     rcx, [rsp+38h+arg_18]
0x180026689  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002668e  lea     r8, [rsp+38h+var_18]
0x180026693  lea     rdx, [rsp+38h+arg_10]
0x180026698  lea     rcx, [rsp+38h+arg_18]
0x18002669d  call    ??$MakeAndInitialize@VMcpRefreshAuthorizationOperation@@V1@_NPEAVMcpService@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpRefreshAuthorizationOperation@@$$QEA_N$$QEAPEAVMcpService@@@Z; Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationOperation,McpRefreshAuthorizationOperation,bool,McpService *>(McpRefreshAuthorizationOperation * *,bool &&,McpService * &&)
0x1800266a2  mov     ebx, eax
0x1800266a4  test    eax, eax
0x1800266a6  js      short loc_1800266EE
0x1800266a8  mov     rcx, [rsp+38h+arg_18]
0x1800266ad  mov     rcx, [rcx+80h]; lpParameter
0x1800266b4  call    ?CreateOperationThread@McpOperationHandler@@SA_NPEAX@Z; McpOperationHandler::CreateOperationThread(void *)
0x1800266b9  test    al, al
0x1800266bb  jz      short loc_1800266D0
0x1800266bd  mov     rax, [rsp+38h+arg_18]
0x1800266c2  mov     [rsp+38h+arg_18], 0
0x1800266cb  mov     [rdi], rax
0x1800266ce  jmp     short loc_1800266EE
0x1800266d0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800266d5  mov     ebx, eax
0x1800266d7  mov     r8d, eax
0x1800266da  lea     rdx, aFailedToSpawnR; "Failed to spawn RefreshAuth McpOperatio"...
0x1800266e1  lea     rcx, aMcpserviceRefr; "McpService::RefreshAuthorizationAsync"
0x1800266e8  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800266ed  nop
0x1800266ee  lea     rcx, [rsp+38h+arg_18]
0x1800266f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800266f8  mov     eax, ebx
0x1800266fa  jmp     short loc_180026700
0x1800266fc  mov     eax, [rsp+38h+arg_10]
0x180026700  mov     rbx, [rsp+38h+arg_0]
0x180026705  add     rsp, 30h
0x180026709  pop     rdi
0x18002670a  retn
```
