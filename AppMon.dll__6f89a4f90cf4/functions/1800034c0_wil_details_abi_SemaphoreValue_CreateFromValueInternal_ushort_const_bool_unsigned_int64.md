# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800034c0`
- end: `0x1800035d0`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004508`

## callees

- `0x180001620`
- `0x1800034c0`
- `0x180004bd4`
- `0x1800050ac`
- `0x180005128`
- `0x18000560c`
- `0x1800056d0`

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
0x1800034c0  mov     [rsp+arg_10], rbx
0x1800034c5  push    rbp
0x1800034c6  push    rsi
0x1800034c7  push    rdi
0x1800034c8  sub     rsp, 260h
0x1800034cf  mov     rax, cs:__security_cookie
0x1800034d6  xor     rax, rsp
0x1800034d9  mov     [rsp+278h+var_28], rax
0x1800034e1  mov     rax, 0C000000000000000h
0x1800034eb  mov     rbx, r9
0x1800034ee  mov     rbp, rcx
0x1800034f1  test    rax, r9
0x1800034f4  jz      short loc_1800034FC
0x1800034f6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800034fc  mov     r8, rdx; unsigned __int16 *
0x1800034ff  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003504  mov     edx, 104h; unsigned __int64
0x180003509  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000350e  lea     r8, aP0; "_p0"
0x180003515  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000351a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000351f  mov     edx, ebx
0x180003521  lea     r9, [rsp+278h+var_238]
0x180003526  and     edx, 7FFFFFFFh
0x18000352c  mov     esi, 1
0x180003531  mov     r8d, esi
0x180003534  mov     rcx, rbp
0x180003537  cmova   r8d, edx
0x18000353b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003540  mov     edi, eax
0x180003542  test    eax, eax
0x180003544  jns     short loc_18000355F
0x180003546  mov     rcx, [rsp+278h]; this
0x18000354e  mov     r9d, eax; char *
0x180003551  mov     edx, 8Bh; void *
0x180003556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000355b  mov     eax, edi
0x18000355d  jmp     short loc_1800035AD
0x18000355f  lea     r8, asc_1800121D8; "h"
0x180003566  shr     rbx, 1Fh
0x18000356a  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000356f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003574  test    ebx, ebx
0x180003576  lea     rcx, [rbp+8]
0x18000357a  lea     r9, [rsp+278h+var_238]
0x18000357f  mov     edx, ebx
0x180003581  cmovnz  esi, ebx
0x180003584  mov     r8d, esi
0x180003587  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000358c  mov     ebx, eax
0x18000358e  test    eax, eax
0x180003590  jns     short loc_1800035AB
0x180003592  mov     rcx, [rsp+278h]; this
0x18000359a  mov     r9d, eax; char *
0x18000359d  mov     edx, 90h; void *
0x1800035a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800035a7  mov     eax, ebx
0x1800035a9  jmp     short loc_1800035AD
0x1800035ab  xor     eax, eax
0x1800035ad  mov     rcx, [rsp+278h+var_28]
0x1800035b5  xor     rcx, rsp; StackCookie
0x1800035b8  call    __security_check_cookie
0x1800035bd  mov     rbx, [rsp+278h+arg_10]
0x1800035c5  add     rsp, 260h
0x1800035cc  pop     rdi
0x1800035cd  pop     rsi
0x1800035ce  pop     rbp
0x1800035cf  retn
```
