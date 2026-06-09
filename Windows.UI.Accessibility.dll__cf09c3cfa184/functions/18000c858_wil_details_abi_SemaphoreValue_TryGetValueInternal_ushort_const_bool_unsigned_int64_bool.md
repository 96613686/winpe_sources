# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c858`
- end: `0x18000ca10`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c7d4`

## callees

- `0x180003980`
- `0x180009020`
- `0x18000a588`
- `0x18000bdfc`
- `0x18000be1c`
- `0x18000c438`
- `0x18000c4b4`
- `0x18000c858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c8bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c95a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c8bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c95a`

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
0x18000c858  mov     [rsp-8+arg_8], rbx
0x18000c85d  mov     [rsp-8+arg_18], rdi
0x18000c862  push    rbp
0x18000c863  lea     rbp, [rsp-170h]
0x18000c86b  sub     rsp, 270h
0x18000c872  mov     rax, cs:__security_cookie
0x18000c879  xor     rax, rsp
0x18000c87c  mov     [rbp+170h+var_10], rax
0x18000c883  mov     r9, rcx; pszSrc
0x18000c886  mov     qword ptr [r8], 0
0x18000c88d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000c892  mov     edx, 104h; cchDest
0x18000c897  mov     rdi, r8
0x18000c89a  call    StringCopyWorkerW
0x18000c89f  lea     r8, aP0; "_p0"
0x18000c8a6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000c8ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c8b0  lea     r8, [rsp+270h+pszDest]; lpName
0x18000c8b5  xor     edx, edx; bInheritHandle
0x18000c8b7  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c8bc  call    cs:__imp_OpenSemaphoreW
0x18000c8c2  mov     [rsp+270h+var_230], rax
0x18000c8c7  test    rax, rax
0x18000c8ca  jnz     short loc_18000C8FA
0x18000c8cc  call    cs:__imp_GetLastError
0x18000c8d2  cmp     eax, 2
0x18000c8d5  jz      loc_18000C9DE
0x18000c8db  mov     rcx, [rbp+178h]; this
0x18000c8e2  lea     r8, aWil; "wil"
0x18000c8e9  mov     edx, 0D0h; void *
0x18000c8ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c8f3  mov     ebx, eax
0x18000c8f5  jmp     loc_18000C9E0
0x18000c8fa  lea     rdx, [rsp+270h+var_23C]; int *
0x18000c8ff  mov     [rsp+270h+var_23C], 0
0x18000c907  mov     rcx, rax; hHandle
0x18000c90a  mov     [rsp+270h+var_240], 0
0x18000c912  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c917  mov     ebx, eax
0x18000c919  test    eax, eax
0x18000c91b  jns     short loc_18000C93D
0x18000c91d  mov     rcx, [rbp+178h]; this
0x18000c924  lea     r8, aWil; "wil"
0x18000c92b  mov     r9d, eax; char *
0x18000c92e  mov     edx, 0D6h; void *
0x18000c933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c938  jmp     loc_18000C9E0
0x18000c93d  lea     r8, asc_180039B88; "h"
0x18000c944  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000c949  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c94e  lea     r8, [rsp+270h+pszDest]; lpName
0x18000c953  xor     edx, edx; bInheritHandle
0x18000c955  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c95a  call    cs:__imp_OpenSemaphoreW
0x18000c960  mov     [rsp+270h+var_238], rax
0x18000c965  test    rax, rax
0x18000c968  jnz     short loc_18000C990
0x18000c96a  mov     rcx, [rbp+178h]; this
0x18000c971  lea     r8, aWil; "wil"
0x18000c978  mov     edx, 0DCh; void *
0x18000c97d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c982  mov     ebx, eax
0x18000c984  lea     rcx, [rsp+270h+var_238]
0x18000c989  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c98e  jmp     short loc_18000C9E0
0x18000c990  lea     rdx, [rsp+270h+var_240]; int *
0x18000c995  mov     rcx, rax; hHandle
0x18000c998  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c99d  mov     ebx, eax
0x18000c99f  test    eax, eax
0x18000c9a1  jns     short loc_18000C9C0
0x18000c9a3  mov     rcx, [rbp+178h]; this
0x18000c9aa  lea     r8, aWil; "wil"
0x18000c9b1  mov     r9d, eax; char *
0x18000c9b4  mov     edx, 0DEh; void *
0x18000c9b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9be  jmp     short loc_18000C984
0x18000c9c0  lea     rcx, [rsp+270h+var_238]
0x18000c9c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c9ca  movsxd  rcx, [rsp+270h+var_240]
0x18000c9cf  movsxd  rax, [rsp+270h+var_23C]
0x18000c9d4  shl     rcx, 1Fh
0x18000c9d8  or      rcx, rax
0x18000c9db  mov     [rdi], rcx
0x18000c9de  xor     ebx, ebx
0x18000c9e0  lea     rcx, [rsp+270h+var_230]
0x18000c9e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c9ea  mov     eax, ebx
0x18000c9ec  mov     rcx, [rbp+170h+var_10]
0x18000c9f3  xor     rcx, rsp; StackCookie
0x18000c9f6  call    __security_check_cookie
0x18000c9fb  lea     r11, [rsp+270h+var_s0]
0x18000ca03  mov     rbx, [r11+18h]
0x18000ca07  mov     rdi, [r11+28h]
0x18000ca0b  mov     rsp, r11
0x18000ca0e  pop     rbp
0x18000ca0f  retn
```
