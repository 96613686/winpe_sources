# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000542c`
- end: `0x18000554e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006538`
- `0x1800093e0`

## callees

- `0x180002ac8`
- `0x180002d38`
- `0x1800033d0`
- `0x18000542c`
- `0x180006c90`
- `0x180007558`
- `0x18000763c`

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
0x18000542c  mov     [rsp+arg_10], rbx
0x180005431  push    rbp
0x180005432  push    rsi
0x180005433  push    rdi
0x180005434  sub     rsp, 260h
0x18000543b  mov     rax, cs:__security_cookie
0x180005442  xor     rax, rsp
0x180005445  mov     [rsp+278h+var_28], rax
0x18000544d  mov     rax, 0C000000000000000h
0x180005457  mov     rbx, r9
0x18000545a  mov     rbp, rcx
0x18000545d  test    rax, r9
0x180005460  jnz     loc_180005548
0x180005466  mov     r8, rdx; unsigned __int16 *
0x180005469  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000546e  mov     edx, 104h; unsigned __int64
0x180005473  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005478  lea     r8, aP0; "_p0"
0x18000547f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180005484  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005489  mov     edx, ebx
0x18000548b  lea     r9, [rsp+278h+var_238]
0x180005490  and     edx, 7FFFFFFFh
0x180005496  mov     esi, 1
0x18000549b  mov     r8d, esi
0x18000549e  mov     rcx, rbp
0x1800054a1  cmova   r8d, edx
0x1800054a5  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800054aa  mov     edi, eax
0x1800054ac  test    eax, eax
0x1800054ae  jns     short loc_1800054D0
0x1800054b0  mov     rcx, [rsp+278h]; this
0x1800054b8  lea     r8, aWil; "wil"
0x1800054bf  mov     r9d, eax; char *
0x1800054c2  mov     edx, 8Bh; void *
0x1800054c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054cc  mov     eax, edi
0x1800054ce  jmp     short loc_180005525
0x1800054d0  lea     r8, asc_18001A928; "h"
0x1800054d7  shr     rbx, 1Fh
0x1800054db  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800054e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800054e5  test    ebx, ebx
0x1800054e7  lea     rcx, [rbp+8]
0x1800054eb  lea     r9, [rsp+278h+var_238]
0x1800054f0  mov     edx, ebx
0x1800054f2  cmovnz  esi, ebx
0x1800054f5  mov     r8d, esi
0x1800054f8  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800054fd  mov     ebx, eax
0x1800054ff  test    eax, eax
0x180005501  jns     short loc_180005523
0x180005503  mov     rcx, [rsp+278h]; this
0x18000550b  lea     r8, aWil; "wil"
0x180005512  mov     r9d, eax; char *
0x180005515  mov     edx, 90h; void *
0x18000551a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000551f  mov     eax, ebx
0x180005521  jmp     short loc_180005525
0x180005523  xor     eax, eax
0x180005525  mov     rcx, [rsp+278h+var_28]
0x18000552d  xor     rcx, rsp; StackCookie
0x180005530  call    __security_check_cookie
0x180005535  mov     rbx, [rsp+278h+arg_10]
0x18000553d  add     rsp, 260h
0x180005544  pop     rdi
0x180005545  pop     rsi
0x180005546  pop     rbp
0x180005547  retn
0x180005548  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
