# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000aff0`
- end: `0x18000b19a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000966c`

## callees

- `0x180009544`
- `0x18000a18c`
- `0x18000ab34`
- `0x18000ab5c`
- `0x18000adec`
- `0x18000aee0`
- `0x18000aff0`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b054`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b0eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b054`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b064`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  wil::details *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  size_t v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v20);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24 = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v23,
          v18);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v23,
      v16);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v24,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000aff0  mov     [rsp-8+arg_8], rbx
0x18000aff5  mov     [rsp-8+arg_18], rdi
0x18000affa  push    rbp
0x18000affb  lea     rbp, [rsp-170h]
0x18000b003  sub     rsp, 270h
0x18000b00a  mov     rax, cs:__security_cookie
0x18000b011  xor     rax, rsp
0x18000b014  mov     [rbp+170h+var_10], rax
0x18000b01b  mov     r9, rcx; pszSrc
0x18000b01e  mov     qword ptr [r8], 0
0x18000b025  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000b02a  mov     edx, 104h; cchDest
0x18000b02f  mov     rdi, r8
0x18000b032  call    StringCopyWorkerW
0x18000b037  lea     r8, aP0; "_p0"
0x18000b03e  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000b043  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b048  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b04d  xor     edx, edx; bInheritHandle
0x18000b04f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b054  call    cs:__imp_OpenSemaphoreW
0x18000b05a  mov     [rsp+270h+var_230], rax
0x18000b05f  test    rax, rax
0x18000b062  jnz     short loc_18000B08B
0x18000b064  call    cs:__imp_GetLastError
0x18000b06a  cmp     eax, 2
0x18000b06d  jz      loc_18000B168
0x18000b073  mov     rcx, [rbp+178h]; this
0x18000b07a  mov     edx, 0D0h; void *
0x18000b07f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b084  mov     ebx, eax
0x18000b086  jmp     loc_18000B16A
0x18000b08b  lea     rdx, [rsp+270h+var_23C]; int *
0x18000b090  mov     [rsp+270h+var_23C], 0
0x18000b098  mov     rcx, rax; hHandle
0x18000b09b  mov     [rsp+270h+var_240], 0
0x18000b0a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b0a8  mov     ebx, eax
0x18000b0aa  test    eax, eax
0x18000b0ac  jns     short loc_18000B0CE
0x18000b0ae  mov     rcx, [rbp+178h]; this
0x18000b0b5  lea     r8, aWil; "wil"
0x18000b0bc  mov     r9d, eax; char *
0x18000b0bf  mov     edx, 0D6h; void *
0x18000b0c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0c9  jmp     loc_18000B16A
0x18000b0ce  lea     r8, asc_18001E1F0; "h"
0x18000b0d5  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000b0da  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b0df  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b0e4  xor     edx, edx; bInheritHandle
0x18000b0e6  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b0eb  call    cs:__imp_OpenSemaphoreW
0x18000b0f1  mov     [rsp+270h+var_238], rax
0x18000b0f6  test    rax, rax
0x18000b0f9  jnz     short loc_18000B11A
0x18000b0fb  mov     rcx, [rbp+178h]; this
0x18000b102  mov     edx, 0DCh; void *
0x18000b107  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b10c  mov     ebx, eax
0x18000b10e  lea     rcx, [rsp+270h+var_238]
0x18000b113  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b118  jmp     short loc_18000B16A
0x18000b11a  lea     rdx, [rsp+270h+var_240]; int *
0x18000b11f  mov     rcx, rax; hHandle
0x18000b122  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b127  mov     ebx, eax
0x18000b129  test    eax, eax
0x18000b12b  jns     short loc_18000B14A
0x18000b12d  mov     rcx, [rbp+178h]; this
0x18000b134  lea     r8, aWil; "wil"
0x18000b13b  mov     r9d, eax; char *
0x18000b13e  mov     edx, 0DEh; void *
0x18000b143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b148  jmp     short loc_18000B10E
0x18000b14a  lea     rcx, [rsp+270h+var_238]
0x18000b14f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b154  movsxd  rcx, [rsp+270h+var_240]
0x18000b159  movsxd  rax, [rsp+270h+var_23C]
0x18000b15e  shl     rcx, 1Fh
0x18000b162  or      rcx, rax
0x18000b165  mov     [rdi], rcx
0x18000b168  xor     ebx, ebx
0x18000b16a  lea     rcx, [rsp+270h+var_230]
0x18000b16f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b174  mov     eax, ebx
0x18000b176  mov     rcx, [rbp+170h+var_10]
0x18000b17d  xor     rcx, rsp; StackCookie
0x18000b180  call    __security_check_cookie
0x18000b185  lea     r11, [rsp+270h+var_s0]
0x18000b18d  mov     rbx, [r11+18h]
0x18000b191  mov     rdi, [r11+28h]
0x18000b195  mov     rsp, r11
0x18000b198  pop     rbp
0x18000b199  retn
```
