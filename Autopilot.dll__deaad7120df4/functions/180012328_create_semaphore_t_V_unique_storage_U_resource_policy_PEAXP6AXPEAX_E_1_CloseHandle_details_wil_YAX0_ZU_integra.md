# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012328`
- end: `0x1800123ca`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `162`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c184`

## callees

- `0x18000d5c0`
- `0x180012220`
- `0x180012328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012346`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001235a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001236e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001235a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001236e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012391`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001237f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001237f`

## string_xrefs

- `0x1800123b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    SetLastError(LastError);
  }
  *a1 = Semaphore;
  return 0;
}

```

## disassembly

```asm
0x180012328  push    rbx
0x18001232a  push    rbp
0x18001232b  push    rsi
0x18001232c  push    rdi
0x18001232d  sub     rsp, 38h
0x180012331  mov     rdi, rcx
0x180012334  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001233c  xor     ecx, ecx; lpSemaphoreAttributes
0x18001233e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180012346  call    cs:__imp_CreateSemaphoreExW
0x18001234d  nop     dword ptr [rax+rax+00h]
0x180012352  mov     rbp, rax
0x180012355  test    rax, rax
0x180012358  jz      short loc_1800123A4
0x18001235a  call    cs:__imp_GetLastError
0x180012361  nop     dword ptr [rax+rax+00h]
0x180012366  mov     rbx, [rdi]
0x180012369  test    rbx, rbx
0x18001236c  jz      short loc_18001239D
0x18001236e  call    cs:__imp_GetLastError
0x180012375  nop     dword ptr [rax+rax+00h]
0x18001237a  mov     rcx, rbx; hObject
0x18001237d  mov     esi, eax
0x18001237f  call    cs:__imp_CloseHandle
0x180012386  nop     dword ptr [rax+rax+00h]
0x18001238b  test    eax, eax
0x18001238d  jz      short loc_1800123B3
0x18001238f  mov     ecx, esi; dwErrCode
0x180012391  call    cs:__imp_SetLastError
0x180012398  nop     dword ptr [rax+rax+00h]
0x18001239d  mov     [rdi], rbp
0x1800123a0  xor     eax, eax
0x1800123a2  jmp     short loc_1800123A9
0x1800123a4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800123a9  add     rsp, 38h
0x1800123ad  pop     rdi
0x1800123ae  pop     rsi
0x1800123af  pop     rbp
0x1800123b0  pop     rbx
0x1800123b1  retn
0x1800123b3  mov     rcx, [rsp+58h]; this
0x1800123b8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800123bf  mov     edx, 0A0Bh; void *
0x1800123c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
