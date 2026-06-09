# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a179c`
- end: `0x1800a1946`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a1718`

## callees

- `0x18009a7e8`
- `0x18009d670`
- `0x18009fc80`
- `0x1800a08d0`
- `0x1800a1054`
- `0x1800a1530`
- `0x1800a1610`
- `0x1800a179c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a1800`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a1897`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a1800`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a1897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1810`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800a179c  mov     [rsp-8+arg_8], rbx
0x1800a17a1  mov     [rsp-8+arg_18], rdi
0x1800a17a6  push    rbp
0x1800a17a7  lea     rbp, [rsp-170h]
0x1800a17af  sub     rsp, 270h
0x1800a17b6  mov     rax, cs:__security_cookie
0x1800a17bd  xor     rax, rsp
0x1800a17c0  mov     [rbp+170h+var_10], rax
0x1800a17c7  mov     r9, rcx; pszSrc
0x1800a17ca  mov     qword ptr [r8], 0
0x1800a17d1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a17d6  mov     edx, 104h; cchDest
0x1800a17db  mov     rdi, r8
0x1800a17de  call    StringCopyWorkerW
0x1800a17e3  lea     r8, aP0; "_p0"
0x1800a17ea  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a17ef  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a17f4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a17f9  xor     edx, edx; bInheritHandle
0x1800a17fb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a1800  call    cs:__imp_OpenSemaphoreW
0x1800a1806  mov     [rsp+270h+var_230], rax
0x1800a180b  test    rax, rax
0x1800a180e  jnz     short loc_1800A1837
0x1800a1810  call    cs:__imp_GetLastError
0x1800a1816  cmp     eax, 2
0x1800a1819  jz      loc_1800A1914
0x1800a181f  mov     rcx, [rbp+178h]; this
0x1800a1826  mov     edx, 0D0h; void *
0x1800a182b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a1830  mov     ebx, eax
0x1800a1832  jmp     loc_1800A1916
0x1800a1837  lea     rdx, [rsp+270h+var_23C]; int *
0x1800a183c  mov     [rsp+270h+var_23C], 0
0x1800a1844  mov     rcx, rax; hHandle
0x1800a1847  mov     [rsp+270h+var_240], 0
0x1800a184f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a1854  mov     ebx, eax
0x1800a1856  test    eax, eax
0x1800a1858  jns     short loc_1800A187A
0x1800a185a  mov     rcx, [rbp+178h]; this
0x1800a1861  lea     r8, aWil; "wil"
0x1800a1868  mov     r9d, eax; char *
0x1800a186b  mov     edx, 0D6h; void *
0x1800a1870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1875  jmp     loc_1800A1916
0x1800a187a  lea     r8, asc_1800E6480; "h"
0x1800a1881  lea     rcx, [rsp+270h+pszDest]; wchar_t *
0x1800a1886  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a188b  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a1890  xor     edx, edx; bInheritHandle
0x1800a1892  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a1897  call    cs:__imp_OpenSemaphoreW
0x1800a189d  mov     [rsp+270h+var_238], rax
0x1800a18a2  test    rax, rax
0x1800a18a5  jnz     short loc_1800A18C6
0x1800a18a7  mov     rcx, [rbp+178h]; this
0x1800a18ae  mov     edx, 0DCh; void *
0x1800a18b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a18b8  mov     ebx, eax
0x1800a18ba  lea     rcx, [rsp+270h+var_238]
0x1800a18bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a18c4  jmp     short loc_1800A1916
0x1800a18c6  lea     rdx, [rsp+270h+var_240]; int *
0x1800a18cb  mov     rcx, rax; hHandle
0x1800a18ce  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a18d3  mov     ebx, eax
0x1800a18d5  test    eax, eax
0x1800a18d7  jns     short loc_1800A18F6
0x1800a18d9  mov     rcx, [rbp+178h]; this
0x1800a18e0  lea     r8, aWil; "wil"
0x1800a18e7  mov     r9d, eax; char *
0x1800a18ea  mov     edx, 0DEh; void *
0x1800a18ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a18f4  jmp     short loc_1800A18BA
0x1800a18f6  lea     rcx, [rsp+270h+var_238]
0x1800a18fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a1900  movsxd  rcx, [rsp+270h+var_240]
0x1800a1905  movsxd  rax, [rsp+270h+var_23C]
0x1800a190a  shl     rcx, 1Fh
0x1800a190e  or      rcx, rax
0x1800a1911  mov     [rdi], rcx
0x1800a1914  xor     ebx, ebx
0x1800a1916  lea     rcx, [rsp+270h+var_230]
0x1800a191b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a1920  mov     eax, ebx
0x1800a1922  mov     rcx, [rbp+170h+var_10]
0x1800a1929  xor     rcx, rsp; StackCookie
0x1800a192c  call    __security_check_cookie
0x1800a1931  lea     r11, [rsp+270h+var_s0]
0x1800a1939  mov     rbx, [r11+18h]
0x1800a193d  mov     rdi, [r11+28h]
0x1800a1941  mov     rsp, r11
0x1800a1944  pop     rbp
0x1800a1945  retn
```
