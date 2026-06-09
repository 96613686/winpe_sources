# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140028f4c`
- end: `0x140029117`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140028ec8`

## callees

- `0x14000a420`
- `0x14001bd40`
- `0x1400258a4`
- `0x140026cbc`
- `0x14002826c`
- `0x140028958`
- `0x140028a88`
- `0x140028f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140028fb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14002905a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140028fb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14002905a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028fc6`

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
0x140028f4c  mov     [rsp-8+arg_8], rbx
0x140028f51  mov     [rsp-8+arg_18], rdi
0x140028f56  push    rbp
0x140028f57  lea     rbp, [rsp-170h]
0x140028f5f  sub     rsp, 270h
0x140028f66  mov     rax, cs:__security_cookie
0x140028f6d  xor     rax, rsp
0x140028f70  mov     [rbp+170h+var_10], rax
0x140028f77  mov     r9, rcx; pszSrc
0x140028f7a  mov     qword ptr [r8], 0
0x140028f81  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140028f86  mov     edx, 104h; cchDest
0x140028f8b  mov     rdi, r8
0x140028f8e  call    StringCopyWorkerW
0x140028f93  lea     r8, aP0; "_p0"
0x140028f9a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140028f9f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140028fa4  lea     r8, [rsp+270h+pszDest]; lpName
0x140028fa9  xor     edx, edx; bInheritHandle
0x140028fab  mov     ecx, 1F0003h; dwDesiredAccess
0x140028fb0  call    cs:__imp_OpenSemaphoreW
0x140028fb7  nop     dword ptr [rax+rax+00h]
0x140028fbc  mov     [rsp+270h+var_230], rax
0x140028fc1  test    rax, rax
0x140028fc4  jnz     short loc_140028FFA
0x140028fc6  call    cs:__imp_GetLastError
0x140028fcd  nop     dword ptr [rax+rax+00h]
0x140028fd2  cmp     eax, 2
0x140028fd5  jz      loc_1400290E4
0x140028fdb  mov     rcx, [rbp+178h]; this
0x140028fe2  lea     r8, aWil; "wil"
0x140028fe9  mov     edx, 0D0h; void *
0x140028fee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140028ff3  mov     ebx, eax
0x140028ff5  jmp     loc_1400290E6
0x140028ffa  lea     rdx, [rsp+270h+var_23C]; int *
0x140028fff  mov     [rsp+270h+var_23C], 0
0x140029007  mov     rcx, rax; hHandle
0x14002900a  mov     [rsp+270h+var_240], 0
0x140029012  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140029017  mov     ebx, eax
0x140029019  test    eax, eax
0x14002901b  jns     short loc_14002903D
0x14002901d  mov     rcx, [rbp+178h]; this
0x140029024  lea     r8, aWil; "wil"
0x14002902b  mov     r9d, eax; char *
0x14002902e  mov     edx, 0D6h; void *
0x140029033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140029038  jmp     loc_1400290E6
0x14002903d  lea     r8, asc_14008C048; "h"
0x140029044  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140029049  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002904e  lea     r8, [rsp+270h+pszDest]; lpName
0x140029053  xor     edx, edx; bInheritHandle
0x140029055  mov     ecx, 1F0003h; dwDesiredAccess
0x14002905a  call    cs:__imp_OpenSemaphoreW
0x140029061  nop     dword ptr [rax+rax+00h]
0x140029066  mov     [rsp+270h+var_238], rax
0x14002906b  test    rax, rax
0x14002906e  jnz     short loc_140029096
0x140029070  mov     rcx, [rbp+178h]; this
0x140029077  lea     r8, aWil; "wil"
0x14002907e  mov     edx, 0DCh; void *
0x140029083  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140029088  mov     ebx, eax
0x14002908a  lea     rcx, [rsp+270h+var_238]
0x14002908f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140029094  jmp     short loc_1400290E6
0x140029096  lea     rdx, [rsp+270h+var_240]; int *
0x14002909b  mov     rcx, rax; hHandle
0x14002909e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400290a3  mov     ebx, eax
0x1400290a5  test    eax, eax
0x1400290a7  jns     short loc_1400290C6
0x1400290a9  mov     rcx, [rbp+178h]; this
0x1400290b0  lea     r8, aWil; "wil"
0x1400290b7  mov     r9d, eax; char *
0x1400290ba  mov     edx, 0DEh; void *
0x1400290bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400290c4  jmp     short loc_14002908A
0x1400290c6  lea     rcx, [rsp+270h+var_238]
0x1400290cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400290d0  movsxd  rcx, [rsp+270h+var_240]
0x1400290d5  movsxd  rax, [rsp+270h+var_23C]
0x1400290da  shl     rcx, 1Fh
0x1400290de  or      rcx, rax
0x1400290e1  mov     [rdi], rcx
0x1400290e4  xor     ebx, ebx
0x1400290e6  lea     rcx, [rsp+270h+var_230]
0x1400290eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400290f0  mov     eax, ebx
0x1400290f2  mov     rcx, [rbp+170h+var_10]
0x1400290f9  xor     rcx, rsp; StackCookie
0x1400290fc  call    __security_check_cookie
0x140029101  lea     r11, [rsp+270h+var_s0]
0x140029109  mov     rbx, [r11+18h]
0x14002910d  mov     rdi, [r11+28h]
0x140029111  mov     rsp, r11
0x140029114  pop     rbp
0x140029115  retn
```
