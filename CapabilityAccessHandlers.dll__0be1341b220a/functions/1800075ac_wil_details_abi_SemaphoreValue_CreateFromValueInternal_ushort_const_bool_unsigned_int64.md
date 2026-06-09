# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800075ac`
- end: `0x1800076ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800089b0`
- `0x18000c01c`

## callees

- `0x180004c70`
- `0x1800075ac`
- `0x1800090f4`
- `0x180009610`
- `0x18000968c`
- `0x180009bb4`
- `0x180009c78`

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
  StringCchCopyW(v17, 0x104u, a2);
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
0x1800075ac  mov     [rsp+arg_10], rbx
0x1800075b1  push    rbp
0x1800075b2  push    rsi
0x1800075b3  push    rdi
0x1800075b4  sub     rsp, 260h
0x1800075bb  mov     rax, cs:__security_cookie
0x1800075c2  xor     rax, rsp
0x1800075c5  mov     [rsp+278h+var_28], rax
0x1800075cd  mov     rax, 0C000000000000000h
0x1800075d7  mov     rbx, r9
0x1800075da  mov     rbp, rcx
0x1800075dd  test    rax, r9
0x1800075e0  jz      short loc_1800075E8
0x1800075e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800075e8  mov     r8, rdx; unsigned __int16 *
0x1800075eb  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800075f0  mov     edx, 104h; unsigned __int64
0x1800075f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800075fa  lea     r8, aP0; "_p0"
0x180007601  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180007606  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000760b  mov     edx, ebx
0x18000760d  lea     r9, [rsp+278h+var_238]
0x180007612  and     edx, 7FFFFFFFh
0x180007618  mov     esi, 1
0x18000761d  mov     r8d, esi
0x180007620  mov     rcx, rbp
0x180007623  cmova   r8d, edx
0x180007627  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000762c  mov     edi, eax
0x18000762e  test    eax, eax
0x180007630  jns     short loc_180007652
0x180007632  mov     rcx, [rsp+278h]; this
0x18000763a  lea     r8, aWil; "wil"
0x180007641  mov     r9d, eax; char *
0x180007644  mov     edx, 8Bh; void *
0x180007649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000764e  mov     eax, edi
0x180007650  jmp     short loc_1800076A7
0x180007652  lea     r8, asc_180016BA0; "h"
0x180007659  shr     rbx, 1Fh
0x18000765d  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180007662  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007667  test    ebx, ebx
0x180007669  lea     rcx, [rbp+8]
0x18000766d  lea     r9, [rsp+278h+var_238]
0x180007672  mov     edx, ebx
0x180007674  cmovnz  esi, ebx
0x180007677  mov     r8d, esi
0x18000767a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000767f  mov     ebx, eax
0x180007681  test    eax, eax
0x180007683  jns     short loc_1800076A5
0x180007685  mov     rcx, [rsp+278h]; this
0x18000768d  lea     r8, aWil; "wil"
0x180007694  mov     r9d, eax; char *
0x180007697  mov     edx, 90h; void *
0x18000769c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076a1  mov     eax, ebx
0x1800076a3  jmp     short loc_1800076A7
0x1800076a5  xor     eax, eax
0x1800076a7  mov     rcx, [rsp+278h+var_28]
0x1800076af  xor     rcx, rsp; StackCookie
0x1800076b2  call    __security_check_cookie
0x1800076b7  mov     rbx, [rsp+278h+arg_10]
0x1800076bf  add     rsp, 260h
0x1800076c6  pop     rdi
0x1800076c7  pop     rsi
0x1800076c8  pop     rbp
0x1800076c9  retn
```
