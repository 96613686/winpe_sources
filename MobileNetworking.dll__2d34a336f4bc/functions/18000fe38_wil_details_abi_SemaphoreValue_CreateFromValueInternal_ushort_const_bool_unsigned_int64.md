# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000fe38`
- end: `0x18000ff4b`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010b38`

## callees

- `0x1800065f0`
- `0x180006630`
- `0x180009850`
- `0x18000fe38`
- `0x180010ee8`
- `0x1800115b4`
- `0x180011634`

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
0x18000fe38  push    rbx
0x18000fe3a  push    rbp
0x18000fe3b  push    rsi
0x18000fe3c  push    rdi
0x18000fe3d  push    r14
0x18000fe3f  sub     rsp, 260h
0x18000fe46  mov     rax, cs:__security_cookie
0x18000fe4d  xor     rax, rsp
0x18000fe50  mov     [rsp+288h+var_38], rax
0x18000fe58  mov     rax, 0C000000000000000h
0x18000fe62  mov     rbx, r9
0x18000fe65  mov     rbp, rcx
0x18000fe68  test    rax, r9
0x18000fe6b  jz      short loc_18000FE73
0x18000fe6d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000fe73  mov     r8, rdx; unsigned __int16 *
0x18000fe76  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000fe7b  mov     r14d, 104h
0x18000fe81  mov     edx, r14d; unsigned __int64
0x18000fe84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fe89  lea     r8, aP0; "_p0"
0x18000fe90  mov     edx, r14d; unsigned __int64
0x18000fe93  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000fe98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fe9d  mov     edx, ebx
0x18000fe9f  lea     r9, [rsp+288h+var_248]
0x18000fea4  and     edx, 7FFFFFFFh
0x18000feaa  mov     esi, 1
0x18000feaf  mov     r8d, esi
0x18000feb2  mov     rcx, rbp
0x18000feb5  cmova   r8d, edx
0x18000feb9  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000febe  mov     edi, eax
0x18000fec0  test    eax, eax
0x18000fec2  jns     short loc_18000FEDC
0x18000fec4  mov     rcx, [rsp+288h]; this
0x18000fecc  lea     edx, [r14-79h]; void *
0x18000fed0  mov     r9d, eax; char *
0x18000fed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fed8  mov     eax, edi
0x18000feda  jmp     short loc_18000FF2D
0x18000fedc  lea     r8, asc_180015AB8; "h"
0x18000fee3  shr     rbx, 1Fh
0x18000fee7  mov     rdx, r14; unsigned __int64
0x18000feea  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000feef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fef4  test    ebx, ebx
0x18000fef6  lea     rcx, [rbp+8]
0x18000fefa  lea     r9, [rsp+288h+var_248]
0x18000feff  mov     edx, ebx
0x18000ff01  cmovnz  esi, ebx
0x18000ff04  mov     r8d, esi
0x18000ff07  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ff0c  mov     ebx, eax
0x18000ff0e  test    eax, eax
0x18000ff10  jns     short loc_18000FF2B
0x18000ff12  mov     rcx, [rsp+288h]; this
0x18000ff1a  mov     r9d, eax; char *
0x18000ff1d  mov     edx, 90h; void *
0x18000ff22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff27  mov     eax, ebx
0x18000ff29  jmp     short loc_18000FF2D
0x18000ff2b  xor     eax, eax
0x18000ff2d  mov     rcx, [rsp+288h+var_38]
0x18000ff35  xor     rcx, rsp; StackCookie
0x18000ff38  call    __security_check_cookie
0x18000ff3d  add     rsp, 260h
0x18000ff44  pop     r14
0x18000ff46  pop     rdi
0x18000ff47  pop     rsi
0x18000ff48  pop     rbp
0x18000ff49  pop     rbx
0x18000ff4a  retn
```
