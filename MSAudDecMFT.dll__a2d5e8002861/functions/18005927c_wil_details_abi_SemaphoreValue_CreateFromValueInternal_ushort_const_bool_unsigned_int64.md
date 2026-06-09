# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18005927c`
- end: `0x18005938d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `273`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ba74`

## callees

- `0x18004d320`
- `0x18005673c`
- `0x18005927c`
- `0x18005c408`
- `0x18005c654`
- `0x18005cb18`
- `0x18005cd58`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x18005927c  mov     [rsp+arg_10], rbx
0x180059281  push    rbp
0x180059282  push    rsi
0x180059283  push    rdi
0x180059284  sub     rsp, 260h
0x18005928b  mov     rax, cs:__security_cookie
0x180059292  xor     rax, rsp
0x180059295  mov     [rsp+278h+var_28], rax
0x18005929d  mov     rax, 0C000000000000000h
0x1800592a7  mov     rbx, r9
0x1800592aa  mov     rbp, rcx
0x1800592ad  test    rax, r9
0x1800592b0  jz      short loc_1800592B8
0x1800592b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800592b8  mov     r8, rdx; unsigned __int16 *
0x1800592bb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800592c0  mov     edx, 104h; unsigned __int64
0x1800592c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800592ca  lea     r8, aP0; "_p0"
0x1800592d1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800592d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800592db  mov     edx, ebx
0x1800592dd  lea     r9, [rsp+278h+var_238]
0x1800592e2  and     edx, 7FFFFFFFh
0x1800592e8  mov     esi, 1
0x1800592ed  mov     r8d, esi
0x1800592f0  mov     rcx, rbp
0x1800592f3  cmova   r8d, edx
0x1800592f7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800592fc  mov     edi, eax
0x1800592fe  test    eax, eax
0x180059300  jns     short loc_18005931B
0x180059302  mov     rcx, [rsp+278h]; this
0x18005930a  mov     r9d, eax; char *
0x18005930d  mov     edx, 8Bh; void *
0x180059312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059317  mov     eax, edi
0x180059319  jmp     short loc_180059369
0x18005931b  lea     r8, asc_1800B6080; "h"
0x180059322  shr     rbx, 1Fh
0x180059326  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18005932b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180059330  test    ebx, ebx
0x180059332  lea     rcx, [rbp+8]
0x180059336  lea     r9, [rsp+278h+var_238]
0x18005933b  mov     edx, ebx
0x18005933d  cmovnz  esi, ebx
0x180059340  mov     r8d, esi
0x180059343  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180059348  mov     ebx, eax
0x18005934a  test    eax, eax
0x18005934c  jns     short loc_180059367
0x18005934e  mov     rcx, [rsp+278h]; this
0x180059356  mov     r9d, eax; char *
0x180059359  mov     edx, 90h; void *
0x18005935e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059363  mov     eax, ebx
0x180059365  jmp     short loc_180059369
0x180059367  xor     eax, eax
0x180059369  mov     rcx, [rsp+278h+var_28]
0x180059371  xor     rcx, rsp; StackCookie
0x180059374  call    __security_check_cookie
0x180059379  mov     rbx, [rsp+278h+arg_10]
0x180059381  add     rsp, 260h
0x180059388  pop     rdi
0x180059389  pop     rsi
0x18005938a  pop     rbp
0x18005938b  retn
```
