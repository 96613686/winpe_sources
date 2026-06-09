# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003328`
- end: `0x180003438`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043b4`

## callees

- `0x180003328`
- `0x180004a44`
- `0x180004f1c`
- `0x180004ffc`
- `0x180005560`
- `0x1800058d8`
- `0x18001e020`

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
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  size_t v18; // [rsp+20h] [rbp-258h]
  int v19; // [rsp+20h] [rbp-258h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v18);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v12 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v14 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v14 )
      v7 = v14;
    v15 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (__int64)this + 8,
            v14,
            v7,
            pszDest);
    v17 = v15;
    if ( v15 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v16, (const char *)(unsigned int)v15, v19);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      v11,
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v19);
    return v12;
  }
}

```

## disassembly

```asm
0x180003328  mov     [rsp+arg_10], rbx
0x18000332d  push    rbp
0x18000332e  push    rsi
0x18000332f  push    rdi
0x180003330  sub     rsp, 260h
0x180003337  mov     rax, cs:__security_cookie
0x18000333e  xor     rax, rsp
0x180003341  mov     [rsp+278h+var_28], rax
0x180003349  mov     rax, 0C000000000000000h
0x180003353  mov     rbx, r9
0x180003356  mov     rbp, rcx
0x180003359  test    rax, r9
0x18000335c  jz      short loc_180003364
0x18000335e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003364  mov     r9, rdx; pszSrc
0x180003367  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000336c  mov     edx, 104h; cchDest
0x180003371  call    StringCopyWorkerW
0x180003376  lea     r8, aP0; "_p0"
0x18000337d  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180003382  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003387  mov     edx, ebx
0x180003389  lea     r9, [rsp+278h+pszDest]
0x18000338e  and     edx, 7FFFFFFFh
0x180003394  mov     esi, 1
0x180003399  mov     r8d, esi
0x18000339c  mov     rcx, rbp
0x18000339f  cmova   r8d, edx
0x1800033a3  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800033a8  mov     edi, eax
0x1800033aa  test    eax, eax
0x1800033ac  jns     short loc_1800033C7
0x1800033ae  mov     rcx, [rsp+278h]; this
0x1800033b6  mov     r9d, eax; char *
0x1800033b9  mov     edx, 8Bh; void *
0x1800033be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033c3  mov     eax, edi
0x1800033c5  jmp     short loc_180003415
0x1800033c7  lea     r8, asc_180023840; "h"
0x1800033ce  shr     rbx, 1Fh
0x1800033d2  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800033d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800033dc  test    ebx, ebx
0x1800033de  lea     rcx, [rbp+8]
0x1800033e2  lea     r9, [rsp+278h+pszDest]
0x1800033e7  mov     edx, ebx
0x1800033e9  cmovnz  esi, ebx
0x1800033ec  mov     r8d, esi
0x1800033ef  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800033f4  mov     ebx, eax
0x1800033f6  test    eax, eax
0x1800033f8  jns     short loc_180003413
0x1800033fa  mov     rcx, [rsp+278h]; this
0x180003402  mov     r9d, eax; char *
0x180003405  mov     edx, 90h; void *
0x18000340a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000340f  mov     eax, ebx
0x180003411  jmp     short loc_180003415
0x180003413  xor     eax, eax
0x180003415  mov     rcx, [rsp+278h+var_28]
0x18000341d  xor     rcx, rsp; StackCookie
0x180003420  call    __security_check_cookie
0x180003425  mov     rbx, [rsp+278h+arg_10]
0x18000342d  add     rsp, 260h
0x180003434  pop     rdi
0x180003435  pop     rsi
0x180003436  pop     rbp
0x180003437  retn
```
