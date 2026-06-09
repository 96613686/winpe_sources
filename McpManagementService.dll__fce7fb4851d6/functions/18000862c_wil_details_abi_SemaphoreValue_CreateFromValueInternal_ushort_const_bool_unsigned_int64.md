# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000862c`
- end: `0x18000874a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `286`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a914`
- `0x18000aa78`

## callees

- `0x180003a60`
- `0x18000862c`
- `0x18000c4cc`
- `0x18000ccc0`
- `0x18000cde8`
- `0x18000e0c8`
- `0x18000e3ec`

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
0x18000862c  mov     [rsp+arg_10], rbx
0x180008631  push    rbp
0x180008632  push    rsi
0x180008633  push    rdi
0x180008634  sub     rsp, 260h
0x18000863b  mov     rax, cs:__security_cookie
0x180008642  xor     rax, rsp
0x180008645  mov     [rsp+278h+var_28], rax
0x18000864d  mov     rax, 0C000000000000000h
0x180008657  mov     rbx, r9
0x18000865a  mov     rbp, rcx
0x18000865d  test    rax, r9
0x180008660  jz      short loc_180008668
0x180008662  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008668  mov     r9, rdx; pszSrc
0x18000866b  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180008670  mov     edx, 104h; cchDest
0x180008675  call    StringCopyWorkerW
0x18000867a  lea     r8, aP0; "_p0"
0x180008681  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180008686  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000868b  mov     edx, ebx
0x18000868d  lea     r9, [rsp+278h+pszDest]
0x180008692  and     edx, 7FFFFFFFh
0x180008698  mov     esi, 1
0x18000869d  mov     r8d, esi
0x1800086a0  mov     rcx, rbp
0x1800086a3  cmova   r8d, edx
0x1800086a7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800086ac  mov     edi, eax
0x1800086ae  test    eax, eax
0x1800086b0  jns     short loc_1800086D2
0x1800086b2  mov     rcx, [rsp+278h]; this
0x1800086ba  lea     r8, aWil; "wil"
0x1800086c1  mov     r9d, eax; char *
0x1800086c4  mov     edx, 8Bh; void *
0x1800086c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086ce  mov     eax, edi
0x1800086d0  jmp     short loc_180008727
0x1800086d2  lea     r8, asc_18002E218; "h"
0x1800086d9  shr     rbx, 1Fh
0x1800086dd  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800086e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800086e7  test    ebx, ebx
0x1800086e9  lea     rcx, [rbp+8]
0x1800086ed  lea     r9, [rsp+278h+pszDest]
0x1800086f2  mov     edx, ebx
0x1800086f4  cmovnz  esi, ebx
0x1800086f7  mov     r8d, esi
0x1800086fa  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800086ff  mov     ebx, eax
0x180008701  test    eax, eax
0x180008703  jns     short loc_180008725
0x180008705  mov     rcx, [rsp+278h]; this
0x18000870d  lea     r8, aWil; "wil"
0x180008714  mov     r9d, eax; char *
0x180008717  mov     edx, 90h; void *
0x18000871c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008721  mov     eax, ebx
0x180008723  jmp     short loc_180008727
0x180008725  xor     eax, eax
0x180008727  mov     rcx, [rsp+278h+var_28]
0x18000872f  xor     rcx, rsp; StackCookie
0x180008732  call    __security_check_cookie
0x180008737  mov     rbx, [rsp+278h+arg_10]
0x18000873f  add     rsp, 260h
0x180008746  pop     rdi
0x180008747  pop     rsi
0x180008748  pop     rbp
0x180008749  retn
```
