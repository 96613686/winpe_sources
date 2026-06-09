# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cd68`
- end: `0x18000ce86`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014608`
- `0x180014738`

## callees

- `0x18000cd68`
- `0x1800166cc`
- `0x180016e54`
- `0x180016eb0`
- `0x180018020`
- `0x180018ac4`
- `0x18002cfa0`

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
0x18000cd68  mov     [rsp+arg_10], rbx
0x18000cd6d  push    rbp
0x18000cd6e  push    rsi
0x18000cd6f  push    rdi
0x18000cd70  sub     rsp, 260h
0x18000cd77  mov     rax, cs:__security_cookie
0x18000cd7e  xor     rax, rsp
0x18000cd81  mov     [rsp+278h+var_28], rax
0x18000cd89  mov     rax, 0C000000000000000h
0x18000cd93  mov     rbx, r9
0x18000cd96  mov     rbp, rcx
0x18000cd99  test    rax, r9
0x18000cd9c  jz      short loc_18000CDA4
0x18000cd9e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cda4  mov     r8, rdx; unsigned __int16 *
0x18000cda7  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000cdac  mov     edx, 104h; unsigned __int64
0x18000cdb1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cdb6  lea     r8, aP0; "_p0"
0x18000cdbd  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000cdc2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cdc7  mov     edx, ebx
0x18000cdc9  lea     r9, [rsp+278h+var_238]
0x18000cdce  and     edx, 7FFFFFFFh
0x18000cdd4  mov     esi, 1
0x18000cdd9  mov     r8d, esi
0x18000cddc  mov     rcx, rbp
0x18000cddf  cmova   r8d, edx
0x18000cde3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cde8  mov     edi, eax
0x18000cdea  test    eax, eax
0x18000cdec  jns     short loc_18000CE0E
0x18000cdee  mov     rcx, [rsp+278h]; this
0x18000cdf6  lea     r8, aWil; "wil"
0x18000cdfd  mov     r9d, eax; char *
0x18000ce00  mov     edx, 8Bh; void *
0x18000ce05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce0a  mov     eax, edi
0x18000ce0c  jmp     short loc_18000CE63
0x18000ce0e  lea     r8, asc_180034620; "h"
0x18000ce15  shr     rbx, 1Fh
0x18000ce19  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000ce1e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ce23  test    ebx, ebx
0x18000ce25  lea     rcx, [rbp+8]
0x18000ce29  lea     r9, [rsp+278h+var_238]
0x18000ce2e  mov     edx, ebx
0x18000ce30  cmovnz  esi, ebx
0x18000ce33  mov     r8d, esi
0x18000ce36  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ce3b  mov     ebx, eax
0x18000ce3d  test    eax, eax
0x18000ce3f  jns     short loc_18000CE61
0x18000ce41  mov     rcx, [rsp+278h]; this
0x18000ce49  lea     r8, aWil; "wil"
0x18000ce50  mov     r9d, eax; char *
0x18000ce53  mov     edx, 90h; void *
0x18000ce58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce5d  mov     eax, ebx
0x18000ce5f  jmp     short loc_18000CE63
0x18000ce61  xor     eax, eax
0x18000ce63  mov     rcx, [rsp+278h+var_28]
0x18000ce6b  xor     rcx, rsp; StackCookie
0x18000ce6e  call    __security_check_cookie
0x18000ce73  mov     rbx, [rsp+278h+arg_10]
0x18000ce7b  add     rsp, 260h
0x18000ce82  pop     rdi
0x18000ce83  pop     rsi
0x18000ce84  pop     rbp
0x18000ce85  retn
```
