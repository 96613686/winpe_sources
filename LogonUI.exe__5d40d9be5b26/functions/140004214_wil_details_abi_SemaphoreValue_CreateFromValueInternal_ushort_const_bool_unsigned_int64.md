# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004214`
- end: `0x140004324`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005484`
- `0x1400055a8`

## callees

- `0x14000190c`
- `0x140002910`
- `0x140004214`
- `0x1400061ac`
- `0x140006650`
- `0x140006f58`
- `0x1400070c8`

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
0x140004214  mov     [rsp+arg_10], rbx
0x140004219  push    rbp
0x14000421a  push    rsi
0x14000421b  push    rdi
0x14000421c  sub     rsp, 260h
0x140004223  mov     rax, cs:__security_cookie
0x14000422a  xor     rax, rsp
0x14000422d  mov     [rsp+278h+var_28], rax
0x140004235  mov     rax, 0C000000000000000h
0x14000423f  mov     rbx, r9
0x140004242  mov     rbp, rcx
0x140004245  test    rax, r9
0x140004248  jz      short loc_140004250
0x14000424a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004250  mov     r9, rdx; pszSrc
0x140004253  lea     rcx, [rsp+278h+pszDest]; pszDest
0x140004258  mov     edx, 104h; cchDest
0x14000425d  call    StringCopyWorkerW
0x140004262  lea     r8, aP0; "_p0"
0x140004269  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x14000426e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004273  mov     edx, ebx
0x140004275  lea     r9, [rsp+278h+pszDest]
0x14000427a  and     edx, 7FFFFFFFh
0x140004280  mov     esi, 1
0x140004285  mov     r8d, esi
0x140004288  mov     rcx, rbp
0x14000428b  cmova   r8d, edx
0x14000428f  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140004294  mov     edi, eax
0x140004296  test    eax, eax
0x140004298  jns     short loc_1400042B3
0x14000429a  mov     rcx, [rsp+278h]; this
0x1400042a2  mov     r9d, eax; char *
0x1400042a5  mov     edx, 8Bh; void *
0x1400042aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042af  mov     eax, edi
0x1400042b1  jmp     short loc_140004301
0x1400042b3  lea     r8, asc_1400099F0; "h"
0x1400042ba  shr     rbx, 1Fh
0x1400042be  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1400042c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400042c8  test    ebx, ebx
0x1400042ca  lea     rcx, [rbp+8]
0x1400042ce  lea     r9, [rsp+278h+pszDest]
0x1400042d3  mov     edx, ebx
0x1400042d5  cmovnz  esi, ebx
0x1400042d8  mov     r8d, esi
0x1400042db  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400042e0  mov     ebx, eax
0x1400042e2  test    eax, eax
0x1400042e4  jns     short loc_1400042FF
0x1400042e6  mov     rcx, [rsp+278h]; this
0x1400042ee  mov     r9d, eax; char *
0x1400042f1  mov     edx, 90h; void *
0x1400042f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042fb  mov     eax, ebx
0x1400042fd  jmp     short loc_140004301
0x1400042ff  xor     eax, eax
0x140004301  mov     rcx, [rsp+278h+var_28]
0x140004309  xor     rcx, rsp; StackCookie
0x14000430c  call    __security_check_cookie
0x140004311  mov     rbx, [rsp+278h+arg_10]
0x140004319  add     rsp, 260h
0x140004320  pop     rdi
0x140004321  pop     rsi
0x140004322  pop     rbp
0x140004323  retn
```
