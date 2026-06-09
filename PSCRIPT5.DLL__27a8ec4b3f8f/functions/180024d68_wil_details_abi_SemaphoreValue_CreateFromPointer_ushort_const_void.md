# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180024d68`
- end: `0x180024eb4`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, wchar_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024584`
- `0x180024960`

## callees

- `0x180001f20`
- `0x180020acc`
- `0x180024d68`
- `0x180027c74`
- `0x180028cf0`
- `0x180028d74`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(void **this, wchar_t *a2, unsigned __int64 a3)
{
  unsigned __int64 v6; // rdi
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // esi
  wchar_t *v11; // rcx
  LONG v12; // r8d
  signed int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = pszDest;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, pszDest);
  v14 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(pszDest, 0x104u, L"h");
    v16 = v6 >> 31;
    if ( (_DWORD)v16 )
      v10 = v16;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v16, v10, pszDest);
    v14 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v15 = 144;
  }
  else
  {
    v15 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (__int64)"wil",
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
  return v14;
}

```

## disassembly

```asm
0x180024d68  mov     [rsp+arg_8], rbx
0x180024d6d  push    rbp
0x180024d6e  push    rsi
0x180024d6f  push    rdi
0x180024d70  push    r14
0x180024d72  push    r15
0x180024d74  sub     rsp, 260h
0x180024d7b  mov     rax, cs:__security_cookie
0x180024d82  xor     rax, rsp
0x180024d85  mov     [rsp+288h+var_38], rax
0x180024d8d  mov     rdi, r8
0x180024d90  mov     rbp, rcx
0x180024d93  mov     r8, rdx
0x180024d96  test    dil, 3
0x180024d9a  jnz     loc_180024EAE
0x180024da0  shr     rdi, 2
0x180024da4  lea     rax, [rsp+288h+pszDest]
0x180024da9  xor     r14d, r14d
0x180024dac  mov     r15d, 104h
0x180024db2  mov     ecx, 7FFFFFFEh
0x180024db7  mov     edx, r15d
0x180024dba  lea     esi, [r14+1]
0x180024dbe  test    rcx, rcx
0x180024dc1  jz      short loc_180024DE1
0x180024dc3  movzx   r9d, word ptr [r8]
0x180024dc7  test    r9w, r9w
0x180024dcb  jz      short loc_180024DE1
0x180024dcd  mov     [rax], r9w
0x180024dd1  add     r8, 2
0x180024dd5  add     rax, 2
0x180024dd9  sub     rcx, rsi
0x180024ddc  sub     rdx, rsi
0x180024ddf  jnz     short loc_180024DBE
0x180024de1  test    rdx, rdx
0x180024de4  lea     rcx, [rax-2]
0x180024de8  lea     r8, aP0; "_p0"
0x180024def  mov     rdx, r15; cchDest
0x180024df2  cmovnz  rcx, rax
0x180024df6  mov     [rcx], r14w
0x180024dfa  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180024dff  call    StringCchCatW
0x180024e04  mov     edx, edi
0x180024e06  lea     r9, [rsp+288h+pszDest]
0x180024e0b  and     edx, 7FFFFFFFh
0x180024e11  mov     r8d, esi
0x180024e14  mov     rcx, rbp
0x180024e17  cmova   r8d, edx
0x180024e1b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024e20  mov     ebx, eax
0x180024e22  test    eax, eax
0x180024e24  jns     short loc_180024E44
0x180024e26  mov     edx, 8Bh; void *
0x180024e2b  mov     rcx, [rsp+288h]; this
0x180024e33  lea     r8, aWil; "wil"
0x180024e3a  mov     r9d, eax; char *
0x180024e3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e42  jmp     short loc_180024E84
0x180024e44  lea     r8, asc_180066DE0; "h"
0x180024e4b  mov     rdx, r15; cchDest
0x180024e4e  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180024e53  call    StringCchCatW
0x180024e58  shr     rdi, 1Fh
0x180024e5c  lea     rcx, [rbp+8]
0x180024e60  test    edi, edi
0x180024e62  lea     r9, [rsp+288h+pszDest]
0x180024e67  mov     edx, edi
0x180024e69  cmovnz  esi, edi
0x180024e6c  mov     r8d, esi
0x180024e6f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024e74  mov     ebx, eax
0x180024e76  test    eax, eax
0x180024e78  jns     short loc_180024E81
0x180024e7a  mov     edx, 90h
0x180024e7f  jmp     short loc_180024E2B
0x180024e81  mov     ebx, r14d
0x180024e84  mov     eax, ebx
0x180024e86  mov     rcx, [rsp+288h+var_38]
0x180024e8e  xor     rcx, rsp; StackCookie
0x180024e91  call    __security_check_cookie
0x180024e96  mov     rbx, [rsp+288h+arg_8]
0x180024e9e  add     rsp, 260h
0x180024ea5  pop     r15
0x180024ea7  pop     r14
0x180024ea9  pop     rdi
0x180024eaa  pop     rsi
0x180024eab  pop     rbp
0x180024eac  retn
0x180024eae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
