# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140005144`
- end: `0x140005266`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006510`
- `0x14000c1a0`

## callees

- `0x1400029c0`
- `0x140005144`
- `0x140006bf4`
- `0x1400074ec`
- `0x1400075e4`
- `0x140007c78`
- `0x140007dbc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
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
        v14);
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
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x140005144  push    rbx
0x140005146  push    rbp
0x140005147  push    rsi
0x140005148  push    rdi
0x140005149  push    r14
0x14000514b  sub     rsp, 260h
0x140005152  mov     rax, cs:__security_cookie
0x140005159  xor     rax, rsp
0x14000515c  mov     [rsp+288h+var_38], rax
0x140005164  mov     rax, 0C000000000000000h
0x14000516e  mov     rbx, r9
0x140005171  mov     rbp, rcx
0x140005174  test    rax, r9
0x140005177  jz      short loc_14000517F
0x140005179  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000517f  mov     r8, rdx; unsigned __int16 *
0x140005182  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005187  mov     r14d, 104h
0x14000518d  mov     edx, r14d; unsigned __int64
0x140005190  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005195  lea     r8, aP0; "_p0"
0x14000519c  mov     edx, r14d; unsigned __int64
0x14000519f  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1400051a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400051a9  mov     edx, ebx
0x1400051ab  lea     r9, [rsp+288h+var_248]
0x1400051b0  and     edx, 7FFFFFFFh
0x1400051b6  mov     esi, 1
0x1400051bb  mov     r8d, esi
0x1400051be  mov     rcx, rbp
0x1400051c1  cmova   r8d, edx
0x1400051c5  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400051ca  mov     edi, eax
0x1400051cc  test    eax, eax
0x1400051ce  jns     short loc_1400051EF
0x1400051d0  mov     rcx, [rsp+288h]; this
0x1400051d8  lea     r8, aWil; "wil"
0x1400051df  mov     r9d, eax; char *
0x1400051e2  lea     edx, [r14-79h]; void *
0x1400051e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400051eb  mov     eax, edi
0x1400051ed  jmp     short loc_140005247
0x1400051ef  lea     r8, asc_14001C068; "h"
0x1400051f6  shr     rbx, 1Fh
0x1400051fa  mov     rdx, r14; unsigned __int64
0x1400051fd  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005202  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005207  test    ebx, ebx
0x140005209  lea     rcx, [rbp+8]
0x14000520d  lea     r9, [rsp+288h+var_248]
0x140005212  mov     edx, ebx
0x140005214  cmovnz  esi, ebx
0x140005217  mov     r8d, esi
0x14000521a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000521f  mov     ebx, eax
0x140005221  test    eax, eax
0x140005223  jns     short loc_140005245
0x140005225  mov     rcx, [rsp+288h]; this
0x14000522d  lea     r8, aWil; "wil"
0x140005234  mov     r9d, eax; char *
0x140005237  mov     edx, 90h; void *
0x14000523c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005241  mov     eax, ebx
0x140005243  jmp     short loc_140005247
0x140005245  xor     eax, eax
0x140005247  mov     rcx, [rsp+288h+var_38]
0x14000524f  xor     rcx, rsp; StackCookie
0x140005252  call    __security_check_cookie
0x140005257  add     rsp, 260h
0x14000525e  pop     r14
0x140005260  pop     rdi
0x140005261  pop     rsi
0x140005262  pop     rbp
0x140005263  pop     rbx
0x140005264  retn
```
