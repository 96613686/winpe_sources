# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c49c`
- end: `0x18000c638`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c428`

## callees

- `0x1800015f0`
- `0x1800087a4`
- `0x180009ce8`
- `0x18000b89c`
- `0x18000b8bc`
- `0x18000bf80`
- `0x18000c0a8`
- `0x18000c49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c500`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c590`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c500`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c510`

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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x18000c49c  mov     [rsp-8+arg_8], rbx
0x18000c4a1  mov     [rsp-8+arg_18], rdi
0x18000c4a6  push    rbp
0x18000c4a7  lea     rbp, [rsp-170h]
0x18000c4af  sub     rsp, 270h
0x18000c4b6  mov     rax, cs:__security_cookie
0x18000c4bd  xor     rax, rsp
0x18000c4c0  mov     [rbp+170h+var_10], rax
0x18000c4c7  mov     r9, rcx; pszSrc
0x18000c4ca  mov     qword ptr [r8], 0
0x18000c4d1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000c4d6  mov     edx, 104h; cchDest
0x18000c4db  mov     rdi, r8
0x18000c4de  call    StringCopyWorkerW
0x18000c4e3  lea     r8, aP0; "_p0"
0x18000c4ea  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000c4ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c4f4  lea     r8, [rsp+270h+pszDest]; lpName
0x18000c4f9  xor     edx, edx; bInheritHandle
0x18000c4fb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c500  call    cs:__imp_OpenSemaphoreW
0x18000c506  mov     [rsp+270h+var_230], rax
0x18000c50b  test    rax, rax
0x18000c50e  jnz     short loc_18000C537
0x18000c510  call    cs:__imp_GetLastError
0x18000c516  cmp     eax, 2
0x18000c519  jz      loc_18000C606
0x18000c51f  mov     rcx, [rbp+178h]; this
0x18000c526  mov     edx, 0D0h; void *
0x18000c52b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c530  mov     ebx, eax
0x18000c532  jmp     loc_18000C608
0x18000c537  lea     rdx, [rsp+270h+var_23C]; int *
0x18000c53c  mov     [rsp+270h+var_23C], 0
0x18000c544  mov     rcx, rax; hHandle
0x18000c547  mov     [rsp+270h+var_240], 0
0x18000c54f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c554  mov     ebx, eax
0x18000c556  test    eax, eax
0x18000c558  jns     short loc_18000C573
0x18000c55a  mov     rcx, [rbp+178h]; this
0x18000c561  mov     r9d, eax; char *
0x18000c564  mov     edx, 0D6h; void *
0x18000c569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c56e  jmp     loc_18000C608
0x18000c573  lea     r8, asc_1800251B0; "h"
0x18000c57a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000c57f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c584  lea     r8, [rsp+270h+pszDest]; lpName
0x18000c589  xor     edx, edx; bInheritHandle
0x18000c58b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c590  call    cs:__imp_OpenSemaphoreW
0x18000c596  mov     [rsp+270h+var_238], rax
0x18000c59b  test    rax, rax
0x18000c59e  jnz     short loc_18000C5BF
0x18000c5a0  mov     rcx, [rbp+178h]; this
0x18000c5a7  mov     edx, 0DCh; void *
0x18000c5ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c5b1  mov     ebx, eax
0x18000c5b3  lea     rcx, [rsp+270h+var_238]
0x18000c5b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c5bd  jmp     short loc_18000C608
0x18000c5bf  lea     rdx, [rsp+270h+var_240]; int *
0x18000c5c4  mov     rcx, rax; hHandle
0x18000c5c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c5cc  mov     ebx, eax
0x18000c5ce  test    eax, eax
0x18000c5d0  jns     short loc_18000C5E8
0x18000c5d2  mov     rcx, [rbp+178h]; this
0x18000c5d9  mov     r9d, eax; char *
0x18000c5dc  mov     edx, 0DEh; void *
0x18000c5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5e6  jmp     short loc_18000C5B3
0x18000c5e8  lea     rcx, [rsp+270h+var_238]
0x18000c5ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c5f2  movsxd  rcx, [rsp+270h+var_240]
0x18000c5f7  movsxd  rax, [rsp+270h+var_23C]
0x18000c5fc  shl     rcx, 1Fh
0x18000c600  or      rcx, rax
0x18000c603  mov     [rdi], rcx
0x18000c606  xor     ebx, ebx
0x18000c608  lea     rcx, [rsp+270h+var_230]
0x18000c60d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c612  mov     eax, ebx
0x18000c614  mov     rcx, [rbp+170h+var_10]
0x18000c61b  xor     rcx, rsp; StackCookie
0x18000c61e  call    __security_check_cookie
0x18000c623  lea     r11, [rsp+270h+var_s0]
0x18000c62b  mov     rbx, [r11+18h]
0x18000c62f  mov     rdi, [r11+28h]
0x18000c633  mov     rsp, r11
0x18000c636  pop     rbp
0x18000c637  retn
```
