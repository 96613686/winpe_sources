# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180022e3c`
- end: `0x180022f4f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f50`
- `0x1800150a4`

## callees

- `0x18000af20`
- `0x18000c060`
- `0x180015200`
- `0x180016020`
- `0x180022e3c`
- `0x180025af4`
- `0x180025bc8`

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
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned __int64 v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-268h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v17);
  v10 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v12 = a4 >> 31;
    StringCchCatW(v17, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v6 = v12;
    v13 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v12,
            v6,
            v17);
    v15 = v13;
    if ( v13 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v14, (const char *)(unsigned int)v13, v16);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v9,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180022e3c  push    rbx
0x180022e3e  push    rbp
0x180022e3f  push    rsi
0x180022e40  push    rdi
0x180022e41  push    r14
0x180022e43  sub     rsp, 260h
0x180022e4a  mov     rax, cs:__security_cookie
0x180022e51  xor     rax, rsp
0x180022e54  mov     [rsp+288h+var_38], rax
0x180022e5c  mov     rax, 0C000000000000000h
0x180022e66  mov     rbx, r9
0x180022e69  mov     rbp, rcx
0x180022e6c  test    rax, r9
0x180022e6f  jz      short loc_180022E77
0x180022e71  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180022e77  mov     r8, rdx; unsigned __int16 *
0x180022e7a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180022e7f  mov     r14d, 104h
0x180022e85  mov     edx, r14d; unsigned __int64
0x180022e88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022e8d  lea     r8, aP0; "_p0"
0x180022e94  mov     edx, r14d; unsigned __int64
0x180022e97  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180022e9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022ea1  mov     edx, ebx
0x180022ea3  lea     r9, [rsp+288h+var_248]
0x180022ea8  and     edx, 7FFFFFFFh
0x180022eae  mov     esi, 1
0x180022eb3  mov     r8d, esi
0x180022eb6  mov     rcx, rbp
0x180022eb9  cmova   r8d, edx
0x180022ebd  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180022ec2  mov     edi, eax
0x180022ec4  test    eax, eax
0x180022ec6  jns     short loc_180022EE0
0x180022ec8  mov     rcx, [rsp+288h]; this
0x180022ed0  lea     edx, [r14-79h]; void *
0x180022ed4  mov     r9d, eax; char *
0x180022ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022edc  mov     eax, edi
0x180022ede  jmp     short loc_180022F31
0x180022ee0  lea     r8, asc_180091ED8; "h"
0x180022ee7  shr     rbx, 1Fh
0x180022eeb  mov     rdx, r14; unsigned __int64
0x180022eee  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180022ef3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022ef8  test    ebx, ebx
0x180022efa  lea     rcx, [rbp+8]
0x180022efe  lea     r9, [rsp+288h+var_248]
0x180022f03  mov     edx, ebx
0x180022f05  cmovnz  esi, ebx
0x180022f08  mov     r8d, esi
0x180022f0b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180022f10  mov     ebx, eax
0x180022f12  test    eax, eax
0x180022f14  jns     short loc_180022F2F
0x180022f16  mov     rcx, [rsp+288h]; this
0x180022f1e  mov     r9d, eax; char *
0x180022f21  mov     edx, 90h; void *
0x180022f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f2b  mov     eax, ebx
0x180022f2d  jmp     short loc_180022F31
0x180022f2f  xor     eax, eax
0x180022f31  mov     rcx, [rsp+288h+var_38]
0x180022f39  xor     rcx, rsp; StackCookie
0x180022f3c  call    __security_check_cookie
0x180022f41  add     rsp, 260h
0x180022f48  pop     r14
0x180022f4a  pop     rdi
0x180022f4b  pop     rsi
0x180022f4c  pop     rbp
0x180022f4d  pop     rbx
0x180022f4e  retn
```
