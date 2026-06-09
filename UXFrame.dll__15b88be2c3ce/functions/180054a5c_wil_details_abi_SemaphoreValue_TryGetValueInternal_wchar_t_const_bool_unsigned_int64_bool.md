# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180054a5c`
- end: `0x180054c14`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800549d8`

## callees

- `0x180002b20`
- `0x18000e360`
- `0x180015f40`
- `0x1800324c4`
- `0x1800525f8`
- `0x1800545ac`
- `0x180054628`
- `0x180054a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054ac0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054b5e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054ac0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054ad0`

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
  StringCopyWorkerW_0(pszDest, 0x104u, a3, pszSrc, v15);
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
0x180054a5c  mov     [rsp-8+arg_8], rbx
0x180054a61  mov     [rsp-8+arg_18], rdi
0x180054a66  push    rbp
0x180054a67  lea     rbp, [rsp-170h]
0x180054a6f  sub     rsp, 270h
0x180054a76  mov     rax, cs:__security_cookie
0x180054a7d  xor     rax, rsp
0x180054a80  mov     [rbp+170h+var_10], rax
0x180054a87  mov     r9, rcx; pszSrc
0x180054a8a  mov     qword ptr [r8], 0
0x180054a91  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180054a96  mov     edx, 104h; cchDest
0x180054a9b  mov     rdi, r8
0x180054a9e  call    StringCopyWorkerW_0
0x180054aa3  lea     r8, aP0; "_p0"
0x180054aaa  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x180054aaf  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180054ab4  lea     r8, [rsp+270h+pszDest]; lpName
0x180054ab9  xor     edx, edx; bInheritHandle
0x180054abb  mov     ecx, 1F0003h; dwDesiredAccess
0x180054ac0  call    cs:__imp_OpenSemaphoreW
0x180054ac6  mov     [rsp+270h+var_230], rax
0x180054acb  test    rax, rax
0x180054ace  jnz     short loc_180054AFE
0x180054ad0  call    cs:__imp_GetLastError
0x180054ad6  cmp     eax, 2
0x180054ad9  jz      loc_180054BE2
0x180054adf  mov     rcx, [rbp+178h]; this
0x180054ae6  lea     r8, aWil; "wil"
0x180054aed  mov     edx, 0D0h; void *
0x180054af2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054af7  mov     ebx, eax
0x180054af9  jmp     loc_180054BE4
0x180054afe  lea     rdx, [rsp+270h+var_23C]; int *
0x180054b03  mov     [rsp+270h+var_23C], 0
0x180054b0b  mov     rcx, rax; hHandle
0x180054b0e  mov     [rsp+270h+var_240], 0
0x180054b16  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180054b1b  mov     ebx, eax
0x180054b1d  test    eax, eax
0x180054b1f  jns     short loc_180054B41
0x180054b21  mov     rcx, [rbp+178h]; this
0x180054b28  lea     r8, aWil; "wil"
0x180054b2f  mov     r9d, eax; char *
0x180054b32  mov     edx, 0D6h; void *
0x180054b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054b3c  jmp     loc_180054BE4
0x180054b41  lea     r8, asc_180063AC8; "h"
0x180054b48  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x180054b4d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180054b52  lea     r8, [rsp+270h+pszDest]; lpName
0x180054b57  xor     edx, edx; bInheritHandle
0x180054b59  mov     ecx, 1F0003h; dwDesiredAccess
0x180054b5e  call    cs:__imp_OpenSemaphoreW
0x180054b64  mov     [rsp+270h+var_238], rax
0x180054b69  test    rax, rax
0x180054b6c  jnz     short loc_180054B94
0x180054b6e  mov     rcx, [rbp+178h]; this
0x180054b75  lea     r8, aWil; "wil"
0x180054b7c  mov     edx, 0DCh; void *
0x180054b81  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054b86  mov     ebx, eax
0x180054b88  lea     rcx, [rsp+270h+var_238]
0x180054b8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054b92  jmp     short loc_180054BE4
0x180054b94  lea     rdx, [rsp+270h+var_240]; int *
0x180054b99  mov     rcx, rax; hHandle
0x180054b9c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180054ba1  mov     ebx, eax
0x180054ba3  test    eax, eax
0x180054ba5  jns     short loc_180054BC4
0x180054ba7  mov     rcx, [rbp+178h]; this
0x180054bae  lea     r8, aWil; "wil"
0x180054bb5  mov     r9d, eax; char *
0x180054bb8  mov     edx, 0DEh; void *
0x180054bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054bc2  jmp     short loc_180054B88
0x180054bc4  lea     rcx, [rsp+270h+var_238]
0x180054bc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054bce  movsxd  rcx, [rsp+270h+var_240]
0x180054bd3  movsxd  rax, [rsp+270h+var_23C]
0x180054bd8  shl     rcx, 1Fh
0x180054bdc  or      rcx, rax
0x180054bdf  mov     [rdi], rcx
0x180054be2  xor     ebx, ebx
0x180054be4  lea     rcx, [rsp+270h+var_230]
0x180054be9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054bee  mov     eax, ebx
0x180054bf0  mov     rcx, [rbp+170h+var_10]
0x180054bf7  xor     rcx, rsp; StackCookie
0x180054bfa  call    __security_check_cookie
0x180054bff  lea     r11, [rsp+270h+var_s0]
0x180054c07  mov     rbx, [r11+18h]
0x180054c0b  mov     rdi, [r11+28h]
0x180054c0f  mov     rsp, r11
0x180054c12  pop     rbp
0x180054c13  retn
```
