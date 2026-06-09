# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180009848`
- end: `0x180009966`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a680`

## callees

- `0x180009848`
- `0x18000ab5c`
- `0x18000adec`
- `0x18000aee0`
- `0x18000b3c4`
- `0x18000b744`
- `0x1800119f0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
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
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x180009848  mov     [rsp+arg_10], rbx
0x18000984d  push    rbp
0x18000984e  push    rsi
0x18000984f  push    rdi
0x180009850  sub     rsp, 260h
0x180009857  mov     rax, cs:__security_cookie
0x18000985e  xor     rax, rsp
0x180009861  mov     [rsp+278h+var_28], rax
0x180009869  mov     rax, 0C000000000000000h
0x180009873  mov     rbx, r9
0x180009876  mov     rbp, rcx
0x180009879  test    rax, r9
0x18000987c  jz      short loc_180009884
0x18000987e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009884  mov     r9, rdx; pszSrc
0x180009887  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000988c  mov     edx, 104h; cchDest
0x180009891  call    StringCopyWorkerW
0x180009896  lea     r8, aP0; "_p0"
0x18000989d  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x1800098a2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800098a7  mov     edx, ebx
0x1800098a9  lea     r9, [rsp+278h+pszDest]
0x1800098ae  and     edx, 7FFFFFFFh
0x1800098b4  mov     esi, 1
0x1800098b9  mov     r8d, esi
0x1800098bc  mov     rcx, rbp
0x1800098bf  cmova   r8d, edx
0x1800098c3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800098c8  mov     edi, eax
0x1800098ca  test    eax, eax
0x1800098cc  jns     short loc_1800098EE
0x1800098ce  mov     rcx, [rsp+278h]; this
0x1800098d6  lea     r8, aWil; "wil"
0x1800098dd  mov     r9d, eax; char *
0x1800098e0  mov     edx, 8Bh; void *
0x1800098e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098ea  mov     eax, edi
0x1800098ec  jmp     short loc_180009943
0x1800098ee  lea     r8, asc_18001E1F0; "h"
0x1800098f5  shr     rbx, 1Fh
0x1800098f9  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x1800098fe  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009903  test    ebx, ebx
0x180009905  lea     rcx, [rbp+8]
0x180009909  lea     r9, [rsp+278h+pszDest]
0x18000990e  mov     edx, ebx
0x180009910  cmovnz  esi, ebx
0x180009913  mov     r8d, esi
0x180009916  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000991b  mov     ebx, eax
0x18000991d  test    eax, eax
0x18000991f  jns     short loc_180009941
0x180009921  mov     rcx, [rsp+278h]; this
0x180009929  lea     r8, aWil; "wil"
0x180009930  mov     r9d, eax; char *
0x180009933  mov     edx, 90h; void *
0x180009938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000993d  mov     eax, ebx
0x18000993f  jmp     short loc_180009943
0x180009941  xor     eax, eax
0x180009943  mov     rcx, [rsp+278h+var_28]
0x18000994b  xor     rcx, rsp; StackCookie
0x18000994e  call    __security_check_cookie
0x180009953  mov     rbx, [rsp+278h+arg_10]
0x18000995b  add     rsp, 260h
0x180009962  pop     rdi
0x180009963  pop     rsi
0x180009964  pop     rbp
0x180009965  retn
```
