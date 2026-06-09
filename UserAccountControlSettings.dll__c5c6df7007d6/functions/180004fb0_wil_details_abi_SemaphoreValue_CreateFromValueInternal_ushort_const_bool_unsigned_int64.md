# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004fb0`
- end: `0x1800050c3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800061a0`

## callees

- `0x180004fb0`
- `0x1800067ec`
- `0x180006a9c`
- `0x180006af0`
- `0x180007050`
- `0x1800070d0`
- `0x18000b710`

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
0x180004fb0  push    rbx
0x180004fb2  push    rbp
0x180004fb3  push    rsi
0x180004fb4  push    rdi
0x180004fb5  push    r14
0x180004fb7  sub     rsp, 260h
0x180004fbe  mov     rax, cs:__security_cookie
0x180004fc5  xor     rax, rsp
0x180004fc8  mov     [rsp+288h+var_38], rax
0x180004fd0  mov     rax, 0C000000000000000h
0x180004fda  mov     rbx, r9
0x180004fdd  mov     rbp, rcx
0x180004fe0  test    rax, r9
0x180004fe3  jz      short loc_180004FEB
0x180004fe5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004feb  mov     r8, rdx; unsigned __int16 *
0x180004fee  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180004ff3  mov     r14d, 104h
0x180004ff9  mov     edx, r14d; unsigned __int64
0x180004ffc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005001  lea     r8, aP0; "_p0"
0x180005008  mov     edx, r14d; unsigned __int64
0x18000500b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180005010  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005015  mov     edx, ebx
0x180005017  lea     r9, [rsp+288h+var_248]
0x18000501c  and     edx, 7FFFFFFFh
0x180005022  mov     esi, 1
0x180005027  mov     r8d, esi
0x18000502a  mov     rcx, rbp
0x18000502d  cmova   r8d, edx
0x180005031  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005036  mov     edi, eax
0x180005038  test    eax, eax
0x18000503a  jns     short loc_180005054
0x18000503c  mov     rcx, [rsp+288h]; this
0x180005044  lea     edx, [r14-79h]; void *
0x180005048  mov     r9d, eax; char *
0x18000504b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005050  mov     eax, edi
0x180005052  jmp     short loc_1800050A5
0x180005054  lea     r8, asc_18000EC58; "h"
0x18000505b  shr     rbx, 1Fh
0x18000505f  mov     rdx, r14; unsigned __int64
0x180005062  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180005067  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000506c  test    ebx, ebx
0x18000506e  lea     rcx, [rbp+8]
0x180005072  lea     r9, [rsp+288h+var_248]
0x180005077  mov     edx, ebx
0x180005079  cmovnz  esi, ebx
0x18000507c  mov     r8d, esi
0x18000507f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005084  mov     ebx, eax
0x180005086  test    eax, eax
0x180005088  jns     short loc_1800050A3
0x18000508a  mov     rcx, [rsp+288h]; this
0x180005092  mov     r9d, eax; char *
0x180005095  mov     edx, 90h; void *
0x18000509a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000509f  mov     eax, ebx
0x1800050a1  jmp     short loc_1800050A5
0x1800050a3  xor     eax, eax
0x1800050a5  mov     rcx, [rsp+288h+var_38]
0x1800050ad  xor     rcx, rsp; StackCookie
0x1800050b0  call    __security_check_cookie
0x1800050b5  add     rsp, 260h
0x1800050bc  pop     r14
0x1800050be  pop     rdi
0x1800050bf  pop     rsi
0x1800050c0  pop     rbp
0x1800050c1  pop     rbx
0x1800050c2  retn
```
