# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800057d0`
- end: `0x1800058f1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006fa8`
- `0x1800070d8`

## callees

- `0x1800020c0`
- `0x1800057d0`
- `0x1800087bc`
- `0x180008e7c`
- `0x180008f08`
- `0x180009c20`
- `0x180009dd8`

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
0x1800057d0  push    rbx
0x1800057d2  push    rbp
0x1800057d3  push    rsi
0x1800057d4  push    rdi
0x1800057d5  push    r14
0x1800057d7  sub     rsp, 260h
0x1800057de  mov     rax, cs:__security_cookie
0x1800057e5  xor     rax, rsp
0x1800057e8  mov     [rsp+288h+var_38], rax
0x1800057f0  mov     rax, 0C000000000000000h
0x1800057fa  mov     rbx, r9
0x1800057fd  mov     rbp, rcx
0x180005800  test    rax, r9
0x180005803  jz      short loc_18000580B
0x180005805  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000580b  mov     r8, rdx; unsigned __int16 *
0x18000580e  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180005813  mov     r14d, 104h
0x180005819  mov     edx, r14d; unsigned __int64
0x18000581c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005821  lea     r8, aP0; "_p0"
0x180005828  mov     edx, r14d; unsigned __int64
0x18000582b  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180005830  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005835  mov     edx, ebx
0x180005837  lea     r9, [rsp+288h+var_248]
0x18000583c  and     edx, 7FFFFFFFh
0x180005842  mov     esi, 1
0x180005847  mov     r8d, esi
0x18000584a  mov     rcx, rbp
0x18000584d  cmova   r8d, edx
0x180005851  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005856  mov     edi, eax
0x180005858  test    eax, eax
0x18000585a  jns     short loc_18000587B
0x18000585c  mov     rcx, [rsp+288h]; this
0x180005864  lea     r8, aWil; "wil"
0x18000586b  mov     r9d, eax; char *
0x18000586e  lea     edx, [r14-79h]; void *
0x180005872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005877  mov     eax, edi
0x180005879  jmp     short loc_1800058D3
0x18000587b  lea     r8, asc_18001A158; "h"
0x180005882  shr     rbx, 1Fh
0x180005886  mov     rdx, r14; unsigned __int64
0x180005889  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000588e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005893  test    ebx, ebx
0x180005895  lea     rcx, [rbp+8]
0x180005899  lea     r9, [rsp+288h+var_248]
0x18000589e  mov     edx, ebx
0x1800058a0  cmovnz  esi, ebx
0x1800058a3  mov     r8d, esi
0x1800058a6  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800058ab  mov     ebx, eax
0x1800058ad  test    eax, eax
0x1800058af  jns     short loc_1800058D1
0x1800058b1  mov     rcx, [rsp+288h]; this
0x1800058b9  lea     r8, aWil; "wil"
0x1800058c0  mov     r9d, eax; char *
0x1800058c3  mov     edx, 90h; void *
0x1800058c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058cd  mov     eax, ebx
0x1800058cf  jmp     short loc_1800058D3
0x1800058d1  xor     eax, eax
0x1800058d3  mov     rcx, [rsp+288h+var_38]
0x1800058db  xor     rcx, rsp; StackCookie
0x1800058de  call    __security_check_cookie
0x1800058e3  add     rsp, 260h
0x1800058ea  pop     r14
0x1800058ec  pop     rdi
0x1800058ed  pop     rsi
0x1800058ee  pop     rbp
0x1800058ef  pop     rbx
0x1800058f0  retn
```
