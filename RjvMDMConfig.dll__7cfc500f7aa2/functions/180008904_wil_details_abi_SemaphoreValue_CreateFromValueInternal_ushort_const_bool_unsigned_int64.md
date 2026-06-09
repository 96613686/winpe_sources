# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180008904`
- end: `0x180008a26`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `290`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b36c`
- `0x18000b4d0`

## callees

- `0x180001c60`
- `0x180008904`
- `0x18000c938`
- `0x18000ff18`
- `0x18000ff80`
- `0x18001132c`
- `0x180011670`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        size_t *a2,
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
0x180008904  push    rbx
0x180008906  push    rbp
0x180008907  push    rsi
0x180008908  push    rdi
0x180008909  push    r14
0x18000890b  sub     rsp, 260h
0x180008912  mov     rax, cs:__security_cookie
0x180008919  xor     rax, rsp
0x18000891c  mov     [rsp+288h+var_38], rax
0x180008924  mov     rax, 0C000000000000000h
0x18000892e  mov     rbx, r9
0x180008931  mov     rbp, rcx
0x180008934  test    rax, r9
0x180008937  jz      short loc_18000893F
0x180008939  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000893f  mov     r8, rdx; unsigned __int16 *
0x180008942  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180008947  mov     r14d, 104h
0x18000894d  mov     edx, r14d; unsigned __int64
0x180008950  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008955  lea     r8, aP0; "_p0"
0x18000895c  mov     edx, r14d; unsigned __int64
0x18000895f  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180008964  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008969  mov     edx, ebx
0x18000896b  lea     r9, [rsp+288h+var_248]
0x180008970  and     edx, 7FFFFFFFh
0x180008976  mov     esi, 1
0x18000897b  mov     r8d, esi
0x18000897e  mov     rcx, rbp
0x180008981  cmova   r8d, edx
0x180008985  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000898a  mov     edi, eax
0x18000898c  test    eax, eax
0x18000898e  jns     short loc_1800089AF
0x180008990  mov     rcx, [rsp+288h]; this
0x180008998  lea     r8, aWil; "wil"
0x18000899f  mov     r9d, eax; char *
0x1800089a2  lea     edx, [r14-79h]; void *
0x1800089a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089ab  mov     eax, edi
0x1800089ad  jmp     short loc_180008A07
0x1800089af  lea     r8, asc_180020F30; "h"
0x1800089b6  shr     rbx, 1Fh
0x1800089ba  mov     rdx, r14; unsigned __int64
0x1800089bd  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800089c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800089c7  test    ebx, ebx
0x1800089c9  lea     rcx, [rbp+8]
0x1800089cd  lea     r9, [rsp+288h+var_248]
0x1800089d2  mov     edx, ebx
0x1800089d4  cmovnz  esi, ebx
0x1800089d7  mov     r8d, esi
0x1800089da  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800089df  mov     ebx, eax
0x1800089e1  test    eax, eax
0x1800089e3  jns     short loc_180008A05
0x1800089e5  mov     rcx, [rsp+288h]; this
0x1800089ed  lea     r8, aWil; "wil"
0x1800089f4  mov     r9d, eax; char *
0x1800089f7  mov     edx, 90h; void *
0x1800089fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a01  mov     eax, ebx
0x180008a03  jmp     short loc_180008A07
0x180008a05  xor     eax, eax
0x180008a07  mov     rcx, [rsp+288h+var_38]
0x180008a0f  xor     rcx, rsp; StackCookie
0x180008a12  call    __security_check_cookie
0x180008a17  add     rsp, 260h
0x180008a1e  pop     r14
0x180008a20  pop     rdi
0x180008a21  pop     rsi
0x180008a22  pop     rbp
0x180008a23  pop     rbx
0x180008a24  retn
```
