# McpGetCloudPrintServiceResult::GetMcpService(IMcpService * *)

- ea: `0x180023a40`
- end: `0x180023b28`
- name: `?GetMcpService@McpGetCloudPrintServiceResult@@UEAAJPEAPEAUIMcpService@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceResult *this, struct IMcpService **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x180022000`
- `0x1800237f0`
- `0x180023a40`

## string_xrefs

- `0x180023af6`: `Failed to MakeAndInitialize McpService. hr=%#x`
- `0x180023a62`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`
- `0x180023a94`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`
- `0x180023afd`: `McpGetCloudPrintServiceResult::GetMcpService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall McpGetCloudPrintServiceResult::GetMcpService(
        McpGetCloudPrintServiceResult *this,
        struct IMcpService **a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // edi
  struct IMcpService *v7; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  McpService *v11; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    if ( *((int *)this + 6) >= 0 )
    {
      v11 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      try
      {
        v5 = Microsoft::WRL::Details::MakeAndInitialize<McpService,McpService,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>(
               &v11,
               (__int64)this + 32,
               (__int64)this + 48);
        v6 = v5;
        if ( v5 < 0 )
        {
          McpManagementTelemetry::WriteDbgTraceWarning(
            "McpGetCloudPrintServiceResult::GetMcpService",
            L"Failed to MakeAndInitialize McpService. hr=%#x",
            (unsigned int)v5);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
          result = v6;
        }
        else
        {
          v7 = v11;
          v11 = 0;
          *a2 = v7;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
          result = 0;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x36,
                               (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
                               v8);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
        (const char *)0x8007139FLL,
        v9);
      return 2147947423LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180023a40  mov     [rsp+arg_0], rbx
0x180023a45  push    rdi; int
0x180023a46  sub     rsp, 20h
0x180023a4a  mov     rbx, rdx
0x180023a4d  mov     rdi, rcx
0x180023a50  test    rdx, rdx
0x180023a53  jnz     short loc_180023A7A
0x180023a55  mov     rcx, [rsp+28h]; this
0x180023a5a  mov     ebx, 80004003h
0x180023a5f  mov     r9d, ebx; char *
0x180023a62  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023a69  mov     edx, 23h ; '#'; void *
0x180023a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a73  mov     eax, ebx
0x180023a75  jmp     loc_180023B1C
0x180023a7a  mov     qword ptr [rdx], 0
0x180023a81  cmp     dword ptr [rcx+18h], 0
0x180023a85  jge     short loc_180023AA9
0x180023a87  mov     rcx, [rsp+28h]; this
0x180023a8c  mov     ebx, 8007139Fh
0x180023a91  mov     r9d, ebx; char *
0x180023a94  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023a9b  mov     edx, 26h ; '&'; void *
0x180023aa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023aa5  mov     eax, ebx
0x180023aa7  jmp     short loc_180023B1C
0x180023aa9  mov     [rsp+28h+arg_8], 0
0x180023ab2  lea     rcx, [rsp+28h+arg_8]
0x180023ab7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023abc  lea     r8, [rdi+30h]
0x180023ac0  lea     rdx, [rdi+20h]
0x180023ac4  lea     rcx, [rsp+28h+arg_8]
0x180023ac9  call    ??$MakeAndInitialize@VMcpService@@V1@AEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpService@@AEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::WRL::Details::MakeAndInitialize<McpService,McpService,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>(McpService * *,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x180023ace  mov     edi, eax
0x180023ad0  test    eax, eax
0x180023ad2  js      short loc_180023AF3
0x180023ad4  mov     rax, [rsp+28h+arg_8]
0x180023ad9  mov     [rsp+28h+arg_8], 0
0x180023ae2  mov     [rbx], rax
0x180023ae5  lea     rcx, [rsp+28h+arg_8]
0x180023aea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023aef  xor     eax, eax
0x180023af1  jmp     short loc_180023B1C
0x180023af3  mov     r8d, edi
0x180023af6  lea     rdx, aFailedToMakean_2; "Failed to MakeAndInitialize McpService."...
0x180023afd  lea     rcx, aMcpgetcloudpri; "McpGetCloudPrintServiceResult::GetMcpSe"...
0x180023b04  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180023b09  nop
0x180023b0a  lea     rcx, [rsp+28h+arg_8]
0x180023b0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023b14  mov     eax, edi
0x180023b16  jmp     short loc_180023B1C
0x180023b18  mov     eax, dword ptr [rsp+28h+arg_8]
0x180023b1c  mov     rbx, [rsp+28h+arg_0]
0x180023b21  add     rsp, 20h
0x180023b25  pop     rdi
0x180023b26  retn
```
