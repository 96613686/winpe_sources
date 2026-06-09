# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140005630`
- end: `0x14000574e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006e0c`
- `0x140006f70`

## callees

- `0x140002ce0`
- `0x1400031b0`
- `0x140005630`
- `0x1400089fc`
- `0x140008adc`
- `0x140009554`
- `0x14000966c`

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
0x140005630  mov     [rsp+arg_10], rbx
0x140005635  push    rbp
0x140005636  push    rsi
0x140005637  push    rdi
0x140005638  sub     rsp, 260h
0x14000563f  mov     rax, cs:__security_cookie
0x140005646  xor     rax, rsp
0x140005649  mov     [rsp+278h+var_28], rax
0x140005651  mov     rax, 0C000000000000000h
0x14000565b  mov     rbx, r9
0x14000565e  mov     rbp, rcx
0x140005661  test    rax, r9
0x140005664  jz      short loc_14000566C
0x140005666  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000566c  mov     r9, rdx; pszSrc
0x14000566f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x140005674  mov     edx, 104h; cchDest
0x140005679  call    StringCopyWorkerW
0x14000567e  lea     r8, aP0; "_p0"
0x140005685  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x14000568a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000568f  mov     edx, ebx
0x140005691  lea     r9, [rsp+278h+pszDest]
0x140005696  and     edx, 7FFFFFFFh
0x14000569c  mov     esi, 1
0x1400056a1  mov     r8d, esi
0x1400056a4  mov     rcx, rbp
0x1400056a7  cmova   r8d, edx
0x1400056ab  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400056b0  mov     edi, eax
0x1400056b2  test    eax, eax
0x1400056b4  jns     short loc_1400056D6
0x1400056b6  mov     rcx, [rsp+278h]; this
0x1400056be  lea     r8, aWil; "wil"
0x1400056c5  mov     r9d, eax; char *
0x1400056c8  mov     edx, 8Bh; void *
0x1400056cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400056d2  mov     eax, edi
0x1400056d4  jmp     short loc_14000572B
0x1400056d6  lea     r8, asc_14000DCD0; "h"
0x1400056dd  shr     rbx, 1Fh
0x1400056e1  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1400056e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400056eb  test    ebx, ebx
0x1400056ed  lea     rcx, [rbp+8]
0x1400056f1  lea     r9, [rsp+278h+pszDest]
0x1400056f6  mov     edx, ebx
0x1400056f8  cmovnz  esi, ebx
0x1400056fb  mov     r8d, esi
0x1400056fe  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005703  mov     ebx, eax
0x140005705  test    eax, eax
0x140005707  jns     short loc_140005729
0x140005709  mov     rcx, [rsp+278h]; this
0x140005711  lea     r8, aWil; "wil"
0x140005718  mov     r9d, eax; char *
0x14000571b  mov     edx, 90h; void *
0x140005720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005725  mov     eax, ebx
0x140005727  jmp     short loc_14000572B
0x140005729  xor     eax, eax
0x14000572b  mov     rcx, [rsp+278h+var_28]
0x140005733  xor     rcx, rsp; StackCookie
0x140005736  call    __security_check_cookie
0x14000573b  mov     rbx, [rsp+278h+arg_10]
0x140005743  add     rsp, 260h
0x14000574a  pop     rdi
0x14000574b  pop     rsi
0x14000574c  pop     rbp
0x14000574d  retn
```
