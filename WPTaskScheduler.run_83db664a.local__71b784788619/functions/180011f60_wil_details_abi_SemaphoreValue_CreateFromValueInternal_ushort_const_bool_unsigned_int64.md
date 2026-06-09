# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180011f60`
- end: `0x180012074`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800135dc`
- `0x180013704`

## callees

- `0x18000be70`
- `0x180011f60`
- `0x1800147ac`
- `0x180014e74`
- `0x1800163fc`
- `0x18001685c`
- `0x180020c30`

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
0x180011f60  mov     [rsp+arg_10], rbx
0x180011f65  push    rbp
0x180011f66  push    rsi
0x180011f67  push    rdi
0x180011f68  sub     rsp, 260h
0x180011f6f  mov     rax, cs:__security_cookie
0x180011f76  xor     rax, rsp
0x180011f79  mov     [rsp+278h+var_28], rax
0x180011f81  mov     rax, 0C000000000000000h
0x180011f8b  mov     rbx, r9
0x180011f8e  mov     rbp, rcx
0x180011f91  test    rax, r9
0x180011f94  jnz     loc_18001206E
0x180011f9a  mov     r8, rdx; unsigned __int16 *
0x180011f9d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180011fa2  mov     edx, 104h; unsigned __int64
0x180011fa7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011fac  lea     r8, aP0; "_p0"
0x180011fb3  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180011fb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011fbd  mov     edx, ebx
0x180011fbf  lea     r9, [rsp+278h+var_238]
0x180011fc4  and     edx, 7FFFFFFFh
0x180011fca  mov     esi, 1
0x180011fcf  mov     r8d, esi
0x180011fd2  mov     rcx, rbp
0x180011fd5  cmova   r8d, edx
0x180011fd9  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011fde  mov     edi, eax
0x180011fe0  test    eax, eax
0x180011fe2  jns     short loc_180011FFD
0x180011fe4  mov     rcx, [rsp+278h]; this
0x180011fec  mov     r9d, eax; char *
0x180011fef  mov     edx, 8Bh; void *
0x180011ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ff9  mov     eax, edi
0x180011ffb  jmp     short loc_18001204B
0x180011ffd  lea     r8, asc_1800289C0; "h"
0x180012004  shr     rbx, 1Fh
0x180012008  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x18001200d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012012  test    ebx, ebx
0x180012014  lea     rcx, [rbp+8]
0x180012018  lea     r9, [rsp+278h+var_238]
0x18001201d  mov     edx, ebx
0x18001201f  cmovnz  esi, ebx
0x180012022  mov     r8d, esi
0x180012025  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001202a  mov     ebx, eax
0x18001202c  test    eax, eax
0x18001202e  jns     short loc_180012049
0x180012030  mov     rcx, [rsp+278h]; this
0x180012038  mov     r9d, eax; char *
0x18001203b  mov     edx, 90h; void *
0x180012040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012045  mov     eax, ebx
0x180012047  jmp     short loc_18001204B
0x180012049  xor     eax, eax
0x18001204b  mov     rcx, [rsp+278h+var_28]
0x180012053  xor     rcx, rsp; StackCookie
0x180012056  call    __security_check_cookie
0x18001205b  mov     rbx, [rsp+278h+arg_10]
0x180012063  add     rsp, 260h
0x18001206a  pop     rdi
0x18001206b  pop     rsi
0x18001206c  pop     rbp
0x18001206d  retn
0x18001206e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
