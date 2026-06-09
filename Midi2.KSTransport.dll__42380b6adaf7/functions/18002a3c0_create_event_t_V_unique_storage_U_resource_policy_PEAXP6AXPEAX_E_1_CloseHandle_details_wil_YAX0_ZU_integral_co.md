# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002a3c0`
- end: `0x18002a438`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028bc8`
- `0x180029038`
- `0x18003cb40`

## callees

- `0x1800083cc`
- `0x18000bb04`
- `0x18002a3c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a3da`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a3da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a40d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a401`

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

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
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
0x18002a3c0  push    rbx
0x18002a3c2  push    rbp
0x18002a3c3  push    rsi
0x18002a3c4  push    rdi
0x18002a3c5  sub     rsp, 28h
0x18002a3c9  xor     edx, edx; lpName
0x18002a3cb  mov     rdi, rcx
0x18002a3ce  xor     ecx, ecx; lpEventAttributes
0x18002a3d0  mov     r9d, 1F0003h; dwDesiredAccess
0x18002a3d6  lea     r8d, [rdx+1]; dwFlags
0x18002a3da  call    cs:__imp_CreateEventExW
0x18002a3e0  mov     rbp, rax
0x18002a3e3  test    rax, rax
0x18002a3e6  jz      short loc_18002A41A
0x18002a3e8  call    cs:__imp_GetLastError
0x18002a3ee  mov     rbx, [rdi]
0x18002a3f1  test    rbx, rbx
0x18002a3f4  jz      short loc_18002A413
0x18002a3f6  call    cs:__imp_GetLastError
0x18002a3fc  mov     rcx, rbx; hObject
0x18002a3ff  mov     esi, eax
0x18002a401  call    cs:__imp_CloseHandle
0x18002a407  test    eax, eax
0x18002a409  jz      short loc_18002A428
0x18002a40b  mov     ecx, esi; dwErrCode
0x18002a40d  call    cs:__imp_SetLastError
0x18002a413  mov     [rdi], rbp
0x18002a416  xor     eax, eax
0x18002a418  jmp     short loc_18002A41F
0x18002a41a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002a41f  add     rsp, 28h
0x18002a423  pop     rdi
0x18002a424  pop     rsi
0x18002a425  pop     rbp
0x18002a426  pop     rbx
0x18002a427  retn
0x18002a428  mov     rcx, [rsp+48h]; this
0x18002a42d  mov     edx, 0A0Bh; void *
0x18002a432  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
