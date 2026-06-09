# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180055c70`
- end: `0x180055e12`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180055bfc`

## callees

- `0x180024718`
- `0x180033504`
- `0x1800487e0`
- `0x18005120c`
- `0x180053008`
- `0x180055410`
- `0x180055430`
- `0x180055c70`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180055cd9`
- `KERNEL32!OpenSemaphoreW` at `0x180055d6b`
- `KERNEL32!OpenSemaphoreW` at `0x180055cd9`
- `KERNEL32!OpenSemaphoreW` at `0x180055d6b`
- `KERNEL32!GetLastError` at `0x180055ce9`
- `KERNEL32!GetLastError` at `0x180055ce9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180055c70  mov     [rsp-8+arg_8], rbx
0x180055c75  push    rbp
0x180055c76  push    rdi
0x180055c77  push    r14
0x180055c79  lea     rbp, [rsp-160h]
0x180055c81  sub     rsp, 260h
0x180055c88  mov     rax, cs:__security_cookie
0x180055c8f  xor     rax, rsp
0x180055c92  mov     [rbp+170h+var_20], rax
0x180055c99  mov     rdi, r8
0x180055c9c  mov     qword ptr [r8], 0
0x180055ca3  mov     r8, rcx; pszSrc
0x180055ca6  mov     r14d, 104h
0x180055cac  mov     edx, r14d; cchDest
0x180055caf  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180055cb4  call    StringCchCopyW
0x180055cb9  lea     r8, aP0; "_p0"
0x180055cc0  mov     edx, r14d; cchDest
0x180055cc3  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180055cc8  call    StringCchCatW
0x180055ccd  lea     r8, [rsp+270h+pszDest]; lpName
0x180055cd2  xor     edx, edx; bInheritHandle
0x180055cd4  mov     ecx, 1F0003h; dwDesiredAccess
0x180055cd9  call    cs:__imp_OpenSemaphoreW
0x180055cdf  mov     [rsp+270h+var_240], rax
0x180055ce4  test    rax, rax
0x180055ce7  jnz     short loc_180055D0F
0x180055ce9  call    cs:__imp_GetLastError
0x180055cef  cmp     eax, 2
0x180055cf2  jz      loc_180055DE1
0x180055cf8  mov     rcx, [rbp+178h]; this
0x180055cff  lea     edx, [r14-34h]; void *
0x180055d03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055d08  mov     ebx, eax
0x180055d0a  jmp     loc_180055DE3
0x180055d0f  lea     rdx, [rsp+270h+var_24C]; int *
0x180055d14  mov     [rsp+270h+var_24C], 0
0x180055d1c  mov     rcx, rax; hHandle
0x180055d1f  mov     [rsp+270h+var_250], 0; int
0x180055d27  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055d2c  mov     ebx, eax
0x180055d2e  test    eax, eax
0x180055d30  jns     short loc_180055D4B
0x180055d32  mov     rcx, [rbp+178h]; this
0x180055d39  mov     r9d, eax; char *
0x180055d3c  mov     edx, 0D6h; void *
0x180055d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055d46  jmp     loc_180055DE3
0x180055d4b  lea     r8, asc_180080EA8; "h"
0x180055d52  mov     rdx, r14; cchDest
0x180055d55  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180055d5a  call    StringCchCatW
0x180055d5f  lea     r8, [rsp+270h+pszDest]; lpName
0x180055d64  xor     edx, edx; bInheritHandle
0x180055d66  mov     ecx, 1F0003h; dwDesiredAccess
0x180055d6b  call    cs:__imp_OpenSemaphoreW
0x180055d71  mov     [rsp+270h+var_248], rax
0x180055d76  test    rax, rax
0x180055d79  jnz     short loc_180055D9A
0x180055d7b  mov     rcx, [rbp+178h]; this
0x180055d82  mov     edx, 0DCh; void *
0x180055d87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055d8c  mov     ebx, eax
0x180055d8e  lea     rcx, [rsp+270h+var_248]
0x180055d93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055d98  jmp     short loc_180055DE3
0x180055d9a  lea     rdx, [rsp+270h+var_250]; int *
0x180055d9f  mov     rcx, rax; hHandle
0x180055da2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180055da7  mov     ebx, eax
0x180055da9  test    eax, eax
0x180055dab  jns     short loc_180055DC3
0x180055dad  mov     rcx, [rbp+178h]; this
0x180055db4  mov     r9d, eax; char *
0x180055db7  mov     edx, 0DEh; void *
0x180055dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055dc1  jmp     short loc_180055D8E
0x180055dc3  lea     rcx, [rsp+270h+var_248]
0x180055dc8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055dcd  movsxd  rcx, [rsp+270h+var_250]
0x180055dd2  movsxd  rax, [rsp+270h+var_24C]
0x180055dd7  shl     rcx, 1Fh
0x180055ddb  or      rcx, rax
0x180055dde  mov     [rdi], rcx
0x180055de1  xor     ebx, ebx
0x180055de3  lea     rcx, [rsp+270h+var_240]
0x180055de8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180055ded  mov     eax, ebx
0x180055def  mov     rcx, [rbp+170h+var_20]
0x180055df6  xor     rcx, rsp; StackCookie
0x180055df9  call    __security_check_cookie
0x180055dfe  mov     rbx, [rsp+270h+arg_8]
0x180055e06  add     rsp, 260h
0x180055e0d  pop     r14
0x180055e0f  pop     rdi
0x180055e10  pop     rbp
0x180055e11  retn
```
