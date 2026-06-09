# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800044d0`
- end: `0x1800045ee`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005610`
- `0x18000accc`

## callees

- `0x1800027c0`
- `0x1800044d0`
- `0x180005c34`
- `0x180006154`
- `0x1800061d0`
- `0x180006830`
- `0x1800068f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v11; // edi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-258h]
  wchar_t v17[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v17, 0x104u, a2);
  StringCchCatW(v17, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, v17);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(v17, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x1800044d0  mov     [rsp+arg_10], rbx
0x1800044d5  push    rbp
0x1800044d6  push    rsi
0x1800044d7  push    rdi
0x1800044d8  sub     rsp, 260h
0x1800044df  mov     rax, cs:__security_cookie
0x1800044e6  xor     rax, rsp
0x1800044e9  mov     [rsp+278h+var_28], rax
0x1800044f1  mov     rax, 0C000000000000000h
0x1800044fb  mov     rbx, r9
0x1800044fe  mov     rbp, rcx
0x180004501  test    rax, r9
0x180004504  jz      short loc_18000450C
0x180004506  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000450c  mov     r8, rdx; wchar_t *
0x18000450f  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180004514  mov     edx, 104h; unsigned __int64
0x180004519  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000451e  lea     r8, aP0; "_p0"
0x180004525  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x18000452a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000452f  mov     edx, ebx
0x180004531  lea     r9, [rsp+278h+var_238]
0x180004536  and     edx, 7FFFFFFFh
0x18000453c  mov     esi, 1
0x180004541  mov     r8d, esi
0x180004544  mov     rcx, rbp
0x180004547  cmova   r8d, edx
0x18000454b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004550  mov     edi, eax
0x180004552  test    eax, eax
0x180004554  jns     short loc_180004576
0x180004556  mov     rcx, [rsp+278h]; this
0x18000455e  lea     r8, aWil; "wil"
0x180004565  mov     r9d, eax; char *
0x180004568  mov     edx, 8Bh; void *
0x18000456d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004572  mov     eax, edi
0x180004574  jmp     short loc_1800045CB
0x180004576  lea     r8, asc_1800366D8; "h"
0x18000457d  shr     rbx, 1Fh
0x180004581  lea     rcx, [rsp+278h+var_238]; wchar_t *
0x180004586  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000458b  test    ebx, ebx
0x18000458d  lea     rcx, [rbp+8]
0x180004591  lea     r9, [rsp+278h+var_238]
0x180004596  mov     edx, ebx
0x180004598  cmovnz  esi, ebx
0x18000459b  mov     r8d, esi
0x18000459e  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800045a3  mov     ebx, eax
0x1800045a5  test    eax, eax
0x1800045a7  jns     short loc_1800045C9
0x1800045a9  mov     rcx, [rsp+278h]; this
0x1800045b1  lea     r8, aWil; "wil"
0x1800045b8  mov     r9d, eax; char *
0x1800045bb  mov     edx, 90h; void *
0x1800045c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045c5  mov     eax, ebx
0x1800045c7  jmp     short loc_1800045CB
0x1800045c9  xor     eax, eax
0x1800045cb  mov     rcx, [rsp+278h+var_28]
0x1800045d3  xor     rcx, rsp; StackCookie
0x1800045d6  call    __security_check_cookie
0x1800045db  mov     rbx, [rsp+278h+arg_10]
0x1800045e3  add     rsp, 260h
0x1800045ea  pop     rdi
0x1800045eb  pop     rsi
0x1800045ec  pop     rbp
0x1800045ed  retn
```
