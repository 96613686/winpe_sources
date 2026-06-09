# McpOperationHandler::Initialize(std::function<long (void)>)

- ea: `0x180023538`
- end: `0x1800235c0`
- name: `?Initialize@McpOperationHandler@@QEAAJV?$function@$$A6AJXZ@std@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022580`
- `0x180022e80`
- `0x180024ca0`

## callees

- `0x18001de88`
- `0x180022000`
- `0x18002204c`
- `0x180023350`
- `0x180023538`

## string_xrefs

- `0x180023569`: `Failed to create operationCompletedEvent. hr=%#x`

## pseudocode

```c
__int64 __fastcall McpOperationHandler::Initialize(__int64 a1, __int64 a2)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v9; // [rsp+40h] [rbp+8h]

  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 72, 1);
  v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    try
    {
      std::function<long (void)>::operator=(a1 + 8, a2);
      std::_Func_class<long,>::_Tidy(a2);
      result = 0;
    }
    catch ( ... )
    {
      v9 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x1B,
             (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpoperationhandler.cpp",
             v7);
      std::_Func_class<long,>::_Tidy(a2);
      return v9;
    }
  }
  else
  {
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpOperationHandler::Initialize",
      L"Failed to create operationCompletedEvent. hr=%#x",
      (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    std::_Func_class<long,>::_Tidy(a2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180023538  mov     [rsp+arg_10], rbx
0x18002353d  mov     [rsp+arg_18], rsi
0x180023542  mov     [rsp+arg_8], rdx
0x180023547  push    rdi
0x180023548  sub     rsp, 30h
0x18002354c  mov     rbx, rdx
0x18002354f  mov     rsi, rcx
0x180023552  add     rcx, 48h ; 'H'
0x180023556  mov     edx, 1
0x18002355b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180023560  mov     edi, eax
0x180023562  test    eax, eax
0x180023564  jns     short loc_180023589
0x180023566  mov     r8d, eax
0x180023569  lea     rdx, aFailedToCreate_6; "Failed to create operationCompletedEven"...
0x180023570  lea     rcx, aMcpoperationha_1; "McpOperationHandler::Initialize"
0x180023577  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002357c  nop
0x18002357d  mov     rcx, rbx
0x180023580  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x180023585  mov     eax, edi
0x180023587  jmp     short loc_1800235B0
0x180023589  lea     rcx, [rsi+8]
0x18002358d  mov     rdx, rbx
0x180023590  call    ??4?$function@$$A6AJXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<long (void)>::operator=(std::function<long (void)> const &)
0x180023595  nop
0x180023596  mov     rcx, rbx
0x180023599  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x18002359e  xor     eax, eax
0x1800235a0  jmp     short loc_1800235B0
0x1800235a2  mov     rcx, [rsp+38h+arg_8]
0x1800235a7  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x1800235ac  mov     eax, [rsp+38h+arg_0]
0x1800235b0  mov     rbx, [rsp+38h+arg_10]
0x1800235b5  mov     rsi, [rsp+38h+arg_18]
0x1800235ba  add     rsp, 30h
0x1800235be  pop     rdi
0x1800235bf  retn
```
