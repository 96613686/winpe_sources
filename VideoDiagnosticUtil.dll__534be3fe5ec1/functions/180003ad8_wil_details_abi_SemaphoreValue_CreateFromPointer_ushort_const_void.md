# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180003ad8`
- end: `0x180003c16`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003354`
- `0x180003700`

## callees

- `0x180003ad8`
- `0x180006870`
- `0x180006be8`
- `0x18000786c`
- `0x180008188`
- `0x1800096b0`

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
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  unsigned __int16 *v11; // rcx
  LONG v12; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // rdi
  int v20; // [rsp+20h] [rbp-258h]
  unsigned __int16 v21[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)this);
  v6 = a3 >> 2;
  v7 = v21;
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
  StringCchCatW(v21, v9, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6 & 0x7FFFFFFF, v12, v21);
  v16 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    StringCchCatW(v21, v14, L"h");
    v18 = v6 >> 31;
    if ( (_DWORD)v18 )
      v10 = v18;
    semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 1, v18, v10, v21);
    v16 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      return 0;
    v17 = 144;
  }
  else
  {
    v17 = 139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    v15,
    (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    v20);
  return v16;
}

```

## disassembly

```asm
0x180003ad8  mov     [rsp+arg_8], rbx
0x180003add  mov     [rsp+arg_18], rbp
0x180003ae2  push    rsi
0x180003ae3  push    rdi
0x180003ae4  push    r14
0x180003ae6  sub     rsp, 260h
0x180003aed  mov     rax, cs:__security_cookie
0x180003af4  xor     rax, rsp
0x180003af7  mov     [rsp+278h+var_28], rax
0x180003aff  mov     rdi, r8
0x180003b02  mov     rbp, rcx
0x180003b05  mov     r8, rdx
0x180003b08  test    dil, 3
0x180003b0c  jnz     loc_180003C10
0x180003b12  shr     rdi, 2
0x180003b16  lea     rax, [rsp+278h+var_238]
0x180003b1b  xor     r14d, r14d
0x180003b1e  mov     ecx, 7FFFFFFEh
0x180003b23  mov     edx, 104h
0x180003b28  lea     esi, [r14+1]
0x180003b2c  test    rcx, rcx
0x180003b2f  jz      short loc_180003B4F
0x180003b31  movzx   r9d, word ptr [r8]
0x180003b35  test    r9w, r9w
0x180003b39  jz      short loc_180003B4F
0x180003b3b  mov     [rax], r9w
0x180003b3f  add     r8, 2
0x180003b43  add     rax, 2
0x180003b47  sub     rcx, rsi
0x180003b4a  sub     rdx, rsi; unsigned __int64
0x180003b4d  jnz     short loc_180003B2C
0x180003b4f  test    rdx, rdx
0x180003b52  lea     rcx, [rax-2]
0x180003b56  lea     r8, aP0; "_p0"
0x180003b5d  cmovnz  rcx, rax
0x180003b61  mov     [rcx], r14w
0x180003b65  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003b6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b6f  mov     edx, edi
0x180003b71  lea     r9, [rsp+278h+var_238]
0x180003b76  and     edx, 7FFFFFFFh
0x180003b7c  mov     r8d, esi
0x180003b7f  mov     rcx, rbp
0x180003b82  cmova   r8d, edx
0x180003b86  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003b8b  mov     ebx, eax
0x180003b8d  test    eax, eax
0x180003b8f  jns     short loc_180003BA8
0x180003b91  mov     edx, 8Bh; void *
0x180003b96  mov     rcx, [rsp+278h]; this
0x180003b9e  mov     r9d, eax; char *
0x180003ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ba6  jmp     short loc_180003BE5
0x180003ba8  lea     r8, asc_18000B810; "h"
0x180003baf  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003bb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003bb9  shr     rdi, 1Fh
0x180003bbd  lea     rcx, [rbp+8]
0x180003bc1  test    edi, edi
0x180003bc3  lea     r9, [rsp+278h+var_238]
0x180003bc8  mov     edx, edi
0x180003bca  cmovnz  esi, edi
0x180003bcd  mov     r8d, esi
0x180003bd0  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003bd5  mov     ebx, eax
0x180003bd7  test    eax, eax
0x180003bd9  jns     short loc_180003BE2
0x180003bdb  mov     edx, 90h
0x180003be0  jmp     short loc_180003B96
0x180003be2  mov     ebx, r14d
0x180003be5  mov     eax, ebx
0x180003be7  mov     rcx, [rsp+278h+var_28]
0x180003bef  xor     rcx, rsp; StackCookie
0x180003bf2  call    __security_check_cookie
0x180003bf7  lea     r11, [rsp+278h+var_18]
0x180003bff  mov     rbx, [r11+28h]
0x180003c03  mov     rbp, [r11+38h]
0x180003c07  mov     rsp, r11
0x180003c0a  pop     r14
0x180003c0c  pop     rdi
0x180003c0d  pop     rsi
0x180003c0e  retn
0x180003c10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
