# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003fc0`
- end: `0x1400040de`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005270`
- `0x14000ded8`

## callees

- `0x140003fc0`
- `0x1400056a4`
- `0x140005bc0`
- `0x140005ca0`
- `0x140006340`
- `0x1400067c0`
- `0x14001a8d0`

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
0x140003fc0  mov     [rsp+arg_10], rbx
0x140003fc5  push    rbp
0x140003fc6  push    rsi
0x140003fc7  push    rdi
0x140003fc8  sub     rsp, 260h
0x140003fcf  mov     rax, cs:__security_cookie
0x140003fd6  xor     rax, rsp
0x140003fd9  mov     [rsp+278h+var_28], rax
0x140003fe1  mov     rax, 0C000000000000000h
0x140003feb  mov     rbx, r9
0x140003fee  mov     rbp, rcx
0x140003ff1  test    rax, r9
0x140003ff4  jz      short loc_140003FFC
0x140003ff6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003ffc  mov     r9, rdx; pszSrc
0x140003fff  lea     rcx, [rsp+278h+pszDest]; pszDest
0x140004004  mov     edx, 104h; cchDest
0x140004009  call    StringCopyWorkerW
0x14000400e  lea     r8, aP0; "_p0"
0x140004015  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x14000401a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000401f  mov     edx, ebx
0x140004021  lea     r9, [rsp+278h+pszDest]
0x140004026  and     edx, 7FFFFFFFh
0x14000402c  mov     esi, 1
0x140004031  mov     r8d, esi
0x140004034  mov     rcx, rbp
0x140004037  cmova   r8d, edx
0x14000403b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004040  mov     edi, eax
0x140004042  test    eax, eax
0x140004044  jns     short loc_140004066
0x140004046  mov     rcx, [rsp+278h]; this
0x14000404e  lea     r8, aWil; "wil"
0x140004055  mov     r9d, eax; char *
0x140004058  mov     edx, 8Bh; void *
0x14000405d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004062  mov     eax, edi
0x140004064  jmp     short loc_1400040BB
0x140004066  lea     r8, asc_14001DE78; "h"
0x14000406d  shr     rbx, 1Fh
0x140004071  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x140004076  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000407b  test    ebx, ebx
0x14000407d  lea     rcx, [rbp+8]
0x140004081  lea     r9, [rsp+278h+pszDest]
0x140004086  mov     edx, ebx
0x140004088  cmovnz  esi, ebx
0x14000408b  mov     r8d, esi
0x14000408e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004093  mov     ebx, eax
0x140004095  test    eax, eax
0x140004097  jns     short loc_1400040B9
0x140004099  mov     rcx, [rsp+278h]; this
0x1400040a1  lea     r8, aWil; "wil"
0x1400040a8  mov     r9d, eax; char *
0x1400040ab  mov     edx, 90h; void *
0x1400040b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040b5  mov     eax, ebx
0x1400040b7  jmp     short loc_1400040BB
0x1400040b9  xor     eax, eax
0x1400040bb  mov     rcx, [rsp+278h+var_28]
0x1400040c3  xor     rcx, rsp; StackCookie
0x1400040c6  call    __security_check_cookie
0x1400040cb  mov     rbx, [rsp+278h+arg_10]
0x1400040d3  add     rsp, 260h
0x1400040da  pop     rdi
0x1400040db  pop     rsi
0x1400040dc  pop     rbp
0x1400040dd  retn
```
