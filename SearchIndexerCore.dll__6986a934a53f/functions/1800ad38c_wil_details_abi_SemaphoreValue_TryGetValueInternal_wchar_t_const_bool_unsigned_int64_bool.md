# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800ad38c`
- end: `0x1800ad528`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ad318`

## callees

- `0x1800789c0`
- `0x1800a8d5c`
- `0x1800aa9f4`
- `0x1800ac73c`
- `0x1800ac75c`
- `0x1800ace1c`
- `0x1800acefc`
- `0x1800ad38c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ad3f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ad480`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ad3f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ad480`

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
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x1800ad38c  mov     [rsp-8+arg_8], rbx
0x1800ad391  mov     [rsp-8+arg_18], rdi
0x1800ad396  push    rbp
0x1800ad397  lea     rbp, [rsp-170h]
0x1800ad39f  sub     rsp, 270h
0x1800ad3a6  mov     rax, cs:__security_cookie
0x1800ad3ad  xor     rax, rsp
0x1800ad3b0  mov     [rbp+170h+var_10], rax
0x1800ad3b7  mov     rdi, r8
0x1800ad3ba  mov     qword ptr [r8], 0
0x1800ad3c1  mov     r9, rcx; pszSrc
0x1800ad3c4  mov     edx, 104h; cchDest
0x1800ad3c9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800ad3ce  call    StringCopyWorkerW
0x1800ad3d3  lea     r8, aP0; "_p0"
0x1800ad3da  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800ad3df  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800ad3e4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800ad3e9  xor     edx, edx; bInheritHandle
0x1800ad3eb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ad3f0  call    cs:__imp_OpenSemaphoreW
0x1800ad3f6  mov     [rsp+270h+var_230], rax
0x1800ad3fb  test    rax, rax
0x1800ad3fe  jnz     short loc_1800AD427
0x1800ad400  call    cs:__imp_GetLastError
0x1800ad406  cmp     eax, 2
0x1800ad409  jz      loc_1800AD4F6
0x1800ad40f  mov     rcx, [rbp+178h]; this
0x1800ad416  mov     edx, 0D0h; void *
0x1800ad41b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ad420  mov     ebx, eax
0x1800ad422  jmp     loc_1800AD4F8
0x1800ad427  mov     [rsp+270h+var_23C], 0
0x1800ad42f  mov     [rsp+270h+var_240], 0
0x1800ad437  lea     rdx, [rsp+270h+var_23C]; int *
0x1800ad43c  mov     rcx, rax; hHandle
0x1800ad43f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ad444  mov     ebx, eax
0x1800ad446  test    eax, eax
0x1800ad448  jns     short loc_1800AD463
0x1800ad44a  mov     rcx, [rbp+178h]; this
0x1800ad451  mov     r9d, eax; char *
0x1800ad454  mov     edx, 0D6h; void *
0x1800ad459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad45e  jmp     loc_1800AD4F8
0x1800ad463  lea     r8, asc_1800C1928; "h"
0x1800ad46a  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800ad46f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800ad474  lea     r8, [rsp+270h+pszDest]; lpName
0x1800ad479  xor     edx, edx; bInheritHandle
0x1800ad47b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ad480  call    cs:__imp_OpenSemaphoreW
0x1800ad486  mov     [rsp+270h+var_238], rax
0x1800ad48b  test    rax, rax
0x1800ad48e  jnz     short loc_1800AD4AF
0x1800ad490  mov     rcx, [rbp+178h]; this
0x1800ad497  mov     edx, 0DCh; void *
0x1800ad49c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ad4a1  mov     ebx, eax
0x1800ad4a3  lea     rcx, [rsp+270h+var_238]
0x1800ad4a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ad4ad  jmp     short loc_1800AD4F8
0x1800ad4af  lea     rdx, [rsp+270h+var_240]; int *
0x1800ad4b4  mov     rcx, rax; hHandle
0x1800ad4b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ad4bc  mov     ebx, eax
0x1800ad4be  test    eax, eax
0x1800ad4c0  jns     short loc_1800AD4D8
0x1800ad4c2  mov     rcx, [rbp+178h]; this
0x1800ad4c9  mov     r9d, eax; char *
0x1800ad4cc  mov     edx, 0DEh; void *
0x1800ad4d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad4d6  jmp     short loc_1800AD4A3
0x1800ad4d8  lea     rcx, [rsp+270h+var_238]
0x1800ad4dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ad4e2  movsxd  rcx, [rsp+270h+var_240]
0x1800ad4e7  shl     rcx, 1Fh
0x1800ad4eb  movsxd  rax, [rsp+270h+var_23C]
0x1800ad4f0  or      rcx, rax
0x1800ad4f3  mov     [rdi], rcx
0x1800ad4f6  xor     ebx, ebx
0x1800ad4f8  lea     rcx, [rsp+270h+var_230]
0x1800ad4fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ad502  mov     eax, ebx
0x1800ad504  mov     rcx, [rbp+170h+var_10]
0x1800ad50b  xor     rcx, rsp; StackCookie
0x1800ad50e  call    __security_check_cookie
0x1800ad513  lea     r11, [rsp+270h+var_s0]
0x1800ad51b  mov     rbx, [r11+18h]
0x1800ad51f  mov     rdi, [r11+28h]
0x1800ad523  mov     rsp, r11
0x1800ad526  pop     rbp
0x1800ad527  retn
```
