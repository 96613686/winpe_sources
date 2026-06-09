# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a3ac`
- end: `0x18000a4bc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd94`
- `0x18000ceb8`

## callees

- `0x180001720`
- `0x180005a28`
- `0x180005b30`
- `0x18000a3ac`
- `0x18000f0cc`
- `0x180010e28`
- `0x180011048`

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
0x18000a3ac  mov     [rsp+arg_10], rbx
0x18000a3b1  push    rbp
0x18000a3b2  push    rsi
0x18000a3b3  push    rdi
0x18000a3b4  sub     rsp, 260h
0x18000a3bb  mov     rax, cs:__security_cookie
0x18000a3c2  xor     rax, rsp
0x18000a3c5  mov     [rsp+278h+var_28], rax
0x18000a3cd  mov     rax, 0C000000000000000h
0x18000a3d7  mov     rbx, r9
0x18000a3da  mov     rbp, rcx
0x18000a3dd  test    rax, r9
0x18000a3e0  jz      short loc_18000A3E8
0x18000a3e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a3e8  mov     r8, rdx; unsigned __int16 *
0x18000a3eb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000a3f0  mov     edx, 104h; unsigned __int64
0x18000a3f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a3fa  lea     r8, aP0; "_p0"
0x18000a401  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000a406  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a40b  mov     edx, ebx
0x18000a40d  lea     r9, [rsp+278h+var_238]
0x18000a412  and     edx, 7FFFFFFFh
0x18000a418  mov     esi, 1
0x18000a41d  mov     r8d, esi
0x18000a420  mov     rcx, rbp
0x18000a423  cmova   r8d, edx
0x18000a427  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a42c  mov     edi, eax
0x18000a42e  test    eax, eax
0x18000a430  jns     short loc_18000A44B
0x18000a432  mov     rcx, [rsp+278h]; this
0x18000a43a  mov     r9d, eax; char *
0x18000a43d  mov     edx, 8Bh; void *
0x18000a442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a447  mov     eax, edi
0x18000a449  jmp     short loc_18000A499
0x18000a44b  lea     r8, asc_180018DC8; "h"
0x18000a452  shr     rbx, 1Fh
0x18000a456  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000a45b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a460  test    ebx, ebx
0x18000a462  lea     rcx, [rbp+8]
0x18000a466  lea     r9, [rsp+278h+var_238]
0x18000a46b  mov     edx, ebx
0x18000a46d  cmovnz  esi, ebx
0x18000a470  mov     r8d, esi
0x18000a473  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000a478  mov     ebx, eax
0x18000a47a  test    eax, eax
0x18000a47c  jns     short loc_18000A497
0x18000a47e  mov     rcx, [rsp+278h]; this
0x18000a486  mov     r9d, eax; char *
0x18000a489  mov     edx, 90h; void *
0x18000a48e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a493  mov     eax, ebx
0x18000a495  jmp     short loc_18000A499
0x18000a497  xor     eax, eax
0x18000a499  mov     rcx, [rsp+278h+var_28]
0x18000a4a1  xor     rcx, rsp; StackCookie
0x18000a4a4  call    __security_check_cookie
0x18000a4a9  mov     rbx, [rsp+278h+arg_10]
0x18000a4b1  add     rsp, 260h
0x18000a4b8  pop     rdi
0x18000a4b9  pop     rsi
0x18000a4ba  pop     rbp
0x18000a4bb  retn
```
