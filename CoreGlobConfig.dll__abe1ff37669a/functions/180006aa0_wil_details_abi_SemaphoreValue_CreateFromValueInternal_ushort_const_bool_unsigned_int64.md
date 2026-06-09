# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006aa0`
- end: `0x180006bc1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c68`
- `0x180016360`

## callees

- `0x180002380`
- `0x180006aa0`
- `0x180008294`
- `0x1800087e4`
- `0x180008870`
- `0x180008ec4`
- `0x180008f94`

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
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
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
0x180006aa0  push    rbx
0x180006aa2  push    rbp
0x180006aa3  push    rsi
0x180006aa4  push    rdi
0x180006aa5  push    r14
0x180006aa7  sub     rsp, 260h
0x180006aae  mov     rax, cs:__security_cookie
0x180006ab5  xor     rax, rsp
0x180006ab8  mov     [rsp+288h+var_38], rax
0x180006ac0  mov     rax, 0C000000000000000h
0x180006aca  mov     rbx, r9
0x180006acd  mov     rbp, rcx
0x180006ad0  test    rax, r9
0x180006ad3  jz      short loc_180006ADB
0x180006ad5  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180006adb  mov     r8, rdx; unsigned __int16 *
0x180006ade  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180006ae3  mov     r14d, 104h
0x180006ae9  mov     edx, r14d; unsigned __int64
0x180006aec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006af1  lea     r8, aP0; "_p0"
0x180006af8  mov     edx, r14d; unsigned __int64
0x180006afb  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180006b00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006b05  mov     edx, ebx
0x180006b07  lea     r9, [rsp+288h+var_248]
0x180006b0c  and     edx, 7FFFFFFFh
0x180006b12  mov     esi, 1
0x180006b17  mov     r8d, esi
0x180006b1a  mov     rcx, rbp
0x180006b1d  cmova   r8d, edx
0x180006b21  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006b26  mov     edi, eax
0x180006b28  test    eax, eax
0x180006b2a  jns     short loc_180006B4B
0x180006b2c  mov     rcx, [rsp+288h]; this
0x180006b34  lea     r8, aWil; "wil"
0x180006b3b  mov     r9d, eax; char *
0x180006b3e  lea     edx, [r14-79h]; void *
0x180006b42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b47  mov     eax, edi
0x180006b49  jmp     short loc_180006BA3
0x180006b4b  lea     r8, asc_1800282C8; "h"
0x180006b52  shr     rbx, 1Fh
0x180006b56  mov     rdx, r14; unsigned __int64
0x180006b59  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180006b5e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006b63  test    ebx, ebx
0x180006b65  lea     rcx, [rbp+8]
0x180006b69  lea     r9, [rsp+288h+var_248]
0x180006b6e  mov     edx, ebx
0x180006b70  cmovnz  esi, ebx
0x180006b73  mov     r8d, esi
0x180006b76  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006b7b  mov     ebx, eax
0x180006b7d  test    eax, eax
0x180006b7f  jns     short loc_180006BA1
0x180006b81  mov     rcx, [rsp+288h]; this
0x180006b89  lea     r8, aWil; "wil"
0x180006b90  mov     r9d, eax; char *
0x180006b93  mov     edx, 90h; void *
0x180006b98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b9d  mov     eax, ebx
0x180006b9f  jmp     short loc_180006BA3
0x180006ba1  xor     eax, eax
0x180006ba3  mov     rcx, [rsp+288h+var_38]
0x180006bab  xor     rcx, rsp; StackCookie
0x180006bae  call    __security_check_cookie
0x180006bb3  add     rsp, 260h
0x180006bba  pop     r14
0x180006bbc  pop     rdi
0x180006bbd  pop     rsi
0x180006bbe  pop     rbp
0x180006bbf  pop     rbx
0x180006bc0  retn
```
