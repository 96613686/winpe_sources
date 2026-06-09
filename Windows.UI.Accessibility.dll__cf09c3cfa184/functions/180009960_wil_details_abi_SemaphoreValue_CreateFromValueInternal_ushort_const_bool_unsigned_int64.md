# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180009960`
- end: `0x180009a7e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9f4`
- `0x18000ab58`

## callees

- `0x180003980`
- `0x180006e44`
- `0x180009960`
- `0x18000be1c`
- `0x18000c438`
- `0x18000c4b4`
- `0x18000d10c`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
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
0x180009960  mov     [rsp+arg_10], rbx
0x180009965  push    rbp
0x180009966  push    rsi
0x180009967  push    rdi
0x180009968  sub     rsp, 260h
0x18000996f  mov     rax, cs:__security_cookie
0x180009976  xor     rax, rsp
0x180009979  mov     [rsp+278h+var_28], rax
0x180009981  mov     rax, 0C000000000000000h
0x18000998b  mov     rbx, r9
0x18000998e  mov     rbp, rcx
0x180009991  test    rax, r9
0x180009994  jz      short loc_18000999C
0x180009996  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18000999c  mov     r9, rdx; pszSrc
0x18000999f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800099a4  mov     edx, 104h; cchDest
0x1800099a9  call    StringCopyWorkerW
0x1800099ae  lea     r8, aP0; "_p0"
0x1800099b5  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800099ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099bf  mov     edx, ebx
0x1800099c1  lea     r9, [rsp+278h+pszDest]
0x1800099c6  and     edx, 7FFFFFFFh
0x1800099cc  mov     esi, 1
0x1800099d1  mov     r8d, esi
0x1800099d4  mov     rcx, rbp
0x1800099d7  cmova   r8d, edx
0x1800099db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800099e0  mov     edi, eax
0x1800099e2  test    eax, eax
0x1800099e4  jns     short loc_180009A06
0x1800099e6  mov     rcx, [rsp+278h]; this
0x1800099ee  lea     r8, aWil; "wil"
0x1800099f5  mov     r9d, eax; char *
0x1800099f8  mov     edx, 8Bh; void *
0x1800099fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a02  mov     eax, edi
0x180009a04  jmp     short loc_180009A5B
0x180009a06  lea     r8, asc_180039B88; "h"
0x180009a0d  shr     rbx, 1Fh
0x180009a11  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180009a16  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a1b  test    ebx, ebx
0x180009a1d  lea     rcx, [rbp+8]
0x180009a21  lea     r9, [rsp+278h+pszDest]
0x180009a26  mov     edx, ebx
0x180009a28  cmovnz  esi, ebx
0x180009a2b  mov     r8d, esi
0x180009a2e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180009a33  mov     ebx, eax
0x180009a35  test    eax, eax
0x180009a37  jns     short loc_180009A59
0x180009a39  mov     rcx, [rsp+278h]; this
0x180009a41  lea     r8, aWil; "wil"
0x180009a48  mov     r9d, eax; char *
0x180009a4b  mov     edx, 90h; void *
0x180009a50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a55  mov     eax, ebx
0x180009a57  jmp     short loc_180009A5B
0x180009a59  xor     eax, eax
0x180009a5b  mov     rcx, [rsp+278h+var_28]
0x180009a63  xor     rcx, rsp; StackCookie
0x180009a66  call    __security_check_cookie
0x180009a6b  mov     rbx, [rsp+278h+arg_10]
0x180009a73  add     rsp, 260h
0x180009a7a  pop     rdi
0x180009a7b  pop     rsi
0x180009a7c  pop     rbp
0x180009a7d  retn
```
