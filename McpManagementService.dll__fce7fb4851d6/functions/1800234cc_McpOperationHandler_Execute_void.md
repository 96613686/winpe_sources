# McpOperationHandler::Execute(void)

- ea: `0x1800234cc`
- end: `0x180023532`
- name: `?Execute@McpOperationHandler@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(McpOperationHandler *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002243c`
- `0x180022d9c`
- `0x180024bcc`

## callees

- `0x180004d1c`
- `0x180022000`
- `0x180023270`
- `0x180023334`
- `0x1800234cc`
- `0x1800236b4`

## string_xrefs

- `0x180023505`: `Exception was thrown during operation. hr=%#x`

## pseudocode

```c
void __fastcall McpOperationHandler::Execute(McpOperationHandler *this)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF
  char v6; // [rsp+38h] [rbp+10h] BYREF

  _SetEvent_scope_exit___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_XZ(
    (char *)this + 72,
    &v5);
  v2 = _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(&v6, this);
  v3 = wil::ResultFromException__lambda_cfa7517b0ac90ae322c0d5b729bc3af3___(v2);
  v4 = v3;
  if ( v3 < 0 )
  {
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpOperationHandler::Execute",
      L"Exception was thrown during operation. hr=%#x",
      (unsigned int)v3);
    *(_DWORD *)this = v4;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_SetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v5);
}

```

## disassembly

```asm
0x1800234cc  mov     [rsp+arg_10], rbx
0x1800234d1  push    rdi
0x1800234d2  sub     rsp, 20h
0x1800234d6  mov     rbx, rcx
0x1800234d9  add     rcx, 48h ; 'H'
0x1800234dd  lea     rdx, [rsp+28h+arg_0]
0x1800234e2  call    ?SetEvent_scope_exit@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x1800234e7  mov     rdx, rbx
0x1800234ea  lea     rcx, [rsp+28h+arg_8]
0x1800234ef  call    ??0_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@Z; _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *)
0x1800234f4  mov     rcx, rax
0x1800234f7  call    wil__ResultFromException__lambda_cfa7517b0ac90ae322c0d5b729bc3af3___
0x1800234fc  mov     edi, eax
0x1800234fe  test    eax, eax
0x180023500  jns     short loc_18002351A
0x180023502  mov     r8d, eax
0x180023505  lea     rdx, aExceptionWasTh; "Exception was thrown during operation. "...
0x18002350c  lea     rcx, aMcpoperationha_2; "McpOperationHandler::Execute"
0x180023513  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180023518  mov     [rbx], edi
0x18002351a  lea     rcx, [rsp+28h+arg_0]
0x18002351f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?SetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023524  nop
0x180023525  jmp     short $+2
0x180023527  mov     rbx, [rsp+28h+arg_10]
0x18002352c  add     rsp, 20h
0x180023530  pop     rdi
0x180023531  retn
```
