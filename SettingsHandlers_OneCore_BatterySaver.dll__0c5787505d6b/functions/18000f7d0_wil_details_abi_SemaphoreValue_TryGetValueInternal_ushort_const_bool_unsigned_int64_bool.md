# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f7d0`
- end: `0x18000f988`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f74c`

## callees

- `0x180009190`
- `0x18000b5ac`
- `0x18000cc88`
- `0x18000eaac`
- `0x18000eacc`
- `0x18000f18c`
- `0x18000f2b4`
- `0x18000f7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f834`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f8d2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f834`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f844`

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
0x18000f7d0  mov     [rsp-8+arg_8], rbx
0x18000f7d5  mov     [rsp-8+arg_18], rdi
0x18000f7da  push    rbp
0x18000f7db  lea     rbp, [rsp-170h]
0x18000f7e3  sub     rsp, 270h
0x18000f7ea  mov     rax, cs:__security_cookie
0x18000f7f1  xor     rax, rsp
0x18000f7f4  mov     [rbp+170h+var_10], rax
0x18000f7fb  mov     r9, rcx; pszSrc
0x18000f7fe  mov     qword ptr [r8], 0
0x18000f805  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000f80a  mov     edx, 104h; cchDest
0x18000f80f  mov     rdi, r8
0x18000f812  call    StringCopyWorkerW
0x18000f817  lea     r8, aP0; "_p0"
0x18000f81e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000f823  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f828  lea     r8, [rsp+270h+pszDest]; lpName
0x18000f82d  xor     edx, edx; bInheritHandle
0x18000f82f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f834  call    cs:__imp_OpenSemaphoreW
0x18000f83a  mov     [rsp+270h+var_230], rax
0x18000f83f  test    rax, rax
0x18000f842  jnz     short loc_18000F872
0x18000f844  call    cs:__imp_GetLastError
0x18000f84a  cmp     eax, 2
0x18000f84d  jz      loc_18000F956
0x18000f853  mov     rcx, [rbp+178h]; this
0x18000f85a  lea     r8, aWil; "wil"
0x18000f861  mov     edx, 0D0h; void *
0x18000f866  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f86b  mov     ebx, eax
0x18000f86d  jmp     loc_18000F958
0x18000f872  lea     rdx, [rsp+270h+var_23C]; int *
0x18000f877  mov     [rsp+270h+var_23C], 0
0x18000f87f  mov     rcx, rax; hHandle
0x18000f882  mov     [rsp+270h+var_240], 0
0x18000f88a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f88f  mov     ebx, eax
0x18000f891  test    eax, eax
0x18000f893  jns     short loc_18000F8B5
0x18000f895  mov     rcx, [rbp+178h]; this
0x18000f89c  lea     r8, aWil; "wil"
0x18000f8a3  mov     r9d, eax; char *
0x18000f8a6  mov     edx, 0D6h; void *
0x18000f8ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8b0  jmp     loc_18000F958
0x18000f8b5  lea     r8, asc_1800546F0; "h"
0x18000f8bc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000f8c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f8c6  lea     r8, [rsp+270h+pszDest]; lpName
0x18000f8cb  xor     edx, edx; bInheritHandle
0x18000f8cd  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f8d2  call    cs:__imp_OpenSemaphoreW
0x18000f8d8  mov     [rsp+270h+var_238], rax
0x18000f8dd  test    rax, rax
0x18000f8e0  jnz     short loc_18000F908
0x18000f8e2  mov     rcx, [rbp+178h]; this
0x18000f8e9  lea     r8, aWil; "wil"
0x18000f8f0  mov     edx, 0DCh; void *
0x18000f8f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f8fa  mov     ebx, eax
0x18000f8fc  lea     rcx, [rsp+270h+var_238]
0x18000f901  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f906  jmp     short loc_18000F958
0x18000f908  lea     rdx, [rsp+270h+var_240]; int *
0x18000f90d  mov     rcx, rax; hHandle
0x18000f910  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f915  mov     ebx, eax
0x18000f917  test    eax, eax
0x18000f919  jns     short loc_18000F938
0x18000f91b  mov     rcx, [rbp+178h]; this
0x18000f922  lea     r8, aWil; "wil"
0x18000f929  mov     r9d, eax; char *
0x18000f92c  mov     edx, 0DEh; void *
0x18000f931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f936  jmp     short loc_18000F8FC
0x18000f938  lea     rcx, [rsp+270h+var_238]
0x18000f93d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f942  movsxd  rcx, [rsp+270h+var_240]
0x18000f947  movsxd  rax, [rsp+270h+var_23C]
0x18000f94c  shl     rcx, 1Fh
0x18000f950  or      rcx, rax
0x18000f953  mov     [rdi], rcx
0x18000f956  xor     ebx, ebx
0x18000f958  lea     rcx, [rsp+270h+var_230]
0x18000f95d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f962  mov     eax, ebx
0x18000f964  mov     rcx, [rbp+170h+var_10]
0x18000f96b  xor     rcx, rsp; StackCookie
0x18000f96e  call    __security_check_cookie
0x18000f973  lea     r11, [rsp+270h+var_s0]
0x18000f97b  mov     rbx, [r11+18h]
0x18000f97f  mov     rdi, [r11+28h]
0x18000f983  mov     rsp, r11
0x18000f986  pop     rbp
0x18000f987  retn
```
