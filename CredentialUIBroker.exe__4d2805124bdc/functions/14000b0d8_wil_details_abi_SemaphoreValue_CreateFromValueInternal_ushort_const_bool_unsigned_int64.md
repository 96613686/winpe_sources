# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000b0d8`
- end: `0x14000b1f6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f370`
- `0x14000f4d4`

## callees

- `0x140003620`
- `0x14000b0d8`
- `0x1400136fc`
- `0x14001620c`
- `0x140016378`
- `0x140017d60`
- `0x140019294`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        __int64 a3,
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
  int v16; // [rsp+20h] [rbp-258h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            v17);
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
        v16);
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
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x14000b0d8  mov     [rsp+arg_10], rbx
0x14000b0dd  push    rbp
0x14000b0de  push    rsi
0x14000b0df  push    rdi
0x14000b0e0  sub     rsp, 260h
0x14000b0e7  mov     rax, cs:__security_cookie
0x14000b0ee  xor     rax, rsp
0x14000b0f1  mov     [rsp+278h+var_28], rax
0x14000b0f9  mov     rax, 0C000000000000000h
0x14000b103  mov     rbx, r9
0x14000b106  mov     rbp, rcx
0x14000b109  test    rax, r9
0x14000b10c  jz      short loc_14000B114
0x14000b10e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000b114  mov     r8, rdx; unsigned __int16 *
0x14000b117  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b11c  mov     edx, 104h; unsigned __int64
0x14000b121  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b126  lea     r8, aP0; "_p0"
0x14000b12d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b132  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b137  mov     edx, ebx
0x14000b139  lea     r9, [rsp+278h+var_238]
0x14000b13e  and     edx, 7FFFFFFFh
0x14000b144  mov     esi, 1
0x14000b149  mov     r8d, esi
0x14000b14c  mov     rcx, rbp
0x14000b14f  cmova   r8d, edx
0x14000b153  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b158  mov     edi, eax
0x14000b15a  test    eax, eax
0x14000b15c  jns     short loc_14000B17E
0x14000b15e  mov     rcx, [rsp+278h]; this
0x14000b166  lea     r8, aWil; "wil"
0x14000b16d  mov     r9d, eax; char *
0x14000b170  mov     edx, 8Bh; void *
0x14000b175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b17a  mov     eax, edi
0x14000b17c  jmp     short loc_14000B1D3
0x14000b17e  lea     r8, asc_140023270; "h"
0x14000b185  shr     rbx, 1Fh
0x14000b189  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b18e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b193  test    ebx, ebx
0x14000b195  lea     rcx, [rbp+8]
0x14000b199  lea     r9, [rsp+278h+var_238]
0x14000b19e  mov     edx, ebx
0x14000b1a0  cmovnz  esi, ebx
0x14000b1a3  mov     r8d, esi
0x14000b1a6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b1ab  mov     ebx, eax
0x14000b1ad  test    eax, eax
0x14000b1af  jns     short loc_14000B1D1
0x14000b1b1  mov     rcx, [rsp+278h]; this
0x14000b1b9  lea     r8, aWil; "wil"
0x14000b1c0  mov     r9d, eax; char *
0x14000b1c3  mov     edx, 90h; void *
0x14000b1c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b1cd  mov     eax, ebx
0x14000b1cf  jmp     short loc_14000B1D3
0x14000b1d1  xor     eax, eax
0x14000b1d3  mov     rcx, [rsp+278h+var_28]
0x14000b1db  xor     rcx, rsp; StackCookie
0x14000b1de  call    __security_check_cookie
0x14000b1e3  mov     rbx, [rsp+278h+arg_10]
0x14000b1eb  add     rsp, 260h
0x14000b1f2  pop     rdi
0x14000b1f3  pop     rsi
0x14000b1f4  pop     rbp
0x14000b1f5  retn
```
