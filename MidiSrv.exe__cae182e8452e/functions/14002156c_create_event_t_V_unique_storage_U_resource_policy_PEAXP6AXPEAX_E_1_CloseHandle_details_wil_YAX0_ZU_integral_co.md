# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14002156c`
- end: `0x1400215e4`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001fe88`
- `0x140041a40`
- `0x140043720`
- `0x140046954`

## callees

- `0x14000914c`
- `0x14000c55c`
- `0x14002156c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140021586`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140021586`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400215b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400215b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400215a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400215a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400215ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400215ad`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  __int64 v6; // r8
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
0x14002156c  push    rbx
0x14002156e  push    rbp
0x14002156f  push    rsi
0x140021570  push    rdi
0x140021571  sub     rsp, 28h
0x140021575  xor     edx, edx; lpName
0x140021577  mov     rdi, rcx
0x14002157a  xor     ecx, ecx; lpEventAttributes
0x14002157c  mov     r9d, 1F0003h; dwDesiredAccess
0x140021582  lea     r8d, [rdx+1]; dwFlags
0x140021586  call    cs:__imp_CreateEventExW
0x14002158c  mov     rbp, rax
0x14002158f  test    rax, rax
0x140021592  jz      short loc_1400215C6
0x140021594  call    cs:__imp_GetLastError
0x14002159a  mov     rbx, [rdi]
0x14002159d  test    rbx, rbx
0x1400215a0  jz      short loc_1400215BF
0x1400215a2  call    cs:__imp_GetLastError
0x1400215a8  mov     rcx, rbx; hObject
0x1400215ab  mov     esi, eax
0x1400215ad  call    cs:__imp_CloseHandle
0x1400215b3  test    eax, eax
0x1400215b5  jz      short loc_1400215D4
0x1400215b7  mov     ecx, esi; dwErrCode
0x1400215b9  call    cs:__imp_SetLastError
0x1400215bf  mov     [rdi], rbp
0x1400215c2  xor     eax, eax
0x1400215c4  jmp     short loc_1400215CB
0x1400215c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400215cb  add     rsp, 28h
0x1400215cf  pop     rdi
0x1400215d0  pop     rsi
0x1400215d1  pop     rbp
0x1400215d2  pop     rbx
0x1400215d3  retn
0x1400215d4  mov     rcx, [rsp+48h]; this
0x1400215d9  mov     edx, 0A0Bh; void *
0x1400215de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
