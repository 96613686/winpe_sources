# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009280`
- end: `0x1800093a3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `291`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a60c`

## callees

- `0x180005210`
- `0x180006584`
- `0x180009280`
- `0x18000b364`
- `0x18000c664`
- `0x18000d1c8`
- `0x18000f0a0`

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
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-258h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, (unsigned __int64)a2, a2);
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
0x180009280  mov     [rsp+arg_10], rbx
0x180009285  push    rbp
0x180009286  push    rsi
0x180009287  push    rdi
0x180009288  sub     rsp, 260h
0x18000928f  mov     rax, cs:__security_cookie
0x180009296  xor     rax, rsp
0x180009299  mov     [rsp+278h+var_28], rax
0x1800092a1  mov     rax, 0C000000000000000h
0x1800092ab  mov     rbx, r9
0x1800092ae  mov     rbp, rcx
0x1800092b1  test    rax, r9
0x1800092b4  jz      short loc_1800092BC
0x1800092b6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800092bc  mov     r8, rdx; unsigned __int16 *
0x1800092bf  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800092c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800092c9  lea     r8, aP0; "_p0"
0x1800092d0  mov     edx, 104h; unsigned __int64
0x1800092d5  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800092da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800092df  mov     edx, ebx
0x1800092e1  lea     r9, [rsp+278h+var_238]
0x1800092e6  and     edx, 7FFFFFFFh
0x1800092ec  mov     esi, 1
0x1800092f1  mov     r8d, esi
0x1800092f4  mov     rcx, rbp
0x1800092f7  cmova   r8d, edx
0x1800092fb  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180009300  mov     edi, eax
0x180009302  test    eax, eax
0x180009304  jns     short loc_180009326
0x180009306  mov     rcx, [rsp+278h]; this
0x18000930e  lea     r8, aWil; "wil"
0x180009315  mov     r9d, eax; char *
0x180009318  mov     edx, 8Bh; void *
0x18000931d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009322  mov     eax, edi
0x180009324  jmp     short loc_180009380
0x180009326  lea     r8, asc_180013DC0; "h"
0x18000932d  shr     rbx, 1Fh
0x180009331  mov     edx, 104h; unsigned __int64
0x180009336  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000933b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009340  test    ebx, ebx
0x180009342  lea     rcx, [rbp+8]
0x180009346  lea     r9, [rsp+278h+var_238]
0x18000934b  mov     edx, ebx
0x18000934d  cmovnz  esi, ebx
0x180009350  mov     r8d, esi
0x180009353  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180009358  mov     ebx, eax
0x18000935a  test    eax, eax
0x18000935c  jns     short loc_18000937E
0x18000935e  mov     rcx, [rsp+278h]; this
0x180009366  lea     r8, aWil; "wil"
0x18000936d  mov     r9d, eax; char *
0x180009370  mov     edx, 90h; void *
0x180009375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000937a  mov     eax, ebx
0x18000937c  jmp     short loc_180009380
0x18000937e  xor     eax, eax
0x180009380  mov     rcx, [rsp+278h+var_28]
0x180009388  xor     rcx, rsp; StackCookie
0x18000938b  call    __security_check_cookie
0x180009390  mov     rbx, [rsp+278h+arg_10]
0x180009398  add     rsp, 260h
0x18000939f  pop     rdi
0x1800093a0  pop     rsi
0x1800093a1  pop     rbp
0x1800093a2  retn
```
