# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140006a40`
- end: `0x140006b61`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008a14`
- `0x140008b78`

## callees

- `0x140002f40`
- `0x140006a40`
- `0x14000a4bc`
- `0x14000cbc8`
- `0x14000cd00`
- `0x14000dbf8`
- `0x14000e0e4`

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
0x140006a40  push    rbx
0x140006a42  push    rbp
0x140006a43  push    rsi
0x140006a44  push    rdi
0x140006a45  push    r14
0x140006a47  sub     rsp, 260h
0x140006a4e  mov     rax, cs:__security_cookie
0x140006a55  xor     rax, rsp
0x140006a58  mov     [rsp+288h+var_38], rax
0x140006a60  mov     rax, 0C000000000000000h
0x140006a6a  mov     rbx, r9
0x140006a6d  mov     rbp, rcx
0x140006a70  test    rax, r9
0x140006a73  jz      short loc_140006A7B
0x140006a75  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006a7b  mov     r9, rdx; pszSrc
0x140006a7e  lea     rcx, [rsp+288h+pszDest]; pszDest
0x140006a83  mov     r14d, 104h
0x140006a89  mov     edx, r14d; cchDest
0x140006a8c  call    StringCopyWorkerW
0x140006a91  lea     r8, aP0; "_p0"
0x140006a98  mov     edx, r14d; unsigned __int64
0x140006a9b  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x140006aa0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006aa5  mov     edx, ebx
0x140006aa7  lea     r9, [rsp+288h+pszDest]
0x140006aac  and     edx, 7FFFFFFFh
0x140006ab2  mov     esi, 1
0x140006ab7  mov     r8d, esi
0x140006aba  mov     rcx, rbp
0x140006abd  cmova   r8d, edx
0x140006ac1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140006ac6  mov     edi, eax
0x140006ac8  test    eax, eax
0x140006aca  jns     short loc_140006AEB
0x140006acc  mov     rcx, [rsp+288h]; this
0x140006ad4  lea     r8, aWil; "wil"
0x140006adb  mov     r9d, eax; char *
0x140006ade  lea     edx, [r14-79h]; void *
0x140006ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006ae7  mov     eax, edi
0x140006ae9  jmp     short loc_140006B43
0x140006aeb  lea     r8, asc_14001C610; "h"
0x140006af2  shr     rbx, 1Fh
0x140006af6  mov     rdx, r14; unsigned __int64
0x140006af9  lea     rcx, [rsp+288h+pszDest]; unsigned __int16 *
0x140006afe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006b03  test    ebx, ebx
0x140006b05  lea     rcx, [rbp+8]
0x140006b09  lea     r9, [rsp+288h+pszDest]
0x140006b0e  mov     edx, ebx
0x140006b10  cmovnz  esi, ebx
0x140006b13  mov     r8d, esi
0x140006b16  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140006b1b  mov     ebx, eax
0x140006b1d  test    eax, eax
0x140006b1f  jns     short loc_140006B41
0x140006b21  mov     rcx, [rsp+288h]; this
0x140006b29  lea     r8, aWil; "wil"
0x140006b30  mov     r9d, eax; char *
0x140006b33  mov     edx, 90h; void *
0x140006b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006b3d  mov     eax, ebx
0x140006b3f  jmp     short loc_140006B43
0x140006b41  xor     eax, eax
0x140006b43  mov     rcx, [rsp+288h+var_38]
0x140006b4b  xor     rcx, rsp; StackCookie
0x140006b4e  call    __security_check_cookie
0x140006b53  add     rsp, 260h
0x140006b5a  pop     r14
0x140006b5c  pop     rdi
0x140006b5d  pop     rsi
0x140006b5e  pop     rbp
0x140006b5f  pop     rbx
0x140006b60  retn
```
