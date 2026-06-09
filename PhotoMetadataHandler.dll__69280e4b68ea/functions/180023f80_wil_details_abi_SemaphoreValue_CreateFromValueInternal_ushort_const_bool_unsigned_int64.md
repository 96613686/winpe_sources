# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180023f80`
- end: `0x180024094`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `276`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001595c`
- `0x180015ab4`

## callees

- `0x18000ab60`
- `0x18000c610`
- `0x180015c10`
- `0x180016a40`
- `0x180023f80`
- `0x180026d28`
- `0x180026dfc`

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
0x180023f80  push    rbx
0x180023f82  push    rbp
0x180023f83  push    rsi
0x180023f84  push    rdi
0x180023f85  push    r14
0x180023f87  sub     rsp, 260h
0x180023f8e  mov     rax, cs:__security_cookie
0x180023f95  xor     rax, rsp
0x180023f98  mov     [rsp+288h+var_38], rax
0x180023fa0  mov     rax, 0C000000000000000h
0x180023faa  mov     rbx, r9
0x180023fad  mov     rbp, rcx
0x180023fb0  test    rax, r9
0x180023fb3  jz      short loc_180023FBB
0x180023fb5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023fbb  mov     r8, rdx; unsigned __int16 *
0x180023fbe  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180023fc3  mov     r14d, 104h
0x180023fc9  mov     edx, r14d; unsigned __int64
0x180023fcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023fd1  lea     r8, aP0; "_p0"
0x180023fd8  mov     edx, r14d; unsigned __int64
0x180023fdb  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180023fe0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023fe5  mov     edx, ebx
0x180023fe7  lea     r9, [rsp+288h+var_248]
0x180023fec  and     edx, 7FFFFFFFh
0x180023ff2  mov     esi, 1
0x180023ff7  mov     r8d, esi
0x180023ffa  mov     rcx, rbp
0x180023ffd  cmova   r8d, edx
0x180024001  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024006  mov     edi, eax
0x180024008  test    eax, eax
0x18002400a  jns     short loc_180024024
0x18002400c  mov     rcx, [rsp+288h]; this
0x180024014  lea     edx, [r14-79h]; void *
0x180024018  mov     r9d, eax; char *
0x18002401b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024020  mov     eax, edi
0x180024022  jmp     short loc_180024075
0x180024024  lea     r8, asc_180092E98; "h"
0x18002402b  shr     rbx, 1Fh
0x18002402f  mov     rdx, r14; unsigned __int64
0x180024032  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180024037  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002403c  test    ebx, ebx
0x18002403e  lea     rcx, [rbp+8]
0x180024042  lea     r9, [rsp+288h+var_248]
0x180024047  mov     edx, ebx
0x180024049  cmovnz  esi, ebx
0x18002404c  mov     r8d, esi
0x18002404f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180024054  mov     ebx, eax
0x180024056  test    eax, eax
0x180024058  jns     short loc_180024073
0x18002405a  mov     rcx, [rsp+288h]; this
0x180024062  mov     r9d, eax; char *
0x180024065  mov     edx, 90h; void *
0x18002406a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002406f  mov     eax, ebx
0x180024071  jmp     short loc_180024075
0x180024073  xor     eax, eax
0x180024075  mov     rcx, [rsp+288h+var_38]
0x18002407d  xor     rcx, rsp; StackCookie
0x180024080  call    __security_check_cookie
0x180024085  add     rsp, 260h
0x18002408c  pop     r14
0x18002408e  pop     rdi
0x18002408f  pop     rsi
0x180024090  pop     rbp
0x180024091  pop     rbx
0x180024092  retn
```
