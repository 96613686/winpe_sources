# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180003dcc`
- end: `0x180003f11`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003648`
- `0x1800039f4`

## callees

- `0x180003dcc`
- `0x180007a94`
- `0x180008374`
- `0x1800094f0`
- `0x180009574`
- `0x18003d510`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        void **this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // esi
  unsigned __int16 *v11; // rcx
  LONG v12; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  int v19; // [rsp+20h] [rbp-268h]
  unsigned __int16 v20[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = v20;
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
  StringCchCatW(v20, 0x104u, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, v20);
  v15 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(v20, 0x104u, L"h");
    v17 = v6 >> 31;
    if ( (_DWORD)v17 )
      v10 = v17;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v17, v10, v20);
    v15 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v16 = 144;
  }
  else
  {
    v16 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    v14,
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    v19);
  return v15;
}

```

## disassembly

```asm
0x180003dcc  mov     [rsp+arg_8], rbx
0x180003dd1  push    rbp
0x180003dd2  push    rsi
0x180003dd3  push    rdi
0x180003dd4  push    r14
0x180003dd6  push    r15
0x180003dd8  sub     rsp, 260h
0x180003ddf  mov     rax, cs:__security_cookie
0x180003de6  xor     rax, rsp
0x180003de9  mov     [rsp+288h+var_38], rax
0x180003df1  mov     rdi, r8
0x180003df4  mov     rbp, rcx
0x180003df7  mov     r8, rdx
0x180003dfa  test    dil, 3
0x180003dfe  jnz     loc_180003F0B
0x180003e04  shr     rdi, 2
0x180003e08  lea     rax, [rsp+288h+var_248]
0x180003e0d  xor     r14d, r14d
0x180003e10  mov     r15d, 104h
0x180003e16  mov     ecx, 7FFFFFFEh
0x180003e1b  mov     edx, r15d
0x180003e1e  lea     esi, [r14+1]
0x180003e22  test    rcx, rcx
0x180003e25  jz      short loc_180003E45
0x180003e27  movzx   r9d, word ptr [r8]
0x180003e2b  test    r9w, r9w
0x180003e2f  jz      short loc_180003E45
0x180003e31  mov     [rax], r9w
0x180003e35  add     r8, 2
0x180003e39  add     rax, 2
0x180003e3d  sub     rcx, rsi
0x180003e40  sub     rdx, rsi
0x180003e43  jnz     short loc_180003E22
0x180003e45  test    rdx, rdx
0x180003e48  lea     rcx, [rax-2]
0x180003e4c  lea     r8, aP0; "_p0"
0x180003e53  mov     rdx, r15; unsigned __int64
0x180003e56  cmovnz  rcx, rax
0x180003e5a  mov     [rcx], r14w
0x180003e5e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180003e63  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e68  mov     edx, edi
0x180003e6a  lea     r9, [rsp+288h+var_248]
0x180003e6f  and     edx, 7FFFFFFFh
0x180003e75  mov     r8d, esi
0x180003e78  mov     rcx, rbp
0x180003e7b  cmova   r8d, edx
0x180003e7f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003e84  mov     ebx, eax
0x180003e86  test    eax, eax
0x180003e88  jns     short loc_180003EA1
0x180003e8a  mov     edx, 8Bh; void *
0x180003e8f  mov     rcx, [rsp+288h]; this
0x180003e97  mov     r9d, eax; char *
0x180003e9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e9f  jmp     short loc_180003EE1
0x180003ea1  lea     r8, asc_180043298; "h"
0x180003ea8  mov     rdx, r15; unsigned __int64
0x180003eab  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180003eb0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003eb5  shr     rdi, 1Fh
0x180003eb9  lea     rcx, [rbp+8]
0x180003ebd  test    edi, edi
0x180003ebf  lea     r9, [rsp+288h+var_248]
0x180003ec4  mov     edx, edi
0x180003ec6  cmovnz  esi, edi
0x180003ec9  mov     r8d, esi
0x180003ecc  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003ed1  mov     ebx, eax
0x180003ed3  test    eax, eax
0x180003ed5  jns     short loc_180003EDE
0x180003ed7  mov     edx, 90h
0x180003edc  jmp     short loc_180003E8F
0x180003ede  mov     ebx, r14d
0x180003ee1  mov     eax, ebx
0x180003ee3  mov     rcx, [rsp+288h+var_38]
0x180003eeb  xor     rcx, rsp; StackCookie
0x180003eee  call    __security_check_cookie
0x180003ef3  mov     rbx, [rsp+288h+arg_8]
0x180003efb  add     rsp, 260h
0x180003f02  pop     r15
0x180003f04  pop     r14
0x180003f06  pop     rdi
0x180003f07  pop     rsi
0x180003f08  pop     rbp
0x180003f09  retn
0x180003f0b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
