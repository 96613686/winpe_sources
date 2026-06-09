# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x18000adbc`
- end: `0x18000aecc`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be74`
- `0x18001f1b8`

## callees

- `0x180008830`
- `0x18000adbc`
- `0x18000c264`
- `0x18000c780`
- `0x18000c7fc`
- `0x18000cd58`
- `0x18000ce34`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-258h]
  wchar_t v19[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v19, 0x104u, a2);
  StringCchCatW(v19, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v19);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(v19, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v18);
    return v12;
  }
}

```

## disassembly

```asm
0x18000adbc  mov     [rsp+arg_10], rbx
0x18000adc1  push    rbp
0x18000adc2  push    rsi
0x18000adc3  push    rdi
0x18000adc4  sub     rsp, 260h
0x18000adcb  mov     rax, cs:__security_cookie
0x18000add2  xor     rax, rsp
0x18000add5  mov     [rsp+278h+var_28], rax
0x18000addd  mov     rax, 0C000000000000000h
0x18000ade7  mov     rbx, r9
0x18000adea  mov     rbp, rcx
0x18000aded  test    rax, r9
0x18000adf0  jz      short loc_18000ADF8
0x18000adf2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000adf8  mov     r8, rdx; wchar_t *
0x18000adfb  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000ae00  mov     edx, 104h; unsigned __int64
0x18000ae05  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ae0a  lea     r8, aP0; "_p0"
0x18000ae11  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000ae16  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ae1b  mov     edx, ebx
0x18000ae1d  lea     r9, [rsp+278h+var_238]
0x18000ae22  and     edx, 7FFFFFFFh
0x18000ae28  mov     esi, 1
0x18000ae2d  mov     r8d, esi
0x18000ae30  mov     rcx, rbp
0x18000ae33  cmova   r8d, edx
0x18000ae37  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ae3c  mov     edi, eax
0x18000ae3e  test    eax, eax
0x18000ae40  jns     short loc_18000AE5B
0x18000ae42  mov     rcx, [rsp+278h]; this
0x18000ae4a  mov     r9d, eax; char *
0x18000ae4d  mov     edx, 8Bh; void *
0x18000ae52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae57  mov     eax, edi
0x18000ae59  jmp     short loc_18000AEA9
0x18000ae5b  lea     r8, asc_18004CEB0; "h"
0x18000ae62  shr     rbx, 1Fh
0x18000ae66  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000ae6b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ae70  test    ebx, ebx
0x18000ae72  lea     rcx, [rbp+8]
0x18000ae76  lea     r9, [rsp+278h+var_238]
0x18000ae7b  mov     edx, ebx
0x18000ae7d  cmovnz  esi, ebx
0x18000ae80  mov     r8d, esi
0x18000ae83  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ae88  mov     ebx, eax
0x18000ae8a  test    eax, eax
0x18000ae8c  jns     short loc_18000AEA7
0x18000ae8e  mov     rcx, [rsp+278h]; this
0x18000ae96  mov     r9d, eax; char *
0x18000ae99  mov     edx, 90h; void *
0x18000ae9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aea3  mov     eax, ebx
0x18000aea5  jmp     short loc_18000AEA9
0x18000aea7  xor     eax, eax
0x18000aea9  mov     rcx, [rsp+278h+var_28]
0x18000aeb1  xor     rcx, rsp; StackCookie
0x18000aeb4  call    __security_check_cookie
0x18000aeb9  mov     rbx, [rsp+278h+arg_10]
0x18000aec1  add     rsp, 260h
0x18000aec8  pop     rdi
0x18000aec9  pop     rsi
0x18000aeca  pop     rbp
0x18000aecb  retn
```
