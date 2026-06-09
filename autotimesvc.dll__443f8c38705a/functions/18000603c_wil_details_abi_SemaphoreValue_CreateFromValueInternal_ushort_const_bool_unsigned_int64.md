# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000603c`
- end: `0x18000615a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007e70`

## callees

- `0x180002a70`
- `0x18000603c`
- `0x180009194`
- `0x1800099e4`
- `0x180009b0c`
- `0x18000a348`
- `0x18000a834`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const unsigned __int16 *a2,
        size_t *a3,
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
  size_t v16; // [rsp+20h] [rbp-258h]
  int v17; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v13,
            v7,
            pszDest);
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
        v17);
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
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x18000603c  mov     [rsp+arg_10], rbx
0x180006041  push    rbp
0x180006042  push    rsi
0x180006043  push    rdi
0x180006044  sub     rsp, 260h
0x18000604b  mov     rax, cs:__security_cookie
0x180006052  xor     rax, rsp
0x180006055  mov     [rsp+278h+var_28], rax
0x18000605d  mov     rax, 0C000000000000000h
0x180006067  mov     rbx, r9
0x18000606a  mov     rbp, rcx
0x18000606d  test    rax, r9
0x180006070  jz      short loc_180006078
0x180006072  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006078  mov     r9, rdx; pszSrc
0x18000607b  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180006080  mov     edx, 104h; cchDest
0x180006085  call    StringCopyWorkerW
0x18000608a  lea     r8, aP0; "_p0"
0x180006091  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180006096  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000609b  mov     edx, ebx
0x18000609d  lea     r9, [rsp+278h+pszDest]
0x1800060a2  and     edx, 7FFFFFFFh
0x1800060a8  mov     esi, 1
0x1800060ad  mov     r8d, esi
0x1800060b0  mov     rcx, rbp
0x1800060b3  cmova   r8d, edx
0x1800060b7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800060bc  mov     edi, eax
0x1800060be  test    eax, eax
0x1800060c0  jns     short loc_1800060E2
0x1800060c2  mov     rcx, [rsp+278h]; this
0x1800060ca  lea     r8, aWil; "wil"
0x1800060d1  mov     r9d, eax; char *
0x1800060d4  mov     edx, 8Bh; void *
0x1800060d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060de  mov     eax, edi
0x1800060e0  jmp     short loc_180006137
0x1800060e2  lea     r8, asc_1800153D8; "h"
0x1800060e9  shr     rbx, 1Fh
0x1800060ed  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800060f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800060f7  test    ebx, ebx
0x1800060f9  lea     rcx, [rbp+8]
0x1800060fd  lea     r9, [rsp+278h+pszDest]
0x180006102  mov     edx, ebx
0x180006104  cmovnz  esi, ebx
0x180006107  mov     r8d, esi
0x18000610a  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000610f  mov     ebx, eax
0x180006111  test    eax, eax
0x180006113  jns     short loc_180006135
0x180006115  mov     rcx, [rsp+278h]; this
0x18000611d  lea     r8, aWil; "wil"
0x180006124  mov     r9d, eax; char *
0x180006127  mov     edx, 90h; void *
0x18000612c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006131  mov     eax, ebx
0x180006133  jmp     short loc_180006137
0x180006135  xor     eax, eax
0x180006137  mov     rcx, [rsp+278h+var_28]
0x18000613f  xor     rcx, rsp; StackCookie
0x180006142  call    __security_check_cookie
0x180006147  mov     rbx, [rsp+278h+arg_10]
0x18000614f  add     rsp, 260h
0x180006156  pop     rdi
0x180006157  pop     rsi
0x180006158  pop     rbp
0x180006159  retn
```
