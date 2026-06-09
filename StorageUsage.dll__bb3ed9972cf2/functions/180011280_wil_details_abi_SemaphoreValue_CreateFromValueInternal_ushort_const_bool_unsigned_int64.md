# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180011280`
- end: `0x18001139e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013f80`
- `0x180027d34`

## callees

- `0x1800050f0`
- `0x180011280`
- `0x1800152d4`
- `0x180015b30`
- `0x180015c10`
- `0x1800167a0`
- `0x1800168fc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
    v15 = v14;
    if ( v14 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v14,
        v17);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x180011280  mov     [rsp+arg_10], rbx
0x180011285  push    rbp
0x180011286  push    rsi
0x180011287  push    rdi
0x180011288  sub     rsp, 260h
0x18001128f  mov     rax, cs:__security_cookie
0x180011296  xor     rax, rsp
0x180011299  mov     [rsp+278h+var_28], rax
0x1800112a1  mov     rax, 0C000000000000000h
0x1800112ab  mov     rbx, r9
0x1800112ae  mov     rbp, rcx
0x1800112b1  test    rax, r9
0x1800112b4  jz      short loc_1800112BC
0x1800112b6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800112bc  mov     r9, rdx; pszSrc
0x1800112bf  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800112c4  mov     edx, 104h; cchDest
0x1800112c9  call    StringCopyWorkerW
0x1800112ce  lea     r8, aP0; "_p0"
0x1800112d5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800112da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800112df  mov     edx, ebx
0x1800112e1  lea     r9, [rsp+278h+pszDest]
0x1800112e6  and     edx, 7FFFFFFFh
0x1800112ec  mov     esi, 1
0x1800112f1  mov     r8d, esi
0x1800112f4  mov     rcx, rbp
0x1800112f7  cmova   r8d, edx
0x1800112fb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011300  mov     edi, eax
0x180011302  test    eax, eax
0x180011304  jns     short loc_180011326
0x180011306  mov     rcx, [rsp+278h]; this
0x18001130e  lea     r8, aWil; "wil"
0x180011315  mov     r9d, eax; char *
0x180011318  mov     edx, 8Bh; void *
0x18001131d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011322  mov     eax, edi
0x180011324  jmp     short loc_18001137B
0x180011326  lea     r8, asc_180032170; "h"
0x18001132d  shr     rbx, 1Fh
0x180011331  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180011336  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001133b  test    ebx, ebx
0x18001133d  lea     rcx, [rbp+8]
0x180011341  lea     r9, [rsp+278h+pszDest]
0x180011346  mov     edx, ebx
0x180011348  cmovnz  esi, ebx
0x18001134b  mov     r8d, esi
0x18001134e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011353  mov     ebx, eax
0x180011355  test    eax, eax
0x180011357  jns     short loc_180011379
0x180011359  mov     rcx, [rsp+278h]; this
0x180011361  lea     r8, aWil; "wil"
0x180011368  mov     r9d, eax; char *
0x18001136b  mov     edx, 90h; void *
0x180011370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011375  mov     eax, ebx
0x180011377  jmp     short loc_18001137B
0x180011379  xor     eax, eax
0x18001137b  mov     rcx, [rsp+278h+var_28]
0x180011383  xor     rcx, rsp; StackCookie
0x180011386  call    __security_check_cookie
0x18001138b  mov     rbx, [rsp+278h+arg_10]
0x180011393  add     rsp, 260h
0x18001139a  pop     rdi
0x18001139b  pop     rsi
0x18001139c  pop     rbp
0x18001139d  retn
```
