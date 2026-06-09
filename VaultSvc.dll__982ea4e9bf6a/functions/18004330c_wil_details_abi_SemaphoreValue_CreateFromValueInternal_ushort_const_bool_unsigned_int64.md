# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18004330c`
- end: `0x18004342d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800440c8`

## callees

- `0x1800031f0`
- `0x180033f94`
- `0x180038c6c`
- `0x18003a580`
- `0x18004330c`
- `0x180045160`
- `0x18004581c`

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
0x18004330c  push    rbx
0x18004330e  push    rbp
0x18004330f  push    rsi
0x180043310  push    rdi
0x180043311  push    r14
0x180043313  sub     rsp, 260h
0x18004331a  mov     rax, cs:__security_cookie
0x180043321  xor     rax, rsp
0x180043324  mov     [rsp+288h+var_38], rax
0x18004332c  mov     rax, 0C000000000000000h
0x180043336  mov     rbx, r9
0x180043339  mov     rbp, rcx
0x18004333c  test    rax, r9
0x18004333f  jz      short loc_180043347
0x180043341  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180043347  mov     r8, rdx; unsigned __int16 *
0x18004334a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18004334f  mov     r14d, 104h
0x180043355  mov     edx, r14d; unsigned __int64
0x180043358  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004335d  lea     r8, aP0; "_p0"
0x180043364  mov     edx, r14d; unsigned __int64
0x180043367  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18004336c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180043371  mov     edx, ebx
0x180043373  lea     r9, [rsp+288h+var_248]
0x180043378  and     edx, 7FFFFFFFh
0x18004337e  mov     esi, 1
0x180043383  mov     r8d, esi
0x180043386  mov     rcx, rbp
0x180043389  cmova   r8d, edx
0x18004338d  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180043392  mov     edi, eax
0x180043394  test    eax, eax
0x180043396  jns     short loc_1800433B7
0x180043398  mov     rcx, [rsp+288h]; this
0x1800433a0  lea     r8, aWil; "wil"
0x1800433a7  mov     r9d, eax; char *
0x1800433aa  lea     edx, [r14-79h]; void *
0x1800433ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800433b3  mov     eax, edi
0x1800433b5  jmp     short loc_18004340F
0x1800433b7  lea     r8, asc_180052FC0; "h"
0x1800433be  shr     rbx, 1Fh
0x1800433c2  mov     rdx, r14; unsigned __int64
0x1800433c5  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800433ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800433cf  test    ebx, ebx
0x1800433d1  lea     rcx, [rbp+8]
0x1800433d5  lea     r9, [rsp+288h+var_248]
0x1800433da  mov     edx, ebx
0x1800433dc  cmovnz  esi, ebx
0x1800433df  mov     r8d, esi
0x1800433e2  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800433e7  mov     ebx, eax
0x1800433e9  test    eax, eax
0x1800433eb  jns     short loc_18004340D
0x1800433ed  mov     rcx, [rsp+288h]; this
0x1800433f5  lea     r8, aWil; "wil"
0x1800433fc  mov     r9d, eax; char *
0x1800433ff  mov     edx, 90h; void *
0x180043404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043409  mov     eax, ebx
0x18004340b  jmp     short loc_18004340F
0x18004340d  xor     eax, eax
0x18004340f  mov     rcx, [rsp+288h+var_38]
0x180043417  xor     rcx, rsp; StackCookie
0x18004341a  call    __security_check_cookie
0x18004341f  add     rsp, 260h
0x180043426  pop     r14
0x180043428  pop     rdi
0x180043429  pop     rsi
0x18004342a  pop     rbp
0x18004342b  pop     rbx
0x18004342c  retn
```
