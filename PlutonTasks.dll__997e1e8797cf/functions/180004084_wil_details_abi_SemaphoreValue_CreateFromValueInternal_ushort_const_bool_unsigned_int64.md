# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004084`
- end: `0x180004194`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, const unsigned __int16 *, size_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005d50`
- `0x180005e74`

## callees

- `0x180001e00`
- `0x180004084`
- `0x1800074cc`
- `0x180007ca0`
- `0x180007dc8`
- `0x180008990`
- `0x180008b48`

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
0x180004084  mov     [rsp+arg_10], rbx
0x180004089  push    rbp
0x18000408a  push    rsi
0x18000408b  push    rdi
0x18000408c  sub     rsp, 260h
0x180004093  mov     rax, cs:__security_cookie
0x18000409a  xor     rax, rsp
0x18000409d  mov     [rsp+278h+var_28], rax
0x1800040a5  mov     rax, 0C000000000000000h
0x1800040af  mov     rbx, r9
0x1800040b2  mov     rbp, rcx
0x1800040b5  test    rax, r9
0x1800040b8  jz      short loc_1800040C0
0x1800040ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800040c0  mov     r9, rdx; pszSrc
0x1800040c3  lea     rcx, [rsp+278h+pszDest]; pszDest
0x1800040c8  mov     edx, 104h; cchDest
0x1800040cd  call    StringCopyWorkerW
0x1800040d2  lea     r8, aP0; "_p0"
0x1800040d9  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x1800040de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800040e3  mov     edx, ebx
0x1800040e5  lea     r9, [rsp+278h+pszDest]
0x1800040ea  and     edx, 7FFFFFFFh
0x1800040f0  mov     esi, 1
0x1800040f5  mov     r8d, esi
0x1800040f8  mov     rcx, rbp
0x1800040fb  cmova   r8d, edx
0x1800040ff  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004104  mov     edi, eax
0x180004106  test    eax, eax
0x180004108  jns     short loc_180004123
0x18000410a  mov     rcx, [rsp+278h]; this
0x180004112  mov     r9d, eax; char *
0x180004115  mov     edx, 8Bh; void *
0x18000411a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000411f  mov     eax, edi
0x180004121  jmp     short loc_180004171
0x180004123  lea     r8, asc_18000BAF8; "h"
0x18000412a  shr     rbx, 1Fh
0x18000412e  lea     rcx, [rsp+278h+pszDest]; unsigned __int16 *
0x180004133  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004138  test    ebx, ebx
0x18000413a  lea     rcx, [rbp+8]
0x18000413e  lea     r9, [rsp+278h+pszDest]
0x180004143  mov     edx, ebx
0x180004145  cmovnz  esi, ebx
0x180004148  mov     r8d, esi
0x18000414b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180004150  mov     ebx, eax
0x180004152  test    eax, eax
0x180004154  jns     short loc_18000416F
0x180004156  mov     rcx, [rsp+278h]; this
0x18000415e  mov     r9d, eax; char *
0x180004161  mov     edx, 90h; void *
0x180004166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000416b  mov     eax, ebx
0x18000416d  jmp     short loc_180004171
0x18000416f  xor     eax, eax
0x180004171  mov     rcx, [rsp+278h+var_28]
0x180004179  xor     rcx, rsp; StackCookie
0x18000417c  call    __security_check_cookie
0x180004181  mov     rbx, [rsp+278h+arg_10]
0x180004189  add     rsp, 260h
0x180004190  pop     rdi
0x180004191  pop     rsi
0x180004192  pop     rbp
0x180004193  retn
```
