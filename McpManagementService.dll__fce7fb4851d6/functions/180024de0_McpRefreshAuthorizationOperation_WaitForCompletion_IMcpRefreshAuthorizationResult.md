# McpRefreshAuthorizationOperation::WaitForCompletion(IMcpRefreshAuthorizationResult * *)

- ea: `0x180024de0`
- end: `0x180024eeb`
- name: `?WaitForCompletion@McpRefreshAuthorizationOperation@@UEAAJPEAPEAUIMcpRefreshAuthorizationResult@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(McpRefreshAuthorizationOperation *__hidden this, struct IMcpRefreshAuthorizationResult **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18000df30`
- `0x18001b0e8`
- `0x180022000`
- `0x1800236e4`
- `0x1800249a8`
- `0x180024de0`

## string_xrefs

- `0x180024e57`: `OperationHandler Failed to WaitForCompletion. hr=%#x`
- `0x180024e26`: `McpRefreshAuthorizationOperation::WaitForCompletion`
- `0x180024ec0`: `McpRefreshAuthorizationOperation::WaitForCompletion`
- `0x180024e1f`: `Waiting for McpRefreshAuthorizationOperation to complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall McpRefreshAuthorizationOperation::WaitForCompletion(
        McpRefreshAuthorizationOperation *this,
        struct IMcpRefreshAuthorizationResult **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int refreshed; // eax
  unsigned int v8; // ebx
  struct IMcpRefreshAuthorizationResult *v9; // rcx
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-18h]
  char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v14; // [rsp+48h] [rbp+10h] BYREF
  struct IMcpRefreshAuthorizationResult *v15; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpRefreshAuthorizationOperation::WaitForCompletion",
      L"Waiting for McpRefreshAuthorizationOperation to complete.");
    v14 = 0;
    v5 = McpOperationHandler::WaitForCompletion((McpRefreshAuthorizationOperation *)((char *)this + 48), &v14);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      try
      {
        refreshed = Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationResult,McpRefreshAuthorizationResult,long &>();
        v8 = refreshed;
        if ( refreshed < 0 )
        {
          McpManagementTelemetry::WriteDbgTraceWarning(
            "McpRefreshAuthorizationOperation::WaitForCompletion",
            L"Failed to MakeAndInitialize McpRefreshAuthorizationResult. hr=%#x",
            (unsigned int)refreshed);
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
                               (void *)0x50,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcprefreshauthorizat"
                                             "ionoperation.cpp",
                               v10);
      }
    }
    else
    {
      LODWORD(v12) = v5;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcprefreshauthorizationoperation.cpp",
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
      (void *)0x3A,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcprefreshauthorizationoperation.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024de0  mov     [rsp+arg_0], rbx
0x180024de5  push    rdi
0x180024de6  sub     rsp, 30h
0x180024dea  mov     rdi, rdx
0x180024ded  mov     rbx, rcx
0x180024df0  test    rdx, rdx
0x180024df3  jnz     short loc_180024E18
0x180024df5  mov     rcx, [rsp+38h]; this
0x180024dfa  mov     ebx, 80004003h
0x180024dff  mov     r9d, ebx; char *
0x180024e02  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180024e09  lea     edx, [rdi+3Ah]; void *
0x180024e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e11  mov     eax, ebx
0x180024e13  jmp     loc_180024EDF
0x180024e18  mov     qword ptr [rdx], 0
0x180024e1f  lea     rdx, aWaitingForMcpr; "Waiting for McpRefreshAuthorizationOper"...
0x180024e26  lea     rcx, aMcprefreshauth_1; "McpRefreshAuthorizationOperation::WaitF"...
0x180024e2d  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180024e32  mov     [rsp+38h+arg_8], 0
0x180024e3a  lea     rcx, [rbx+30h]; this
0x180024e3e  lea     rdx, [rsp+38h+arg_8]; int *
0x180024e43  call    ?WaitForCompletion@McpOperationHandler@@QEAAJPEAJ@Z; McpOperationHandler::WaitForCompletion(long *)
0x180024e48  mov     ebx, eax
0x180024e4a  test    eax, eax
0x180024e4c  jns     short loc_180024E7B
0x180024e4e  mov     rcx, [rsp+38h]; this
0x180024e53  mov     dword ptr [rsp+38h+var_10], eax; char *
0x180024e57  lea     rax, aOperationhandl; "OperationHandler Failed to WaitForCompl"...
0x180024e5e  mov     qword ptr [rsp+38h+var_18], rax; int
0x180024e63  mov     r9d, ebx; char *
0x180024e66  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180024e6d  mov     edx, 41h ; 'A'; void *
0x180024e72  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024e77  mov     eax, ebx
0x180024e79  jmp     short loc_180024EDF
0x180024e7b  mov     [rsp+38h+arg_10], 0
0x180024e84  lea     rcx, [rsp+38h+arg_10]
0x180024e89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024e8e  lea     rdx, [rsp+38h+arg_8]
0x180024e93  lea     rcx, [rsp+38h+arg_10]
0x180024e98  call    ??$MakeAndInitialize@VMcpRefreshAuthorizationResult@@V1@AEAJ@Details@WRL@Microsoft@@YAJPEAPEAVMcpRefreshAuthorizationResult@@AEAJ@Z; Microsoft::WRL::Details::MakeAndInitialize<McpRefreshAuthorizationResult,McpRefreshAuthorizationResult,long &>(McpRefreshAuthorizationResult * *,long &)
0x180024e9d  mov     ebx, eax
0x180024e9f  test    eax, eax
0x180024ea1  js      short loc_180024EB6
0x180024ea3  mov     rcx, [rsp+38h+arg_10]
0x180024ea8  mov     [rsp+38h+arg_10], 0
0x180024eb1  mov     [rdi], rcx
0x180024eb4  jmp     short loc_180024ECD
0x180024eb6  mov     r8d, ebx
0x180024eb9  lea     rdx, aFailedToMakean_1; "Failed to MakeAndInitialize McpRefreshA"...
0x180024ec0  lea     rcx, aMcprefreshauth_1; "McpRefreshAuthorizationOperation::WaitF"...
0x180024ec7  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180024ecc  nop
0x180024ecd  lea     rcx, [rsp+38h+arg_10]
0x180024ed2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024ed7  mov     eax, ebx
0x180024ed9  jmp     short loc_180024EDF
0x180024edb  mov     eax, [rsp+38h+arg_8]
0x180024edf  mov     rbx, [rsp+38h+arg_0]
0x180024ee4  add     rsp, 30h
0x180024ee8  pop     rdi
0x180024ee9  retn
```
