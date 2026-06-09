# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ba00`
- end: `0x18000bbb8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800106a4`

## callees

- `0x18000ba00`
- `0x18000bbc0`
- `0x18000bc3c`
- `0x18000be18`
- `0x18000be38`
- `0x18000d2a0`
- `0x18000fccc`
- `0x180010468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bb02`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bb02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba74`

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
0x18000ba00  mov     [rsp-8+arg_8], rbx
0x18000ba05  mov     [rsp-8+arg_18], rdi
0x18000ba0a  push    rbp
0x18000ba0b  lea     rbp, [rsp-170h]
0x18000ba13  sub     rsp, 270h
0x18000ba1a  mov     rax, cs:__security_cookie
0x18000ba21  xor     rax, rsp
0x18000ba24  mov     [rbp+170h+var_10], rax
0x18000ba2b  mov     r9, rcx; pszSrc
0x18000ba2e  mov     qword ptr [r8], 0
0x18000ba35  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000ba3a  mov     edx, 104h; cchDest
0x18000ba3f  mov     rdi, r8
0x18000ba42  call    StringCopyWorkerW
0x18000ba47  lea     r8, aP0; "_p0"
0x18000ba4e  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000ba53  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ba58  lea     r8, [rsp+270h+pszDest]; lpName
0x18000ba5d  xor     edx, edx; bInheritHandle
0x18000ba5f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ba64  call    cs:__imp_OpenSemaphoreW
0x18000ba6a  mov     [rsp+270h+var_230], rax
0x18000ba6f  test    rax, rax
0x18000ba72  jnz     short loc_18000BAA2
0x18000ba74  call    cs:__imp_GetLastError
0x18000ba7a  cmp     eax, 2
0x18000ba7d  jz      loc_18000BB86
0x18000ba83  mov     rcx, [rbp+178h]; this
0x18000ba8a  lea     r8, aWil; "wil"
0x18000ba91  mov     edx, 0D0h; void *
0x18000ba96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ba9b  mov     ebx, eax
0x18000ba9d  jmp     loc_18000BB88
0x18000baa2  lea     rdx, [rsp+270h+var_23C]; int *
0x18000baa7  mov     [rsp+270h+var_23C], 0
0x18000baaf  mov     rcx, rax; hHandle
0x18000bab2  mov     [rsp+270h+var_240], 0
0x18000baba  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000babf  mov     ebx, eax
0x18000bac1  test    eax, eax
0x18000bac3  jns     short loc_18000BAE5
0x18000bac5  mov     rcx, [rbp+178h]; this
0x18000bacc  lea     r8, aWil; "wil"
0x18000bad3  mov     r9d, eax; char *
0x18000bad6  mov     edx, 0D6h; void *
0x18000badb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bae0  jmp     loc_18000BB88
0x18000bae5  lea     r8, asc_18002B070; "h"
0x18000baec  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x18000baf1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000baf6  lea     r8, [rsp+270h+pszDest]; lpName
0x18000bafb  xor     edx, edx; bInheritHandle
0x18000bafd  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bb02  call    cs:__imp_OpenSemaphoreW
0x18000bb08  mov     [rsp+270h+var_238], rax
0x18000bb0d  test    rax, rax
0x18000bb10  jnz     short loc_18000BB38
0x18000bb12  mov     rcx, [rbp+178h]; this
0x18000bb19  lea     r8, aWil; "wil"
0x18000bb20  mov     edx, 0DCh; void *
0x18000bb25  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bb2a  mov     ebx, eax
0x18000bb2c  lea     rcx, [rsp+270h+var_238]
0x18000bb31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bb36  jmp     short loc_18000BB88
0x18000bb38  lea     rdx, [rsp+270h+var_240]; int *
0x18000bb3d  mov     rcx, rax; hHandle
0x18000bb40  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bb45  mov     ebx, eax
0x18000bb47  test    eax, eax
0x18000bb49  jns     short loc_18000BB68
0x18000bb4b  mov     rcx, [rbp+178h]; this
0x18000bb52  lea     r8, aWil; "wil"
0x18000bb59  mov     r9d, eax; char *
0x18000bb5c  mov     edx, 0DEh; void *
0x18000bb61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb66  jmp     short loc_18000BB2C
0x18000bb68  lea     rcx, [rsp+270h+var_238]
0x18000bb6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bb72  movsxd  rcx, [rsp+270h+var_240]
0x18000bb77  movsxd  rax, [rsp+270h+var_23C]
0x18000bb7c  shl     rcx, 1Fh
0x18000bb80  or      rcx, rax
0x18000bb83  mov     [rdi], rcx
0x18000bb86  xor     ebx, ebx
0x18000bb88  lea     rcx, [rsp+270h+var_230]
0x18000bb8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bb92  mov     eax, ebx
0x18000bb94  mov     rcx, [rbp+170h+var_10]
0x18000bb9b  xor     rcx, rsp; StackCookie
0x18000bb9e  call    __security_check_cookie
0x18000bba3  lea     r11, [rsp+270h+var_s0]
0x18000bbab  mov     rbx, [r11+18h]
0x18000bbaf  mov     rdi, [r11+28h]
0x18000bbb3  mov     rsp, r11
0x18000bbb6  pop     rbp
0x18000bbb7  retn
```
