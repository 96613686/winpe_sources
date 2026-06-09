# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800794d0`
- end: `0x180079688`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800770c8`

## callees

- `0x180014d58`
- `0x180015190`
- `0x180076a7c`
- `0x180078128`
- `0x180078f68`
- `0x180079344`
- `0x180079424`
- `0x1800794d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079544`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180079534`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800795d2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180079534`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800795d2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800794d0  mov     [rsp-8+arg_8], rbx
0x1800794d5  mov     [rsp-8+arg_18], rdi
0x1800794da  push    rbp
0x1800794db  lea     rbp, [rsp-170h]
0x1800794e3  sub     rsp, 270h
0x1800794ea  mov     rax, cs:__security_cookie
0x1800794f1  xor     rax, rsp
0x1800794f4  mov     [rbp+170h+var_10], rax
0x1800794fb  mov     r9, rcx; pszSrc
0x1800794fe  mov     qword ptr [r8], 0
0x180079505  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18007950a  mov     edx, 104h; cchDest
0x18007950f  mov     rdi, r8
0x180079512  call    StringCopyWorkerW
0x180079517  lea     r8, aP0; "_p0"
0x18007951e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180079523  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180079528  lea     r8, [rsp+270h+pszDest]; lpName
0x18007952d  xor     edx, edx; bInheritHandle
0x18007952f  mov     ecx, 1F0003h; dwDesiredAccess
0x180079534  call    cs:__imp_OpenSemaphoreW
0x18007953a  mov     [rsp+270h+var_230], rax
0x18007953f  test    rax, rax
0x180079542  jnz     short loc_180079572
0x180079544  call    cs:__imp_GetLastError
0x18007954a  cmp     eax, 2
0x18007954d  jz      loc_180079656
0x180079553  mov     rcx, [rbp+178h]; this
0x18007955a  lea     r8, aWil; "wil"
0x180079561  mov     edx, 0D0h; void *
0x180079566  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007956b  mov     ebx, eax
0x18007956d  jmp     loc_180079658
0x180079572  lea     rdx, [rsp+270h+var_23C]; int *
0x180079577  mov     [rsp+270h+var_23C], 0
0x18007957f  mov     rcx, rax; hHandle
0x180079582  mov     [rsp+270h+var_240], 0
0x18007958a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007958f  mov     ebx, eax
0x180079591  test    eax, eax
0x180079593  jns     short loc_1800795B5
0x180079595  mov     rcx, [rbp+178h]; this
0x18007959c  lea     r8, aWil; "wil"
0x1800795a3  mov     r9d, eax; char *
0x1800795a6  mov     edx, 0D6h; void *
0x1800795ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800795b0  jmp     loc_180079658
0x1800795b5  lea     r8, asc_1801AFEC0; "h"
0x1800795bc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800795c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800795c6  lea     r8, [rsp+270h+pszDest]; lpName
0x1800795cb  xor     edx, edx; bInheritHandle
0x1800795cd  mov     ecx, 1F0003h; dwDesiredAccess
0x1800795d2  call    cs:__imp_OpenSemaphoreW
0x1800795d8  mov     [rsp+270h+var_238], rax
0x1800795dd  test    rax, rax
0x1800795e0  jnz     short loc_180079608
0x1800795e2  mov     rcx, [rbp+178h]; this
0x1800795e9  lea     r8, aWil; "wil"
0x1800795f0  mov     edx, 0DCh; void *
0x1800795f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800795fa  mov     ebx, eax
0x1800795fc  lea     rcx, [rsp+270h+var_238]
0x180079601  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180079606  jmp     short loc_180079658
0x180079608  lea     rdx, [rsp+270h+var_240]; int *
0x18007960d  mov     rcx, rax; hHandle
0x180079610  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180079615  mov     ebx, eax
0x180079617  test    eax, eax
0x180079619  jns     short loc_180079638
0x18007961b  mov     rcx, [rbp+178h]; this
0x180079622  lea     r8, aWil; "wil"
0x180079629  mov     r9d, eax; char *
0x18007962c  mov     edx, 0DEh; void *
0x180079631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079636  jmp     short loc_1800795FC
0x180079638  lea     rcx, [rsp+270h+var_238]
0x18007963d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180079642  movsxd  rcx, [rsp+270h+var_240]
0x180079647  movsxd  rax, [rsp+270h+var_23C]
0x18007964c  shl     rcx, 1Fh
0x180079650  or      rcx, rax
0x180079653  mov     [rdi], rcx
0x180079656  xor     ebx, ebx
0x180079658  lea     rcx, [rsp+270h+var_230]
0x18007965d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180079662  mov     eax, ebx
0x180079664  mov     rcx, [rbp+170h+var_10]
0x18007966b  xor     rcx, rsp; StackCookie
0x18007966e  call    __security_check_cookie
0x180079673  lea     r11, [rsp+270h+var_s0]
0x18007967b  mov     rbx, [r11+18h]
0x18007967f  mov     rdi, [r11+28h]
0x180079683  mov     rsp, r11
0x180079686  pop     rbp
0x180079687  retn
```
