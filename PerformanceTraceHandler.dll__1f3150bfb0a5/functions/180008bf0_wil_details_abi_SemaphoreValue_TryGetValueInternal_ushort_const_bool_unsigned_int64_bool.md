# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008bf0`
- end: `0x180008da8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008b6c`

## callees

- `0x180002c00`
- `0x1800049b0`
- `0x180006008`
- `0x180007f1c`
- `0x180007f3c`
- `0x180008608`
- `0x1800086e8`
- `0x180008bf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cf2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c64`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180008bf0  mov     [rsp-8+arg_8], rbx
0x180008bf5  mov     [rsp-8+arg_18], rdi
0x180008bfa  push    rbp
0x180008bfb  lea     rbp, [rsp-170h]
0x180008c03  sub     rsp, 270h
0x180008c0a  mov     rax, cs:__security_cookie
0x180008c11  xor     rax, rsp
0x180008c14  mov     [rbp+170h+var_10], rax
0x180008c1b  mov     r9, rcx; pszSrc
0x180008c1e  mov     qword ptr [r8], 0
0x180008c25  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180008c2a  mov     edx, 104h; cchDest
0x180008c2f  mov     rdi, r8
0x180008c32  call    StringCopyWorkerW
0x180008c37  lea     r8, aP0; "_p0"
0x180008c3e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180008c43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c48  lea     r8, [rsp+270h+pszDest]; lpName
0x180008c4d  xor     edx, edx; bInheritHandle
0x180008c4f  mov     ecx, 1F0003h; dwDesiredAccess
0x180008c54  call    cs:__imp_OpenSemaphoreW
0x180008c5a  mov     [rsp+270h+var_230], rax
0x180008c5f  test    rax, rax
0x180008c62  jnz     short loc_180008C92
0x180008c64  call    cs:__imp_GetLastError
0x180008c6a  cmp     eax, 2
0x180008c6d  jz      loc_180008D76
0x180008c73  mov     rcx, [rbp+178h]; this
0x180008c7a  lea     r8, aWil; "wil"
0x180008c81  mov     edx, 0D0h; void *
0x180008c86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c8b  mov     ebx, eax
0x180008c8d  jmp     loc_180008D78
0x180008c92  lea     rdx, [rsp+270h+var_23C]; int *
0x180008c97  mov     [rsp+270h+var_23C], 0
0x180008c9f  mov     rcx, rax; hHandle
0x180008ca2  mov     [rsp+270h+var_240], 0
0x180008caa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008caf  mov     ebx, eax
0x180008cb1  test    eax, eax
0x180008cb3  jns     short loc_180008CD5
0x180008cb5  mov     rcx, [rbp+178h]; this
0x180008cbc  lea     r8, aWil; "wil"
0x180008cc3  mov     r9d, eax; char *
0x180008cc6  mov     edx, 0D6h; void *
0x180008ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cd0  jmp     loc_180008D78
0x180008cd5  lea     r8, asc_18001E4B8; "h"
0x180008cdc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180008ce1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008ce6  lea     r8, [rsp+270h+pszDest]; lpName
0x180008ceb  xor     edx, edx; bInheritHandle
0x180008ced  mov     ecx, 1F0003h; dwDesiredAccess
0x180008cf2  call    cs:__imp_OpenSemaphoreW
0x180008cf8  mov     [rsp+270h+var_238], rax
0x180008cfd  test    rax, rax
0x180008d00  jnz     short loc_180008D28
0x180008d02  mov     rcx, [rbp+178h]; this
0x180008d09  lea     r8, aWil; "wil"
0x180008d10  mov     edx, 0DCh; void *
0x180008d15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d1a  mov     ebx, eax
0x180008d1c  lea     rcx, [rsp+270h+var_238]
0x180008d21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d26  jmp     short loc_180008D78
0x180008d28  lea     rdx, [rsp+270h+var_240]; int *
0x180008d2d  mov     rcx, rax; hHandle
0x180008d30  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008d35  mov     ebx, eax
0x180008d37  test    eax, eax
0x180008d39  jns     short loc_180008D58
0x180008d3b  mov     rcx, [rbp+178h]; this
0x180008d42  lea     r8, aWil; "wil"
0x180008d49  mov     r9d, eax; char *
0x180008d4c  mov     edx, 0DEh; void *
0x180008d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d56  jmp     short loc_180008D1C
0x180008d58  lea     rcx, [rsp+270h+var_238]
0x180008d5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d62  movsxd  rcx, [rsp+270h+var_240]
0x180008d67  movsxd  rax, [rsp+270h+var_23C]
0x180008d6c  shl     rcx, 1Fh
0x180008d70  or      rcx, rax
0x180008d73  mov     [rdi], rcx
0x180008d76  xor     ebx, ebx
0x180008d78  lea     rcx, [rsp+270h+var_230]
0x180008d7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d82  mov     eax, ebx
0x180008d84  mov     rcx, [rbp+170h+var_10]
0x180008d8b  xor     rcx, rsp; StackCookie
0x180008d8e  call    __security_check_cookie
0x180008d93  lea     r11, [rsp+270h+var_s0]
0x180008d9b  mov     rbx, [r11+18h]
0x180008d9f  mov     rdi, [r11+28h]
0x180008da3  mov     rsp, r11
0x180008da6  pop     rbp
0x180008da7  retn
```
