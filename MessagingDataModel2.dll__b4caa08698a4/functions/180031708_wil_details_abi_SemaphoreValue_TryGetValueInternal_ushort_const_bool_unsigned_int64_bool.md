# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180031708`
- end: `0x1800318c0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180031684`

## callees

- `0x18000bae4`
- `0x18002fafc`
- `0x180030898`
- `0x1800313ec`
- `0x18003140c`
- `0x180031708`
- `0x180031b38`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003176c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003180a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003176c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003180a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003177c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003177c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180031708  mov     [rsp-8+arg_8], rbx
0x18003170d  mov     [rsp-8+arg_18], rdi
0x180031712  push    rbp
0x180031713  lea     rbp, [rsp-160h]
0x18003171b  sub     rsp, 260h
0x180031722  mov     rax, cs:__security_cookie
0x180031729  xor     rax, rsp
0x18003172c  mov     [rbp+160h+var_10], rax
0x180031733  mov     rdi, r8
0x180031736  mov     qword ptr [r8], 0
0x18003173d  mov     r8, rcx; pszSrc
0x180031740  mov     edx, 104h; cchDest
0x180031745  lea     rcx, [rsp+260h+pszDest]; pszDest
0x18003174a  call    StringCchCopyW
0x18003174f  lea     r8, aP0; "_p0"
0x180031756  lea     rcx, [rsp+260h+pszDest]; pszDest
0x18003175b  call    StringCchCatW
0x180031760  lea     r8, [rsp+260h+pszDest]; lpName
0x180031765  xor     edx, edx; bInheritHandle
0x180031767  mov     ecx, 1F0003h; dwDesiredAccess
0x18003176c  call    cs:__imp_OpenSemaphoreW
0x180031772  mov     [rsp+260h+var_230], rax
0x180031777  test    rax, rax
0x18003177a  jnz     short loc_1800317AA
0x18003177c  call    cs:__imp_GetLastError
0x180031782  cmp     eax, 2
0x180031785  jz      loc_18003188E
0x18003178b  mov     rcx, [rbp+168h]; this
0x180031792  lea     r8, aWil; "wil"
0x180031799  mov     edx, 0D0h; void *
0x18003179e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800317a3  mov     ebx, eax
0x1800317a5  jmp     loc_180031890
0x1800317aa  lea     rdx, [rsp+260h+var_23C]; int *
0x1800317af  mov     [rsp+260h+var_23C], 0
0x1800317b7  mov     rcx, rax; hHandle
0x1800317ba  mov     [rsp+260h+var_240], 0; int
0x1800317c2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800317c7  mov     ebx, eax
0x1800317c9  test    eax, eax
0x1800317cb  jns     short loc_1800317ED
0x1800317cd  mov     rcx, [rbp+168h]; this
0x1800317d4  lea     r8, aWil; "wil"
0x1800317db  mov     r9d, eax; char *
0x1800317de  mov     edx, 0D6h; void *
0x1800317e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800317e8  jmp     loc_180031890
0x1800317ed  lea     r8, asc_1800D8B40; "h"
0x1800317f4  lea     rcx, [rsp+260h+pszDest]; pszDest
0x1800317f9  call    StringCchCatW
0x1800317fe  lea     r8, [rsp+260h+pszDest]; lpName
0x180031803  xor     edx, edx; bInheritHandle
0x180031805  mov     ecx, 1F0003h; dwDesiredAccess
0x18003180a  call    cs:__imp_OpenSemaphoreW
0x180031810  mov     [rsp+260h+var_238], rax
0x180031815  test    rax, rax
0x180031818  jnz     short loc_180031840
0x18003181a  mov     rcx, [rbp+168h]; this
0x180031821  lea     r8, aWil; "wil"
0x180031828  mov     edx, 0DCh; void *
0x18003182d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031832  mov     ebx, eax
0x180031834  lea     rcx, [rsp+260h+var_238]
0x180031839  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003183e  jmp     short loc_180031890
0x180031840  lea     rdx, [rsp+260h+var_240]; int *
0x180031845  mov     rcx, rax; hHandle
0x180031848  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003184d  mov     ebx, eax
0x18003184f  test    eax, eax
0x180031851  jns     short loc_180031870
0x180031853  mov     rcx, [rbp+168h]; this
0x18003185a  lea     r8, aWil; "wil"
0x180031861  mov     r9d, eax; char *
0x180031864  mov     edx, 0DEh; void *
0x180031869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003186e  jmp     short loc_180031834
0x180031870  lea     rcx, [rsp+260h+var_238]
0x180031875  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003187a  movsxd  rcx, [rsp+260h+var_240]
0x18003187f  movsxd  rax, [rsp+260h+var_23C]
0x180031884  shl     rcx, 1Fh
0x180031888  or      rcx, rax
0x18003188b  mov     [rdi], rcx
0x18003188e  xor     ebx, ebx
0x180031890  lea     rcx, [rsp+260h+var_230]
0x180031895  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003189a  mov     eax, ebx
0x18003189c  mov     rcx, [rbp+160h+var_10]
0x1800318a3  xor     rcx, rsp; StackCookie
0x1800318a6  call    __security_check_cookie
0x1800318ab  lea     r11, [rsp+260h+var_s0]
0x1800318b3  mov     rbx, [r11+18h]
0x1800318b7  mov     rdi, [r11+28h]
0x1800318bb  mov     rsp, r11
0x1800318be  pop     rbp
0x1800318bf  retn
```
