# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004f00`
- end: `0x140005010`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006748`
- `0x14000686c`

## callees

- `0x140004f00`
- `0x1400079cc`
- `0x140008114`
- `0x140008190`
- `0x140009294`
- `0x140009404`
- `0x14001edc0`

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
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            v19);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v18);
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
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x140004f00  mov     [rsp+arg_10], rbx
0x140004f05  push    rbp
0x140004f06  push    rsi
0x140004f07  push    rdi
0x140004f08  sub     rsp, 260h
0x140004f0f  mov     rax, cs:__security_cookie
0x140004f16  xor     rax, rsp
0x140004f19  mov     [rsp+278h+var_28], rax
0x140004f21  mov     rax, 0C000000000000000h
0x140004f2b  mov     rbx, r9
0x140004f2e  mov     rbp, rcx
0x140004f31  test    rax, r9
0x140004f34  jz      short loc_140004F3C
0x140004f36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004f3c  mov     r8, rdx; unsigned __int16 *
0x140004f3f  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004f44  mov     edx, 104h; unsigned __int64
0x140004f49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004f4e  lea     r8, aP0; "_p0"
0x140004f55  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004f5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f5f  mov     edx, ebx
0x140004f61  lea     r9, [rsp+278h+var_238]
0x140004f66  and     edx, 7FFFFFFFh
0x140004f6c  mov     esi, 1
0x140004f71  mov     r8d, esi
0x140004f74  mov     rcx, rbp
0x140004f77  cmova   r8d, edx
0x140004f7b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004f80  mov     edi, eax
0x140004f82  test    eax, eax
0x140004f84  jns     short loc_140004F9F
0x140004f86  mov     rcx, [rsp+278h]; this
0x140004f8e  mov     r9d, eax; char *
0x140004f91  mov     edx, 8Bh; void *
0x140004f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f9b  mov     eax, edi
0x140004f9d  jmp     short loc_140004FED
0x140004f9f  lea     r8, asc_140022190; "h"
0x140004fa6  shr     rbx, 1Fh
0x140004faa  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x140004faf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004fb4  test    ebx, ebx
0x140004fb6  lea     rcx, [rbp+8]
0x140004fba  lea     r9, [rsp+278h+var_238]
0x140004fbf  mov     edx, ebx
0x140004fc1  cmovnz  esi, ebx
0x140004fc4  mov     r8d, esi
0x140004fc7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004fcc  mov     ebx, eax
0x140004fce  test    eax, eax
0x140004fd0  jns     short loc_140004FEB
0x140004fd2  mov     rcx, [rsp+278h]; this
0x140004fda  mov     r9d, eax; char *
0x140004fdd  mov     edx, 90h; void *
0x140004fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004fe7  mov     eax, ebx
0x140004fe9  jmp     short loc_140004FED
0x140004feb  xor     eax, eax
0x140004fed  mov     rcx, [rsp+278h+var_28]
0x140004ff5  xor     rcx, rsp; StackCookie
0x140004ff8  call    __security_check_cookie
0x140004ffd  mov     rbx, [rsp+278h+arg_10]
0x140005005  add     rsp, 260h
0x14000500c  pop     rdi
0x14000500d  pop     rsi
0x14000500e  pop     rbp
0x14000500f  retn
```
