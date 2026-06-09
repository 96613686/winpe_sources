# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180027f60`
- end: `0x180027fd7`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e508`

## callees

- `0x18000a2a8`
- `0x18000e54c`
- `0x180027f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027f79`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027fac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fa0`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x180027f60  push    rbx
0x180027f62  push    rbp
0x180027f63  push    rsi
0x180027f64  push    rdi
0x180027f65  sub     rsp, 28h
0x180027f69  mov     rdi, rcx
0x180027f6c  mov     r9d, 1F0003h; dwDesiredAccess
0x180027f72  xor     ecx, ecx; lpEventAttributes
0x180027f74  xor     r8d, r8d; dwFlags
0x180027f77  xor     edx, edx; lpName
0x180027f79  call    cs:__imp_CreateEventExW
0x180027f7f  mov     rbp, rax
0x180027f82  test    rax, rax
0x180027f85  jz      short loc_180027FB9
0x180027f87  call    cs:__imp_GetLastError
0x180027f8d  mov     rbx, [rdi]
0x180027f90  test    rbx, rbx
0x180027f93  jz      short loc_180027FB2
0x180027f95  call    cs:__imp_GetLastError
0x180027f9b  mov     rcx, rbx; hObject
0x180027f9e  mov     esi, eax
0x180027fa0  call    cs:__imp_CloseHandle
0x180027fa6  test    eax, eax
0x180027fa8  jz      short loc_180027FC7
0x180027faa  mov     ecx, esi; dwErrCode
0x180027fac  call    cs:__imp_SetLastError
0x180027fb2  mov     [rdi], rbp
0x180027fb5  xor     eax, eax
0x180027fb7  jmp     short loc_180027FBE
0x180027fb9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180027fbe  add     rsp, 28h
0x180027fc2  pop     rdi
0x180027fc3  pop     rsi
0x180027fc4  pop     rbp
0x180027fc5  pop     rbx
0x180027fc6  retn
0x180027fc7  mov     rcx, [rsp+48h]; this
0x180027fcc  mov     edx, 0A0Bh; void *
0x180027fd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
