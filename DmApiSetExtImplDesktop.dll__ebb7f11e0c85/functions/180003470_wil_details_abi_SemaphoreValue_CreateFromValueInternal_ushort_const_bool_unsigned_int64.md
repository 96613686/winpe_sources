# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003470`
- end: `0x180003592`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800046f4`

## callees

- `0x180003470`
- `0x180004e04`
- `0x1800052f8`
- `0x180005384`
- `0x180005abc`
- `0x180006300`
- `0x180009f30`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x180003470  push    rbx
0x180003472  push    rbp
0x180003473  push    rsi
0x180003474  push    rdi
0x180003475  push    r14
0x180003477  sub     rsp, 260h
0x18000347e  mov     rax, cs:__security_cookie
0x180003485  xor     rax, rsp
0x180003488  mov     [rsp+288h+var_38], rax
0x180003490  mov     rax, 0C000000000000000h
0x18000349a  mov     rbx, r9
0x18000349d  mov     rbp, rcx
0x1800034a0  test    rax, r9
0x1800034a3  jz      short loc_1800034AB
0x1800034a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800034ab  mov     r8, rdx; unsigned __int16 *
0x1800034ae  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800034b3  mov     r14d, 104h
0x1800034b9  mov     edx, r14d; unsigned __int64
0x1800034bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800034c1  lea     r8, aP0; "_p0"
0x1800034c8  mov     edx, r14d; unsigned __int64
0x1800034cb  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800034d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800034d5  mov     edx, ebx
0x1800034d7  lea     r9, [rsp+288h+var_248]
0x1800034dc  and     edx, 7FFFFFFFh
0x1800034e2  mov     esi, 1
0x1800034e7  mov     r8d, esi
0x1800034ea  mov     rcx, rbp
0x1800034ed  cmova   r8d, edx
0x1800034f1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800034f6  mov     edi, eax
0x1800034f8  test    eax, eax
0x1800034fa  jns     short loc_18000351B
0x1800034fc  mov     rcx, [rsp+288h]; this
0x180003504  lea     r8, aWil; "wil"
0x18000350b  mov     r9d, eax; char *
0x18000350e  lea     edx, [r14-79h]; void *
0x180003512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003517  mov     eax, edi
0x180003519  jmp     short loc_180003573
0x18000351b  lea     r8, asc_18000D1C8; "h"
0x180003522  shr     rbx, 1Fh
0x180003526  mov     rdx, r14; unsigned __int64
0x180003529  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000352e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003533  test    ebx, ebx
0x180003535  lea     rcx, [rbp+8]
0x180003539  lea     r9, [rsp+288h+var_248]
0x18000353e  mov     edx, ebx
0x180003540  cmovnz  esi, ebx
0x180003543  mov     r8d, esi
0x180003546  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000354b  mov     ebx, eax
0x18000354d  test    eax, eax
0x18000354f  jns     short loc_180003571
0x180003551  mov     rcx, [rsp+288h]; this
0x180003559  lea     r8, aWil; "wil"
0x180003560  mov     r9d, eax; char *
0x180003563  mov     edx, 90h; void *
0x180003568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000356d  mov     eax, ebx
0x18000356f  jmp     short loc_180003573
0x180003571  xor     eax, eax
0x180003573  mov     rcx, [rsp+288h+var_38]
0x18000357b  xor     rcx, rsp; StackCookie
0x18000357e  call    __security_check_cookie
0x180003583  add     rsp, 260h
0x18000358a  pop     r14
0x18000358c  pop     rdi
0x18000358d  pop     rsi
0x18000358e  pop     rbp
0x18000358f  pop     rbx
0x180003590  retn
```
