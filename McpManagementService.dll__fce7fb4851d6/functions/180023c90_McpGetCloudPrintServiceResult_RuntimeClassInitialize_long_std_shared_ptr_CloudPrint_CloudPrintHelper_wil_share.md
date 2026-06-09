# McpGetCloudPrintServiceResult::RuntimeClassInitialize(long,std::shared_ptr<CloudPrint::CloudPrintHelper>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180023c90`
- end: `0x180023d3d`
- name: `?RuntimeClassInitialize@McpGetCloudPrintServiceResult@@QEAAJJV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180022084`

## callees

- `0x180011f34`
- `0x1800125e4`
- `0x18001c9a8`
- `0x1800239a4`
- `0x180023c90`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceResult::RuntimeClassInitialize(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  std::_Ref_count_base *v10; // rcx
  _BYTE v12[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v13; // [rsp+28h] [rbp-20h]

  *(_DWORD *)(a1 + 24) = a2;
  std::shared_ptr<CloudPrint::CloudPrintHelper>::operator=(a1 + 32, a3);
  v7 = (__int64 *)std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v12, a4);
  v8 = *v7;
  *v7 = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = v8;
  v9 = v7[1];
  v7[1] = *(_QWORD *)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v9;
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v10 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(a4);
  return 0;
}

```

## disassembly

```asm
0x180023c90  mov     [rsp+arg_18], r9
0x180023c95  mov     [rsp+arg_10], r8
0x180023c9a  push    rbx
0x180023c9b  push    rsi
0x180023c9c  push    rdi
0x180023c9d  sub     rsp, 30h
0x180023ca1  mov     rbx, r9
0x180023ca4  mov     rdi, r8
0x180023ca7  mov     rsi, rcx
0x180023caa  mov     [rcx+18h], edx
0x180023cad  add     rcx, 20h ; ' '
0x180023cb1  mov     rdx, r8
0x180023cb4  call    ??4?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CloudPrint::CloudPrintHelper>::operator=(std::shared_ptr<CloudPrint::CloudPrintHelper> const &)
0x180023cb9  mov     rdx, rbx
0x180023cbc  lea     rcx, [rsp+48h+var_28]
0x180023cc1  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x180023cc6  mov     rdx, [rax]
0x180023cc9  mov     rcx, [rsi+30h]
0x180023ccd  mov     [rax], rcx
0x180023cd0  mov     [rsi+30h], rdx
0x180023cd4  mov     rdx, [rax+8]
0x180023cd8  mov     rcx, [rsi+38h]
0x180023cdc  mov     [rax+8], rcx
0x180023ce0  mov     [rsi+38h], rdx
0x180023ce4  mov     rcx, [rsp+48h+var_20]; this
0x180023ce9  test    rcx, rcx
0x180023cec  jz      short loc_180023CF3
0x180023cee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023cf3  lea     rax, [rdi+8]
0x180023cf7  mov     [rsp+48h+arg_10], rax
0x180023cfc  mov     rcx, [rax]; this
0x180023cff  test    rcx, rcx
0x180023d02  jz      short loc_180023D09
0x180023d04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023d09  mov     rcx, rbx
0x180023d0c  call    ??1?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAA@XZ; std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(void)
0x180023d11  xor     eax, eax
0x180023d13  jmp     short loc_180023D35
0x180023d15  mov     rax, [rsp+48h+arg_10]
0x180023d1a  mov     rcx, [rax]; this
0x180023d1d  test    rcx, rcx
0x180023d20  jz      short loc_180023D27
0x180023d22  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023d27  mov     rcx, [rsp+48h+arg_18]
0x180023d2c  call    ??1?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAA@XZ; std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(void)
0x180023d31  mov     eax, [rsp+48h+arg_8]
0x180023d35  add     rsp, 30h
0x180023d39  pop     rdi
0x180023d3a  pop     rsi
0x180023d3b  pop     rbx
0x180023d3c  retn
```
