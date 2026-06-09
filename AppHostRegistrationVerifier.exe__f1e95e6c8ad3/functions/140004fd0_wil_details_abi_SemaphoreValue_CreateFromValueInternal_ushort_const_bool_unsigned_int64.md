# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004fd0`
- end: `0x1400050e3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `275`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400062dc`

## callees

- `0x140002210`
- `0x140004fd0`
- `0x140006a54`
- `0x140006fc0`
- `0x14000704c`
- `0x14000768c`
- `0x1400078e4`

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
0x140004fd0  push    rbx
0x140004fd2  push    rbp
0x140004fd3  push    rsi
0x140004fd4  push    rdi
0x140004fd5  push    r14
0x140004fd7  sub     rsp, 260h
0x140004fde  mov     rax, cs:__security_cookie
0x140004fe5  xor     rax, rsp
0x140004fe8  mov     [rsp+288h+var_38], rax
0x140004ff0  mov     rax, 0C000000000000000h
0x140004ffa  mov     rbx, r9
0x140004ffd  mov     rbp, rcx
0x140005000  test    rax, r9
0x140005003  jz      short loc_14000500B
0x140005005  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000500b  mov     r8, rdx; unsigned __int16 *
0x14000500e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005013  mov     r14d, 104h
0x140005019  mov     edx, r14d; unsigned __int64
0x14000501c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005021  lea     r8, aP0; "_p0"
0x140005028  mov     edx, r14d; unsigned __int64
0x14000502b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005030  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005035  mov     edx, ebx
0x140005037  lea     r9, [rsp+288h+var_248]
0x14000503c  and     edx, 7FFFFFFFh
0x140005042  mov     esi, 1
0x140005047  mov     r8d, esi
0x14000504a  mov     rcx, rbp
0x14000504d  cmova   r8d, edx
0x140005051  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140005056  mov     edi, eax
0x140005058  test    eax, eax
0x14000505a  jns     short loc_140005074
0x14000505c  mov     rcx, [rsp+288h]; this
0x140005064  lea     edx, [r14-79h]; void *
0x140005068  mov     r9d, eax; char *
0x14000506b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005070  mov     eax, edi
0x140005072  jmp     short loc_1400050C5
0x140005074  lea     r8, asc_140014388; "h"
0x14000507b  shr     rbx, 1Fh
0x14000507f  mov     rdx, r14; unsigned __int64
0x140005082  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005087  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000508c  test    ebx, ebx
0x14000508e  lea     rcx, [rbp+8]
0x140005092  lea     r9, [rsp+288h+var_248]
0x140005097  mov     edx, ebx
0x140005099  cmovnz  esi, ebx
0x14000509c  mov     r8d, esi
0x14000509f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400050a4  mov     ebx, eax
0x1400050a6  test    eax, eax
0x1400050a8  jns     short loc_1400050C3
0x1400050aa  mov     rcx, [rsp+288h]; this
0x1400050b2  mov     r9d, eax; char *
0x1400050b5  mov     edx, 90h; void *
0x1400050ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400050bf  mov     eax, ebx
0x1400050c1  jmp     short loc_1400050C5
0x1400050c3  xor     eax, eax
0x1400050c5  mov     rcx, [rsp+288h+var_38]
0x1400050cd  xor     rcx, rsp; StackCookie
0x1400050d0  call    __security_check_cookie
0x1400050d5  add     rsp, 260h
0x1400050dc  pop     r14
0x1400050de  pop     rdi
0x1400050df  pop     rsi
0x1400050e0  pop     rbp
0x1400050e1  pop     rbx
0x1400050e2  retn
```
