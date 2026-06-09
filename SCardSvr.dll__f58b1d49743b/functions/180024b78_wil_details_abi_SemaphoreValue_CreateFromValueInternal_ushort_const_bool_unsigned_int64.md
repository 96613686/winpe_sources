# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180024b78`
- end: `0x180024c96`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bbb4`
- `0x18001bd18`

## callees

- `0x1800150dc`
- `0x18001be80`
- `0x180024b78`
- `0x1800276bc`
- `0x180028308`
- `0x18002842c`
- `0x1800326d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180024b78  mov     [rsp+arg_10], rbx
0x180024b7d  push    rbp
0x180024b7e  push    rsi
0x180024b7f  push    rdi
0x180024b80  sub     rsp, 260h
0x180024b87  mov     rax, cs:__security_cookie
0x180024b8e  xor     rax, rsp
0x180024b91  mov     [rsp+278h+var_28], rax
0x180024b99  mov     rax, 0C000000000000000h
0x180024ba3  mov     rbx, r9
0x180024ba6  mov     rbp, rcx
0x180024ba9  test    rax, r9
0x180024bac  jz      short loc_180024BB4
0x180024bae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180024bb4  mov     r8, rdx; unsigned __int16 *
0x180024bb7  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180024bbc  mov     edx, 104h; unsigned __int64
0x180024bc1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024bc6  lea     r8, aP0; "_p0"
0x180024bcd  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180024bd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024bd7  mov     edx, ebx
0x180024bd9  lea     r9, [rsp+278h+var_238]
0x180024bde  and     edx, 7FFFFFFFh
0x180024be4  mov     esi, 1
0x180024be9  mov     r8d, esi
0x180024bec  mov     rcx, rbp
0x180024bef  cmova   r8d, edx
0x180024bf3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024bf8  mov     edi, eax
0x180024bfa  test    eax, eax
0x180024bfc  jns     short loc_180024C1E
0x180024bfe  mov     rcx, [rsp+278h]; this
0x180024c06  lea     r8, aWil; "wil"
0x180024c0d  mov     r9d, eax; char *
0x180024c10  mov     edx, 8Bh; void *
0x180024c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c1a  mov     eax, edi
0x180024c1c  jmp     short loc_180024C73
0x180024c1e  lea     r8, asc_180040478; "h"
0x180024c25  shr     rbx, 1Fh
0x180024c29  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180024c2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024c33  test    ebx, ebx
0x180024c35  lea     rcx, [rbp+8]
0x180024c39  lea     r9, [rsp+278h+var_238]
0x180024c3e  mov     edx, ebx
0x180024c40  cmovnz  esi, ebx
0x180024c43  mov     r8d, esi
0x180024c46  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024c4b  mov     ebx, eax
0x180024c4d  test    eax, eax
0x180024c4f  jns     short loc_180024C71
0x180024c51  mov     rcx, [rsp+278h]; this
0x180024c59  lea     r8, aWil; "wil"
0x180024c60  mov     r9d, eax; char *
0x180024c63  mov     edx, 90h; void *
0x180024c68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c6d  mov     eax, ebx
0x180024c6f  jmp     short loc_180024C73
0x180024c71  xor     eax, eax
0x180024c73  mov     rcx, [rsp+278h+var_28]
0x180024c7b  xor     rcx, rsp; StackCookie
0x180024c7e  call    __security_check_cookie
0x180024c83  mov     rbx, [rsp+278h+arg_10]
0x180024c8b  add     rsp, 260h
0x180024c92  pop     rdi
0x180024c93  pop     rsi
0x180024c94  pop     rbp
0x180024c95  retn
```
