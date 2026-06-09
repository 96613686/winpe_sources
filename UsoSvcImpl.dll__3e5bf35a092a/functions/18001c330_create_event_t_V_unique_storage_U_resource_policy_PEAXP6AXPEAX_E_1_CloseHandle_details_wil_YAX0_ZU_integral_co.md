# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001c330`
- end: `0x18001c3cc`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d84`
- `0x180070acc`

## callees

- `0x180008ea8`
- `0x180010f24`
- `0x18001c330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c354`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c370`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c37b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c37b`

## string_xrefs

- `0x18001c3ba`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  HANDLE Event; // rsi
  const char *v3; // r9
  void *v4; // rbx
  DWORD LastError; // ebp
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CA0,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x18001c330  mov     [rsp+arg_0], rbx
0x18001c335  mov     [rsp+arg_8], rbp
0x18001c33a  mov     [rsp+arg_10], rsi
0x18001c33f  push    rdi
0x18001c340  sub     rsp, 20h
0x18001c344  mov     rdi, rcx
0x18001c347  mov     r9d, 1F0003h; dwDesiredAccess
0x18001c34d  xor     ecx, ecx; lpEventAttributes
0x18001c34f  xor     r8d, r8d; dwFlags
0x18001c352  xor     edx, edx; lpName
0x18001c354  call    cs:__imp_CreateEventExW
0x18001c35a  mov     rsi, rax
0x18001c35d  test    rax, rax
0x18001c360  jz      short loc_18001C3B5
0x18001c362  call    cs:__imp_GetLastError
0x18001c368  mov     rbx, [rdi]
0x18001c36b  test    rbx, rbx
0x18001c36e  jz      short loc_18001C38D
0x18001c370  call    cs:__imp_GetLastError
0x18001c376  mov     rcx, rbx; hObject
0x18001c379  mov     ebp, eax
0x18001c37b  call    cs:__imp_CloseHandle
0x18001c381  test    eax, eax
0x18001c383  jz      short loc_18001C3A5
0x18001c385  mov     ecx, ebp; dwErrCode
0x18001c387  call    cs:__imp_SetLastError
0x18001c38d  mov     rbx, [rsp+28h+arg_0]
0x18001c392  mov     rbp, [rsp+28h+arg_8]
0x18001c397  mov     [rdi], rsi
0x18001c39a  mov     rsi, [rsp+28h+arg_10]
0x18001c39f  add     rsp, 20h
0x18001c3a3  pop     rdi
0x18001c3a4  retn
0x18001c3a5  mov     rcx, [rsp+28h]; this
0x18001c3aa  mov     edx, 9D1h; void *
0x18001c3af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c3b5  mov     rcx, [rsp+28h]; this
0x18001c3ba  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001c3c1  mov     edx, 1CA0h; void *
0x18001c3c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
