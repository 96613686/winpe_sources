# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004fe4`
- end: `0x140005105`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400062e8`
- `0x14000bc54`

## callees

- `0x140002930`
- `0x140004fe4`
- `0x140006984`
- `0x140007230`
- `0x140007324`
- `0x140007994`
- `0x140007ac8`

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
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v11,
            v6,
            v15);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"wil",
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x140004fe4  push    rbx
0x140004fe6  push    rbp
0x140004fe7  push    rsi
0x140004fe8  push    rdi
0x140004fe9  push    r14
0x140004feb  sub     rsp, 260h
0x140004ff2  mov     rax, cs:__security_cookie
0x140004ff9  xor     rax, rsp
0x140004ffc  mov     [rsp+288h+var_38], rax
0x140005004  mov     rax, 0C000000000000000h
0x14000500e  mov     rbx, r9
0x140005011  mov     rbp, rcx
0x140005014  test    rax, r9
0x140005017  jz      short loc_14000501F
0x140005019  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000501f  mov     r8, rdx; unsigned __int16 *
0x140005022  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005027  mov     r14d, 104h
0x14000502d  mov     edx, r14d; unsigned __int64
0x140005030  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005035  lea     r8, aP0; "_p0"
0x14000503c  mov     edx, r14d; unsigned __int64
0x14000503f  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140005044  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005049  mov     edx, ebx
0x14000504b  lea     r9, [rsp+288h+var_248]
0x140005050  and     edx, 7FFFFFFFh
0x140005056  mov     esi, 1
0x14000505b  mov     r8d, esi
0x14000505e  mov     rcx, rbp
0x140005061  cmova   r8d, edx
0x140005065  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14000506a  mov     edi, eax
0x14000506c  test    eax, eax
0x14000506e  jns     short loc_14000508F
0x140005070  mov     rcx, [rsp+288h]; this
0x140005078  lea     r8, aWil; "wil"
0x14000507f  mov     r9d, eax; char *
0x140005082  lea     edx, [r14-79h]; void *
0x140005086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000508b  mov     eax, edi
0x14000508d  jmp     short loc_1400050E7
0x14000508f  lea     r8, asc_14001B068; "h"
0x140005096  shr     rbx, 1Fh
0x14000509a  mov     rdx, r14; unsigned __int64
0x14000509d  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1400050a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400050a7  test    ebx, ebx
0x1400050a9  lea     rcx, [rbp+8]
0x1400050ad  lea     r9, [rsp+288h+var_248]
0x1400050b2  mov     edx, ebx
0x1400050b4  cmovnz  esi, ebx
0x1400050b7  mov     r8d, esi
0x1400050ba  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400050bf  mov     ebx, eax
0x1400050c1  test    eax, eax
0x1400050c3  jns     short loc_1400050E5
0x1400050c5  mov     rcx, [rsp+288h]; this
0x1400050cd  lea     r8, aWil; "wil"
0x1400050d4  mov     r9d, eax; char *
0x1400050d7  mov     edx, 90h; void *
0x1400050dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400050e1  mov     eax, ebx
0x1400050e3  jmp     short loc_1400050E7
0x1400050e5  xor     eax, eax
0x1400050e7  mov     rcx, [rsp+288h+var_38]
0x1400050ef  xor     rcx, rsp; StackCookie
0x1400050f2  call    __security_check_cookie
0x1400050f7  add     rsp, 260h
0x1400050fe  pop     r14
0x140005100  pop     rdi
0x140005101  pop     rsi
0x140005102  pop     rbp
0x140005103  pop     rbx
0x140005104  retn
```
