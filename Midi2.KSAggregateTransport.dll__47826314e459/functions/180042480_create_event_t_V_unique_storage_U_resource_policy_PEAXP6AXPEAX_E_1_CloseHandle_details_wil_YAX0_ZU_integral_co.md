# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180042480`
- end: `0x1800424f8`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bf70`
- `0x180049708`
- `0x180049b78`
- `0x18005813c`

## callees

- `0x180008f4c`
- `0x18000c684`
- `0x180042480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004249a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004249a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800424cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800424cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800424c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800424c1`

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
0x180042480  push    rbx
0x180042482  push    rbp
0x180042483  push    rsi
0x180042484  push    rdi
0x180042485  sub     rsp, 28h
0x180042489  xor     edx, edx; lpName
0x18004248b  mov     rdi, rcx
0x18004248e  xor     ecx, ecx; lpEventAttributes
0x180042490  mov     r9d, 1F0003h; dwDesiredAccess
0x180042496  lea     r8d, [rdx+1]; dwFlags
0x18004249a  call    cs:__imp_CreateEventExW
0x1800424a0  mov     rbp, rax
0x1800424a3  test    rax, rax
0x1800424a6  jz      short loc_1800424DA
0x1800424a8  call    cs:__imp_GetLastError
0x1800424ae  mov     rbx, [rdi]
0x1800424b1  test    rbx, rbx
0x1800424b4  jz      short loc_1800424D3
0x1800424b6  call    cs:__imp_GetLastError
0x1800424bc  mov     rcx, rbx; hObject
0x1800424bf  mov     esi, eax
0x1800424c1  call    cs:__imp_CloseHandle
0x1800424c7  test    eax, eax
0x1800424c9  jz      short loc_1800424E8
0x1800424cb  mov     ecx, esi; dwErrCode
0x1800424cd  call    cs:__imp_SetLastError
0x1800424d3  mov     [rdi], rbp
0x1800424d6  xor     eax, eax
0x1800424d8  jmp     short loc_1800424DF
0x1800424da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800424df  add     rsp, 28h
0x1800424e3  pop     rdi
0x1800424e4  pop     rsi
0x1800424e5  pop     rbp
0x1800424e6  pop     rbx
0x1800424e7  retn
0x1800424e8  mov     rcx, [rsp+48h]; this
0x1800424ed  mov     edx, 0A0Bh; void *
0x1800424f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
