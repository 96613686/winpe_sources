# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800052e0`
- end: `0x1800053fe`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `286`
- prototype: `int(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800064ec`
- `0x1800297fc`

## callees

- `0x180003560`
- `0x1800052e0`
- `0x180006b14`
- `0x180007064`
- `0x180007144`
- `0x180007694`
- `0x180007764`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        size_t *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v6; // rdx
  LONG v7; // esi
  LONG v8; // r8d
  int semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
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
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
  StringCopyWorkerW(pszDest, 0x104u, a3, a2, v16);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = 1;
  v8 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v8 = a4 & 0x7FFFFFFF;
  semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this, a4 & 0x7FFFFFFF, v8, pszDest);
  v11 = semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v13 = a4 >> 31;
    StringCchCatW(pszDest, v10, L"h");
    if ( (_DWORD)v13 )
      v7 = v13;
    v14 = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
      (const char *)(unsigned int)semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v17);
    return v11;
  }
}

```

## disassembly

```asm
0x1800052e0  mov     [rsp+arg_10], rbx
0x1800052e5  push    rbp
0x1800052e6  push    rsi
0x1800052e7  push    rdi
0x1800052e8  sub     rsp, 260h
0x1800052ef  mov     rax, cs:__security_cookie
0x1800052f6  xor     rax, rsp
0x1800052f9  mov     [rsp+278h+var_28], rax
0x180005301  mov     rax, 0C000000000000000h
0x18000530b  mov     rbx, r9
0x18000530e  mov     rbp, rcx
0x180005311  test    rax, r9
0x180005314  jz      short loc_18000531C
0x180005316  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18000531c  mov     r9, rdx; pszSrc
0x18000531f  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180005324  mov     edx, 104h; cchDest
0x180005329  call    StringCopyWorkerW
0x18000532e  lea     r8, aP0; "_p0"
0x180005335  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x18000533a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000533f  mov     edx, ebx
0x180005341  lea     r9, [rsp+278h+pszDest]
0x180005346  and     edx, 7FFFFFFFh
0x18000534c  mov     esi, 1
0x180005351  mov     r8d, esi
0x180005354  mov     rcx, rbp
0x180005357  cmova   r8d, edx
0x18000535b  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005360  mov     edi, eax
0x180005362  test    eax, eax
0x180005364  jns     short loc_180005386
0x180005366  mov     rcx, [rsp+278h]; this
0x18000536e  lea     r8, aWil; "wil"
0x180005375  mov     r9d, eax; char *
0x180005378  mov     edx, 8Bh; void *
0x18000537d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005382  mov     eax, edi
0x180005384  jmp     short loc_1800053DB
0x180005386  lea     r8, asc_180033EB0; "h"
0x18000538d  shr     rbx, 1Fh
0x180005391  lea     rcx, [rsp+278h+pszDest]; wchar_t *
0x180005396  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000539b  test    ebx, ebx
0x18000539d  lea     rcx, [rbp+8]
0x1800053a1  lea     r9, [rsp+278h+pszDest]
0x1800053a6  mov     edx, ebx
0x1800053a8  cmovnz  esi, ebx
0x1800053ab  mov     r8d, esi
0x1800053ae  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800053b3  mov     ebx, eax
0x1800053b5  test    eax, eax
0x1800053b7  jns     short loc_1800053D9
0x1800053b9  mov     rcx, [rsp+278h]; this
0x1800053c1  lea     r8, aWil; "wil"
0x1800053c8  mov     r9d, eax; char *
0x1800053cb  mov     edx, 90h; void *
0x1800053d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053d5  mov     eax, ebx
0x1800053d7  jmp     short loc_1800053DB
0x1800053d9  xor     eax, eax
0x1800053db  mov     rcx, [rsp+278h+var_28]
0x1800053e3  xor     rcx, rsp; StackCookie
0x1800053e6  call    __security_check_cookie
0x1800053eb  mov     rbx, [rsp+278h+arg_10]
0x1800053f3  add     rsp, 260h
0x1800053fa  pop     rdi
0x1800053fb  pop     rsi
0x1800053fc  pop     rbp
0x1800053fd  retn
```
