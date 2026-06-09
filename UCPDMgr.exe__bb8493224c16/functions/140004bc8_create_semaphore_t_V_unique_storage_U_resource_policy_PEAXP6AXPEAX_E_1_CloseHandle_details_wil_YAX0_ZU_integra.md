# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140004bc8`
- end: `0x140004c64`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005ba4`

## callees

- `0x140001d60`
- `0x140002be8`
- `0x140004bc8`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140004bf2`
- `KERNEL32!CreateSemaphoreExW` at `0x140004bf2`
- `KERNEL32!SetLastError` at `0x140004c25`
- `KERNEL32!SetLastError` at `0x140004c25`
- `KERNEL32!GetLastError` at `0x140004c00`
- `KERNEL32!GetLastError` at `0x140004c0e`
- `KERNEL32!GetLastError` at `0x140004c00`
- `KERNEL32!GetLastError` at `0x140004c0e`
- `KERNEL32!CloseHandle` at `0x140004c19`
- `KERNEL32!CloseHandle` at `0x140004c19`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v10, v11);
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140004bc8  mov     rax, rsp
0x140004bcb  mov     [rax+8], rbx
0x140004bcf  mov     [rax+10h], rbp
0x140004bd3  mov     [rax+18h], rsi
0x140004bd7  mov     [rax+20h], rdi
0x140004bdb  push    r14
0x140004bdd  sub     rsp, 30h
0x140004be1  mov     rsi, rcx
0x140004be4  mov     dword ptr [rax-10h], 1F0003h
0x140004beb  xor     ebx, ebx
0x140004bed  xor     ecx, ecx; lpSemaphoreAttributes
0x140004bef  mov     [rax-18h], ebx
0x140004bf2  call    cs:__imp_CreateSemaphoreExW
0x140004bf8  mov     r14, rax
0x140004bfb  test    rax, rax
0x140004bfe  jz      short loc_140004C30
0x140004c00  call    cs:__imp_GetLastError
0x140004c06  mov     rdi, [rsi]
0x140004c09  test    rdi, rdi
0x140004c0c  jz      short loc_140004C2B
0x140004c0e  call    cs:__imp_GetLastError
0x140004c14  mov     rcx, rdi; hObject
0x140004c17  mov     ebp, eax
0x140004c19  call    cs:__imp_CloseHandle
0x140004c1f  test    eax, eax
0x140004c21  jz      short loc_140004C54
0x140004c23  mov     ecx, ebp; dwErrCode
0x140004c25  call    cs:__imp_SetLastError
0x140004c2b  mov     [rsi], r14
0x140004c2e  jmp     short loc_140004C37
0x140004c30  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004c35  mov     ebx, eax
0x140004c37  mov     rbp, [rsp+38h+arg_8]
0x140004c3c  mov     eax, ebx
0x140004c3e  mov     rbx, [rsp+38h+arg_0]
0x140004c43  mov     rsi, [rsp+38h+arg_10]
0x140004c48  mov     rdi, [rsp+38h+arg_18]
0x140004c4d  add     rsp, 30h
0x140004c51  pop     r14
0x140004c53  retn
0x140004c54  mov     rcx, [rsp+38h]; this
0x140004c59  mov     edx, 9CDh; void *
0x140004c5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
