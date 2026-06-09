# Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceResult,McpGetCloudPrintServiceResult,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>(McpGetCloudPrintServiceResult * *,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)

- ea: `0x180022084`
- end: `0x18002215d`
- name: `??$MakeAndInitialize@VMcpGetCloudPrintServiceResult@@V1@AEAJAEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpGetCloudPrintServiceResult@@AEAJAEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceResult **, unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022790`

## callees

- `0x180003ae4`
- `0x180006f0c`
- `0x180009fc0`
- `0x180011f34`
- `0x180022084`
- `0x1800221bc`
- `0x180023c90`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<McpGetCloudPrintServiceResult,McpGetCloudPrintServiceResult,long &,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>(
        McpGetCloudPrintServiceResult **a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  McpGetCloudPrintServiceResult *v8; // rax
  int v9; // edi
  McpGetCloudPrintServiceResult *CloudPrintServiceResult; // rbx
  __int64 v11; // rax
  McpGetCloudPrintServiceResult *v13; // [rsp+20h] [rbp-38h] BYREF
  McpGetCloudPrintServiceResult *v14; // [rsp+28h] [rbp-30h]
  _BYTE v15[16]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v16[24]; // [rsp+40h] [rbp-18h] BYREF
  McpGetCloudPrintServiceResult *v17; // [rsp+90h] [rbp+38h] BYREF

  *a1 = 0;
  v8 = (McpGetCloudPrintServiceResult *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v8;
  v17 = v8;
  if ( v8 )
  {
    v14 = v8;
    CloudPrintServiceResult = McpGetCloudPrintServiceResult::McpGetCloudPrintServiceResult(v8);
    v17 = CloudPrintServiceResult;
    std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v15, a4);
    v11 = std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v16, a3);
    v9 = McpGetCloudPrintServiceResult::RuntimeClassInitialize(CloudPrintServiceResult, *a2, v11, v15, 0, v14);
    if ( v9 >= 0 )
    {
      if ( CloudPrintServiceResult )
        (*(void (__fastcall **)(McpGetCloudPrintServiceResult *))(*(_QWORD *)CloudPrintServiceResult + 8LL))(CloudPrintServiceResult);
      *a1 = CloudPrintServiceResult;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      v9 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    }
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022084  push    rbp
0x180022086  push    rbx
0x180022087  push    rsi
0x180022088  push    rdi
0x180022089  push    r14
0x18002208b  push    r15
0x18002208d  mov     rbp, rsp
0x180022090  sub     rsp, 58h
0x180022094  mov     rdi, r9
0x180022097  mov     r14, r8
0x18002209a  mov     r15, rdx
0x18002209d  mov     rsi, rcx
0x1800220a0  mov     qword ptr [rcx], 0
0x1800220a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800220ae  mov     ecx, 70h ; 'p'; unsigned __int64
0x1800220b3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800220b8  mov     [rbp+var_38], rax
0x1800220bc  mov     [rbp+arg_0], rax
0x1800220c0  test    rax, rax
0x1800220c3  jnz     short loc_1800220CC
0x1800220c5  mov     edi, 8007000Eh
0x1800220ca  jmp     short loc_180022145
0x1800220cc  mov     [rbp+var_30], rax
0x1800220d0  mov     rcx, rax; this
0x1800220d3  call    ??0McpGetCloudPrintServiceResult@@QEAA@XZ; McpGetCloudPrintServiceResult::McpGetCloudPrintServiceResult(void)
0x1800220d8  mov     rbx, rax
0x1800220db  mov     [rbp+arg_0], rax
0x1800220df  mov     [rbp+var_38], 0
0x1800220e7  mov     rdx, rdi
0x1800220ea  lea     rcx, [rbp+var_28]
0x1800220ee  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x1800220f3  mov     rdx, r14
0x1800220f6  lea     rcx, [rbp+var_18]
0x1800220fa  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x1800220ff  lea     r9, [rbp+var_28]
0x180022103  mov     r8, rax
0x180022106  mov     edx, [r15]
0x180022109  mov     rcx, rbx
0x18002210c  call    ?RuntimeClassInitialize@McpGetCloudPrintServiceResult@@QEAAJJV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; McpGetCloudPrintServiceResult::RuntimeClassInitialize(long,std::shared_ptr<CloudPrint::CloudPrintHelper>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)
0x180022111  mov     edi, eax
0x180022113  test    eax, eax
0x180022115  jns     short loc_180022122
0x180022117  lea     rcx, [rbp+arg_0]
0x18002211b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022120  jmp     short loc_180022145
0x180022122  test    rbx, rbx
0x180022125  jz      short loc_180022137
0x180022127  mov     rax, [rbx]
0x18002212a  mov     rcx, rbx
0x18002212d  mov     rax, [rax+8]
0x180022131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022136  nop
0x180022137  mov     [rsi], rbx
0x18002213a  lea     rcx, [rbp+arg_0]
0x18002213e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022143  xor     edi, edi
0x180022145  lea     rcx, [rbp+var_38]
0x180022149  call    ??1?$MakeAllocator@VMcpManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(void)
0x18002214e  mov     eax, edi
0x180022150  add     rsp, 58h
0x180022154  pop     r15
0x180022156  pop     r14
0x180022158  pop     rdi
0x180022159  pop     rsi
0x18002215a  pop     rbx
0x18002215b  pop     rbp
0x18002215c  retn
```
