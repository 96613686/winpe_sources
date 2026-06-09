# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000f9a0`
- end: `0x18000fabe`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010140`
- `0x180013abc`

## callees

- `0x18000bbc0`
- `0x18000be38`
- `0x18000d2a0`
- `0x18000f9a0`
- `0x180010468`
- `0x180010728`
- `0x1800107a8`

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
0x18000f9a0  mov     [rsp+arg_10], rbx
0x18000f9a5  push    rbp
0x18000f9a6  push    rsi
0x18000f9a7  push    rdi
0x18000f9a8  sub     rsp, 260h
0x18000f9af  mov     rax, cs:__security_cookie
0x18000f9b6  xor     rax, rsp
0x18000f9b9  mov     [rsp+278h+var_28], rax
0x18000f9c1  mov     rax, 0C000000000000000h
0x18000f9cb  mov     rbx, r9
0x18000f9ce  mov     rbp, rcx
0x18000f9d1  test    rax, r9
0x18000f9d4  jz      short loc_18000F9DC
0x18000f9d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f9dc  mov     r9, rdx; pszSrc
0x18000f9df  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000f9e4  mov     edx, 104h; cchDest
0x18000f9e9  call    StringCopyWorkerW
0x18000f9ee  lea     r8, aP0; "_p0"
0x18000f9f5  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x18000f9fa  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000f9ff  mov     edx, ebx
0x18000fa01  lea     r9, [rsp+278h+pszDest]
0x18000fa06  and     edx, 7FFFFFFFh
0x18000fa0c  mov     esi, 1
0x18000fa11  mov     r8d, esi
0x18000fa14  mov     rcx, rbp
0x18000fa17  cmova   r8d, edx
0x18000fa1b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000fa20  mov     edi, eax
0x18000fa22  test    eax, eax
0x18000fa24  jns     short loc_18000FA46
0x18000fa26  mov     rcx, [rsp+278h]; this
0x18000fa2e  lea     r8, aWil; "wil"
0x18000fa35  mov     r9d, eax; char *
0x18000fa38  mov     edx, 8Bh; void *
0x18000fa3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa42  mov     eax, edi
0x18000fa44  jmp     short loc_18000FA9B
0x18000fa46  lea     r8, asc_18002B070; "h"
0x18000fa4d  shr     rbx, 1Fh
0x18000fa51  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x18000fa56  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000fa5b  test    ebx, ebx
0x18000fa5d  lea     rcx, [rbp+8]
0x18000fa61  lea     r9, [rsp+278h+pszDest]
0x18000fa66  mov     edx, ebx
0x18000fa68  cmovnz  esi, ebx
0x18000fa6b  mov     r8d, esi
0x18000fa6e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000fa73  mov     ebx, eax
0x18000fa75  test    eax, eax
0x18000fa77  jns     short loc_18000FA99
0x18000fa79  mov     rcx, [rsp+278h]; this
0x18000fa81  lea     r8, aWil; "wil"
0x18000fa88  mov     r9d, eax; char *
0x18000fa8b  mov     edx, 90h; void *
0x18000fa90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa95  mov     eax, ebx
0x18000fa97  jmp     short loc_18000FA9B
0x18000fa99  xor     eax, eax
0x18000fa9b  mov     rcx, [rsp+278h+var_28]
0x18000faa3  xor     rcx, rsp; StackCookie
0x18000faa6  call    __security_check_cookie
0x18000faab  mov     rbx, [rsp+278h+arg_10]
0x18000fab3  add     rsp, 260h
0x18000faba  pop     rdi
0x18000fabb  pop     rsi
0x18000fabc  pop     rbp
0x18000fabd  retn
```
