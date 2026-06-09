# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18009f384`
- end: `0x18009f48a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `262`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009fc2c`

## callees

- `0x180002a00`
- `0x18009e6c0`
- `0x18009f384`
- `0x1800a01a0`
- `0x1800a06fc`
- `0x1800a0818`
- `0x1800a0ba0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  LONG v8; // esi
  LONG v9; // ebx
  LONG v10; // r8d
  unsigned __int64 v11; // rdx
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  unsigned int v13; // r8d
  __int64 v14; // rdx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = a4 >> 31;
  v8 = 1;
  v9 = a4 & 0x7FFFFFFF;
  v10 = 1;
  if ( v9 )
    v10 = v9;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, v9, v10, pszDest);
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v14 = 138;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      v13,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return (unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  StringCchCatW(pszDest, v11, L"h");
  if ( (_DWORD)v7 )
    v8 = v7;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 8, v7, v8, pszDest);
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v14 = 143;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x18009f384  mov     [rsp+arg_8], rbx
0x18009f389  push    rbp
0x18009f38a  push    rsi
0x18009f38b  push    rdi
0x18009f38c  sub     rsp, 260h
0x18009f393  mov     rax, cs:__security_cookie
0x18009f39a  xor     rax, rsp
0x18009f39d  mov     [rsp+278h+var_28], rax
0x18009f3a5  mov     rax, 0C000000000000000h
0x18009f3af  mov     rbx, r9
0x18009f3b2  mov     rbp, rcx
0x18009f3b5  test    rax, r9
0x18009f3b8  jnz     loc_18009F484
0x18009f3be  mov     r9, rdx; pszSrc
0x18009f3c1  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18009f3c6  mov     edx, 104h; cchDest
0x18009f3cb  call    StringCopyWorkerW
0x18009f3d0  lea     r8, aP0; "_p0"
0x18009f3d7  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18009f3dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009f3e1  mov     rdi, rbx
0x18009f3e4  lea     r9, [rsp+278h+pszDest]
0x18009f3e9  shr     rdi, 1Fh
0x18009f3ed  mov     esi, 1
0x18009f3f2  and     ebx, 7FFFFFFFh
0x18009f3f8  mov     r8d, esi
0x18009f3fb  mov     edx, ebx
0x18009f3fd  mov     rcx, rbp
0x18009f400  cmova   r8d, ebx
0x18009f404  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18009f409  mov     ebx, eax
0x18009f40b  test    eax, eax
0x18009f40d  jns     short loc_18009F428
0x18009f40f  mov     edx, 8Ah; void *
0x18009f414  mov     rcx, [rsp+278h]; this
0x18009f41c  mov     r9d, ebx; char *
0x18009f41f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f424  mov     eax, ebx
0x18009f426  jmp     short loc_18009F460
0x18009f428  lea     r8, asc_1800D4AB0; "h"
0x18009f42f  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18009f434  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009f439  test    edi, edi
0x18009f43b  lea     rcx, [rbp+8]
0x18009f43f  lea     r9, [rsp+278h+pszDest]
0x18009f444  mov     edx, edi
0x18009f446  cmovnz  esi, edi
0x18009f449  mov     r8d, esi
0x18009f44c  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18009f451  mov     ebx, eax
0x18009f453  test    eax, eax
0x18009f455  jns     short loc_18009F45E
0x18009f457  mov     edx, 8Fh
0x18009f45c  jmp     short loc_18009F414
0x18009f45e  xor     eax, eax
0x18009f460  mov     rcx, [rsp+278h+var_28]
0x18009f468  xor     rcx, rsp; StackCookie
0x18009f46b  call    __security_check_cookie
0x18009f470  mov     rbx, [rsp+278h+arg_8]
0x18009f478  add     rsp, 260h
0x18009f47f  pop     rdi
0x18009f480  pop     rsi
0x18009f481  pop     rbp
0x18009f482  retn
0x18009f484  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
