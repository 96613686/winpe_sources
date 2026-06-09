# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006f30`
- end: `0x1800070e8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006eac`

## callees

- `0x1800036a0`
- `0x180004f4c`
- `0x180005d00`
- `0x180006784`
- `0x1800067a4`
- `0x180006cc0`
- `0x180006da0`
- `0x180006f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007032`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fa4`

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
0x180006f30  mov     [rsp-8+arg_8], rbx
0x180006f35  mov     [rsp-8+arg_18], rdi
0x180006f3a  push    rbp
0x180006f3b  lea     rbp, [rsp-170h]
0x180006f43  sub     rsp, 270h
0x180006f4a  mov     rax, cs:__security_cookie
0x180006f51  xor     rax, rsp
0x180006f54  mov     [rbp+170h+var_10], rax
0x180006f5b  mov     r9, rcx; pszSrc
0x180006f5e  mov     qword ptr [r8], 0
0x180006f65  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180006f6a  mov     edx, 104h; cchDest
0x180006f6f  mov     rdi, r8
0x180006f72  call    StringCopyWorkerW
0x180006f77  lea     r8, aP0; "_p0"
0x180006f7e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006f83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f88  lea     r8, [rsp+270h+pszDest]; lpName
0x180006f8d  xor     edx, edx; bInheritHandle
0x180006f8f  mov     ecx, 1F0003h; dwDesiredAccess
0x180006f94  call    cs:__imp_OpenSemaphoreW
0x180006f9a  mov     [rsp+270h+var_230], rax
0x180006f9f  test    rax, rax
0x180006fa2  jnz     short loc_180006FD2
0x180006fa4  call    cs:__imp_GetLastError
0x180006faa  cmp     eax, 2
0x180006fad  jz      loc_1800070B6
0x180006fb3  mov     rcx, [rbp+178h]; this
0x180006fba  lea     r8, aWil; "wil"
0x180006fc1  mov     edx, 0D0h; void *
0x180006fc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006fcb  mov     ebx, eax
0x180006fcd  jmp     loc_1800070B8
0x180006fd2  lea     rdx, [rsp+270h+var_23C]; int *
0x180006fd7  mov     [rsp+270h+var_23C], 0
0x180006fdf  mov     rcx, rax; hHandle
0x180006fe2  mov     [rsp+270h+var_240], 0
0x180006fea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006fef  mov     ebx, eax
0x180006ff1  test    eax, eax
0x180006ff3  jns     short loc_180007015
0x180006ff5  mov     rcx, [rbp+178h]; this
0x180006ffc  lea     r8, aWil; "wil"
0x180007003  mov     r9d, eax; char *
0x180007006  mov     edx, 0D6h; void *
0x18000700b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007010  jmp     loc_1800070B8
0x180007015  lea     r8, asc_18001F088; "h"
0x18000701c  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180007021  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007026  lea     r8, [rsp+270h+pszDest]; lpName
0x18000702b  xor     edx, edx; bInheritHandle
0x18000702d  mov     ecx, 1F0003h; dwDesiredAccess
0x180007032  call    cs:__imp_OpenSemaphoreW
0x180007038  mov     [rsp+270h+var_238], rax
0x18000703d  test    rax, rax
0x180007040  jnz     short loc_180007068
0x180007042  mov     rcx, [rbp+178h]; this
0x180007049  lea     r8, aWil; "wil"
0x180007050  mov     edx, 0DCh; void *
0x180007055  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000705a  mov     ebx, eax
0x18000705c  lea     rcx, [rsp+270h+var_238]
0x180007061  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007066  jmp     short loc_1800070B8
0x180007068  lea     rdx, [rsp+270h+var_240]; int *
0x18000706d  mov     rcx, rax; hHandle
0x180007070  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007075  mov     ebx, eax
0x180007077  test    eax, eax
0x180007079  jns     short loc_180007098
0x18000707b  mov     rcx, [rbp+178h]; this
0x180007082  lea     r8, aWil; "wil"
0x180007089  mov     r9d, eax; char *
0x18000708c  mov     edx, 0DEh; void *
0x180007091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007096  jmp     short loc_18000705C
0x180007098  lea     rcx, [rsp+270h+var_238]
0x18000709d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070a2  movsxd  rcx, [rsp+270h+var_240]
0x1800070a7  movsxd  rax, [rsp+270h+var_23C]
0x1800070ac  shl     rcx, 1Fh
0x1800070b0  or      rcx, rax
0x1800070b3  mov     [rdi], rcx
0x1800070b6  xor     ebx, ebx
0x1800070b8  lea     rcx, [rsp+270h+var_230]
0x1800070bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070c2  mov     eax, ebx
0x1800070c4  mov     rcx, [rbp+170h+var_10]
0x1800070cb  xor     rcx, rsp; StackCookie
0x1800070ce  call    __security_check_cookie
0x1800070d3  lea     r11, [rsp+270h+var_s0]
0x1800070db  mov     rbx, [r11+18h]
0x1800070df  mov     rdi, [r11+28h]
0x1800070e3  mov     rsp, r11
0x1800070e6  pop     rbp
0x1800070e7  retn
```
