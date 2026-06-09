# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140002bc0`
- end: `0x140002cd0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c80`

## callees

- `0x140001600`
- `0x140002bc0`
- `0x1400040f8`
- `0x140004508`
- `0x1400045e8`
- `0x140004a00`
- `0x140004aa0`

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
0x140002bc0  mov     [rsp+arg_10], rbx
0x140002bc5  push    rbp
0x140002bc6  push    rsi
0x140002bc7  push    rdi
0x140002bc8  sub     rsp, 260h
0x140002bcf  mov     rax, cs:__security_cookie
0x140002bd6  xor     rax, rsp
0x140002bd9  mov     [rsp+278h+var_28], rax
0x140002be1  mov     rax, 0C000000000000000h
0x140002beb  mov     rbx, r9
0x140002bee  mov     rbp, rcx
0x140002bf1  test    rax, r9
0x140002bf4  jz      short loc_140002BFC
0x140002bf6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002bfc  mov     r9, rdx; pszSrc
0x140002bff  lea     rcx, [rsp+278h+pszDest]; pszDest
0x140002c04  mov     edx, 104h; cchDest
0x140002c09  call    StringCopyWorkerW
0x140002c0e  lea     r8, aP0; "_p0"
0x140002c15  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140002c1a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002c1f  mov     edx, ebx
0x140002c21  lea     r9, [rsp+278h+pszDest]
0x140002c26  and     edx, 7FFFFFFFh
0x140002c2c  mov     esi, 1
0x140002c31  mov     r8d, esi
0x140002c34  mov     rcx, rbp
0x140002c37  cmova   r8d, edx
0x140002c3b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140002c40  mov     edi, eax
0x140002c42  test    eax, eax
0x140002c44  jns     short loc_140002C5F
0x140002c46  mov     rcx, [rsp+278h]; this
0x140002c4e  mov     r9d, eax; char *
0x140002c51  mov     edx, 8Bh; void *
0x140002c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002c5b  mov     eax, edi
0x140002c5d  jmp     short loc_140002CAD
0x140002c5f  lea     r8, asc_140008848; "h"
0x140002c66  shr     rbx, 1Fh
0x140002c6a  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140002c6f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140002c74  test    ebx, ebx
0x140002c76  lea     rcx, [rbp+8]
0x140002c7a  lea     r9, [rsp+278h+pszDest]
0x140002c7f  mov     edx, ebx
0x140002c81  cmovnz  esi, ebx
0x140002c84  mov     r8d, esi
0x140002c87  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140002c8c  mov     ebx, eax
0x140002c8e  test    eax, eax
0x140002c90  jns     short loc_140002CAB
0x140002c92  mov     rcx, [rsp+278h]; this
0x140002c9a  mov     r9d, eax; char *
0x140002c9d  mov     edx, 90h; void *
0x140002ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002ca7  mov     eax, ebx
0x140002ca9  jmp     short loc_140002CAD
0x140002cab  xor     eax, eax
0x140002cad  mov     rcx, [rsp+278h+var_28]
0x140002cb5  xor     rcx, rsp; StackCookie
0x140002cb8  call    __security_check_cookie
0x140002cbd  mov     rbx, [rsp+278h+arg_10]
0x140002cc5  add     rsp, 260h
0x140002ccc  pop     rdi
0x140002ccd  pop     rsi
0x140002cce  pop     rbp
0x140002ccf  retn
```
