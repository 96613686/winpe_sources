# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140040e14`
- end: `0x140040eb1`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400402a4`
- `0x140040574`

## callees

- `0x140008140`
- `0x140008e28`
- `0x140040e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040e72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040e5b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140040e3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140040e3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040e66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140040e66`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  unsigned int v2; // ebx
  wil::details *v3; // rcx
  HANDLE Event; // r14
  void *v5; // rdi
  DWORD LastError; // ebp
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v5 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v7, v8);
      SetLastError(LastError);
    }
    *a1 = Event;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x140040e14  mov     rax, rsp
0x140040e17  mov     [rax+8], rbx
0x140040e1b  mov     [rax+10h], rbp
0x140040e1f  mov     [rax+18h], rsi
0x140040e23  mov     [rax+20h], rdi
0x140040e27  push    r14
0x140040e29  sub     rsp, 20h
0x140040e2d  mov     rsi, rcx
0x140040e30  mov     r9d, 1F0003h; dwDesiredAccess
0x140040e36  xor     ecx, ecx; lpEventAttributes
0x140040e38  xor     r8d, r8d; dwFlags
0x140040e3b  xor     edx, edx; lpName
0x140040e3d  call    cs:__imp_CreateEventExW
0x140040e43  xor     ebx, ebx
0x140040e45  mov     r14, rax
0x140040e48  test    rax, rax
0x140040e4b  jz      short loc_140040E7D
0x140040e4d  call    cs:__imp_GetLastError
0x140040e53  mov     rdi, [rsi]
0x140040e56  test    rdi, rdi
0x140040e59  jz      short loc_140040E78
0x140040e5b  call    cs:__imp_GetLastError
0x140040e61  mov     rcx, rdi; hObject
0x140040e64  mov     ebp, eax
0x140040e66  call    cs:__imp_CloseHandle
0x140040e6c  test    eax, eax
0x140040e6e  jz      short loc_140040EA1
0x140040e70  mov     ecx, ebp; dwErrCode
0x140040e72  call    cs:__imp_SetLastError
0x140040e78  mov     [rsi], r14
0x140040e7b  jmp     short loc_140040E84
0x140040e7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140040e82  mov     ebx, eax
0x140040e84  mov     rbp, [rsp+28h+arg_8]
0x140040e89  mov     eax, ebx
0x140040e8b  mov     rbx, [rsp+28h+arg_0]
0x140040e90  mov     rsi, [rsp+28h+arg_10]
0x140040e95  mov     rdi, [rsp+28h+arg_18]
0x140040e9a  add     rsp, 20h
0x140040e9e  pop     r14
0x140040ea0  retn
0x140040ea1  mov     rcx, [rsp+28h]; this
0x140040ea6  mov     edx, 9D1h; void *
0x140040eab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
