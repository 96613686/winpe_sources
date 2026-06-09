# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b280`
- end: `0x18000b438`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b1fc`

## callees

- `0x1800030e0`
- `0x180005f64`
- `0x180007dc4`
- `0x18000a29c`
- `0x18000a2bc`
- `0x18000abfc`
- `0x18000ad24`
- `0x18000b280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b382`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f4`

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
0x18000b280  mov     [rsp-8+arg_8], rbx
0x18000b285  mov     [rsp-8+arg_18], rdi
0x18000b28a  push    rbp
0x18000b28b  lea     rbp, [rsp-170h]
0x18000b293  sub     rsp, 270h
0x18000b29a  mov     rax, cs:__security_cookie
0x18000b2a1  xor     rax, rsp
0x18000b2a4  mov     [rbp+170h+var_10], rax
0x18000b2ab  mov     r9, rcx; pszSrc
0x18000b2ae  mov     qword ptr [r8], 0
0x18000b2b5  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000b2ba  mov     edx, 104h; cchDest
0x18000b2bf  mov     rdi, r8
0x18000b2c2  call    StringCopyWorkerW
0x18000b2c7  lea     r8, aP0; "_p0"
0x18000b2ce  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000b2d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b2d8  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b2dd  xor     edx, edx; bInheritHandle
0x18000b2df  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b2e4  call    cs:__imp_OpenSemaphoreW
0x18000b2ea  mov     [rsp+270h+var_230], rax
0x18000b2ef  test    rax, rax
0x18000b2f2  jnz     short loc_18000B322
0x18000b2f4  call    cs:__imp_GetLastError
0x18000b2fa  cmp     eax, 2
0x18000b2fd  jz      loc_18000B406
0x18000b303  mov     rcx, [rbp+178h]; this
0x18000b30a  lea     r8, aWil; "wil"
0x18000b311  mov     edx, 0D0h; void *
0x18000b316  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b31b  mov     ebx, eax
0x18000b31d  jmp     loc_18000B408
0x18000b322  lea     rdx, [rsp+270h+var_23C]; int *
0x18000b327  mov     [rsp+270h+var_23C], 0
0x18000b32f  mov     rcx, rax; hHandle
0x18000b332  mov     [rsp+270h+var_240], 0
0x18000b33a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b33f  mov     ebx, eax
0x18000b341  test    eax, eax
0x18000b343  jns     short loc_18000B365
0x18000b345  mov     rcx, [rbp+178h]; this
0x18000b34c  lea     r8, aWil; "wil"
0x18000b353  mov     r9d, eax; char *
0x18000b356  mov     edx, 0D6h; void *
0x18000b35b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b360  jmp     loc_18000B408
0x18000b365  lea     r8, asc_180066218; "h"
0x18000b36c  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000b371  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b376  lea     r8, [rsp+270h+pszDest]; lpName
0x18000b37b  xor     edx, edx; bInheritHandle
0x18000b37d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b382  call    cs:__imp_OpenSemaphoreW
0x18000b388  mov     [rsp+270h+var_238], rax
0x18000b38d  test    rax, rax
0x18000b390  jnz     short loc_18000B3B8
0x18000b392  mov     rcx, [rbp+178h]; this
0x18000b399  lea     r8, aWil; "wil"
0x18000b3a0  mov     edx, 0DCh; void *
0x18000b3a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b3aa  mov     ebx, eax
0x18000b3ac  lea     rcx, [rsp+270h+var_238]
0x18000b3b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3b6  jmp     short loc_18000B408
0x18000b3b8  lea     rdx, [rsp+270h+var_240]; int *
0x18000b3bd  mov     rcx, rax; hHandle
0x18000b3c0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b3c5  mov     ebx, eax
0x18000b3c7  test    eax, eax
0x18000b3c9  jns     short loc_18000B3E8
0x18000b3cb  mov     rcx, [rbp+178h]; this
0x18000b3d2  lea     r8, aWil; "wil"
0x18000b3d9  mov     r9d, eax; char *
0x18000b3dc  mov     edx, 0DEh; void *
0x18000b3e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3e6  jmp     short loc_18000B3AC
0x18000b3e8  lea     rcx, [rsp+270h+var_238]
0x18000b3ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b3f2  movsxd  rcx, [rsp+270h+var_240]
0x18000b3f7  movsxd  rax, [rsp+270h+var_23C]
0x18000b3fc  shl     rcx, 1Fh
0x18000b400  or      rcx, rax
0x18000b403  mov     [rdi], rcx
0x18000b406  xor     ebx, ebx
0x18000b408  lea     rcx, [rsp+270h+var_230]
0x18000b40d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b412  mov     eax, ebx
0x18000b414  mov     rcx, [rbp+170h+var_10]
0x18000b41b  xor     rcx, rsp; StackCookie
0x18000b41e  call    __security_check_cookie
0x18000b423  lea     r11, [rsp+270h+var_s0]
0x18000b42b  mov     rbx, [r11+18h]
0x18000b42f  mov     rdi, [r11+28h]
0x18000b433  mov     rsp, r11
0x18000b436  pop     rbp
0x18000b437  retn
```
