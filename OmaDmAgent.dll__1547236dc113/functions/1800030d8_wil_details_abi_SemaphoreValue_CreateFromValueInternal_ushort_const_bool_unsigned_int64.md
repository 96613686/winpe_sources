# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800030d8`
- end: `0x1800031e9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `273`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800045f8`

## callees

- `0x1800030d8`
- `0x180005434`
- `0x180005928`
- `0x1800059a8`
- `0x1800060cc`
- `0x180006730`
- `0x18001f420`

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
0x1800030d8  mov     [rsp+arg_10], rbx
0x1800030dd  push    rbp
0x1800030de  push    rsi
0x1800030df  push    rdi
0x1800030e0  sub     rsp, 260h
0x1800030e7  mov     rax, cs:__security_cookie
0x1800030ee  xor     rax, rsp
0x1800030f1  mov     [rsp+278h+var_28], rax
0x1800030f9  mov     rax, 0C000000000000000h
0x180003103  mov     rbx, r9
0x180003106  mov     rbp, rcx
0x180003109  test    rax, r9
0x18000310c  jz      short loc_180003114
0x18000310e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003114  mov     r8, rdx; unsigned __int16 *
0x180003117  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18000311c  mov     edx, 104h; unsigned __int64
0x180003121  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003126  lea     r8, aP0; "_p0"
0x18000312d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003132  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003137  mov     edx, ebx
0x180003139  lea     r9, [rsp+278h+var_238]
0x18000313e  and     edx, 7FFFFFFFh
0x180003144  mov     esi, 1
0x180003149  mov     r8d, esi
0x18000314c  mov     rcx, rbp
0x18000314f  cmova   r8d, edx
0x180003153  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003158  mov     edi, eax
0x18000315a  test    eax, eax
0x18000315c  jns     short loc_180003177
0x18000315e  mov     rcx, [rsp+278h]; this
0x180003166  mov     r9d, eax; char *
0x180003169  mov     edx, 8Bh; void *
0x18000316e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003173  mov     eax, edi
0x180003175  jmp     short loc_1800031C5
0x180003177  lea     r8, asc_180023218; "h"
0x18000317e  shr     rbx, 1Fh
0x180003182  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003187  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000318c  test    ebx, ebx
0x18000318e  lea     rcx, [rbp+8]
0x180003192  lea     r9, [rsp+278h+var_238]
0x180003197  mov     edx, ebx
0x180003199  cmovnz  esi, ebx
0x18000319c  mov     r8d, esi
0x18000319f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800031a4  mov     ebx, eax
0x1800031a6  test    eax, eax
0x1800031a8  jns     short loc_1800031C3
0x1800031aa  mov     rcx, [rsp+278h]; this
0x1800031b2  mov     r9d, eax; char *
0x1800031b5  mov     edx, 90h; void *
0x1800031ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031bf  mov     eax, ebx
0x1800031c1  jmp     short loc_1800031C5
0x1800031c3  xor     eax, eax
0x1800031c5  mov     rcx, [rsp+278h+var_28]
0x1800031cd  xor     rcx, rsp; StackCookie
0x1800031d0  call    __security_check_cookie
0x1800031d5  mov     rbx, [rsp+278h+arg_10]
0x1800031dd  add     rsp, 260h
0x1800031e4  pop     rdi
0x1800031e5  pop     rsi
0x1800031e6  pop     rbp
0x1800031e7  retn
```
