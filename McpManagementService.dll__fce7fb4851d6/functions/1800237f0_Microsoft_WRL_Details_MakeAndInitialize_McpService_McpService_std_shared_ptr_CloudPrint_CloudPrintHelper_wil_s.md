# Microsoft::WRL::Details::MakeAndInitialize<McpService,McpService,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>(McpService * *,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)

- ea: `0x1800237f0`
- end: `0x1800238c4`
- name: `??$MakeAndInitialize@VMcpService@@V1@AEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVMcpService@@AEAV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(McpService **, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023a40`

## callees

- `0x180003ae4`
- `0x180006f0c`
- `0x180009fc0`
- `0x180011f34`
- `0x18001f758`
- `0x1800237f0`
- `0x1800238cc`
- `0x180026714`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<McpService,McpService,std::shared_ptr<CloudPrint::CloudPrintHelper> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>(
        McpService **a1,
        __int64 a2,
        __int64 a3)
{
  McpService *v6; // rax
  int v7; // ebx
  McpService *v8; // rsi
  _QWORD *v9; // rax
  _QWORD v11[2]; // [rsp+28h] [rbp-28h] BYREF
  _BYTE v12[24]; // [rsp+38h] [rbp-18h] BYREF
  McpService *v13; // [rsp+70h] [rbp+20h] BYREF
  McpService *v14; // [rsp+88h] [rbp+38h] BYREF

  *a1 = 0;
  v6 = (McpService *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v6;
  v13 = v6;
  if ( v6 )
  {
    v8 = McpService::McpService(v6);
    v13 = v8;
    v14 = 0;
    std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v11, a3);
    v9 = (_QWORD *)std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v12, a2);
    v7 = McpService::RuntimeClassInitialize((__int64)v8, v9, v11);
    if ( v7 >= 0 )
    {
      Microsoft::WRL::ComPtr<McpService>::InternalAddRef(&v13);
      *a1 = v8;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      v7 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800237f0  mov     [rsp-18h+arg_8], rbx
0x1800237f5  mov     [rsp-18h+arg_10], rsi
0x1800237fa  push    rbp
0x1800237fb  push    rdi
0x1800237fc  push    r14
0x1800237fe  mov     rbp, rsp
0x180023801  sub     rsp, 50h
0x180023805  mov     rbx, r8
0x180023808  mov     r14, rdx
0x18002380b  mov     rdi, rcx
0x18002380e  mov     qword ptr [rcx], 0
0x180023815  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002381c  mov     ecx, 68h ; 'h'; unsigned __int64
0x180023821  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023826  mov     [rbp+arg_18], rax
0x18002382a  mov     [rbp+arg_0], rax
0x18002382e  test    rax, rax
0x180023831  jnz     short loc_18002383A
0x180023833  mov     ebx, 8007000Eh
0x180023838  jmp     short loc_1800238A4
0x18002383a  mov     [rbp+var_30], rax
0x18002383e  mov     rcx, rax; this
0x180023841  call    ??0McpService@@QEAA@XZ; McpService::McpService(void)
0x180023846  mov     rsi, rax
0x180023849  mov     [rbp+arg_0], rax
0x18002384d  mov     [rbp+arg_18], 0
0x180023855  mov     rdx, rbx
0x180023858  lea     rcx, [rbp+var_28]
0x18002385c  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x180023861  mov     rdx, r14
0x180023864  lea     rcx, [rbp+var_18]
0x180023868  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x18002386d  lea     r8, [rbp+var_28]
0x180023871  mov     rdx, rax
0x180023874  mov     rcx, rsi
0x180023877  call    ?RuntimeClassInitialize@McpService@@QEAAJV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; McpService::RuntimeClassInitialize(std::shared_ptr<CloudPrint::CloudPrintHelper>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)
0x18002387c  mov     ebx, eax
0x18002387e  test    eax, eax
0x180023880  jns     short loc_18002388D
0x180023882  lea     rcx, [rbp+arg_0]
0x180023886  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002388b  jmp     short loc_1800238A4
0x18002388d  lea     rcx, [rbp+arg_0]
0x180023891  call    ?InternalAddRef@?$ComPtr@VMcpService@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<McpService>::InternalAddRef(void)
0x180023896  mov     [rdi], rsi
0x180023899  lea     rcx, [rbp+arg_0]
0x18002389d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800238a2  xor     ebx, ebx
0x1800238a4  lea     rcx, [rbp+arg_18]
0x1800238a8  call    ??1?$MakeAllocator@VMcpManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<McpManager>::~MakeAllocator<McpManager>(void)
0x1800238ad  mov     eax, ebx
0x1800238af  lea     r11, [rsp+50h+var_s0]
0x1800238b4  mov     rbx, [r11+28h]
0x1800238b8  mov     rsi, [r11+30h]
0x1800238bc  mov     rsp, r11
0x1800238bf  pop     r14
0x1800238c1  pop     rdi
0x1800238c2  pop     rbp
0x1800238c3  retn
```
