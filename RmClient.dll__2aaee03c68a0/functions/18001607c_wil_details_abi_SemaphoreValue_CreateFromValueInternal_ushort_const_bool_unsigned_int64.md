# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18001607c`
- end: `0x18001618c`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016a08`
- `0x180016b4c`

## callees

- `0x180001030`
- `0x18000b5d0`
- `0x180012a48`
- `0x18001607c`
- `0x1800174d0`
- `0x180017554`
- `0x18001aec0`

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
0x18001607c  mov     [rsp+arg_10], rbx
0x180016081  push    rbp
0x180016082  push    rsi
0x180016083  push    rdi
0x180016084  sub     rsp, 260h
0x18001608b  mov     rax, cs:__security_cookie
0x180016092  xor     rax, rsp
0x180016095  mov     [rsp+278h+var_28], rax
0x18001609d  mov     rax, 0C000000000000000h
0x1800160a7  mov     rbx, r9
0x1800160aa  mov     rbp, rcx
0x1800160ad  test    rax, r9
0x1800160b0  jz      short loc_1800160B8
0x1800160b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800160b8  mov     r8, rdx; unsigned __int16 *
0x1800160bb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800160c0  mov     edx, 104h; unsigned __int64
0x1800160c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800160ca  lea     r8, aP0; "_p0"
0x1800160d1  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800160d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800160db  mov     edx, ebx
0x1800160dd  lea     r9, [rsp+278h+var_238]
0x1800160e2  and     edx, 7FFFFFFFh
0x1800160e8  mov     esi, 1
0x1800160ed  mov     r8d, esi
0x1800160f0  mov     rcx, rbp
0x1800160f3  cmova   r8d, edx
0x1800160f7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800160fc  mov     edi, eax
0x1800160fe  test    eax, eax
0x180016100  jns     short loc_18001611B
0x180016102  mov     rcx, [rsp+278h]; this
0x18001610a  mov     r9d, eax; char *
0x18001610d  mov     edx, 8Bh; void *
0x180016112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016117  mov     eax, edi
0x180016119  jmp     short loc_180016169
0x18001611b  lea     r8, asc_1800230C8; "h"
0x180016122  shr     rbx, 1Fh
0x180016126  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18001612b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016130  test    ebx, ebx
0x180016132  lea     rcx, [rbp+8]
0x180016136  lea     r9, [rsp+278h+var_238]
0x18001613b  mov     edx, ebx
0x18001613d  cmovnz  esi, ebx
0x180016140  mov     r8d, esi
0x180016143  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180016148  mov     ebx, eax
0x18001614a  test    eax, eax
0x18001614c  jns     short loc_180016167
0x18001614e  mov     rcx, [rsp+278h]; this
0x180016156  mov     r9d, eax; char *
0x180016159  mov     edx, 90h; void *
0x18001615e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016163  mov     eax, ebx
0x180016165  jmp     short loc_180016169
0x180016167  xor     eax, eax
0x180016169  mov     rcx, [rsp+278h+var_28]
0x180016171  xor     rcx, rsp; StackCookie
0x180016174  call    __security_check_cookie
0x180016179  mov     rbx, [rsp+278h+arg_10]
0x180016181  add     rsp, 260h
0x180016188  pop     rdi
0x180016189  pop     rsi
0x18001618a  pop     rbp
0x18001618b  retn
```
