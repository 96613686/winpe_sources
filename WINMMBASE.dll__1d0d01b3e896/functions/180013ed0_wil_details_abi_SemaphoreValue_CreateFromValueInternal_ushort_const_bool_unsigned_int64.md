# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180013ed0`
- end: `0x180013fe4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015214`

## callees

- `0x18000da80`
- `0x1800106c0`
- `0x180013ed0`
- `0x180015a94`
- `0x180015fd4`
- `0x180016514`
- `0x180016614`

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
0x180013ed0  mov     [rsp+arg_10], rbx
0x180013ed5  push    rbp
0x180013ed6  push    rsi
0x180013ed7  push    rdi
0x180013ed8  sub     rsp, 260h
0x180013edf  mov     rax, cs:__security_cookie
0x180013ee6  xor     rax, rsp
0x180013ee9  mov     [rsp+278h+var_28], rax
0x180013ef1  mov     rax, 0C000000000000000h
0x180013efb  mov     rbx, r9
0x180013efe  mov     rbp, rcx
0x180013f01  test    rax, r9
0x180013f04  jnz     loc_180013FDE
0x180013f0a  mov     r8, rdx; unsigned __int16 *
0x180013f0d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180013f12  mov     edx, 104h; unsigned __int64
0x180013f17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013f1c  lea     r8, aP0; "_p0"
0x180013f23  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180013f28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013f2d  mov     edx, ebx
0x180013f2f  lea     r9, [rsp+278h+var_238]
0x180013f34  and     edx, 7FFFFFFFh
0x180013f3a  mov     esi, 1
0x180013f3f  mov     r8d, esi
0x180013f42  mov     rcx, rbp
0x180013f45  cmova   r8d, edx
0x180013f49  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180013f4e  mov     edi, eax
0x180013f50  test    eax, eax
0x180013f52  jns     short loc_180013F6D
0x180013f54  mov     rcx, [rsp+278h]; this
0x180013f5c  mov     r9d, eax; char *
0x180013f5f  mov     edx, 8Bh; void *
0x180013f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f69  mov     eax, edi
0x180013f6b  jmp     short loc_180013FBB
0x180013f6d  lea     r8, asc_180025B08; "h"
0x180013f74  shr     rbx, 1Fh
0x180013f78  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180013f7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013f82  test    ebx, ebx
0x180013f84  lea     rcx, [rbp+8]
0x180013f88  lea     r9, [rsp+278h+var_238]
0x180013f8d  mov     edx, ebx
0x180013f8f  cmovnz  esi, ebx
0x180013f92  mov     r8d, esi
0x180013f95  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180013f9a  mov     ebx, eax
0x180013f9c  test    eax, eax
0x180013f9e  jns     short loc_180013FB9
0x180013fa0  mov     rcx, [rsp+278h]; this
0x180013fa8  mov     r9d, eax; char *
0x180013fab  mov     edx, 90h; void *
0x180013fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fb5  mov     eax, ebx
0x180013fb7  jmp     short loc_180013FBB
0x180013fb9  xor     eax, eax
0x180013fbb  mov     rcx, [rsp+278h+var_28]
0x180013fc3  xor     rcx, rsp; StackCookie
0x180013fc6  call    __security_check_cookie
0x180013fcb  mov     rbx, [rsp+278h+arg_10]
0x180013fd3  add     rsp, 260h
0x180013fda  pop     rdi
0x180013fdb  pop     rsi
0x180013fdc  pop     rbp
0x180013fdd  retn
0x180013fde  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
