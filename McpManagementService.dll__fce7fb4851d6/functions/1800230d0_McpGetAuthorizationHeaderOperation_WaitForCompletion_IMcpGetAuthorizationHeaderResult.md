# McpGetAuthorizationHeaderOperation::WaitForCompletion(IMcpGetAuthorizationHeaderResult * *)

- ea: `0x1800230d0`
- end: `0x180023223`
- name: `?WaitForCompletion@McpGetAuthorizationHeaderOperation@@UEAAJPEAPEAUIMcpGetAuthorizationHeaderResult@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(McpGetAuthorizationHeaderOperation *__hidden this, struct IMcpGetAuthorizationHeaderResult **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18000df30`
- `0x18000e164`
- `0x18001b0e8`
- `0x180022000`
- `0x180022a1c`
- `0x1800230d0`
- `0x1800236e4`

## string_xrefs

- `0x180023148`: `OperationHandler Failed to WaitForCompletion. hr=%#x`
- `0x180023114`: `McpGetAuthorizationHeaderOperation::WaitForCompletion`
- `0x1800231fb`: `McpGetAuthorizationHeaderOperation::WaitForCompletion`
- `0x18002310d`: `Waiting for McpGetAuthorizationHeaderOperation to complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall McpGetAuthorizationHeaderOperation::WaitForCompletion(
        McpGetAuthorizationHeaderOperation *this,
        struct IMcpGetAuthorizationHeaderResult **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int AuthorizationHeader; // eax
  unsigned int v8; // ebx
  struct IMcpGetAuthorizationHeaderResult *v9; // rcx
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-38h]
  char *v12; // [rsp+28h] [rbp-30h]
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v16; // [rsp+68h] [rbp+10h] BYREF
  struct IMcpGetAuthorizationHeaderResult *v17; // [rsp+70h] [rbp+18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpGetAuthorizationHeaderOperation::WaitForCompletion",
      L"Waiting for McpGetAuthorizationHeaderOperation to complete.");
    v16 = 0;
    v5 = McpOperationHandler::WaitForCompletion((McpGetAuthorizationHeaderOperation *)((char *)this + 248), &v16);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v17 = 0;
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      try
      {
        AuthorizationHeader = Microsoft::WRL::Details::MakeAndInitialize<McpGetAuthorizationHeaderResult,McpGetAuthorizationHeaderResult,long &,unsigned short const *,unsigned short const *,unsigned short const *>(
                                (unsigned int)&v17,
                                (unsigned int)&v16,
                                (unsigned int)&v14,
                                (unsigned int)&v13,
                                (__int64)&v18);
        v8 = AuthorizationHeader;
        if ( AuthorizationHeader < 0 )
        {
          McpManagementTelemetry::WriteDbgTraceWarning(
            "McpGetAuthorizationHeaderOperation::WaitForCompletion",
            L"Failed to MakeAndInitialize McpGetAuthorizationHeaderResult. hr=%#x",
            (unsigned int)AuthorizationHeader);
        }
        else
        {
          v9 = v17;
          v17 = 0;
          *a2 = v9;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        result = v8;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x72,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationh"
                                             "eaderoperation.cpp",
                               v10);
      }
    }
    else
    {
      LODWORD(v12) = v5;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationheaderoperation.cpp",
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
      (void *)0x57,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetauthorizationheaderoperation.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800230d0  push    rbx
0x1800230d2  push    rsi
0x1800230d3  push    rdi
0x1800230d4  sub     rsp, 40h
0x1800230d8  mov     rdi, rdx
0x1800230db  mov     rsi, rcx
0x1800230de  test    rdx, rdx
0x1800230e1  jnz     short loc_180023106
0x1800230e3  mov     rcx, [rsp+58h]; this
0x1800230e8  mov     ebx, 80004003h
0x1800230ed  mov     r9d, ebx; char *
0x1800230f0  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800230f7  lea     edx, [rdi+57h]; void *
0x1800230fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800230ff  mov     eax, ebx
0x180023101  jmp     loc_18002321A
0x180023106  mov     qword ptr [rdx], 0
0x18002310d  lea     rdx, aWaitingForMcpg; "Waiting for McpGetAuthorizationHeaderOp"...
0x180023114  lea     rcx, aMcpgetauthoriz_2; "McpGetAuthorizationHeaderOperation::Wai"...
0x18002311b  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023120  mov     [rsp+58h+arg_8], 0
0x180023128  lea     rcx, [rsi+0F8h]; this
0x18002312f  lea     rdx, [rsp+58h+arg_8]; int *
0x180023134  call    ?WaitForCompletion@McpOperationHandler@@QEAAJPEAJ@Z; McpOperationHandler::WaitForCompletion(long *)
0x180023139  mov     ebx, eax
0x18002313b  test    eax, eax
0x18002313d  jns     short loc_18002316F
0x18002313f  mov     rcx, [rsp+58h]; this
0x180023144  mov     dword ptr [rsp+58h+var_30], eax; char *
0x180023148  lea     rax, aOperationhandl; "OperationHandler Failed to WaitForCompl"...
0x18002314f  mov     qword ptr [rsp+58h+var_38], rax; int
0x180023154  mov     r9d, ebx; char *
0x180023157  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002315e  mov     edx, 5Eh ; '^'; void *
0x180023163  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023168  mov     eax, ebx
0x18002316a  jmp     loc_18002321A
0x18002316f  mov     [rsp+58h+arg_10], 0
0x180023178  lea     rcx, [rsi+0C8h]
0x18002317f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023184  mov     [rsp+58h+arg_18], rax
0x180023189  lea     rcx, [rsi+0A8h]
0x180023190  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023195  mov     [rsp+58h+var_28], rax
0x18002319a  lea     rcx, [rsi+88h]
0x1800231a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800231a6  mov     [rsp+58h+var_20], rax
0x1800231ab  lea     rcx, [rsp+58h+arg_10]
0x1800231b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800231b5  lea     rax, [rsp+58h+arg_18]
0x1800231ba  mov     qword ptr [rsp+58h+var_38], rax
0x1800231bf  lea     r9, [rsp+58h+var_28]
0x1800231c4  lea     r8, [rsp+58h+var_20]
0x1800231c9  lea     rdx, [rsp+58h+arg_8]
0x1800231ce  lea     rcx, [rsp+58h+arg_10]
0x1800231d3  call    ??$MakeAndInitialize@VMcpGetAuthorizationHeaderResult@@V1@AEAJPEBGPEBGPEBG@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetAuthorizationHeaderResult@@AEAJ$$QEAPEBG22@Z; Microsoft::WRL::Details::MakeAndInitialize<McpGetAuthorizationHeaderResult,McpGetAuthorizationHeaderResult,long &,ushort const *,ushort const *,ushort const *>(McpGetAuthorizationHeaderResult * *,long &,ushort const * &&,ushort const * &&,ushort const * &&)
0x1800231d8  mov     ebx, eax
0x1800231da  test    eax, eax
0x1800231dc  js      short loc_1800231F1
0x1800231de  mov     rcx, [rsp+58h+arg_10]
0x1800231e3  mov     [rsp+58h+arg_10], 0
0x1800231ec  mov     [rdi], rcx
0x1800231ef  jmp     short loc_180023208
0x1800231f1  mov     r8d, ebx
0x1800231f4  lea     rdx, aFailedToMakean; "Failed to MakeAndInitialize McpGetAutho"...
0x1800231fb  lea     rcx, aMcpgetauthoriz_2; "McpGetAuthorizationHeaderOperation::Wai"...
0x180023202  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180023207  nop
0x180023208  lea     rcx, [rsp+58h+arg_10]
0x18002320d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023212  mov     eax, ebx
0x180023214  jmp     short loc_18002321A
0x180023216  mov     eax, [rsp+58h+arg_8]
0x18002321a  add     rsp, 40h
0x18002321e  pop     rdi
0x18002321f  pop     rsi
0x180023220  pop     rbx
0x180023221  retn
```
