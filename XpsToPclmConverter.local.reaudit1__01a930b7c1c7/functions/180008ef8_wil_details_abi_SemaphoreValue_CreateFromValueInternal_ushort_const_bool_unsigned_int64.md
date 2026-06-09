# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008ef8`
- end: `0x180009008`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a54c`
- `0x18000a69c`

## callees

- `0x1800015f0`
- `0x180008ef8`
- `0x18000b8bc`
- `0x18000bf80`
- `0x18000c0a8`
- `0x18000cad4`
- `0x18000cc88`

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
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
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
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x180008ef8  mov     [rsp+arg_10], rbx
0x180008efd  push    rbp
0x180008efe  push    rsi
0x180008eff  push    rdi
0x180008f00  sub     rsp, 260h
0x180008f07  mov     rax, cs:__security_cookie
0x180008f0e  xor     rax, rsp
0x180008f11  mov     [rsp+278h+var_28], rax
0x180008f19  mov     rax, 0C000000000000000h
0x180008f23  mov     rbx, r9
0x180008f26  mov     rbp, rcx
0x180008f29  test    rax, r9
0x180008f2c  jz      short loc_180008F34
0x180008f2e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008f34  mov     r9, rdx; pszSrc
0x180008f37  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180008f3c  mov     edx, 104h; cchDest
0x180008f41  call    StringCopyWorkerW
0x180008f46  lea     r8, aP0; "_p0"
0x180008f4d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180008f52  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008f57  mov     edx, ebx
0x180008f59  lea     r9, [rsp+278h+pszDest]
0x180008f5e  and     edx, 7FFFFFFFh
0x180008f64  mov     esi, 1
0x180008f69  mov     r8d, esi
0x180008f6c  mov     rcx, rbp
0x180008f6f  cmova   r8d, edx
0x180008f73  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008f78  mov     edi, eax
0x180008f7a  test    eax, eax
0x180008f7c  jns     short loc_180008F97
0x180008f7e  mov     rcx, [rsp+278h]; this
0x180008f86  mov     r9d, eax; char *
0x180008f89  mov     edx, 8Bh; void *
0x180008f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f93  mov     eax, edi
0x180008f95  jmp     short loc_180008FE5
0x180008f97  lea     r8, asc_1800251B0; "h"
0x180008f9e  shr     rbx, 1Fh
0x180008fa2  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180008fa7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008fac  test    ebx, ebx
0x180008fae  lea     rcx, [rbp+8]
0x180008fb2  lea     r9, [rsp+278h+pszDest]
0x180008fb7  mov     edx, ebx
0x180008fb9  cmovnz  esi, ebx
0x180008fbc  mov     r8d, esi
0x180008fbf  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180008fc4  mov     ebx, eax
0x180008fc6  test    eax, eax
0x180008fc8  jns     short loc_180008FE3
0x180008fca  mov     rcx, [rsp+278h]; this
0x180008fd2  mov     r9d, eax; char *
0x180008fd5  mov     edx, 90h; void *
0x180008fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fdf  mov     eax, ebx
0x180008fe1  jmp     short loc_180008FE5
0x180008fe3  xor     eax, eax
0x180008fe5  mov     rcx, [rsp+278h+var_28]
0x180008fed  xor     rcx, rsp; StackCookie
0x180008ff0  call    __security_check_cookie
0x180008ff5  mov     rbx, [rsp+278h+arg_10]
0x180008ffd  add     rsp, 260h
0x180009004  pop     rdi
0x180009005  pop     rsi
0x180009006  pop     rbp
0x180009007  retn
```
