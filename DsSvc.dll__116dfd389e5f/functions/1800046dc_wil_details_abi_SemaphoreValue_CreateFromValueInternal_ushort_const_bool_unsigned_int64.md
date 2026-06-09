# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800046dc`
- end: `0x1800047ec`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800058fc`
- `0x180008dbc`

## callees

- `0x1800046dc`
- `0x18000604c`
- `0x180006528`
- `0x1800065a4`
- `0x180006ba4`
- `0x180006f20`
- `0x18001b340`

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
0x1800046dc  mov     [rsp+arg_10], rbx
0x1800046e1  push    rbp
0x1800046e2  push    rsi
0x1800046e3  push    rdi
0x1800046e4  sub     rsp, 260h
0x1800046eb  mov     rax, cs:__security_cookie
0x1800046f2  xor     rax, rsp
0x1800046f5  mov     [rsp+278h+var_28], rax
0x1800046fd  mov     rax, 0C000000000000000h
0x180004707  mov     rbx, r9
0x18000470a  mov     rbp, rcx
0x18000470d  test    rax, r9
0x180004710  jz      short loc_180004718
0x180004712  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004718  mov     r8, rdx; unsigned __int16 *
0x18000471b  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180004720  mov     edx, 104h; unsigned __int64
0x180004725  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000472a  lea     r8, aP0; "_p0"
0x180004731  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180004736  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000473b  mov     edx, ebx
0x18000473d  lea     r9, [rsp+278h+var_238]
0x180004742  and     edx, 7FFFFFFFh
0x180004748  mov     esi, 1
0x18000474d  mov     r8d, esi
0x180004750  mov     rcx, rbp
0x180004753  cmova   r8d, edx
0x180004757  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000475c  mov     edi, eax
0x18000475e  test    eax, eax
0x180004760  jns     short loc_18000477B
0x180004762  mov     rcx, [rsp+278h]; this
0x18000476a  mov     r9d, eax; char *
0x18000476d  mov     edx, 8Bh; void *
0x180004772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004777  mov     eax, edi
0x180004779  jmp     short loc_1800047C9
0x18000477b  lea     r8, asc_18001ECC8; "h"
0x180004782  shr     rbx, 1Fh
0x180004786  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000478b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004790  test    ebx, ebx
0x180004792  lea     rcx, [rbp+8]
0x180004796  lea     r9, [rsp+278h+var_238]
0x18000479b  mov     edx, ebx
0x18000479d  cmovnz  esi, ebx
0x1800047a0  mov     r8d, esi
0x1800047a3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800047a8  mov     ebx, eax
0x1800047aa  test    eax, eax
0x1800047ac  jns     short loc_1800047C7
0x1800047ae  mov     rcx, [rsp+278h]; this
0x1800047b6  mov     r9d, eax; char *
0x1800047b9  mov     edx, 90h; void *
0x1800047be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047c3  mov     eax, ebx
0x1800047c5  jmp     short loc_1800047C9
0x1800047c7  xor     eax, eax
0x1800047c9  mov     rcx, [rsp+278h+var_28]
0x1800047d1  xor     rcx, rsp; StackCookie
0x1800047d4  call    __security_check_cookie
0x1800047d9  mov     rbx, [rsp+278h+arg_10]
0x1800047e1  add     rsp, 260h
0x1800047e8  pop     rdi
0x1800047e9  pop     rsi
0x1800047ea  pop     rbp
0x1800047eb  retn
```
