# McpManager::GetCloudPrintServiceInternal(bool,bool,bool,IMcpGetCloudPrintServiceOperation * *)

- ea: `0x180021d44`
- end: `0x180021e0f`
- name: `?GetCloudPrintServiceInternal@McpManager@@AEAAJ_N00PEAPEAUIMcpGetCloudPrintServiceOperation@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(McpManager *this, char, char, char, struct IMcpGetCloudPrintServiceOperation **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021d10`
- `0x180021e20`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18001b060`
- `0x1800215d8`
- `0x180021d44`
- `0x180022000`
- `0x18002341c`

## string_xrefs

- `0x180021de8`: `Failed to spawn McpGetCloudPrintServiceOperation worker thread. hr=%#x`
- `0x180021def`: `McpManager::GetCloudPrintServiceInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall McpManager::GetCloudPrintServiceInternal(
        McpManager *this,
        char a2,
        char a3,
        char a4,
        struct IMcpGetCloudPrintServiceOperation **a5)
{
  struct IMcpGetCloudPrintServiceOperation **v5; // rdi
  __int64 Error; // rbx
  struct IMcpGetCloudPrintServiceOperation *v7; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  McpManager *v11; // [rsp+40h] [rbp+20h] BYREF
  char v12; // [rsp+48h] [rbp+28h] BYREF
  char v13; // [rsp+50h] [rbp+30h] BYREF
  char v14; // [rsp+58h] [rbp+38h] BYREF

  v14 = a4;
  v13 = a3;
  v12 = a2;
  v11 = this;
  v5 = a5;
  if ( a5 )
  {
    *a5 = 0;
    v11 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    LODWORD(Error) = Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceOperation,McpGetCloudPrintServiceOperation,bool &,bool &,bool &>(
                       &v11,
                       &v12,
                       &v13,
                       &v14);
    if ( (int)Error >= 0 )
    {
      if ( McpOperationHandler::CreateOperationThread(*((void **)v11 + 19)) )
      {
        v7 = v11;
        v11 = 0;
        *v5 = v7;
      }
      else
      {
        Error = (unsigned int)ResultFromKnownLastError();
        McpManagementTelemetry::WriteDbgTraceWarning(
          "McpManager::GetCloudPrintServiceInternal",
          L"Failed to spawn McpGetCloudPrintServiceOperation worker thread. hr=%#x",
          Error);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  }
  else
  {
    LODWORD(Error) = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpmanager.cpp",
      (const char *)0x80004003LL,
      savedregs);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180021d44  mov     rax, rsp
0x180021d47  mov     [rax+20h], r9b
0x180021d4b  mov     [rax+18h], r8b
0x180021d4f  mov     [rax+10h], dl
0x180021d52  mov     [rax+8], rcx
0x180021d56  push    rbp
0x180021d57  push    rbx
0x180021d58  push    rdi; int
0x180021d59  mov     rbp, rsp
0x180021d5c  sub     rsp, 20h
0x180021d60  mov     rdi, [rbp+arg_20]
0x180021d64  test    rdi, rdi
0x180021d67  jnz     short loc_180021D86
0x180021d69  mov     rcx, [rbp+18h]; this
0x180021d6d  mov     ebx, 80004003h
0x180021d72  mov     r9d, ebx; char *
0x180021d75  lea     r8, aOnecoreuapPrin_10; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180021d7c  lea     edx, [rdi+4Ah]; void *
0x180021d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d84  jmp     short loc_180021E05
0x180021d86  mov     qword ptr [rdi], 0
0x180021d8d  mov     [rbp+arg_0], 0
0x180021d95  lea     rcx, [rbp+arg_0]
0x180021d99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d9e  lea     r9, [rbp+arg_18]
0x180021da2  lea     r8, [rbp+arg_10]
0x180021da6  lea     rdx, [rbp+arg_8]
0x180021daa  lea     rcx, [rbp+arg_0]
0x180021dae  call    ??$MakeAndInitialize@VMcpGetCloudPrintServiceOperation@@V1@AEA_NAEA_NAEA_N@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetCloudPrintServiceOperation@@AEA_N11@Z; Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceOperation,McpGetCloudPrintServiceOperation,bool &,bool &,bool &>(McpGetCloudPrintServiceOperation * *,bool &,bool &,bool &)
0x180021db3  mov     ebx, eax
0x180021db5  test    eax, eax
0x180021db7  js      short loc_180021DFC
0x180021db9  mov     rcx, [rbp+arg_0]
0x180021dbd  mov     rcx, [rcx+98h]; lpParameter
0x180021dc4  call    ?CreateOperationThread@McpOperationHandler@@SA_NPEAX@Z; McpOperationHandler::CreateOperationThread(void *)
0x180021dc9  test    al, al
0x180021dcb  jz      short loc_180021DDE
0x180021dcd  mov     rcx, [rbp+arg_0]
0x180021dd1  mov     [rbp+arg_0], 0
0x180021dd9  mov     [rdi], rcx
0x180021ddc  jmp     short loc_180021DFC
0x180021dde  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021de3  mov     ebx, eax
0x180021de5  mov     r8d, eax
0x180021de8  lea     rdx, aFailedToSpawnM_0; "Failed to spawn McpGetCloudPrintService"...
0x180021def  lea     rcx, aMcpmanagerGetc; "McpManager::GetCloudPrintServiceInterna"...
0x180021df6  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180021dfb  nop
0x180021dfc  lea     rcx, [rbp+arg_0]
0x180021e00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021e05  mov     eax, ebx
0x180021e07  add     rsp, 20h
0x180021e0b  pop     rdi
0x180021e0c  pop     rbx
0x180021e0d  pop     rbp
0x180021e0e  retn
```
