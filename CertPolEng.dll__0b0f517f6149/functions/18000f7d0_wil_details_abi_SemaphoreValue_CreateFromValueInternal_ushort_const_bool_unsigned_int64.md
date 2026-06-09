# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000f7d0`
- end: `0x18000f8f1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010784`
- `0x1800108d4`

## callees

- `0x18000a2ec`
- `0x18000a9cc`
- `0x18000c2d0`
- `0x18000f7d0`
- `0x18001226c`
- `0x180012630`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v6; // rdx
  unsigned int v7; // esi
  __int64 v8; // r8
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-268h]
  unsigned __int16 v16[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v16, 0x104u, a2);
  StringCchCatW(v16, 0x104u, L"_p0");
  v6 = a4 & 0x7FFFFFFF;
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = (unsigned int)v6;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this, v6, v8, v16);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v16, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v7 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (char *)this + 8,
            (unsigned int)v12,
            v7,
            v16);
    v14 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v15);
    return v10;
  }
}

```

## disassembly

```asm
0x18000f7d0  push    rbx
0x18000f7d2  push    rbp
0x18000f7d3  push    rsi
0x18000f7d4  push    rdi
0x18000f7d5  push    r14
0x18000f7d7  sub     rsp, 260h
0x18000f7de  mov     rax, cs:__security_cookie
0x18000f7e5  xor     rax, rsp
0x18000f7e8  mov     [rsp+288h+var_38], rax
0x18000f7f0  mov     rax, 0C000000000000000h
0x18000f7fa  mov     rbx, r9
0x18000f7fd  mov     rbp, rcx
0x18000f800  test    rax, r9
0x18000f803  jz      short loc_18000F80B
0x18000f805  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f80b  mov     r8, rdx; unsigned __int16 *
0x18000f80e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000f813  mov     r14d, 104h
0x18000f819  mov     edx, r14d; unsigned __int64
0x18000f81c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f821  lea     r8, aP0; "_p0"
0x18000f828  mov     edx, r14d; unsigned __int64
0x18000f82b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000f830  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f835  mov     edx, ebx
0x18000f837  lea     r9, [rsp+288h+var_248]
0x18000f83c  and     edx, 7FFFFFFFh
0x18000f842  mov     esi, 1
0x18000f847  mov     r8d, esi
0x18000f84a  mov     rcx, rbp
0x18000f84d  cmova   r8d, edx
0x18000f851  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000f856  mov     edi, eax
0x18000f858  test    eax, eax
0x18000f85a  jns     short loc_18000F87B
0x18000f85c  mov     rcx, [rsp+288h]; this
0x18000f864  lea     r8, aWil; "wil"
0x18000f86b  mov     r9d, eax; char *
0x18000f86e  lea     edx, [r14-79h]; void *
0x18000f872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f877  mov     eax, edi
0x18000f879  jmp     short loc_18000F8D3
0x18000f87b  lea     r8, asc_18001E6F4; "h"
0x18000f882  shr     rbx, 1Fh
0x18000f886  mov     rdx, r14; unsigned __int64
0x18000f889  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000f88e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f893  test    ebx, ebx
0x18000f895  lea     rcx, [rbp+8]
0x18000f899  lea     r9, [rsp+288h+var_248]
0x18000f89e  mov     edx, ebx
0x18000f8a0  cmovnz  esi, ebx
0x18000f8a3  mov     r8d, esi
0x18000f8a6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000f8ab  mov     ebx, eax
0x18000f8ad  test    eax, eax
0x18000f8af  jns     short loc_18000F8D1
0x18000f8b1  mov     rcx, [rsp+288h]; this
0x18000f8b9  lea     r8, aWil; "wil"
0x18000f8c0  mov     r9d, eax; char *
0x18000f8c3  mov     edx, 90h; void *
0x18000f8c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8cd  mov     eax, ebx
0x18000f8cf  jmp     short loc_18000F8D3
0x18000f8d1  xor     eax, eax
0x18000f8d3  mov     rcx, [rsp+288h+var_38]
0x18000f8db  xor     rcx, rsp; StackCookie
0x18000f8de  call    __security_check_cookie
0x18000f8e3  add     rsp, 260h
0x18000f8ea  pop     r14
0x18000f8ec  pop     rdi
0x18000f8ed  pop     rsi
0x18000f8ee  pop     rbp
0x18000f8ef  pop     rbx
0x18000f8f0  retn
```
