# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005b00`
- end: `0x180005c1e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c70`
- `0x18000bae0`

## callees

- `0x180002a90`
- `0x180005b00`
- `0x180007654`
- `0x180007bb0`
- `0x180007c90`
- `0x18000822c`
- `0x18000859c`

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
0x180005b00  mov     [rsp+arg_10], rbx
0x180005b05  push    rbp
0x180005b06  push    rsi
0x180005b07  push    rdi
0x180005b08  sub     rsp, 260h
0x180005b0f  mov     rax, cs:__security_cookie
0x180005b16  xor     rax, rsp
0x180005b19  mov     [rsp+278h+var_28], rax
0x180005b21  mov     rax, 0C000000000000000h
0x180005b2b  mov     rbx, r9
0x180005b2e  mov     rbp, rcx
0x180005b31  test    rax, r9
0x180005b34  jz      short loc_180005B3C
0x180005b36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005b3c  mov     r9, rdx; pszSrc
0x180005b3f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180005b44  mov     edx, 104h; cchDest
0x180005b49  call    StringCopyWorkerW
0x180005b4e  lea     r8, aP0; "_p0"
0x180005b55  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180005b5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005b5f  mov     edx, ebx
0x180005b61  lea     r9, [rsp+278h+pszDest]
0x180005b66  and     edx, 7FFFFFFFh
0x180005b6c  mov     esi, 1
0x180005b71  mov     r8d, esi
0x180005b74  mov     rcx, rbp
0x180005b77  cmova   r8d, edx
0x180005b7b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005b80  mov     edi, eax
0x180005b82  test    eax, eax
0x180005b84  jns     short loc_180005BA6
0x180005b86  mov     rcx, [rsp+278h]; this
0x180005b8e  lea     r8, aWil; "wil"
0x180005b95  mov     r9d, eax; char *
0x180005b98  mov     edx, 8Bh; void *
0x180005b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ba2  mov     eax, edi
0x180005ba4  jmp     short loc_180005BFB
0x180005ba6  lea     r8, asc_18002F180; "h"
0x180005bad  shr     rbx, 1Fh
0x180005bb1  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180005bb6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005bbb  test    ebx, ebx
0x180005bbd  lea     rcx, [rbp+8]
0x180005bc1  lea     r9, [rsp+278h+pszDest]
0x180005bc6  mov     edx, ebx
0x180005bc8  cmovnz  esi, ebx
0x180005bcb  mov     r8d, esi
0x180005bce  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005bd3  mov     ebx, eax
0x180005bd5  test    eax, eax
0x180005bd7  jns     short loc_180005BF9
0x180005bd9  mov     rcx, [rsp+278h]; this
0x180005be1  lea     r8, aWil; "wil"
0x180005be8  mov     r9d, eax; char *
0x180005beb  mov     edx, 90h; void *
0x180005bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bf5  mov     eax, ebx
0x180005bf7  jmp     short loc_180005BFB
0x180005bf9  xor     eax, eax
0x180005bfb  mov     rcx, [rsp+278h+var_28]
0x180005c03  xor     rcx, rsp; StackCookie
0x180005c06  call    __security_check_cookie
0x180005c0b  mov     rbx, [rsp+278h+arg_10]
0x180005c13  add     rsp, 260h
0x180005c1a  pop     rdi
0x180005c1b  pop     rsi
0x180005c1c  pop     rbp
0x180005c1d  retn
```
