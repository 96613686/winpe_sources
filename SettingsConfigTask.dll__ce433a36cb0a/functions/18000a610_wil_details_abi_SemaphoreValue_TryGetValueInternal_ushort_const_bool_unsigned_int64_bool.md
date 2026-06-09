# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a610`
- end: `0x18000a7c8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a58c`

## callees

- `0x1800021d0`
- `0x1800046b0`
- `0x180006dcc`
- `0x18000970c`
- `0x18000972c`
- `0x180009f10`
- `0x180009ff0`
- `0x18000a610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a684`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a674`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a712`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a674`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a712`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23 = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v19);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v16);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000a610  mov     [rsp-8+arg_8], rbx
0x18000a615  mov     [rsp-8+arg_18], rdi
0x18000a61a  push    rbp
0x18000a61b  lea     rbp, [rsp-170h]
0x18000a623  sub     rsp, 270h
0x18000a62a  mov     rax, cs:__security_cookie
0x18000a631  xor     rax, rsp
0x18000a634  mov     [rbp+170h+var_10], rax
0x18000a63b  mov     r9, rcx; pszSrc
0x18000a63e  mov     qword ptr [r8], 0
0x18000a645  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000a64a  mov     edx, 104h; cchDest
0x18000a64f  mov     rdi, r8
0x18000a652  call    StringCopyWorkerW
0x18000a657  lea     r8, aP0; "_p0"
0x18000a65e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000a663  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a668  lea     r8, [rsp+270h+pszDest]; lpName
0x18000a66d  xor     edx, edx; bInheritHandle
0x18000a66f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a674  call    cs:__imp_OpenSemaphoreW
0x18000a67a  mov     [rsp+270h+var_230], rax
0x18000a67f  test    rax, rax
0x18000a682  jnz     short loc_18000A6B2
0x18000a684  call    cs:__imp_GetLastError
0x18000a68a  cmp     eax, 2
0x18000a68d  jz      loc_18000A796
0x18000a693  mov     rcx, [rbp+178h]; this
0x18000a69a  lea     r8, aWil; "wil"
0x18000a6a1  mov     edx, 0D0h; void *
0x18000a6a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a6ab  mov     ebx, eax
0x18000a6ad  jmp     loc_18000A798
0x18000a6b2  lea     rdx, [rsp+270h+var_23C]; int *
0x18000a6b7  mov     [rsp+270h+var_23C], 0
0x18000a6bf  mov     rcx, rax; hHandle
0x18000a6c2  mov     [rsp+270h+var_240], 0
0x18000a6ca  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a6cf  mov     ebx, eax
0x18000a6d1  test    eax, eax
0x18000a6d3  jns     short loc_18000A6F5
0x18000a6d5  mov     rcx, [rbp+178h]; this
0x18000a6dc  lea     r8, aWil; "wil"
0x18000a6e3  mov     r9d, eax; char *
0x18000a6e6  mov     edx, 0D6h; void *
0x18000a6eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6f0  jmp     loc_18000A798
0x18000a6f5  lea     r8, asc_180026308; "h"
0x18000a6fc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000a701  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a706  lea     r8, [rsp+270h+pszDest]; lpName
0x18000a70b  xor     edx, edx; bInheritHandle
0x18000a70d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a712  call    cs:__imp_OpenSemaphoreW
0x18000a718  mov     [rsp+270h+var_238], rax
0x18000a71d  test    rax, rax
0x18000a720  jnz     short loc_18000A748
0x18000a722  mov     rcx, [rbp+178h]; this
0x18000a729  lea     r8, aWil; "wil"
0x18000a730  mov     edx, 0DCh; void *
0x18000a735  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a73a  mov     ebx, eax
0x18000a73c  lea     rcx, [rsp+270h+var_238]
0x18000a741  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a746  jmp     short loc_18000A798
0x18000a748  lea     rdx, [rsp+270h+var_240]; int *
0x18000a74d  mov     rcx, rax; hHandle
0x18000a750  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a755  mov     ebx, eax
0x18000a757  test    eax, eax
0x18000a759  jns     short loc_18000A778
0x18000a75b  mov     rcx, [rbp+178h]; this
0x18000a762  lea     r8, aWil; "wil"
0x18000a769  mov     r9d, eax; char *
0x18000a76c  mov     edx, 0DEh; void *
0x18000a771  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a776  jmp     short loc_18000A73C
0x18000a778  lea     rcx, [rsp+270h+var_238]
0x18000a77d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a782  movsxd  rcx, [rsp+270h+var_240]
0x18000a787  movsxd  rax, [rsp+270h+var_23C]
0x18000a78c  shl     rcx, 1Fh
0x18000a790  or      rcx, rax
0x18000a793  mov     [rdi], rcx
0x18000a796  xor     ebx, ebx
0x18000a798  lea     rcx, [rsp+270h+var_230]
0x18000a79d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a7a2  mov     eax, ebx
0x18000a7a4  mov     rcx, [rbp+170h+var_10]
0x18000a7ab  xor     rcx, rsp; StackCookie
0x18000a7ae  call    __security_check_cookie
0x18000a7b3  lea     r11, [rsp+270h+var_s0]
0x18000a7bb  mov     rbx, [r11+18h]
0x18000a7bf  mov     rdi, [r11+28h]
0x18000a7c3  mov     rsp, r11
0x18000a7c6  pop     rbp
0x18000a7c7  retn
```
