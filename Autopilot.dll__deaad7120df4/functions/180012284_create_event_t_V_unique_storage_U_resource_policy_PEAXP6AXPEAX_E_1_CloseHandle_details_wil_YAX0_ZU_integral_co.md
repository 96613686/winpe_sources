# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012284`
- end: `0x180012321`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a608`

## callees

- `0x18000d5c0`
- `0x180012220`
- `0x180012284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001229d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001229d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122d6`

## string_xrefs

- `0x18001230f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  const char *v6; // r9
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
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x180012284  push    rbx
0x180012286  push    rbp
0x180012287  push    rsi
0x180012288  push    rdi
0x180012289  sub     rsp, 28h
0x18001228d  mov     rdi, rcx
0x180012290  mov     r9d, 1F0003h; dwDesiredAccess
0x180012296  xor     ecx, ecx; lpEventAttributes
0x180012298  xor     r8d, r8d; dwFlags
0x18001229b  xor     edx, edx; lpName
0x18001229d  call    cs:__imp_CreateEventExW
0x1800122a4  nop     dword ptr [rax+rax+00h]
0x1800122a9  mov     rbp, rax
0x1800122ac  test    rax, rax
0x1800122af  jz      short loc_1800122FB
0x1800122b1  call    cs:__imp_GetLastError
0x1800122b8  nop     dword ptr [rax+rax+00h]
0x1800122bd  mov     rbx, [rdi]
0x1800122c0  test    rbx, rbx
0x1800122c3  jz      short loc_1800122F4
0x1800122c5  call    cs:__imp_GetLastError
0x1800122cc  nop     dword ptr [rax+rax+00h]
0x1800122d1  mov     rcx, rbx; hObject
0x1800122d4  mov     esi, eax
0x1800122d6  call    cs:__imp_CloseHandle
0x1800122dd  nop     dword ptr [rax+rax+00h]
0x1800122e2  test    eax, eax
0x1800122e4  jz      short loc_18001230A
0x1800122e6  mov     ecx, esi; dwErrCode
0x1800122e8  call    cs:__imp_SetLastError
0x1800122ef  nop     dword ptr [rax+rax+00h]
0x1800122f4  mov     [rdi], rbp
0x1800122f7  xor     eax, eax
0x1800122f9  jmp     short loc_180012300
0x1800122fb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012300  add     rsp, 28h
0x180012304  pop     rdi
0x180012305  pop     rsi
0x180012306  pop     rbp
0x180012307  pop     rbx
0x180012308  retn
0x18001230a  mov     rcx, [rsp+48h]; this
0x18001230f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012316  mov     edx, 0A0Bh; void *
0x18001231b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
