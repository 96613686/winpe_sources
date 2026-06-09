# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140003ecc`
- end: `0x140003fed`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const wchar_t *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004fb8`
- `0x14000b6cc`

## callees

- `0x140002310`
- `0x140003ecc`
- `0x1400053c0`
- `0x1400056c8`
- `0x140005754`
- `0x140005cc8`
- `0x140005d48`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  LONG v6; // esi
  LONG v7; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v9; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-268h]
  wchar_t v15[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCchCopyW(v15, 0x104u, a2);
  StringCchCatW(v15, 0x104u, L"_p0");
  v6 = 1;
  v7 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v7 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v7, v15);
  v9 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v11 = a4 >> 31;
    StringCchCatW(v15, 0x104u, L"h");
    if ( (_DWORD)v11 )
      v6 = v11;
    v12 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v14);
    return v9;
  }
}

```

## disassembly

```asm
0x140003ecc  push    rbx
0x140003ece  push    rbp
0x140003ecf  push    rsi
0x140003ed0  push    rdi
0x140003ed1  push    r14
0x140003ed3  sub     rsp, 260h
0x140003eda  mov     rax, cs:__security_cookie
0x140003ee1  xor     rax, rsp
0x140003ee4  mov     [rsp+288h+var_38], rax
0x140003eec  mov     rax, 0C000000000000000h
0x140003ef6  mov     rbx, r9
0x140003ef9  mov     rbp, rcx
0x140003efc  test    rax, r9
0x140003eff  jz      short loc_140003F07
0x140003f01  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003f07  mov     r8, rdx; wchar_t *
0x140003f0a  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140003f0f  mov     r14d, 104h
0x140003f15  mov     edx, r14d; unsigned __int64
0x140003f18  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140003f1d  lea     r8, aP0; "_p0"
0x140003f24  mov     edx, r14d; unsigned __int64
0x140003f27  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140003f2c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140003f31  mov     edx, ebx
0x140003f33  lea     r9, [rsp+288h+var_248]
0x140003f38  and     edx, 7FFFFFFFh
0x140003f3e  mov     esi, 1
0x140003f43  mov     r8d, esi
0x140003f46  mov     rcx, rbp
0x140003f49  cmova   r8d, edx
0x140003f4d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003f52  mov     edi, eax
0x140003f54  test    eax, eax
0x140003f56  jns     short loc_140003F77
0x140003f58  mov     rcx, [rsp+288h]; this
0x140003f60  lea     r8, aWil; "wil"
0x140003f67  mov     r9d, eax; char *
0x140003f6a  lea     edx, [r14-79h]; void *
0x140003f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f73  mov     eax, edi
0x140003f75  jmp     short loc_140003FCF
0x140003f77  lea     r8, asc_14002EB90; "h"
0x140003f7e  shr     rbx, 1Fh
0x140003f82  mov     rdx, r14; unsigned __int64
0x140003f85  lea     rcx, [rsp+288h+var_248]; wchar_t *
0x140003f8a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140003f8f  test    ebx, ebx
0x140003f91  lea     rcx, [rbp+8]
0x140003f95  lea     r9, [rsp+288h+var_248]
0x140003f9a  mov     edx, ebx
0x140003f9c  cmovnz  esi, ebx
0x140003f9f  mov     r8d, esi
0x140003fa2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140003fa7  mov     ebx, eax
0x140003fa9  test    eax, eax
0x140003fab  jns     short loc_140003FCD
0x140003fad  mov     rcx, [rsp+288h]; this
0x140003fb5  lea     r8, aWil; "wil"
0x140003fbc  mov     r9d, eax; char *
0x140003fbf  mov     edx, 90h; void *
0x140003fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fc9  mov     eax, ebx
0x140003fcb  jmp     short loc_140003FCF
0x140003fcd  xor     eax, eax
0x140003fcf  mov     rcx, [rsp+288h+var_38]
0x140003fd7  xor     rcx, rsp; StackCookie
0x140003fda  call    __security_check_cookie
0x140003fdf  add     rsp, 260h
0x140003fe6  pop     r14
0x140003fe8  pop     rdi
0x140003fe9  pop     rsi
0x140003fea  pop     rbp
0x140003feb  pop     rbx
0x140003fec  retn
```
