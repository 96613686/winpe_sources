# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000bb60`
- end: `0x18000bc73`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c9ac`

## callees

- `0x180005d40`
- `0x1800097d0`
- `0x18000bb60`
- `0x18000ce54`
- `0x18000d32c`
- `0x18000d84c`
- `0x18000d910`

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
0x18000bb60  push    rbx
0x18000bb62  push    rbp
0x18000bb63  push    rsi
0x18000bb64  push    rdi
0x18000bb65  push    r14
0x18000bb67  sub     rsp, 260h
0x18000bb6e  mov     rax, cs:__security_cookie
0x18000bb75  xor     rax, rsp
0x18000bb78  mov     [rsp+288h+var_38], rax
0x18000bb80  mov     rax, 0C000000000000000h
0x18000bb8a  mov     rbx, r9
0x18000bb8d  mov     rbp, rcx
0x18000bb90  test    rax, r9
0x18000bb93  jz      short loc_18000BB9B
0x18000bb95  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bb9b  mov     r8, rdx; unsigned __int16 *
0x18000bb9e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000bba3  mov     r14d, 104h
0x18000bba9  mov     edx, r14d; unsigned __int64
0x18000bbac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bbb1  lea     r8, aP0; "_p0"
0x18000bbb8  mov     edx, r14d; unsigned __int64
0x18000bbbb  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000bbc0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bbc5  mov     edx, ebx
0x18000bbc7  lea     r9, [rsp+288h+var_248]
0x18000bbcc  and     edx, 7FFFFFFFh
0x18000bbd2  mov     esi, 1
0x18000bbd7  mov     r8d, esi
0x18000bbda  mov     rcx, rbp
0x18000bbdd  cmova   r8d, edx
0x18000bbe1  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000bbe6  mov     edi, eax
0x18000bbe8  test    eax, eax
0x18000bbea  jns     short loc_18000BC04
0x18000bbec  mov     rcx, [rsp+288h]; this
0x18000bbf4  lea     edx, [r14-79h]; void *
0x18000bbf8  mov     r9d, eax; char *
0x18000bbfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc00  mov     eax, edi
0x18000bc02  jmp     short loc_18000BC55
0x18000bc04  lea     r8, asc_180018610; "h"
0x18000bc0b  shr     rbx, 1Fh
0x18000bc0f  mov     rdx, r14; unsigned __int64
0x18000bc12  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000bc17  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc1c  test    ebx, ebx
0x18000bc1e  lea     rcx, [rbp+8]
0x18000bc22  lea     r9, [rsp+288h+var_248]
0x18000bc27  mov     edx, ebx
0x18000bc29  cmovnz  esi, ebx
0x18000bc2c  mov     r8d, esi
0x18000bc2f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000bc34  mov     ebx, eax
0x18000bc36  test    eax, eax
0x18000bc38  jns     short loc_18000BC53
0x18000bc3a  mov     rcx, [rsp+288h]; this
0x18000bc42  mov     r9d, eax; char *
0x18000bc45  mov     edx, 90h; void *
0x18000bc4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc4f  mov     eax, ebx
0x18000bc51  jmp     short loc_18000BC55
0x18000bc53  xor     eax, eax
0x18000bc55  mov     rcx, [rsp+288h+var_38]
0x18000bc5d  xor     rcx, rsp; StackCookie
0x18000bc60  call    __security_check_cookie
0x18000bc65  add     rsp, 260h
0x18000bc6c  pop     r14
0x18000bc6e  pop     rdi
0x18000bc6f  pop     rsi
0x18000bc70  pop     rbp
0x18000bc71  pop     rbx
0x18000bc72  retn
```
