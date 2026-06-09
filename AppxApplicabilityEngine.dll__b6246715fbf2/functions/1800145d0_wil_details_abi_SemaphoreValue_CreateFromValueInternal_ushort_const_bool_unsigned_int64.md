# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800145d0`
- end: `0x1800146ee`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150cc`
- `0x18001ca9c`

## callees

- `0x18000a378`
- `0x1800145d0`
- `0x18001577c`
- `0x180015cbc`
- `0x180016098`
- `0x180016164`
- `0x1800227c0`

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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
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
        v16);
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
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x1800145d0  mov     [rsp+arg_10], rbx
0x1800145d5  push    rbp
0x1800145d6  push    rsi
0x1800145d7  push    rdi
0x1800145d8  sub     rsp, 260h
0x1800145df  mov     rax, cs:__security_cookie
0x1800145e6  xor     rax, rsp
0x1800145e9  mov     [rsp+278h+var_28], rax
0x1800145f1  mov     rax, 0C000000000000000h
0x1800145fb  mov     rbx, r9
0x1800145fe  mov     rbp, rcx
0x180014601  test    rax, r9
0x180014604  jz      short loc_18001460C
0x180014606  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001460c  mov     r8, rdx; unsigned __int16 *
0x18001460f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180014614  mov     edx, 104h; unsigned __int64
0x180014619  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001461e  lea     r8, aP0; "_p0"
0x180014625  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18001462a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001462f  mov     edx, ebx
0x180014631  lea     r9, [rsp+278h+var_238]
0x180014636  and     edx, 7FFFFFFFh
0x18001463c  mov     esi, 1
0x180014641  mov     r8d, esi
0x180014644  mov     rcx, rbp
0x180014647  cmova   r8d, edx
0x18001464b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180014650  mov     edi, eax
0x180014652  test    eax, eax
0x180014654  jns     short loc_180014676
0x180014656  mov     rcx, [rsp+278h]; this
0x18001465e  lea     r8, aWil; "wil"
0x180014665  mov     r9d, eax; char *
0x180014668  mov     edx, 8Bh; void *
0x18001466d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014672  mov     eax, edi
0x180014674  jmp     short loc_1800146CB
0x180014676  lea     r8, asc_18002EC00; "h"
0x18001467d  shr     rbx, 1Fh
0x180014681  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180014686  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001468b  test    ebx, ebx
0x18001468d  lea     rcx, [rbp+8]
0x180014691  lea     r9, [rsp+278h+var_238]
0x180014696  mov     edx, ebx
0x180014698  cmovnz  esi, ebx
0x18001469b  mov     r8d, esi
0x18001469e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800146a3  mov     ebx, eax
0x1800146a5  test    eax, eax
0x1800146a7  jns     short loc_1800146C9
0x1800146a9  mov     rcx, [rsp+278h]; this
0x1800146b1  lea     r8, aWil; "wil"
0x1800146b8  mov     r9d, eax; char *
0x1800146bb  mov     edx, 90h; void *
0x1800146c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146c5  mov     eax, ebx
0x1800146c7  jmp     short loc_1800146CB
0x1800146c9  xor     eax, eax
0x1800146cb  mov     rcx, [rsp+278h+var_28]
0x1800146d3  xor     rcx, rsp; StackCookie
0x1800146d6  call    __security_check_cookie
0x1800146db  mov     rbx, [rsp+278h+arg_10]
0x1800146e3  add     rsp, 260h
0x1800146ea  pop     rdi
0x1800146eb  pop     rsi
0x1800146ec  pop     rbp
0x1800146ed  retn
```
