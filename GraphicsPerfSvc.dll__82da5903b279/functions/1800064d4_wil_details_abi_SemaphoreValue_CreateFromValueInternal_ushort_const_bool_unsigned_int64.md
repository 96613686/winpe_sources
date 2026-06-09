# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800064d4`
- end: `0x1800065f5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007cf0`
- `0x180007e54`

## callees

- `0x180003ab0`
- `0x1800064d4`
- `0x1800091bc`
- `0x18000987c`
- `0x1800099b4`
- `0x18000a720`
- `0x18000a8d8`

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
0x1800064d4  push    rbx
0x1800064d6  push    rbp
0x1800064d7  push    rsi
0x1800064d8  push    rdi
0x1800064d9  push    r14
0x1800064db  sub     rsp, 260h
0x1800064e2  mov     rax, cs:__security_cookie
0x1800064e9  xor     rax, rsp
0x1800064ec  mov     [rsp+288h+var_38], rax
0x1800064f4  mov     rax, 0C000000000000000h
0x1800064fe  mov     rbx, r9
0x180006501  mov     rbp, rcx
0x180006504  test    rax, r9
0x180006507  jz      short loc_18000650F
0x180006509  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000650f  mov     r9, rdx; pszSrc
0x180006512  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180006517  mov     r14d, 104h
0x18000651d  mov     edx, r14d; cchDest
0x180006520  call    StringCopyWorkerW
0x180006525  lea     r8, aP0; "_p0"
0x18000652c  mov     edx, r14d; unsigned __int64
0x18000652f  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x180006534  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006539  mov     edx, ebx
0x18000653b  lea     r9, [rsp+288h+pszDest]
0x180006540  and     edx, 7FFFFFFFh
0x180006546  mov     esi, 1
0x18000654b  mov     r8d, esi
0x18000654e  mov     rcx, rbp
0x180006551  cmova   r8d, edx
0x180006555  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000655a  mov     edi, eax
0x18000655c  test    eax, eax
0x18000655e  jns     short loc_18000657F
0x180006560  mov     rcx, [rsp+288h]; this
0x180006568  lea     r8, aWil; "wil"
0x18000656f  mov     r9d, eax; char *
0x180006572  lea     edx, [r14-79h]; void *
0x180006576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000657b  mov     eax, edi
0x18000657d  jmp     short loc_1800065D7
0x18000657f  lea     r8, asc_180033E60; "h"
0x180006586  shr     rbx, 1Fh
0x18000658a  mov     rdx, r14; unsigned __int64
0x18000658d  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x180006592  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006597  test    ebx, ebx
0x180006599  lea     rcx, [rbp+8]
0x18000659d  lea     r9, [rsp+288h+pszDest]
0x1800065a2  mov     edx, ebx
0x1800065a4  cmovnz  esi, ebx
0x1800065a7  mov     r8d, esi
0x1800065aa  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800065af  mov     ebx, eax
0x1800065b1  test    eax, eax
0x1800065b3  jns     short loc_1800065D5
0x1800065b5  mov     rcx, [rsp+288h]; this
0x1800065bd  lea     r8, aWil; "wil"
0x1800065c4  mov     r9d, eax; char *
0x1800065c7  mov     edx, 90h; void *
0x1800065cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065d1  mov     eax, ebx
0x1800065d3  jmp     short loc_1800065D7
0x1800065d5  xor     eax, eax
0x1800065d7  mov     rcx, [rsp+288h+var_38]
0x1800065df  xor     rcx, rsp; StackCookie
0x1800065e2  call    __security_check_cookie
0x1800065e7  add     rsp, 260h
0x1800065ee  pop     r14
0x1800065f0  pop     rdi
0x1800065f1  pop     rsi
0x1800065f2  pop     rbp
0x1800065f3  pop     rbx
0x1800065f4  retn
```
