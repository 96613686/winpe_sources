# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006e34`
- end: `0x140006fff`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140003874`

## callees

- `0x140003498`
- `0x140005238`
- `0x1400065c4`
- `0x1400065e4`
- `0x140006b08`
- `0x140006bec`
- `0x140006e34`
- `0x140009d00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006e98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006f42`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006e98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eae`

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
0x140006e34  mov     [rsp-8+arg_8], rbx
0x140006e39  mov     [rsp-8+arg_18], rdi
0x140006e3e  push    rbp
0x140006e3f  lea     rbp, [rsp-170h]
0x140006e47  sub     rsp, 270h
0x140006e4e  mov     rax, cs:__security_cookie
0x140006e55  xor     rax, rsp
0x140006e58  mov     [rbp+170h+var_10], rax
0x140006e5f  mov     r9, rcx; pszSrc
0x140006e62  mov     qword ptr [r8], 0
0x140006e69  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140006e6e  mov     edx, 104h; cchDest
0x140006e73  mov     rdi, r8
0x140006e76  call    StringCopyWorkerW
0x140006e7b  lea     r8, aP0; "_p0"
0x140006e82  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006e87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006e8c  lea     r8, [rsp+270h+pszDest]; lpName
0x140006e91  xor     edx, edx; bInheritHandle
0x140006e93  mov     ecx, 1F0003h; dwDesiredAccess
0x140006e98  call    cs:__imp_OpenSemaphoreW
0x140006e9f  nop     dword ptr [rax+rax+00h]
0x140006ea4  mov     [rsp+270h+var_230], rax
0x140006ea9  test    rax, rax
0x140006eac  jnz     short loc_140006EE2
0x140006eae  call    cs:__imp_GetLastError
0x140006eb5  nop     dword ptr [rax+rax+00h]
0x140006eba  cmp     eax, 2
0x140006ebd  jz      loc_140006FCC
0x140006ec3  mov     rcx, [rbp+178h]; this
0x140006eca  lea     r8, aWil; "wil"
0x140006ed1  mov     edx, 0D0h; void *
0x140006ed6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006edb  mov     ebx, eax
0x140006edd  jmp     loc_140006FCE
0x140006ee2  lea     rdx, [rsp+270h+var_23C]; int *
0x140006ee7  mov     [rsp+270h+var_23C], 0
0x140006eef  mov     rcx, rax; hHandle
0x140006ef2  mov     [rsp+270h+var_240], 0
0x140006efa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006eff  mov     ebx, eax
0x140006f01  test    eax, eax
0x140006f03  jns     short loc_140006F25
0x140006f05  mov     rcx, [rbp+178h]; this
0x140006f0c  lea     r8, aWil; "wil"
0x140006f13  mov     r9d, eax; char *
0x140006f16  mov     edx, 0D6h; void *
0x140006f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006f20  jmp     loc_140006FCE
0x140006f25  lea     r8, asc_14000DEF0; "h"
0x140006f2c  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006f31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006f36  lea     r8, [rsp+270h+pszDest]; lpName
0x140006f3b  xor     edx, edx; bInheritHandle
0x140006f3d  mov     ecx, 1F0003h; dwDesiredAccess
0x140006f42  call    cs:__imp_OpenSemaphoreW
0x140006f49  nop     dword ptr [rax+rax+00h]
0x140006f4e  mov     [rsp+270h+var_238], rax
0x140006f53  test    rax, rax
0x140006f56  jnz     short loc_140006F7E
0x140006f58  mov     rcx, [rbp+178h]; this
0x140006f5f  lea     r8, aWil; "wil"
0x140006f66  mov     edx, 0DCh; void *
0x140006f6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006f70  mov     ebx, eax
0x140006f72  lea     rcx, [rsp+270h+var_238]
0x140006f77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006f7c  jmp     short loc_140006FCE
0x140006f7e  lea     rdx, [rsp+270h+var_240]; int *
0x140006f83  mov     rcx, rax; hHandle
0x140006f86  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006f8b  mov     ebx, eax
0x140006f8d  test    eax, eax
0x140006f8f  jns     short loc_140006FAE
0x140006f91  mov     rcx, [rbp+178h]; this
0x140006f98  lea     r8, aWil; "wil"
0x140006f9f  mov     r9d, eax; char *
0x140006fa2  mov     edx, 0DEh; void *
0x140006fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006fac  jmp     short loc_140006F72
0x140006fae  lea     rcx, [rsp+270h+var_238]
0x140006fb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006fb8  movsxd  rcx, [rsp+270h+var_240]
0x140006fbd  movsxd  rax, [rsp+270h+var_23C]
0x140006fc2  shl     rcx, 1Fh
0x140006fc6  or      rcx, rax
0x140006fc9  mov     [rdi], rcx
0x140006fcc  xor     ebx, ebx
0x140006fce  lea     rcx, [rsp+270h+var_230]
0x140006fd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006fd8  mov     eax, ebx
0x140006fda  mov     rcx, [rbp+170h+var_10]
0x140006fe1  xor     rcx, rsp; StackCookie
0x140006fe4  call    __security_check_cookie
0x140006fe9  lea     r11, [rsp+270h+var_s0]
0x140006ff1  mov     rbx, [r11+18h]
0x140006ff5  mov     rdi, [r11+28h]
0x140006ff9  mov     rsp, r11
0x140006ffc  pop     rbp
0x140006ffd  retn
```
