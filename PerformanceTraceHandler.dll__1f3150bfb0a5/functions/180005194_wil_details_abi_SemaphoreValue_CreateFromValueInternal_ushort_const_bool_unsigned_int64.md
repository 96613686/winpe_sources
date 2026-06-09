# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005194`
- end: `0x1800052b2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000698c`
- `0x180006abc`

## callees

- `0x180002c00`
- `0x180005194`
- `0x180007f3c`
- `0x180008608`
- `0x1800086e8`
- `0x180009390`
- `0x1800095fc`

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
0x180005194  mov     [rsp+arg_10], rbx
0x180005199  push    rbp
0x18000519a  push    rsi
0x18000519b  push    rdi
0x18000519c  sub     rsp, 260h
0x1800051a3  mov     rax, cs:__security_cookie
0x1800051aa  xor     rax, rsp
0x1800051ad  mov     [rsp+278h+var_28], rax
0x1800051b5  mov     rax, 0C000000000000000h
0x1800051bf  mov     rbx, r9
0x1800051c2  mov     rbp, rcx
0x1800051c5  test    rax, r9
0x1800051c8  jz      short loc_1800051D0
0x1800051ca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800051d0  mov     r9, rdx; pszSrc
0x1800051d3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800051d8  mov     edx, 104h; cchDest
0x1800051dd  call    StringCopyWorkerW
0x1800051e2  lea     r8, aP0; "_p0"
0x1800051e9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800051ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051f3  mov     edx, ebx
0x1800051f5  lea     r9, [rsp+278h+pszDest]
0x1800051fa  and     edx, 7FFFFFFFh
0x180005200  mov     esi, 1
0x180005205  mov     r8d, esi
0x180005208  mov     rcx, rbp
0x18000520b  cmova   r8d, edx
0x18000520f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005214  mov     edi, eax
0x180005216  test    eax, eax
0x180005218  jns     short loc_18000523A
0x18000521a  mov     rcx, [rsp+278h]; this
0x180005222  lea     r8, aWil; "wil"
0x180005229  mov     r9d, eax; char *
0x18000522c  mov     edx, 8Bh; void *
0x180005231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005236  mov     eax, edi
0x180005238  jmp     short loc_18000528F
0x18000523a  lea     r8, asc_18001E4B8; "h"
0x180005241  shr     rbx, 1Fh
0x180005245  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000524a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000524f  test    ebx, ebx
0x180005251  lea     rcx, [rbp+8]
0x180005255  lea     r9, [rsp+278h+pszDest]
0x18000525a  mov     edx, ebx
0x18000525c  cmovnz  esi, ebx
0x18000525f  mov     r8d, esi
0x180005262  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005267  mov     ebx, eax
0x180005269  test    eax, eax
0x18000526b  jns     short loc_18000528D
0x18000526d  mov     rcx, [rsp+278h]; this
0x180005275  lea     r8, aWil; "wil"
0x18000527c  mov     r9d, eax; char *
0x18000527f  mov     edx, 90h; void *
0x180005284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005289  mov     eax, ebx
0x18000528b  jmp     short loc_18000528F
0x18000528d  xor     eax, eax
0x18000528f  mov     rcx, [rsp+278h+var_28]
0x180005297  xor     rcx, rsp; StackCookie
0x18000529a  call    __security_check_cookie
0x18000529f  mov     rbx, [rsp+278h+arg_10]
0x1800052a7  add     rsp, 260h
0x1800052ae  pop     rdi
0x1800052af  pop     rsi
0x1800052b0  pop     rbp
0x1800052b1  retn
```
