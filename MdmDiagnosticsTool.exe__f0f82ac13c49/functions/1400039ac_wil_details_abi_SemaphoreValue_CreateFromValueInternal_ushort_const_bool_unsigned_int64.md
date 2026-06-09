# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400039ac`
- end: `0x140003aca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005648`

## callees

- `0x1400039ac`
- `0x140006244`
- `0x14000673c`
- `0x14000681c`
- `0x140006f90`
- `0x1400079bc`
- `0x1400096d0`

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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
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
0x1400039ac  mov     [rsp+arg_10], rbx
0x1400039b1  push    rbp
0x1400039b2  push    rsi
0x1400039b3  push    rdi
0x1400039b4  sub     rsp, 260h
0x1400039bb  mov     rax, cs:__security_cookie
0x1400039c2  xor     rax, rsp
0x1400039c5  mov     [rsp+278h+var_28], rax
0x1400039cd  mov     rax, 0C000000000000000h
0x1400039d7  mov     rbx, r9
0x1400039da  mov     rbp, rcx
0x1400039dd  test    rax, r9
0x1400039e0  jz      short loc_1400039E8
0x1400039e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400039e8  mov     r9, rdx; pszSrc
0x1400039eb  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1400039f0  mov     edx, 104h; cchDest
0x1400039f5  call    StringCopyWorkerW
0x1400039fa  lea     r8, aP0; "_p0"
0x140003a01  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140003a06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003a0b  mov     edx, ebx
0x140003a0d  lea     r9, [rsp+278h+pszDest]
0x140003a12  and     edx, 7FFFFFFFh
0x140003a18  mov     esi, 1
0x140003a1d  mov     r8d, esi
0x140003a20  mov     rcx, rbp
0x140003a23  cmova   r8d, edx
0x140003a27  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003a2c  mov     edi, eax
0x140003a2e  test    eax, eax
0x140003a30  jns     short loc_140003A52
0x140003a32  mov     rcx, [rsp+278h]; this
0x140003a3a  lea     r8, aWil; "wil"
0x140003a41  mov     r9d, eax; char *
0x140003a44  mov     edx, 8Bh; void *
0x140003a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a4e  mov     eax, edi
0x140003a50  jmp     short loc_140003AA7
0x140003a52  lea     r8, asc_14000CEF0; "h"
0x140003a59  shr     rbx, 1Fh
0x140003a5d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140003a62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003a67  test    ebx, ebx
0x140003a69  lea     rcx, [rbp+8]
0x140003a6d  lea     r9, [rsp+278h+pszDest]
0x140003a72  mov     edx, ebx
0x140003a74  cmovnz  esi, ebx
0x140003a77  mov     r8d, esi
0x140003a7a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003a7f  mov     ebx, eax
0x140003a81  test    eax, eax
0x140003a83  jns     short loc_140003AA5
0x140003a85  mov     rcx, [rsp+278h]; this
0x140003a8d  lea     r8, aWil; "wil"
0x140003a94  mov     r9d, eax; char *
0x140003a97  mov     edx, 90h; void *
0x140003a9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003aa1  mov     eax, ebx
0x140003aa3  jmp     short loc_140003AA7
0x140003aa5  xor     eax, eax
0x140003aa7  mov     rcx, [rsp+278h+var_28]
0x140003aaf  xor     rcx, rsp; StackCookie
0x140003ab2  call    __security_check_cookie
0x140003ab7  mov     rbx, [rsp+278h+arg_10]
0x140003abf  add     rsp, 260h
0x140003ac6  pop     rdi
0x140003ac7  pop     rsi
0x140003ac8  pop     rbp
0x140003ac9  retn
```
