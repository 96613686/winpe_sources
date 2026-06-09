# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000bb7c`
- end: `0x18000bc8c`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dba0`
- `0x18001323c`

## callees

- `0x180002020`
- `0x1800066fc`
- `0x18000bb7c`
- `0x18000e784`
- `0x18000ebd0`
- `0x18000ec4c`
- `0x18000f3f4`

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
0x18000bb7c  mov     [rsp+arg_10], rbx
0x18000bb81  push    rbp
0x18000bb82  push    rsi
0x18000bb83  push    rdi
0x18000bb84  sub     rsp, 260h
0x18000bb8b  mov     rax, cs:__security_cookie
0x18000bb92  xor     rax, rsp
0x18000bb95  mov     [rsp+278h+var_28], rax
0x18000bb9d  mov     rax, 0C000000000000000h
0x18000bba7  mov     rbx, r9
0x18000bbaa  mov     rbp, rcx
0x18000bbad  test    rax, r9
0x18000bbb0  jz      short loc_18000BBB8
0x18000bbb2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bbb8  mov     r9, rdx; pszSrc
0x18000bbbb  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18000bbc0  mov     edx, 104h; cchDest
0x18000bbc5  call    StringCopyWorkerW
0x18000bbca  lea     r8, aP0; "_p0"
0x18000bbd1  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000bbd6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bbdb  mov     edx, ebx
0x18000bbdd  lea     r9, [rsp+278h+pszDest]
0x18000bbe2  and     edx, 7FFFFFFFh
0x18000bbe8  mov     esi, 1
0x18000bbed  mov     r8d, esi
0x18000bbf0  mov     rcx, rbp
0x18000bbf3  cmova   r8d, edx
0x18000bbf7  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000bbfc  mov     edi, eax
0x18000bbfe  test    eax, eax
0x18000bc00  jns     short loc_18000BC1B
0x18000bc02  mov     rcx, [rsp+278h]; this
0x18000bc0a  mov     r9d, eax; char *
0x18000bc0d  mov     edx, 8Bh; void *
0x18000bc12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc17  mov     eax, edi
0x18000bc19  jmp     short loc_18000BC69
0x18000bc1b  lea     r8, asc_18001A900; "h"
0x18000bc22  shr     rbx, 1Fh
0x18000bc26  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x18000bc2b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc30  test    ebx, ebx
0x18000bc32  lea     rcx, [rbp+8]
0x18000bc36  lea     r9, [rsp+278h+pszDest]
0x18000bc3b  mov     edx, ebx
0x18000bc3d  cmovnz  esi, ebx
0x18000bc40  mov     r8d, esi
0x18000bc43  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000bc48  mov     ebx, eax
0x18000bc4a  test    eax, eax
0x18000bc4c  jns     short loc_18000BC67
0x18000bc4e  mov     rcx, [rsp+278h]; this
0x18000bc56  mov     r9d, eax; char *
0x18000bc59  mov     edx, 90h; void *
0x18000bc5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc63  mov     eax, ebx
0x18000bc65  jmp     short loc_18000BC69
0x18000bc67  xor     eax, eax
0x18000bc69  mov     rcx, [rsp+278h+var_28]
0x18000bc71  xor     rcx, rsp; StackCookie
0x18000bc74  call    __security_check_cookie
0x18000bc79  mov     rbx, [rsp+278h+arg_10]
0x18000bc81  add     rsp, 260h
0x18000bc88  pop     rdi
0x18000bc89  pop     rsi
0x18000bc8a  pop     rbp
0x18000bc8b  retn
```
