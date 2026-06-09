# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800095d4`
- end: `0x1800096f6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a810`
- `0x1800376d0`

## callees

- `0x180006f60`
- `0x1800095d4`
- `0x18000b014`
- `0x18000b550`
- `0x18000b68c`
- `0x18000bda0`
- `0x18000bf18`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  size_t v14; // [rsp+20h] [rbp-268h]
  int v15; // [rsp+20h] [rbp-268h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v14);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, pszDest);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(pszDest, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            pszDest);
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
        v15);
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
      v15);
    return v9;
  }
}

```

## disassembly

```asm
0x1800095d4  push    rbx
0x1800095d6  push    rbp
0x1800095d7  push    rsi
0x1800095d8  push    rdi
0x1800095d9  push    r14
0x1800095db  sub     rsp, 260h
0x1800095e2  mov     rax, cs:__security_cookie
0x1800095e9  xor     rax, rsp
0x1800095ec  mov     [rsp+288h+var_38], rax
0x1800095f4  mov     rax, 0C000000000000000h
0x1800095fe  mov     rbx, r9
0x180009601  mov     rbp, rcx
0x180009604  test    rax, r9
0x180009607  jz      short loc_18000960F
0x180009609  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000960f  mov     r9, rdx; pszSrc
0x180009612  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180009617  mov     r14d, 104h
0x18000961d  mov     edx, r14d; cchDest
0x180009620  call    StringCopyWorkerW
0x180009625  lea     r8, aP0; "_p0"
0x18000962c  mov     edx, r14d; unsigned __int64
0x18000962f  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x180009634  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009639  mov     edx, ebx
0x18000963b  lea     r9, [rsp+288h+pszDest]
0x180009640  and     edx, 7FFFFFFFh
0x180009646  mov     esi, 1
0x18000964b  mov     r8d, esi
0x18000964e  mov     rcx, rbp
0x180009651  cmova   r8d, edx
0x180009655  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000965a  mov     edi, eax
0x18000965c  test    eax, eax
0x18000965e  jns     short loc_18000967F
0x180009660  mov     rcx, [rsp+288h]; this
0x180009668  lea     r8, aWil; "wil"
0x18000966f  mov     r9d, eax; char *
0x180009672  lea     edx, [r14-79h]; void *
0x180009676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000967b  mov     eax, edi
0x18000967d  jmp     short loc_1800096D7
0x18000967f  lea     r8, asc_180042618; "h"
0x180009686  shr     rbx, 1Fh
0x18000968a  mov     rdx, r14; unsigned __int64
0x18000968d  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x180009692  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009697  test    ebx, ebx
0x180009699  lea     rcx, [rbp+8]
0x18000969d  lea     r9, [rsp+288h+pszDest]
0x1800096a2  mov     edx, ebx
0x1800096a4  cmovnz  esi, ebx
0x1800096a7  mov     r8d, esi
0x1800096aa  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800096af  mov     ebx, eax
0x1800096b1  test    eax, eax
0x1800096b3  jns     short loc_1800096D5
0x1800096b5  mov     rcx, [rsp+288h]; this
0x1800096bd  lea     r8, aWil; "wil"
0x1800096c4  mov     r9d, eax; char *
0x1800096c7  mov     edx, 90h; void *
0x1800096cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096d1  mov     eax, ebx
0x1800096d3  jmp     short loc_1800096D7
0x1800096d5  xor     eax, eax
0x1800096d7  mov     rcx, [rsp+288h+var_38]
0x1800096df  xor     rcx, rsp; StackCookie
0x1800096e2  call    __security_check_cookie
0x1800096e7  add     rsp, 260h
0x1800096ee  pop     r14
0x1800096f0  pop     rdi
0x1800096f1  pop     rsi
0x1800096f2  pop     rbp
0x1800096f3  pop     rbx
0x1800096f4  retn
```
