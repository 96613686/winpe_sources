# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000361c`
- end: `0x14000373a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400046d4`

## callees

- `0x14000361c`
- `0x140004d74`
- `0x14000524c`
- `0x14000532c`
- `0x140005890`
- `0x140005c30`
- `0x1400094d0`

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
0x14000361c  mov     [rsp+arg_10], rbx
0x140003621  push    rbp
0x140003622  push    rsi
0x140003623  push    rdi
0x140003624  sub     rsp, 260h
0x14000362b  mov     rax, cs:__security_cookie
0x140003632  xor     rax, rsp
0x140003635  mov     [rsp+278h+var_28], rax
0x14000363d  mov     rax, 0C000000000000000h
0x140003647  mov     rbx, r9
0x14000364a  mov     rbp, rcx
0x14000364d  test    rax, r9
0x140003650  jz      short loc_140003658
0x140003652  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003658  mov     r9, rdx; pszSrc
0x14000365b  lea     rcx, [rsp+278h+pszDest]; pszDest
0x140003660  mov     edx, 104h; cchDest
0x140003665  call    StringCopyWorkerW
0x14000366a  lea     r8, aP0; "_p0"
0x140003671  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140003676  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000367b  mov     edx, ebx
0x14000367d  lea     r9, [rsp+278h+pszDest]
0x140003682  and     edx, 7FFFFFFFh
0x140003688  mov     esi, 1
0x14000368d  mov     r8d, esi
0x140003690  mov     rcx, rbp
0x140003693  cmova   r8d, edx
0x140003697  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000369c  mov     edi, eax
0x14000369e  test    eax, eax
0x1400036a0  jns     short loc_1400036C2
0x1400036a2  mov     rcx, [rsp+278h]; this
0x1400036aa  lea     r8, aWil; "wil"
0x1400036b1  mov     r9d, eax; char *
0x1400036b4  mov     edx, 8Bh; void *
0x1400036b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400036be  mov     eax, edi
0x1400036c0  jmp     short loc_140003717
0x1400036c2  lea     r8, asc_14000D3F8; "h"
0x1400036c9  shr     rbx, 1Fh
0x1400036cd  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1400036d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400036d7  test    ebx, ebx
0x1400036d9  lea     rcx, [rbp+8]
0x1400036dd  lea     r9, [rsp+278h+pszDest]
0x1400036e2  mov     edx, ebx
0x1400036e4  cmovnz  esi, ebx
0x1400036e7  mov     r8d, esi
0x1400036ea  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400036ef  mov     ebx, eax
0x1400036f1  test    eax, eax
0x1400036f3  jns     short loc_140003715
0x1400036f5  mov     rcx, [rsp+278h]; this
0x1400036fd  lea     r8, aWil; "wil"
0x140003704  mov     r9d, eax; char *
0x140003707  mov     edx, 90h; void *
0x14000370c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003711  mov     eax, ebx
0x140003713  jmp     short loc_140003717
0x140003715  xor     eax, eax
0x140003717  mov     rcx, [rsp+278h+var_28]
0x14000371f  xor     rcx, rsp; StackCookie
0x140003722  call    __security_check_cookie
0x140003727  mov     rbx, [rsp+278h+arg_10]
0x14000372f  add     rsp, 260h
0x140003736  pop     rdi
0x140003737  pop     rsi
0x140003738  pop     rbp
0x140003739  retn
```
