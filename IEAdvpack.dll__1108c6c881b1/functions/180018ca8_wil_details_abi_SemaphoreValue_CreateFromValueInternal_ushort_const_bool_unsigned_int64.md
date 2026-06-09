# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180018ca8`
- end: `0x180018dbb`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d60`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x180018ca8`
- `0x18001a9d4`
- `0x18001b054`
- `0x18001b0d4`
- `0x18001b980`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180018ca8  push    rbx
0x180018caa  push    rbp
0x180018cab  push    rsi
0x180018cac  push    rdi
0x180018cad  push    r14
0x180018caf  sub     rsp, 260h
0x180018cb6  mov     rax, cs:__security_cookie
0x180018cbd  xor     rax, rsp
0x180018cc0  mov     [rsp+288h+var_38], rax
0x180018cc8  mov     rax, 0C000000000000000h
0x180018cd2  mov     rbx, r9
0x180018cd5  mov     rbp, rcx
0x180018cd8  test    rax, r9
0x180018cdb  jz      short loc_180018CE3
0x180018cdd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180018ce3  mov     r8, rdx; unsigned __int16 *
0x180018ce6  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180018ceb  mov     r14d, 104h
0x180018cf1  mov     edx, r14d; unsigned __int64
0x180018cf4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018cf9  lea     r8, aP0; "_p0"
0x180018d00  mov     edx, r14d; unsigned __int64
0x180018d03  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180018d08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018d0d  mov     edx, ebx
0x180018d0f  lea     r9, [rsp+288h+var_248]
0x180018d14  and     edx, 7FFFFFFFh
0x180018d1a  mov     esi, 1
0x180018d1f  mov     r8d, esi
0x180018d22  mov     rcx, rbp
0x180018d25  cmova   r8d, edx
0x180018d29  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180018d2e  mov     edi, eax
0x180018d30  test    eax, eax
0x180018d32  jns     short loc_180018D4C
0x180018d34  mov     rcx, [rsp+288h]; this
0x180018d3c  lea     edx, [r14-79h]; void *
0x180018d40  mov     r9d, eax; char *
0x180018d43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d48  mov     eax, edi
0x180018d4a  jmp     short loc_180018D9D
0x180018d4c  lea     r8, asc_1800210D0; "h"
0x180018d53  shr     rbx, 1Fh
0x180018d57  mov     rdx, r14; unsigned __int64
0x180018d5a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180018d5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018d64  test    ebx, ebx
0x180018d66  lea     rcx, [rbp+8]
0x180018d6a  lea     r9, [rsp+288h+var_248]
0x180018d6f  mov     edx, ebx
0x180018d71  cmovnz  esi, ebx
0x180018d74  mov     r8d, esi
0x180018d77  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180018d7c  mov     ebx, eax
0x180018d7e  test    eax, eax
0x180018d80  jns     short loc_180018D9B
0x180018d82  mov     rcx, [rsp+288h]; this
0x180018d8a  mov     r9d, eax; char *
0x180018d8d  mov     edx, 90h; void *
0x180018d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d97  mov     eax, ebx
0x180018d99  jmp     short loc_180018D9D
0x180018d9b  xor     eax, eax
0x180018d9d  mov     rcx, [rsp+288h+var_38]
0x180018da5  xor     rcx, rsp; StackCookie
0x180018da8  call    __security_check_cookie
0x180018dad  add     rsp, 260h
0x180018db4  pop     r14
0x180018db6  pop     rdi
0x180018db7  pop     rsi
0x180018db8  pop     rbp
0x180018db9  pop     rbx
0x180018dba  retn
```
