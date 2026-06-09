# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000b1a4`
- end: `0x14000b2bd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `281`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008668`
- `0x1400087cc`

## callees

- `0x1400027ac`
- `0x140005110`
- `0x140005bf4`
- `0x140008c80`
- `0x14000b1a4`
- `0x14000cd74`
- `0x14000ce24`

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
  StringCchCopyW(v17, (unsigned __int64)a2, a2);
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
0x14000b1a4  mov     [rsp+arg_10], rbx
0x14000b1a9  push    rbp
0x14000b1aa  push    rsi
0x14000b1ab  push    rdi
0x14000b1ac  sub     rsp, 260h
0x14000b1b3  mov     rax, cs:__security_cookie
0x14000b1ba  xor     rax, rsp
0x14000b1bd  mov     [rsp+278h+var_28], rax
0x14000b1c5  mov     rax, 0C000000000000000h
0x14000b1cf  mov     rbx, r9
0x14000b1d2  mov     rbp, rcx
0x14000b1d5  test    rax, r9
0x14000b1d8  jz      short loc_14000B1E0
0x14000b1da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000b1e0  mov     r8, rdx; unsigned __int16 *
0x14000b1e3  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b1e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b1ed  lea     r8, aP0; "_p0"
0x14000b1f4  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b1f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b1fe  mov     edx, ebx
0x14000b200  lea     r9, [rsp+278h+var_238]
0x14000b205  and     edx, 7FFFFFFFh
0x14000b20b  mov     esi, 1
0x14000b210  mov     r8d, esi
0x14000b213  mov     rcx, rbp
0x14000b216  cmova   r8d, edx
0x14000b21a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b21f  mov     edi, eax
0x14000b221  test    eax, eax
0x14000b223  jns     short loc_14000B245
0x14000b225  mov     rcx, [rsp+278h]; this
0x14000b22d  lea     r8, aWil; "wil"
0x14000b234  mov     r9d, eax; char *
0x14000b237  mov     edx, 8Bh; void *
0x14000b23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b241  mov     eax, edi
0x14000b243  jmp     short loc_14000B29A
0x14000b245  lea     r8, asc_140012E3C; "h"
0x14000b24c  shr     rbx, 1Fh
0x14000b250  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x14000b255  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b25a  test    ebx, ebx
0x14000b25c  lea     rcx, [rbp+8]
0x14000b260  lea     r9, [rsp+278h+var_238]
0x14000b265  mov     edx, ebx
0x14000b267  cmovnz  esi, ebx
0x14000b26a  mov     r8d, esi
0x14000b26d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000b272  mov     ebx, eax
0x14000b274  test    eax, eax
0x14000b276  jns     short loc_14000B298
0x14000b278  mov     rcx, [rsp+278h]; this
0x14000b280  lea     r8, aWil; "wil"
0x14000b287  mov     r9d, eax; char *
0x14000b28a  mov     edx, 90h; void *
0x14000b28f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b294  mov     eax, ebx
0x14000b296  jmp     short loc_14000B29A
0x14000b298  xor     eax, eax
0x14000b29a  mov     rcx, [rsp+278h+var_28]
0x14000b2a2  xor     rcx, rsp; StackCookie
0x14000b2a5  call    __security_check_cookie
0x14000b2aa  mov     rbx, [rsp+278h+arg_10]
0x14000b2b2  add     rsp, 260h
0x14000b2b9  pop     rdi
0x14000b2ba  pop     rsi
0x14000b2bb  pop     rbp
0x14000b2bc  retn
```
